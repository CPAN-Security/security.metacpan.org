---
layout: single
published: true
toc: false
title: "Security Considerations for Statsd Clients"
date: 2026-07-06 09:00:00 +0100
tags: command injection leak metrics privacy sidejacking statsd
author: robrwo
author_profile: true
excerpt: "There is no official specification or request for comments... A side-effect is that the security is often overlooked."
header:
  overlay_image: /assets/images/header/SJN07821.JPG
  teaser: assets/images/teaser/SJN07821.JPG
  overlay_filter: 0.6
  caption: "Photo credit: [@sjn](https://github.com/sjn)"
---

# Security Considerations for Statsd Clients

## What is Statsd

Statsd (also written as "StatsD") is a line protocol on UDP port 8125 for collecting metrics,
such as the time it takes to process a request or to count the number of requests for a specific method.

It is a very simple protocol. The client sends a packet with a line of the format

    name:value|type

Where the metric is a name of what is being measured, and type is the kind of measurement.
The most common types are to increment counters for events, measure timings or track the number of unique items, like users.

There are extensions. For example an optional sample rate

    name:value|type|@rate

or DataDog's tags

    name:value|type|#tag1,tag2

Many servers support multi-metric packets, where a packet contains multiple metrics separated by newlines.

One might send a metrics about a request, for example:

    server-01.app.api.v1.users.request.ip:1.2.3.4|s
    server-01.app.api.v1.users.request.method.post:1|c
    server-01.app.api.v1.users.request.time:20|ms

This adds the IP address to a set, so that the number of unique IP addresses can be tracked.
It also increments a counter for the number of HTTP POST request, and logs the time it took to process the request (20ms).

## Problems with the specification

There is no official specification or request for comments (RFC).
There are informal specifications [\[4\]](#references).
A side-effect is that the security is often overlooked.

The specifications for statsd do not give much guidance on acceptable data.

The values are usually numeric [\[4\]](#references), although the "set" metric allows arbitrary strings and can be used to count the number of unique items, such as IP addresses or usernames.

There is no specification about what the metric name can contain.
In many implementations they consist of multiple names separated by dots, e.g. "myapp.response.time".

The simplicity of the protocol has allowed many client implementations.
A list at [\[5\]](#references) shows 58 clients.
It lists three Perl clients, but we are aware of 11 Perl distributions that support statsd or an extension.

There are several common security issues that we have found in the Perl modules we have looked at.

## Metric Injection

All of the Perl modules we looked at as part of the April Task Force had missing or incomplete defenses against metric injections, where the metric names, values or tags could contain a newline and then additional metrics, for example

    myapp.response.
    malicious.counter:1|c
    :123|g

This concern is not unreasonable.

Note the synopsis from an example using DogStatsd tags:

    $statsd->increment( 'user.login', { tags => [ $s->cs->param( 'loginName' ) ] } );

which could be a problem if parameter were not validated beforehand.

If the statsd server supports command-extensions or has a security vulnerability that can be triggered through the protocol,
then the impact of metric injection can be much worse.

These can be defended against by disallowing newlines or control characters (the colon and pipe) in metric names.

Metrics that require numeric input should enforce ASCII digits and a decimal.

For sets, newlines and pipes should be disallowed from values.

Similarly, commas and newlines should be disallowed from tags.

It seems reasonable to disallow metrics to contain characters below ASCII 32 (which includes the newline) from metric names, values and tags.

Also note the effect of metric injections on servers is unknown. If there are vulnerabilities in the server, or special commands, then these could be used for futher explots.

## Data Leakage

The set counter and tags can lead to data leakage.
While the client may send data to a local statsd server, it is unclear if the data saved locally, or if it is being forwarded over an unsecured network to an aggregation server that may also save copies of the data.

The set metric that is used to count the number of unique items, e.g.

    myapp.users:ling@example.com|s
    myapp.ip:1.2.3.4|s
    myapp.sessions:a6a073f8ac226a336375d54706f9555c|s

It is useful to count the number of unique usernames, IP addresses, and sessions,
but this can be seen as personally identifying information.
In the case of counting session ids, this data can be used for session hijacking and should be encoded.

An alternative is to replace sensitive data with anonymised data, for example, an internal user id rather than an email address.

Otherwise, a generic alternative is to hash sensitive data using a message digest or HMAC signature.
For [Net::Statsd::Lite](https://metacpan.org/pod/Net::Statsd::Lite) (which I maintain), I added the [secure_set_add](https://metacpan.org/pod/Net::Statsd::Lite#secure_set_add) method to do this using HMAC-SHA-256.

[Plack::Middleware::Statsd](https://metacpan.org/pod/Plack::Middleware::Statsd) (which I maintain) was modified to do the same, or use a "secure_set_add" method if the underlying statsd client supports it.


## Perl Modules

| Module | Vulnerability | Description | Version Fixed |
| --- | --- | --- | --- |
| [Catalyst::Plugin::Statsd](https://metacpan.org/pod/Catalyst::Plugin::Statsd)   | [CVE-2026-45180](https://www.cve.org/CVERecord?id=CVE-2026-45180) | Leak session ids  | 0.10.0 |
| [DataDog::DogStatsd](https://metacpan.org/pod/DataDog::DogStatsd)               | [CVE-2026-9270](https://www.cve.org/CVERecord?id=CVE-2026-9270), [CVE-2026-11362](https://www.cve.org/CVERecord?id=CVE-2026-11362)  | Metric injection | |
| [Etsy::StatsD](https://metacpan.org/pod/Etsy::StatsD)                           | [CVE-2026-46741](https://www.cve.org/CVERecord?id=CVE-2026-46741) | Metric injection  | |
| [Metrics::Any::Adapter::DogStatsd](https://metacpan.org/pod/Metrics::Any::Adapter::DogStatsd) | [CVE-2026-50638](https://www.cve.org/CVERecord?id=CVE-2026-50638) | Metric injection | 0.04 |
| [Metrics::Any::Adapter::SignalFx](https://metacpan.org/pod/Metrics::Any::Adapter::SignalFx)   | [CVE-2026-50639](https://www.cve.org/CVERecord?id=CVE-2026-50639) | Metric injection | 0.04 |
| [Metrics::Any::Adapter::Statsd](https://metacpan.org/pod/Metrics::Any::Adapter::Statsd)       | [CVE-2026-50637](https://www.cve.org/CVERecord?id=CVE-2026-50637) | Metric injection | 0.04 |
| [Mojolicious::Plugin::Statsd](https://metacpan.org/pod/Mojolicious::Plugin::Statsd) | [CVE-2026-46740](https://www.cve.org/CVERecord?id=CVE-2026-46740) | Metric injection | 0.05 |
| [Net::Async::Statsd](https://metacpan.org/pod/Net::Async::Statsd)               | [CVE-2026-8722](https://www.cve.org/CVERecord?id=CVE-2026-8722)  | Metric injection  | 0.005 |
| [Net::Statsd::Lite](https://metacpan.org/pod/Net::Statsd::Lite)                 | [CVE-2026-46719](https://www.cve.org/CVERecord?id=CVE-2026-46719), [CVE-2026-8788](https://www.cve.org/CVERecord?id=CVE-2026-8788)  | Metric injection  | 0.10.0  |
| [Net::Statsd::Tiny](https://metacpan.org/pod/Net::Statsd::Tiny)                 | [CVE-2026-46720](https://www.cve.org/CVERecord?id=CVE-2026-46720) | Metric injection  | 0.3.8  |
| [Net::Statsd](https://metacpan.org/pod/Net::Statsd)                             | [CVE-2026-46739](https://www.cve.org/CVERecord?id=CVE-2026-46739) | Metric injection  | 0.13   |
| [Net::Statsite::Client](https://metacpan.org/pod/Net::Statsite::Client) | [CVE-2026-11373](https://www.cve.org/CVERecord?id=CVE-2026-11373) | Metric injection | |
| [Plack::Middleware::Statsd](https://metacpan.org/pod/Plack::Middleware::Statsd) | [CVE-2026-45179](https://www.cve.org/CVERecord?id=CVE-2026-45179) | Leak IP Addresses | 0.9.0  |

## References

[1] [https://code.flickr.net/2008/10/27/counting-timing/](https://code.flickr.net/2008/10/27/counting-timing/)

[2] [https://github.com/iamcal/Flickr-StatsD](https://github.com/iamcal/Flickr-StatsD)

[3] [https://www.etsy.com/codeascraft/measure-anything-measure-everything/](https://www.etsy.com/codeascraft/measure-anything-measure-everything/)

[4] [https://github.com/b/statsd_spec](https://github.com/b/statsd_spec)

[5] [https://github.com/statsd/statsd/blob/master/docs/client_implementations.md](https://github.com/statsd/statsd/blob/master/docs/client_implementations.md)

[6] [http://armon.github.io/statsite](http://armon.github.io/statsite)