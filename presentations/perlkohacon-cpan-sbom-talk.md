[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides perlkohacon-cpan-sbom-talk.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)
[comment]: # (diagram was made on https://dreampuf.github.io/GraphvizOnline/ using media/CPAN-deps-1.dot as input)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.2)
[comment]: # (maxScale: 4.0)
[comment]: # (controls: true)
[comment]: # (width: "960")
[comment]: # (height: "700")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")


## Software Bill of Materials

(in the Perl/CPAN world)


Perl & Koha Conference 2023


Note:

Hei!

Welcome to the SBOM talk at PerlKohaCon!


[comment]: # (!!!)

### What is & why SBOM?

Imagine…

A serious vulnerability just got announced!

Note:

Imagine an announcement...


[comment]: # (!!!)

### A new vulnerability!

(previous examples)

* [Heartbleed](https://en.wikipedia.org/wiki/Heartbleed) – OpenSSL, April 2014
* [Solarwinds](https://en.wikipedia.org/wiki/2020_United_States_federal_government_data_breach) – US Gov't data breach, March 2020
* [Log4Shell](https://en.wikipedia.org/wiki/Log4Shell) – Java logging library, December 2021

Note:

* These are the large well-known ones in recent years.
* There are more, and many that only affect a few of us.


[comment]: # (!!! data-auto-animate)

### A new vulnerability!

* Do you know if **any** of your software **anywhere** in your organization is affected?


[comment]: # (!!! data-auto-animate)

### A new vulnerability!

* Do you know if **any** of your software **anywhere** in your organization is affected?
* Can you **quickly** show where it is used?


[comment]: # (!!! data-auto-animate)

### A new vulnerability!

* Do you know if **any** of your software **anywhere** in your organization is affected?
* Can you **quickly** show where it is used?
* Even if it's in your transitive (indirect) dependencies?


[comment]: # (!!! data-auto-animate)

### A new vulnerability!

* Do you know if **any** of your software **anywhere** in your organization is affected?
* Can you **quickly** show where it is used?
* Even if it's in your transitive (indirect) dependencies?
* Even if it's an **Open Source** dependency outside your control?


[comment]: # (!!! data-auto-animate)

## Regulators and lawmakers step in

* US [EO 14028](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) _Improving the Nation’s Cybersecurity_
* EU [NIS2 Directive](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive) 
* EU [Cyber Resilience Act](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act)

![CE Mark](media/280px-Conformité_Européenne.png)


Note:

* EO 14028
    * Executive Order on Improving the Nation’s Cybersecurity
    * Issued May 12, 2021
    * All federal agencies, businesses or contractors that work with or sell to the US federal government
* NIS2
    * Directive (EU) 2022/2555 (NIS2)
    * Software used by EU institutions that manage **critical infrastructure**
    * Must be implemented by 17 October 2024
* CRA
    * Cyber Resilience Act
    * CE certification of software used in and with **internet-connected devices**
    * Must be implemented by July 2025 (estimated)



[comment]: # (!!!)


### Keep track of dependencies

* Across language ecosystems
* Independent of source
* With metadata for your security needs

Note:

SBOMs are for keeping track of important information across dependencies


[comment]: # (!!!)

![Example dependency tree](media/CPAN-deps-1.svg)


[comment]: # (!!!)

## Software Bill of Materials



[comment]: # (!!!)

## SBOM standards

- OWASP CycloneDX
- Software Package Data Exchange (SPDX)

- CPE
- SWID
- PackageURL

[comment]: # (!!!)

## Software identification

* [CPE](https://csrc.nist.gov/projects/security-content-automation-protocol/specifications/cpe) – _Common Platform Enumeration_
    * Used in the US Federal _National Vulnerability Database_
    * [System::Info](https://metacpan.org/pod/System::Info) by HMBRAND
    * [Net::NVD](https://metacpan.org/pod/Net::NVD) by GARU

```txt
cpe:2.3:a:cpan:parallel\:\:forkmanager:-:*:*:*:*:*:*:*
```


[comment]: # (!!!)

## Software identification

* [SWID](https://www.iso.org/standard/65666.html) – _ISO/IEC 19770-2:2015_
    * Non-free: CHF 187,00
    * Nothing on CPAN


[comment]: # (!!!)

## Software identification

* [PURL](https://github.com/package-url/purl-spec) – _Package URL_
    * [URI::PackageURL](https://metacpan.org/pod/URI::PackageURL) by GTD


```txt
pkg:cpan/SJN/Acme-Godot@0.1
```


[comment]: # (!!!)

## What can go into an SBOM?



[comment]: # (!!!)

## The Minimum Elements For a Software Bill of Materials (SBOM)

[Pursuant to Executive Order 14028 on Improving the Nation’s Cybersecurity](https://www.ntia.doc.gov/sites/default/files/publications/sbom_minimum_elements_report_0.pdf)

July 12, 2021


Note:

US Department of Commerce published a list of minimum required fields in an SBOM


[comment]: # (!!!)

| Data Field               | SBOM | CPAN |
| ------------------------ | ---- | ---- |
| Supplier Name            | yes  | yes  |
| Component Name           | yes  | yes  |
| Version of the Component | yes  | yes  |
| Other Unique Identifiers | yes  | no   |
| Dependency Relationship  | yes  | yes  |
| Author of SBOM Data      | yes  | no   |
| Time-stamp               | yes  | no   |


[comment]: # (!!!)

## What can we use SBOMs for?


[comment]: # (!!!)

## [Component inventory](https://cyclonedx.org/use-cases/#inventory)

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "name": "acme-library",
      "version": "1.0.0"
    }
  ]
}
```
[comment]: # (!!! data-auto-animate)

## Identify known vulnerabilities


```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "application",
      "name": "Acme Application",
      "version": "9.1.1",
      "cpe": "cpe:/a:acme:application:9.1.1",
      "swid": {
        "tagId": "swidgen-242eb18a-503e-ca37-393b-cf156ef09691_9.1.1",
        "name": "Acme Application",
        "version": "9.1.1",
        "text": {
          "contentType": "text/xml",
          "encoding": "base64",
          "content": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiID8+CjxTb2Z0d2FyZUlkZW50aXR5IHhtbDpsYW5nPSJFTiIgbmFtZT0iQWNtZSBBcHBsaWNhdGlvbiIgdmVyc2lvbj0iOS4xLjEiIAogdmVyc2lvblNjaGVtZT0ibXVsdGlwYXJ0bnVtZXJpYyIgCiB0YWdJZD0ic3dpZGdlbi1iNTk1MWFjOS00MmMwLWYzODItM2YxZS1iYzdhMmE0NDk3Y2JfOS4xLjEiIAogeG1sbnM9Imh0dHA6Ly9zdGFuZGFyZHMuaXNvLm9yZy9pc28vMTk3NzAvLTIvMjAxNS9zY2hlbWEueHNkIj4gCiB4bWxuczp4c2k9Imh0dHA6Ly93d3cudzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIiAKIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL3N0YW5kYXJkcy5pc28ub3JnL2lzby8xOTc3MC8tMi8yMDE1LWN1cnJlbnQvc2NoZW1hLnhzZCBzY2hlbWEueHNkIiA+CiAgPE1ldGEgZ2VuZXJhdG9yPSJTV0lEIFRhZyBPbmxpbmUgR2VuZXJhdG9yIHYwLjEiIC8+IAogIDxFbnRpdHkgbmFtZT0iQWNtZSwgSW5jLiIgcmVnaWQ9ImV4YW1wbGUuY29tIiByb2xlPSJ0YWdDcmVhdG9yIiAvPiAKPC9Tb2Z0d2FyZUlkZW50aXR5Pg=="
        }
      }
    },
    {
      "type": "library",
      "group": "org.apache.tomcat",
      "name": "tomcat-catalina",
      "version": "9.0.14",
      "purl": "pkg:maven/org.apache.tomcat/tomcat-catalina@9.0.14"
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Verify Integrity

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "name": "acme-example",
      "version": "1.0.0",
      "hashes": [{
        "alg": "MD5",
        "content": "641b6e166f8b33c5e959e2adcc18b1c7"
      },{
        "alg": "SHA-1",
        "content": "9188560f22e0b73070d2efce670c74af2bdf30af"
      },{
        "alg": "SHA-256",
        "content": "d88bc4e70bfb34d18b5542136639acbb26a8ae2429aa1e47489332fb389cc964"
      },{
        "alg": "SHA-384",
        "content": "d4835048a0f57c74b8fb617d5366ab81376fc92bebe9a93bf24ba7f9da6c9aeeb6179f5d1361f6533211b15f3224cbad"
      },{
        "alg": "SHA-512",
        "content": "74a51ff45e4c11df9ba1f0094282c80489649cb157a75fa337992d2d4592a5a1b8cb4525de8db0ae25233553924d76c36e093ea7fa9df4e5b8b07fd2e074efd6"
      },{
        "alg": "SHA3-256",
        "content": "7478c7cf41c883a04ee89f1813f687886d53fa86f791fff90690c6221e3853aa"
      },{
        "alg": "SHA3-384",
        "content": "a1eea7229716487ad2ebe96b2f997a8408f32f14047994fbcc99b49012cf86c96dbd518e5d57a61b0e57dd37dd0b48f5"
      },{
        "alg": "SHA3-512",
        "content": "7d584825bc1767dfabe7e82b45ccb7a1119b145fa17e76b885e71429c706cef0a3171bc6575b968eec5da56a7966c02fec5402fcee55097ac01d40c550de9d20"
      },{
        "alg": "BLAKE2b-256",
        "content": "d8779633380c050bccf4e733b763ab2abd8ad2db60b517d47fd29bbf76433237"
      },{
        "alg": "BLAKE2b-384",
        "content": "e728ba56c2da995a559a178116c594e8bee4894a79ceb4399d8f479e5563cb1942b85936f646d14170717c576b14db7a"
      },{
        "alg": "BLAKE2b-512",
        "content": "f8ce8d612a6c85c96cf7cebc230f6ddef26e6cedcfbc4a41c766033cc08c6ba097d1470948226807fb2d88d2a2b6fc0ff5e5440e93a603086fdd568bafcd1a9d"
      },{
        "alg": "BLAKE3",
        "content": "26cdc7fb3fd65fc3b621a4ef70bc7d2489d5c19e70c76cf7ec20e538df0047cf"
      }]
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Verify Authenticity

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [{
    "type": "library",
    "publisher": "Apache",
    "group": "org.apache.tomcat",
    "name": "tomcat-catalina",
    "version": "9.0.14",
    "hashes": [{
      "alg": "MD5",
      "content": "3942447fac867ae5cdb3229b658f4d48"
    },{
      "alg": "SHA-1",
      "content": "e6b1000b94e835ffd37f4c6dcbdad43f4b48a02a"
    },{
      "alg": "SHA-256",
      "content": "f498a8ff2dd007e29c2074f5e4b01a9a01775c3ff3aeaf6906ea503bc5791b7b"
    },{
      "alg": "SHA-512",
      "content": "e8f33e424f3f4ed6db76a482fde1a5298970e442c531729119e37991884bdffab4f9426b7ee11fccd074eeda0634d71697d6f88a460dce0ac8d627a29f7d1282"
    }],
    "licenses": [{
      "license": {
        "id": "Apache-2.0"
      }
    }],
    "purl": "pkg:maven/org.apache.tomcat/tomcat-catalina@9.0.14"
  }],
  "signature": {
    "algorithm": "RS512",
    "publicKey": {
      "kty": "RSA",
      "n": "qOSWbDOGS31lv3aUZVOgqZyLVrKXXRfmxFQxEylcFY_bRqakeY1EYCkvwTkD9kxlLEd_2SSQYWEZZTjYa1EK1SlfyOsKd2eNKjxGtUSSxPkJRvYi_KgVedgp15C5p1Emsd3bKUs5knLebw4k576RxvY69AChXk48u1Pa7_Bicm89Io8JaQaDvSUXWD19j6686EniS6MSqvhsLsgmeS4V0TdKdWvjQIq0wJmPnBtWUy5DJn3glMtbeh_2xuEZ2Dkkjzr5O0W-vJUKVKm_qW2zbgdqP2_XA8LSywrRlZbvuVo_Jq8rWNxRhUDNtI98lXkSJ5hqk0wwXpUGvwjuCSqgZZmnmBCLzWGxbPfgJamnYr8AzudUaXT6PXz0qbAacmTL-ktm1zblDC_kZPfVsiiUzzND02YUS2euGVxIZc95EFlaEpa3MMIpurI-i0VG-SEagN5cURVCOjVysokC2pkKfrd__ThlvS9aywnMO8haNLPC4TEzzIr-KJff4UFYk_vCAsw7K9DjPWYheP1GoBUZbSApVe9HI4dQ6bGY80CEVRmo_LkPyXbX0c-BONyou1NGtlaYaP7eqaC1Z3b-OrZF-Z2BrTFuFnzKA2X5UPaWo77yra9owdcKG-p7FPlU5gHFmcuAQjx_l8nw8P9EhQXVHHiSSbT1iHmBQ1GO6J6bX_s",
      "e": "AQAB"
    },
    "value": "HGIX_ccdIcqmaOpkxDzKH_j0ozSHUAUyBxGpXS_cCi4Qq34jhXxbKD8qu8r-u4EpX1PzChUqytVD36H-shBEzpr-bgvPONFSMUpsp36ILwTSI0YfsQbJIt1wKt-YiMQW2xQUNo6OpOAryLVFr8ZISf0GmnQ1RENH6wVR8XLkbyqYDN-JNoBrEdcbaANKgdsLBMg9h8tfPxS_C229MrnsershcSs7uiYOTx-Xt8T3yEcZLTTbEN9-jn5SJxS2av3oLp_VaC3bSIg65KoFwqQCweujH0csTr6dD2tCGcHE2xMkUtwscyPXK9He_m-LM4REss_MauAJpOHGacmNgN_auDZ97DZmgC4DX46hgXXqnp2qG-x4QCbrjd5ja3R9e5na7jKBROKqVM5IyYE07jHc9c9Jtma9jo90iVSXp0oSJieG8pDD0zD_Mhx_EOj75L8l5qSd9brJn_MyMkeWXob4eMOQmmVQ9t7zAcdtSCSlZh9lNeFxu2sS5FU-1jqrQM_ewSv292dPDVkx-PmBnfuK9ZasNT-_l3RUfUNPfhRCmK1M7g0REusS2c-jgSi0a3QUvXKfCJg8btbku4IDWqWsUcAIzjUFPlNz5Exyb_pkxy2Ah_hwcfTbGHClzCtVLSy6DCqxcBlTKQSKEGPcP4wUV8Oq0uOQkDokb5xYJVZX4VE"
  }
}
```

[comment]: # (!!! data-auto-animate)

## Verify License compliance

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "group": "com.acme",
      "name": "tomcat-catalina",
      "version": "9.0.14",
      "licenses": [
        {
          "license": {
            "id": "Apache-2.0",
            "text": {
              "contentType": "text/plain",
              "encoding": "base64",
              "content": "CiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIEFwYWNoZSBMaWNlbnNlCiAgICAgICAgICAgICAgICAgICAgICAgICAgIFZlcnNpb24gMi4wLCBKYW51YXJ5IDIwMDQKICAgICAgICAgICAgICAgICAgICAgICAgaHR0cDovL3d3dy5hcGFjaGUub3JnL2xpY2Vuc2VzLwoKICAgVEVSTVMgQU5EIENPTkRJVElPTlMgRk9SIFVTRSwgUkVQUk9EVUNUSU9OLCBBTkQgRElTVFJJQlVUSU9OCgogICAxLiBEZWZpbml0aW9ucy4KCiAgICAgICJMaWNlbnNlIiBzaGFsbCBtZWFuIHRoZSB0ZXJtcyBhbmQgY29uZGl0aW9ucyBmb3IgdXNlLCByZXByb2R1Y3Rpb24sCiAgICAgIGFuZCBkaXN0cmlidXRpb24gYXMgZGVmaW5lZCBieSBTZWN0aW9ucyAxIHRocm91Z2ggOSBvZiB0aGlzIGRvY3VtZW50LgoKICAgICAgIkxpY2Vuc29yIiBzaGFsbCBtZWFuIHRoZSBjb3B5cmlnaHQgb3duZXIgb3IgZW50aXR5IGF1dGhvcml6ZWQgYnkKICAgICAgdGhlIGNvcHlyaWdodCBvd25lciB0aGF0IGlzIGdyYW50aW5nIHRoZSBMaWNlbnNlLgoKICAgICAgIkxlZ2FsIEVudGl0eSIgc2hhbGwgbWVhbiB0aGUgdW5pb24gb2YgdGhlIGFjdGluZyBlbnRpdHkgYW5kIGFsbAogICAgICBvdGhlciBlbnRpdGllcyB0aGF0IGNvbnRyb2wsIGFyZSBjb250cm9sbGVkIGJ5LCBvciBhcmUgdW5kZXIgY29tbW9uCiAgICAgIGNvbnRyb2wgd2l0aCB0aGF0IGVudGl0eS4gRm9yIHRoZSBwdXJwb3NlcyBvZiB0aGlzIGRlZmluaXRpb24sCiAgICAgICJjb250cm9sIiBtZWFucyAoaSkgdGhlIHBvd2VyLCBkaXJlY3Qgb3IgaW5kaXJlY3QsIHRvIGNhdXNlIHRoZQogICAgICBkaXJlY3Rpb24gb3IgbWFuYWdlbWVudCBvZiBzdWNoIGVudGl0eSwgd2hldGhlciBieSBjb250cmFjdCBvcgogICAgICBvdGhlcndpc2UsIG9yIChpaSkgb3duZXJzaGlwIG9mIGZpZnR5IHBlcmNlbnQgKDUwJSkgb3IgbW9yZSBvZiB0aGUKICAgICAgb3V0c3RhbmRpbmcgc2hhcmVzLCBvciAoaWlpKSBiZW5lZmljaWFsIG93bmVyc2hpcCBvZiBzdWNoIGVudGl0eS4KCiAgICAgICJZb3UiIChvciAiWW91ciIpIHNoYWxsIG1lYW4gYW4gaW5kaXZpZHVhbCBvciBMZWdhbCBFbnRpdHkKICAgICAgZXhlcmNpc2luZyBwZXJtaXNzaW9ucyBncmFudGVkIGJ5IHRoaXMgTGljZW5zZS4KCiAgICAgICJTb3VyY2UiIGZvcm0gc2hhbGwgbWVhbiB0aGUgcHJlZmVycmVkIGZvcm0gZm9yIG1ha2luZyBtb2RpZmljYXRpb25zLAogICAgICBpbmNsdWRpbmcgYnV0IG5vdCBsaW1pdGVkIHRvIHNvZnR3YXJlIHNvdXJjZSBjb2RlLCBkb2N1bWVudGF0aW9uCiAgICAgIHNvdXJjZSwgYW5kIGNvbmZpZ3VyYXRpb24gZmlsZXMuCgogICAgICAiT2JqZWN0IiBmb3JtIHNoYWxsIG1lYW4gYW55IGZvcm0gcmVzdWx0aW5nIGZyb20gbWVjaGFuaWNhbAogICAgICB0cmFuc2Zvcm1hdGlvbiBvciB0cmFuc2xhdGlvbiBvZiBhIFNvdXJjZSBmb3JtLCBpbmNsdWRpbmcgYnV0CiAgICAgIG5vdCBsaW1pdGVkIHRvIGNvbXBpbGVkIG9iamVjdCBjb2RlLCBnZW5lcmF0ZWQgZG9jdW1lbnRhdGlvbiwKICAgICAgYW5kIGNvbnZlcnNpb25zIHRvIG90aGVyIG1lZGlhIHR5cGVzLgoKICAgICAgIldvcmsiIHNoYWxsIG1lYW4gdGhlIHdvcmsgb2YgYXV0aG9yc2hpcCwgd2hldGhlciBpbiBTb3VyY2Ugb3IKICAgICAgT2JqZWN0IGZvcm0sIG1hZGUgYXZhaWxhYmxlIHVuZGVyIHRoZSBMaWNlbnNlLCBhcyBpbmRpY2F0ZWQgYnkgYQogICAgICBjb3B5cmlnaHQgbm90aWNlIHRoYXQgaXMgaW5jbHVkZWQgaW4gb3IgYXR0YWNoZWQgdG8gdGhlIHdvcmsKICAgICAgKGFuIGV4YW1wbGUgaXMgcHJvdmlkZWQgaW4gdGhlIEFwcGVuZGl4IGJlbG93KS4KCiAgICAgICJEZXJpdmF0aXZlIFdvcmtzIiBzaGFsbCBtZWFuIGFueSB3b3JrLCB3aGV0aGVyIGluIFNvdXJjZSBvciBPYmplY3QKICAgICAgZm9ybSwgdGhhdCBpcyBiYXNlZCBvbiAob3IgZGVyaXZlZCBmcm9tKSB0aGUgV29yayBhbmQgZm9yIHdoaWNoIHRoZQogICAgICBlZGl0b3JpYWwgcmV2aXNpb25zLCBhbm5vdGF0aW9ucywgZWxhYm9yYXRpb25zLCBvciBvdGhlciBtb2RpZmljYXRpb25zCiAgICAgIHJlcHJlc2VudCwgYXMgYSB3aG9sZSwgYW4gb3JpZ2luYWwgd29yayBvZiBhdXRob3JzaGlwLiBGb3IgdGhlIHB1cnBvc2VzCiAgICAgIG9mIHRoaXMgTGljZW5zZSwgRGVyaXZhdGl2ZSBXb3JrcyBzaGFsbCBub3QgaW5jbHVkZSB3b3JrcyB0aGF0IHJlbWFpbgogICAgICBzZXBhcmFibGUgZnJvbSwgb3IgbWVyZWx5IGxpbmsgKG9yIGJpbmQgYnkgbmFtZSkgdG8gdGhlIGludGVyZmFjZXMgb2YsCiAgICAgIHRoZSBXb3JrIGFuZCBEZXJpdmF0aXZlIFdvcmtzIHRoZXJlb2YuCgogICAgICAiQ29udHJpYnV0aW9uIiBzaGFsbCBtZWFuIGFueSB3b3JrIG9mIGF1dGhvcnNoaXAsIGluY2x1ZGluZwogICAgICB0aGUgb3JpZ2luYWwgdmVyc2lvbiBvZiB0aGUgV29yayBhbmQgYW55IG1vZGlmaWNhdGlvbnMgb3IgYWRkaXRpb25zCiAgICAgIHRvIHRoYXQgV29yayBvciBEZXJpdmF0aXZlIFdvcmtzIHRoZXJlb2YsIHRoYXQgaXMgaW50ZW50aW9uYWxseQogICAgICBzdWJtaXR0ZWQgdG8gTGljZW5zb3IgZm9yIGluY2x1c2lvbiBpbiB0aGUgV29yayBieSB0aGUgY29weXJpZ2h0IG93bmVyCiAgICAgIG9yIGJ5IGFuIGluZGl2aWR1YWwgb3IgTGVnYWwgRW50aXR5IGF1dGhvcml6ZWQgdG8gc3VibWl0IG9uIGJlaGFsZiBvZgogICAgICB0aGUgY29weXJpZ2h0IG93bmVyLiBGb3IgdGhlIHB1cnBvc2VzIG9mIHRoaXMgZGVmaW5pdGlvbiwgInN1Ym1pdHRlZCIKICAgICAgbWVhbnMgYW55IGZvcm0gb2YgZWxlY3Ryb25pYywgdmVyYmFsLCBvciB3cml0dGVuIGNvbW11bmljYXRpb24gc2VudAogICAgICB0byB0aGUgTGljZW5zb3Igb3IgaXRzIHJlcHJlc2VudGF0aXZlcywgaW5jbHVkaW5nIGJ1dCBub3QgbGltaXRlZCB0bwogICAgICBjb21tdW5pY2F0aW9uIG9uIGVsZWN0cm9uaWMgbWFpbGluZyBsaXN0cywgc291cmNlIGNvZGUgY29udHJvbCBzeXN0ZW1zLAogICAgICBhbmQgaXNzdWUgdHJhY2tpbmcgc3lzdGVtcyB0aGF0IGFyZSBtYW5hZ2VkIGJ5LCBvciBvbiBiZWhhbGYgb2YsIHRoZQogICAgICBMaWNlbnNvciBmb3IgdGhlIHB1cnBvc2Ugb2YgZGlzY3Vzc2luZyBhbmQgaW1wcm92aW5nIHRoZSBXb3JrLCBidXQKICAgICAgZXhjbHVkaW5nIGNvbW11bmljYXRpb24gdGhhdCBpcyBjb25zcGljdW91c2x5IG1hcmtlZCBvciBvdGhlcndpc2UKICAgICAgZGVzaWduYXRlZCBpbiB3cml0aW5nIGJ5IHRoZSBjb3B5cmlnaHQgb3duZXIgYXMgIk5vdCBhIENvbnRyaWJ1dGlvbi4iCgogICAgICAiQ29udHJpYnV0b3IiIHNoYWxsIG1lYW4gTGljZW5zb3IgYW5kIGFueSBpbmRpdmlkdWFsIG9yIExlZ2FsIEVudGl0eQogICAgICBvbiBiZWhhbGYgb2Ygd2hvbSBhIENvbnRyaWJ1dGlvbiBoYXMgYmVlbiByZWNlaXZlZCBieSBMaWNlbnNvciBhbmQKICAgICAgc3Vic2VxdWVudGx5IGluY29ycG9yYXRlZCB3aXRoaW4gdGhlIFdvcmsuCgogICAyLiBHcmFudCBvZiBDb3B5cmlnaHQgTGljZW5zZS4gU3ViamVjdCB0byB0aGUgdGVybXMgYW5kIGNvbmRpdGlvbnMgb2YKICAgICAgdGhpcyBMaWNlbnNlLCBlYWNoIENvbnRyaWJ1dG9yIGhlcmVieSBncmFudHMgdG8gWW91IGEgcGVycGV0dWFsLAogICAgICB3b3JsZHdpZGUsIG5vbi1leGNsdXNpdmUsIG5vLWNoYXJnZSwgcm95YWx0eS1mcmVlLCBpcnJldm9jYWJsZQogICAgICBjb3B5cmlnaHQgbGljZW5zZSB0byByZXByb2R1Y2UsIHByZXBhcmUgRGVyaXZhdGl2ZSBXb3JrcyBvZiwKICAgICAgcHVibGljbHkgZGlzcGxheSwgcHVibGljbHkgcGVyZm9ybSwgc3VibGljZW5zZSwgYW5kIGRpc3RyaWJ1dGUgdGhlCiAgICAgIFdvcmsgYW5kIHN1Y2ggRGVyaXZhdGl2ZSBXb3JrcyBpbiBTb3VyY2Ugb3IgT2JqZWN0IGZvcm0uCgogICAzLiBHcmFudCBvZiBQYXRlbnQgTGljZW5zZS4gU3ViamVjdCB0byB0aGUgdGVybXMgYW5kIGNvbmRpdGlvbnMgb2YKICAgICAgdGhpcyBMaWNlbnNlLCBlYWNoIENvbnRyaWJ1dG9yIGhlcmVieSBncmFudHMgdG8gWW91IGEgcGVycGV0dWFsLAogICAgICB3b3JsZHdpZGUsIG5vbi1leGNsdXNpdmUsIG5vLWNoYXJnZSwgcm95YWx0eS1mcmVlLCBpcnJldm9jYWJsZQogICAgICAoZXhjZXB0IGFzIHN0YXRlZCBpbiB0aGlzIHNlY3Rpb24pIHBhdGVudCBsaWNlbnNlIHRvIG1ha2UsIGhhdmUgbWFkZSwKICAgICAgdXNlLCBvZmZlciB0byBzZWxsLCBzZWxsLCBpbXBvcnQsIGFuZCBvdGhlcndpc2UgdHJhbnNmZXIgdGhlIFdvcmssCiAgICAgIHdoZXJlIHN1Y2ggbGljZW5zZSBhcHBsaWVzIG9ubHkgdG8gdGhvc2UgcGF0ZW50IGNsYWltcyBsaWNlbnNhYmxlCiAgICAgIGJ5IHN1Y2ggQ29udHJpYnV0b3IgdGhhdCBhcmUgbmVjZXNzYXJpbHkgaW5mcmluZ2VkIGJ5IHRoZWlyCiAgICAgIENvbnRyaWJ1dGlvbihzKSBhbG9uZSBvciBieSBjb21iaW5hdGlvbiBvZiB0aGVpciBDb250cmlidXRpb24ocykKICAgICAgd2l0aCB0aGUgV29yayB0byB3aGljaCBzdWNoIENvbnRyaWJ1dGlvbihzKSB3YXMgc3VibWl0dGVkLiBJZiBZb3UKICAgICAgaW5zdGl0dXRlIHBhdGVudCBsaXRpZ2F0aW9uIGFnYWluc3QgYW55IGVudGl0eSAoaW5jbHVkaW5nIGEKICAgICAgY3Jvc3MtY2xhaW0gb3IgY291bnRlcmNsYWltIGluIGEgbGF3c3VpdCkgYWxsZWdpbmcgdGhhdCB0aGUgV29yawogICAgICBvciBhIENvbnRyaWJ1dGlvbiBpbmNvcnBvcmF0ZWQgd2l0aGluIHRoZSBXb3JrIGNvbnN0aXR1dGVzIGRpcmVjdAogICAgICBvciBjb250cmlidXRvcnkgcGF0ZW50IGluZnJpbmdlbWVudCwgdGhlbiBhbnkgcGF0ZW50IGxpY2Vuc2VzCiAgICAgIGdyYW50ZWQgdG8gWW91IHVuZGVyIHRoaXMgTGljZW5zZSBmb3IgdGhhdCBXb3JrIHNoYWxsIHRlcm1pbmF0ZQogICAgICBhcyBvZiB0aGUgZGF0ZSBzdWNoIGxpdGlnYXRpb24gaXMgZmlsZWQuCgogICA0LiBSZWRpc3RyaWJ1dGlvbi4gWW91IG1heSByZXByb2R1Y2UgYW5kIGRpc3RyaWJ1dGUgY29waWVzIG9mIHRoZQogICAgICBXb3JrIG9yIERlcml2YXRpdmUgV29ya3MgdGhlcmVvZiBpbiBhbnkgbWVkaXVtLCB3aXRoIG9yIHdpdGhvdXQKICAgICAgbW9kaWZpY2F0aW9ucywgYW5kIGluIFNvdXJjZSBvciBPYmplY3QgZm9ybSwgcHJvdmlkZWQgdGhhdCBZb3UKICAgICAgbWVldCB0aGUgZm9sbG93aW5nIGNvbmRpdGlvbnM6CgogICAgICAoYSkgWW91IG11c3QgZ2l2ZSBhbnkgb3RoZXIgcmVjaXBpZW50cyBvZiB0aGUgV29yayBvcgogICAgICAgICAgRGVyaXZhdGl2ZSBXb3JrcyBhIGNvcHkgb2YgdGhpcyBMaWNlbnNlOyBhbmQKCiAgICAgIChiKSBZb3UgbXVzdCBjYXVzZSBhbnkgbW9kaWZpZWQgZmlsZXMgdG8gY2FycnkgcHJvbWluZW50IG5vdGljZXMKICAgICAgICAgIHN0YXRpbmcgdGhhdCBZb3UgY2hhbmdlZCB0aGUgZmlsZXM7IGFuZAoKICAgICAgKGMpIFlvdSBtdXN0IHJldGFpbiwgaW4gdGhlIFNvdXJjZSBmb3JtIG9mIGFueSBEZXJpdmF0aXZlIFdvcmtzCiAgICAgICAgICB0aGF0IFlvdSBkaXN0cmlidXRlLCBhbGwgY29weXJpZ2h0LCBwYXRlbnQsIHRyYWRlbWFyaywgYW5kCiAgICAgICAgICBhdHRyaWJ1dGlvbiBub3RpY2VzIGZyb20gdGhlIFNvdXJjZSBmb3JtIG9mIHRoZSBXb3JrLAogICAgICAgICAgZXhjbHVkaW5nIHRob3NlIG5vdGljZXMgdGhhdCBkbyBub3QgcGVydGFpbiB0byBhbnkgcGFydCBvZgogICAgICAgICAgdGhlIERlcml2YXRpdmUgV29ya3M7IGFuZAoKICAgICAgKGQpIElmIHRoZSBXb3JrIGluY2x1ZGVzIGEgIk5PVElDRSIgdGV4dCBmaWxlIGFzIHBhcnQgb2YgaXRzCiAgICAgICAgICBkaXN0cmlidXRpb24sIHRoZW4gYW55IERlcml2YXRpdmUgV29ya3MgdGhhdCBZb3UgZGlzdHJpYnV0ZSBtdXN0CiAgICAgICAgICBpbmNsdWRlIGEgcmVhZGFibGUgY29weSBvZiB0aGUgYXR0cmlidXRpb24gbm90aWNlcyBjb250YWluZWQKICAgICAgICAgIHdpdGhpbiBzdWNoIE5PVElDRSBmaWxlLCBleGNsdWRpbmcgdGhvc2Ugbm90aWNlcyB0aGF0IGRvIG5vdAogICAgICAgICAgcGVydGFpbiB0byBhbnkgcGFydCBvZiB0aGUgRGVyaXZhdGl2ZSBXb3JrcywgaW4gYXQgbGVhc3Qgb25lCiAgICAgICAgICBvZiB0aGUgZm9sbG93aW5nIHBsYWNlczogd2l0aGluIGEgTk9USUNFIHRleHQgZmlsZSBkaXN0cmlidXRlZAogICAgICAgICAgYXMgcGFydCBvZiB0aGUgRGVyaXZhdGl2ZSBXb3Jrczsgd2l0aGluIHRoZSBTb3VyY2UgZm9ybSBvcgogICAgICAgICAgZG9jdW1lbnRhdGlvbiwgaWYgcHJvdmlkZWQgYWxvbmcgd2l0aCB0aGUgRGVyaXZhdGl2ZSBXb3Jrczsgb3IsCiAgICAgICAgICB3aXRoaW4gYSBkaXNwbGF5IGdlbmVyYXRlZCBieSB0aGUgRGVyaXZhdGl2ZSBXb3JrcywgaWYgYW5kCiAgICAgICAgICB3aGVyZXZlciBzdWNoIHRoaXJkLXBhcnR5IG5vdGljZXMgbm9ybWFsbHkgYXBwZWFyLiBUaGUgY29udGVudHMKICAgICAgICAgIG9mIHRoZSBOT1RJQ0UgZmlsZSBhcmUgZm9yIGluZm9ybWF0aW9uYWwgcHVycG9zZXMgb25seSBhbmQKICAgICAgICAgIGRvIG5vdCBtb2RpZnkgdGhlIExpY2Vuc2UuIFlvdSBtYXkgYWRkIFlvdXIgb3duIGF0dHJpYnV0aW9uCiAgICAgICAgICBub3RpY2VzIHdpdGhpbiBEZXJpdmF0aXZlIFdvcmtzIHRoYXQgWW91IGRpc3RyaWJ1dGUsIGFsb25nc2lkZQogICAgICAgICAgb3IgYXMgYW4gYWRkZW5kdW0gdG8gdGhlIE5PVElDRSB0ZXh0IGZyb20gdGhlIFdvcmssIHByb3ZpZGVkCiAgICAgICAgICB0aGF0IHN1Y2ggYWRkaXRpb25hbCBhdHRyaWJ1dGlvbiBub3RpY2VzIGNhbm5vdCBiZSBjb25zdHJ1ZWQKICAgICAgICAgIGFzIG1vZGlmeWluZyB0aGUgTGljZW5zZS4KCiAgICAgIFlvdSBtYXkgYWRkIFlvdXIgb3duIGNvcHlyaWdodCBzdGF0ZW1lbnQgdG8gWW91ciBtb2RpZmljYXRpb25zIGFuZAogICAgICBtYXkgcHJvdmlkZSBhZGRpdGlvbmFsIG9yIGRpZmZlcmVudCBsaWNlbnNlIHRlcm1zIGFuZCBjb25kaXRpb25zCiAgICAgIGZvciB1c2UsIHJlcHJvZHVjdGlvbiwgb3IgZGlzdHJpYnV0aW9uIG9mIFlvdXIgbW9kaWZpY2F0aW9ucywgb3IKICAgICAgZm9yIGFueSBzdWNoIERlcml2YXRpdmUgV29ya3MgYXMgYSB3aG9sZSwgcHJvdmlkZWQgWW91ciB1c2UsCiAgICAgIHJlcHJvZHVjdGlvbiwgYW5kIGRpc3RyaWJ1dGlvbiBvZiB0aGUgV29yayBvdGhlcndpc2UgY29tcGxpZXMgd2l0aAogICAgICB0aGUgY29uZGl0aW9ucyBzdGF0ZWQgaW4gdGhpcyBMaWNlbnNlLgoKICAgNS4gU3VibWlzc2lvbiBvZiBDb250cmlidXRpb25zLiBVbmxlc3MgWW91IGV4cGxpY2l0bHkgc3RhdGUgb3RoZXJ3aXNlLAogICAgICBhbnkgQ29udHJpYnV0aW9uIGludGVudGlvbmFsbHkgc3VibWl0dGVkIGZvciBpbmNsdXNpb24gaW4gdGhlIFdvcmsKICAgICAgYnkgWW91IHRvIHRoZSBMaWNlbnNvciBzaGFsbCBiZSB1bmRlciB0aGUgdGVybXMgYW5kIGNvbmRpdGlvbnMgb2YKICAgICAgdGhpcyBMaWNlbnNlLCB3aXRob3V0IGFueSBhZGRpdGlvbmFsIHRlcm1zIG9yIGNvbmRpdGlvbnMuCiAgICAgIE5vdHdpdGhzdGFuZGluZyB0aGUgYWJvdmUsIG5vdGhpbmcgaGVyZWluIHNoYWxsIHN1cGVyc2VkZSBvciBtb2RpZnkKICAgICAgdGhlIHRlcm1zIG9mIGFueSBzZXBhcmF0ZSBsaWNlbnNlIGFncmVlbWVudCB5b3UgbWF5IGhhdmUgZXhlY3V0ZWQKICAgICAgd2l0aCBMaWNlbnNvciByZWdhcmRpbmcgc3VjaCBDb250cmlidXRpb25zLgoKICAgNi4gVHJhZGVtYXJrcy4gVGhpcyBMaWNlbnNlIGRvZXMgbm90IGdyYW50IHBlcm1pc3Npb24gdG8gdXNlIHRoZSB0cmFkZQogICAgICBuYW1lcywgdHJhZGVtYXJrcywgc2VydmljZSBtYXJrcywgb3IgcHJvZHVjdCBuYW1lcyBvZiB0aGUgTGljZW5zb3IsCiAgICAgIGV4Y2VwdCBhcyByZXF1aXJlZCBmb3IgcmVhc29uYWJsZSBhbmQgY3VzdG9tYXJ5IHVzZSBpbiBkZXNjcmliaW5nIHRoZQogICAgICBvcmlnaW4gb2YgdGhlIFdvcmsgYW5kIHJlcHJvZHVjaW5nIHRoZSBjb250ZW50IG9mIHRoZSBOT1RJQ0UgZmlsZS4KCiAgIDcuIERpc2NsYWltZXIgb2YgV2FycmFudHkuIFVubGVzcyByZXF1aXJlZCBieSBhcHBsaWNhYmxlIGxhdyBvcgogICAgICBhZ3JlZWQgdG8gaW4gd3JpdGluZywgTGljZW5zb3IgcHJvdmlkZXMgdGhlIFdvcmsgKGFuZCBlYWNoCiAgICAgIENvbnRyaWJ1dG9yIHByb3ZpZGVzIGl0cyBDb250cmlidXRpb25zKSBvbiBhbiAiQVMgSVMiIEJBU0lTLAogICAgICBXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IKICAgICAgaW1wbGllZCwgaW5jbHVkaW5nLCB3aXRob3V0IGxpbWl0YXRpb24sIGFueSB3YXJyYW50aWVzIG9yIGNvbmRpdGlvbnMKICAgICAgb2YgVElUTEUsIE5PTi1JTkZSSU5HRU1FTlQsIE1FUkNIQU5UQUJJTElUWSwgb3IgRklUTkVTUyBGT1IgQQogICAgICBQQVJUSUNVTEFSIFBVUlBPU0UuIFlvdSBhcmUgc29sZWx5IHJlc3BvbnNpYmxlIGZvciBkZXRlcm1pbmluZyB0aGUKICAgICAgYXBwcm9wcmlhdGVuZXNzIG9mIHVzaW5nIG9yIHJlZGlzdHJpYnV0aW5nIHRoZSBXb3JrIGFuZCBhc3N1bWUgYW55CiAgICAgIHJpc2tzIGFzc29jaWF0ZWQgd2l0aCBZb3VyIGV4ZXJjaXNlIG9mIHBlcm1pc3Npb25zIHVuZGVyIHRoaXMgTGljZW5zZS4KCiAgIDguIExpbWl0YXRpb24gb2YgTGlhYmlsaXR5LiBJbiBubyBldmVudCBhbmQgdW5kZXIgbm8gbGVnYWwgdGhlb3J5LAogICAgICB3aGV0aGVyIGluIHRvcnQgKGluY2x1ZGluZyBuZWdsaWdlbmNlKSwgY29udHJhY3QsIG9yIG90aGVyd2lzZSwKICAgICAgdW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IChzdWNoIGFzIGRlbGliZXJhdGUgYW5kIGdyb3NzbHkKICAgICAgbmVnbGlnZW50IGFjdHMpIG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzaGFsbCBhbnkgQ29udHJpYnV0b3IgYmUKICAgICAgbGlhYmxlIHRvIFlvdSBmb3IgZGFtYWdlcywgaW5jbHVkaW5nIGFueSBkaXJlY3QsIGluZGlyZWN0LCBzcGVjaWFsLAogICAgICBpbmNpZGVudGFsLCBvciBjb25zZXF1ZW50aWFsIGRhbWFnZXMgb2YgYW55IGNoYXJhY3RlciBhcmlzaW5nIGFzIGEKICAgICAgcmVzdWx0IG9mIHRoaXMgTGljZW5zZSBvciBvdXQgb2YgdGhlIHVzZSBvciBpbmFiaWxpdHkgdG8gdXNlIHRoZQogICAgICBXb3JrIChpbmNsdWRpbmcgYnV0IG5vdCBsaW1pdGVkIHRvIGRhbWFnZXMgZm9yIGxvc3Mgb2YgZ29vZHdpbGwsCiAgICAgIHdvcmsgc3RvcHBhZ2UsIGNvbXB1dGVyIGZhaWx1cmUgb3IgbWFsZnVuY3Rpb24sIG9yIGFueSBhbmQgYWxsCiAgICAgIG90aGVyIGNvbW1lcmNpYWwgZGFtYWdlcyBvciBsb3NzZXMpLCBldmVuIGlmIHN1Y2ggQ29udHJpYnV0b3IKICAgICAgaGFzIGJlZW4gYWR2aXNlZCBvZiB0aGUgcG9zc2liaWxpdHkgb2Ygc3VjaCBkYW1hZ2VzLgoKICAgOS4gQWNjZXB0aW5nIFdhcnJhbnR5IG9yIEFkZGl0aW9uYWwgTGlhYmlsaXR5LiBXaGlsZSByZWRpc3RyaWJ1dGluZwogICAgICB0aGUgV29yayBvciBEZXJpdmF0aXZlIFdvcmtzIHRoZXJlb2YsIFlvdSBtYXkgY2hvb3NlIHRvIG9mZmVyLAogICAgICBhbmQgY2hhcmdlIGEgZmVlIGZvciwgYWNjZXB0YW5jZSBvZiBzdXBwb3J0LCB3YXJyYW50eSwgaW5kZW1uaXR5LAogICAgICBvciBvdGhlciBsaWFiaWxpdHkgb2JsaWdhdGlvbnMgYW5kL29yIHJpZ2h0cyBjb25zaXN0ZW50IHdpdGggdGhpcwogICAgICBMaWNlbnNlLiBIb3dldmVyLCBpbiBhY2NlcHRpbmcgc3VjaCBvYmxpZ2F0aW9ucywgWW91IG1heSBhY3Qgb25seQogICAgICBvbiBZb3VyIG93biBiZWhhbGYgYW5kIG9uIFlvdXIgc29sZSByZXNwb25zaWJpbGl0eSwgbm90IG9uIGJlaGFsZgogICAgICBvZiBhbnkgb3RoZXIgQ29udHJpYnV0b3IsIGFuZCBvbmx5IGlmIFlvdSBhZ3JlZSB0byBpbmRlbW5pZnksCiAgICAgIGRlZmVuZCwgYW5kIGhvbGQgZWFjaCBDb250cmlidXRvciBoYXJtbGVzcyBmb3IgYW55IGxpYWJpbGl0eQogICAgICBpbmN1cnJlZCBieSwgb3IgY2xhaW1zIGFzc2VydGVkIGFnYWluc3QsIHN1Y2ggQ29udHJpYnV0b3IgYnkgcmVhc29uCiAgICAgIG9mIHlvdXIgYWNjZXB0aW5nIGFueSBzdWNoIHdhcnJhbnR5IG9yIGFkZGl0aW9uYWwgbGlhYmlsaXR5LgoKICAgRU5EIE9GIFRFUk1TIEFORCBDT05ESVRJT05TCgogICBBUFBFTkRJWDogSG93IHRvIGFwcGx5IHRoZSBBcGFjaGUgTGljZW5zZSB0byB5b3VyIHdvcmsuCgogICAgICBUbyBhcHBseSB0aGUgQXBhY2hlIExpY2Vuc2UgdG8geW91ciB3b3JrLCBhdHRhY2ggdGhlIGZvbGxvd2luZwogICAgICBib2lsZXJwbGF0ZSBub3RpY2UsIHdpdGggdGhlIGZpZWxkcyBlbmNsb3NlZCBieSBicmFja2V0cyAiW10iCiAgICAgIHJlcGxhY2VkIHdpdGggeW91ciBvd24gaWRlbnRpZnlpbmcgaW5mb3JtYXRpb24uIChEb24ndCBpbmNsdWRlCiAgICAgIHRoZSBicmFja2V0cyEpICBUaGUgdGV4dCBzaG91bGQgYmUgZW5jbG9zZWQgaW4gdGhlIGFwcHJvcHJpYXRlCiAgICAgIGNvbW1lbnQgc3ludGF4IGZvciB0aGUgZmlsZSBmb3JtYXQuIFdlIGFsc28gcmVjb21tZW5kIHRoYXQgYQogICAgICBmaWxlIG9yIGNsYXNzIG5hbWUgYW5kIGRlc2NyaXB0aW9uIG9mIHB1cnBvc2UgYmUgaW5jbHVkZWQgb24gdGhlCiAgICAgIHNhbWUgInByaW50ZWQgcGFnZSIgYXMgdGhlIGNvcHlyaWdodCBub3RpY2UgZm9yIGVhc2llcgogICAgICBpZGVudGlmaWNhdGlvbiB3aXRoaW4gdGhpcmQtcGFydHkgYXJjaGl2ZXMuCgogICBDb3B5cmlnaHQgW3l5eXldIFtuYW1lIG9mIGNvcHlyaWdodCBvd25lcl0KCiAgIExpY2Vuc2VkIHVuZGVyIHRoZSBBcGFjaGUgTGljZW5zZSwgVmVyc2lvbiAyLjAgKHRoZSAiTGljZW5zZSIpOwogICB5b3UgbWF5IG5vdCB1c2UgdGhpcyBmaWxlIGV4Y2VwdCBpbiBjb21wbGlhbmNlIHdpdGggdGhlIExpY2Vuc2UuCiAgIFlvdSBtYXkgb2J0YWluIGEgY29weSBvZiB0aGUgTGljZW5zZSBhdAoKICAgICAgIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKICAgVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQogICBkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLAogICBXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KICAgU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZAogICBsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4="
            },
            "url": "https://www.apache.org/licenses/LICENSE-2.0.txt"
          }
        }
      ]
    },
    {
      "type": "library",
      "group": "org.acme",
      "name": "card-verifier",
      "version": "1.0.2",
      "licenses": [
        {
          "expression": "EPL-2.0 OR GPL-2.0 WITH Classpath-exception-2.0"
        }
      ]
    },
    {
      "type": "library",
      "group": "com.example",
      "name": "util",
      "version": "2.0.0",
      "licenses": [
        {
          "license": {
            "name": "Example, Inc. Commercial License",
            "text": {
              "contentType": "text/plain",
              "encoding": "base64",
              "content": "VGhlIHRleHQgZm9yIHRoZSBFeGFtcGxlLCBJbmMuIENvbW1lcmNpYWwgTGljZW5zZSBnb2VzIGhlcmU="
            }
          }
        }
      ]
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Describe software assembly

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "application",
      "name": "Acme Commerce Suite",
      "version": "2.0.0",
      "swid": {
        "tagId": "swidgen-cebab27e-da95-213c-8b73-d1d3afcb806f_2.0.0",
        "name": "Acme Commerce Suite",
        "version": "2.0.0"
      },
      "components": [
        {
          "type": "application",
          "name": "Acme Storefront Server",
          "version": "3.7.0",
          "swid": {
            "tagId": "swidgen-80d7e827-4031-288b-2313-2781923fe86e_3.7.0",
            "name": "Acme Storefront Server",
            "version": "3.7.0"
          }
        },
        {
          "type": "application",
          "name": "Acme Payment Processor",
          "version": "3.1.1",
          "swid": {
            "tagId": "swidgen-ac2f2eec-05c0-907e-3a54-a6782a24885e_3.1.1",
            "name": "Acme Payment Processor",
            "version": "3.1.1"
          }
        }
      ]
    },
    {
      "type": "application",
      "name": "Acme Management App",
      "version": "2.0.0",
      "swid": {
        "tagId": "swidgen-8429d5b6-2dbf-0fde-768b-aaab0e5881c8_2.0.0",
        "name": "Acme Management App",
        "version": "2.0.0"
      }
    },
    {
      "type": "application",
      "name": "Acme License Utility",
      "version": "2.0.0",
      "swid": {
        "tagId": "swidgen-4332a8dc-13e3-7d44-2f52-0a53f4898995_2.0.0",
        "name": "Acme License Utility",
        "version": "2.0.0"
      }
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Describe dependency graph

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "metadata": {
    "component": {
      "bom-ref": "acme-app",
      "type": "application",
      "name": "Acme Application",
      "version": "9.1.1"
    }
  },
  "components": [
    {
      "bom-ref": "pkg:maven/org.acme/web-framework@1.0.0",
      "type": "library",
      "group": "org.acme",
      "name": "web-framework",
      "version": "1.0.0",
      "purl": "pkg:maven/org.acme/web-framework@1.0.0"
    },
    {
      "bom-ref": "pkg:maven/org.acme/persistence@3.1.0",
      "type": "library",
      "group": "org.acme",
      "name": "persistence",
      "version": "3.1.0",
      "purl": "pkg:maven/org.acme/persistence@3.1.0"
    },
    {
      "bom-ref": "pkg:maven/org.acme/common-util@3.0.0",
      "type": "library",
      "group": "org.acme",
      "name": "common-util",
      "version": "3.0.0",
      "purl": "pkg:maven/org.acme/common-util@3.0.0"
    }
  ],
  "dependencies": [
    {
      "ref": "acme-app",
      "dependsOn": [
        "pkg:maven/org.acme/web-framework@1.0.0",
        "pkg:maven/org.acme/persistence@3.1.0"
      ]
    },
    {
      "ref": "pkg:maven/org.acme/web-framework@1.0.0",
      "dependsOn": [
        "pkg:maven/org.acme/common-util@3.0.0"
      ]
    },
    {
      "ref": "pkg:maven/org.acme/persistence@3.1.0",
      "dependsOn": [
        "pkg:maven/org.acme/common-util@3.0.0"
      ]
    },
    {
      "ref": "pkg:maven/org.acme/common-util@3.0.0",
      "dependsOn": []
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Describe component Provenance
(origin, history, lineage)

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "supplier": {
        "name": "Example, Inc.",
        "url": [
          "https://example.com",
          "https://example.net"
        ],
        "contact": [
          {
            "name": "Example Support AMER Distribution",
            "email": "support@example.com",
            "phone": "800-555-1212"
          },
          {
            "name": "Example Support APAC",
            "email": "support@apac.example.com"
          }
        ]
      },
      "author": "Example Development Labs - Alpha Team",
      "publisher": "Example Development Labs",
      "group": "com.example",
      "name": "crypto-library",
      "version": "3.0.0",
      "swid": {
        "tagId": "swidgen-5dcb79af-a1d2-61b3-34fd-536c53b08810_3.0.0",
        "name": "Crypto Library",
        "version": "3.0.0",
        "text": {
          "contentType": "text/xml",
          "encoding": "base64",
          "content": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiID8+CjxTb2Z0d2FyZUlkZW50aXR5IHhtbDpsYW5nPSJFTiIgbmFtZT0iQ3J5cHRvIExpYnJhcnkiIHZlcnNpb249IjMuMC4wIiAKIHZlcnNpb25TY2hlbWU9Im11bHRpcGFydG51bWVyaWMiIAogdGFnSWQ9InN3aWRnZW4tNWRjYjc5YWYtYTFkMi02MWIzLTM0ZmQtNTM2YzUzYjA4ODEwXzMuMC4wIiAKIHhtbG5zPSJodHRwOi8vc3RhbmRhcmRzLmlzby5vcmcvaXNvLzE5NzcwLy0yLzIwMTUvc2NoZW1hLnhzZCI+IAogeG1sbnM6eHNpPSJodHRwOi8vd3d3LnczLm9yZy8yMDAxL1hNTFNjaGVtYS1pbnN0YW5jZSIgCiB4c2k6c2NoZW1hTG9jYXRpb249Imh0dHA6Ly9zdGFuZGFyZHMuaXNvLm9yZy9pc28vMTk3NzAvLTIvMjAxNS1jdXJyZW50L3NjaGVtYS54c2Qgc2NoZW1hLnhzZCIgPgogIDxNZXRhIGdlbmVyYXRvcj0iU1dJRCBUYWcgT25saW5lIEdlbmVyYXRvciB2MC4xIiAvPiAKICA8RW50aXR5IG5hbWU9IkV4YW1wbGUsIEluYy4iIHJlZ2lkPSJleGFtcGxlLmNvbSIgcm9sZT0idGFnQ3JlYXRvciIgLz4gCjwvU29mdHdhcmVJZGVudGl0eT4="
        }
      },
      "purl": "pkg:maven/com.example/crypto-library@3.0.0?repository_url=repo.example.com"
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Describe component Pedigree
(ancestors, descendants, variants)

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "group": "com.acme",
      "name": "sample-library",
      "version": "1.0.0",
      "pedigree": {
        "ancestors": [
          {
            "type": "library",
            "group": "org.example",
            "name": "sample-library",
            "version": "1.0.0"
          }
        ],
        "commits": [
          {
            "uid": "7638417db6d59f3c431d3e1f261cc637155684cd",
            "url": "https://location/to/7638417db6d59f3c431d3e1f261cc637155684cd",
            "author": {
              "timestamp": "2018-11-13T20:20:39+00:00",
              "name": "John Doe",
              "email": "john.doe@example.com"
            },
            "committer": {
              "timestamp": "2018-11-13T20:20:39+00:00",
              "name": "Jane Doe",
              "email": "jane.doe@example.com"
            },
            "message": "Initial commit"
          }
        ],
        "patches": [
          {
            "type": "unofficial",
            "diff": {
              "text": {
                "contentType": "text/plain",
                "encoding": "base64",
                "content": "ZXhhbXBsZSBkaWZmIGhlcmU="
              },
              "url": "uri/to/changes.diff"
            },
            "resolves": [
              {
                "type": "enhancement",
                "id": "JIRA-17240",
                "description": "Great new feature that does something",
                "source": {
                  "name": "Acme Org",
                  "url": "https://issues.acme.org/17240"
                }
              }
            ]
          },
          {
            "type": "backport",
            "diff": {
              "text": {
                "contentType": "text/plain",
                "encoding": "base64",
                "content": "ZXhhbXBsZSBkaWZmIGhlcmU="
              },
              "url": "uri/to/changes.diff"
            },
            "resolves": [
              {
                "type": "security",
                "id": "CVE-2019-9997",
                "name": "CVE-2019-9997",
                "description": "Issue description here",
                "source": {
                  "name": "NVD",
                  "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-9997"
                },
                "references": [
                  "http://some/other/site-1",
                  "http://some/other/site-2"
                ]
              },
              {
                "type": "defect",
                "id": "JIRA-874319",
                "description": "Description of fix here",
                "source": {
                  "name": "Example Org",
                  "url": "https://issues.example.org/874319"
                },
                "references": [
                  "http://some/other/site-1",
                  "http://some/other/site-2"
                ]
              }
            ]
          }
        ]
      }
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)
## Packaging & Distribution details

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "metadata": {
    "timestamp": "2020-04-13T20:20:39+00:00",
    "tools": [
      {
        "vendor": "Awesome Vendor",
        "name": "Awesome Tool",
        "version": "9.1.2",
        "hashes": [
          {
            "alg": "SHA-1",
            "content": "25ed8e31b995bb927966616df2a42b979a2717f0"
          },
          {
            "alg": "SHA-256",
            "content": "a74f733635a19aefb1f73e5947cef59cd7440c6952ef0f03d09d974274cbd6df"
          }
        ]
      }
    ],
    "authors": [
      {
        "name": "Samantha Wright",
        "email": "samantha.wright@example.com",
        "phone": "800-555-1212"
      }
    ],
    "component": {
      "type": "application",
      "author": "Acme Super Heros",
      "name": "Acme Application",
      "version": "9.1.1",
      "swid": {
        "tagId": "swidgen-242eb18a-503e-ca37-393b-cf156ef09691_9.1.1",
        "name": "Acme Application",
        "version": "9.1.1",
        "text": {
          "contentType": "text/xml",
          "encoding": "base64",
          "content": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiID8+CjxTb2Z0d2FyZUlkZW50aXR5IHhtbDpsYW5nPSJFTiIgbmFtZT0iQWNtZSBBcHBsaWNhdGlvbiIgdmVyc2lvbj0iOS4xLjEiIAogdmVyc2lvblNjaGVtZT0ibXVsdGlwYXJ0bnVtZXJpYyIgCiB0YWdJZD0ic3dpZGdlbi1iNTk1MWFjOS00MmMwLWYzODItM2YxZS1iYzdhMmE0NDk3Y2JfOS4xLjEiIAogeG1sbnM9Imh0dHA6Ly9zdGFuZGFyZHMuaXNvLm9yZy9pc28vMTk3NzAvLTIvMjAxNS9zY2hlbWEueHNkIj4gCiB4bWxuczp4c2k9Imh0dHA6Ly93d3cudzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIiAKIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL3N0YW5kYXJkcy5pc28ub3JnL2lzby8xOTc3MC8tMi8yMDE1LWN1cnJlbnQvc2NoZW1hLnhzZCBzY2hlbWEueHNkIiA+CiAgPE1ldGEgZ2VuZXJhdG9yPSJTV0lEIFRhZyBPbmxpbmUgR2VuZXJhdG9yIHYwLjEiIC8+IAogIDxFbnRpdHkgbmFtZT0iQWNtZSwgSW5jLiIgcmVnaWQ9ImV4YW1wbGUuY29tIiByb2xlPSJ0YWdDcmVhdG9yIiAvPiAKPC9Tb2Z0d2FyZUlkZW50aXR5Pg=="
        }
      }
    },
    "manufacture": {
      "name": "Acme, Inc.",
      "url": [
        "https://example.com"
      ],
      "contact": [
        {
          "name": "Acme Professional Services",
          "email": "professional.services@example.com"
        }
      ]
    },
    "supplier": {
      "name": "Acme, Inc.",
      "url": [
        "https://example.com"
      ],
      "contact": [
        {
          "name": "Acme Distribution",
          "email": "distribution@example.com"
        }
      ]
    }
  },
  "components": [
  ]
}
```


[comment]: # (!!! data-auto-animate)

## Composition completeness

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "metadata": {
    "component": {
      "bom-ref": "acme-application-1.0",
      "type": "application",
      "name": "Acme Application",
      "version": "1.0"
    }
  },
  "components": [
    {
      "bom-ref": "pkg:maven/partner/shaded-library@1.0",
      "type": "library",
      "name": "Partner Shaded Library",
      "version": "1.0",
      "purl": "pkg:maven/partner/shaded-library@1.0",
      "components": [
        {
          "bom-ref": "pkg:maven/ossproject/library@2.0",
          "type": "library",
          "name": "Some Opensource Library",
          "version": "2.0",
          "purl": "pkg:maven/ossproject/library@2.0"
        }
      ]
    },
    {
      "type": "library",
      "name": "Acme Library",
      "version": "3.0",
      "purl": "pkg:maven/acme/library@3.0"
    }
  ],
  "dependencies": [
    {
      "ref": "acme-application-1.0",
      "dependsOn": [
        "pkg:maven/partner/shaded-library@1.0",
        "pkg:maven/acme/library@3.0"
      ]
    }
  ],
  "compositions": [
    {
      "aggregate": "complete",
      "assemblies": [
        "pkg:maven/partner/shaded-library@1.0"
      ],
      "dependencies": [
        "acme-application-1.0"
      ]
    },
    {
      "aggregate": "unknown",
      "assemblies": [
        "pkg:maven/acme/library@3.0"
      ]
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Vulnerability remediation
(communicate temporary workarounds)


```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "group": "com.acme",
      "name": "sample-library",
      "version": "1.0.0",
      "pedigree": {
        "ancestors": [
          {
            "type": "library",
            "group": "org.example",
            "name": "sample-library",
            "version": "1.0.0"
          }
        ],
        "commits": [
          {
            "uid": "7638417db6d59f3c431d3e1f261cc637155684cd",
            "url": "https://location/to/7638417db6d59f3c431d3e1f261cc637155684cd",
            "author": {
              "timestamp": "2018-11-13T20:20:39+00:00",
              "name": "John Doe",
              "email": "john.doe@example.com"
            },
            "committer": {
              "timestamp": "2018-11-13T20:20:39+00:00",
              "name": "Jane Doe",
              "email": "jane.doe@example.com"
            },
            "message": "Initial commit"
          }
        ],
        "patches": [
          {
            "type": "backport",
            "diff": {
              "text": {
                "contentType": "text/plain",
                "encoding": "base64",
                "content": "ZXhhbXBsZSBkaWZmIGhlcmU="
              },
              "url": "uri/to/changes.diff"
            },
            "resolves": [
              {
                "type": "security",
                "id": "CVE-2019-9997",
                "name": "CVE-2019-9997",
                "description": "Issue description here",
                "source": {
                  "name": "NVD",
                  "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-9997"
                },
                "references": [
                  "http://some/other/site-1",
                  "http://some/other/site-2"
                ]
              }
            ]
          }
        ]
      }
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Vulnerability exploitability
(communicate known unhandled cases)

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "version": 1,
  "vulnerabilities": [
    {
      "id": "CVE-2018-7489",
      "source": {
        "name": "NVD",
        "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-9997"
      },
      "ratings": [
        {
          "source": {
            "name": "NVD",
            "url": "https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.0"
          },
          "score": 9.8,
          "severity": "critical",
          "method": "CVSSv3",
          "vector": "AN/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H"
        }
      ],
      "cwes": [
        184,
        502
      ],
      "description": "FasterXML jackson-databind before 2.7.9.3, 2.8.x before 2.8.11.1 and 2.9.x before 2.9.5 allows unauthenticated remote code execution because of an incomplete fix for the CVE-2017-7525 deserialization flaw. This is exploitable by sending maliciously crafted JSON input to the readValue method of the ObjectMapper, bypassing a blacklist that is ineffective if the c3p0 libraries are available in the classpath.",
      "recommendation": "Upgrade com.fasterxml.jackson.core:jackson-databind to version 2.6.7.5, 2.8.11.1, 2.9.5 or higher.",
      "advisories": [
        {
          "title": "GitHub Commit",
          "url": "https://github.com/FasterXML/jackson-databind/commit/6799f8f10cc78e9af6d443ed6982d00a13f2e7d2"
        },
        {
          "title": "GitHub Issue",
          "url": "https://github.com/FasterXML/jackson-databind/issues/1931"
        }
      ],
      "created": "2021-01-01T00:00:00.000Z",
      "published": "2021-01-01T00:00:00.000Z",
      "updated": "2021-01-01T00:00:00.000Z",
      "analysis": {
        "state": "not_affected",
        "justification": "code_not_reachable",
        "response": ["will_not_fix", "update"],
        "detail": "An optional explanation of why the application is not affected by the vulnerable component."
      },
      "affects": [
        {
          "ref": "urn:cdx:3e671687-395b-41f5-a30f-a58921a69b79/1#jackson-databind-2.8.0"
        }
      ]
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)

## Security advisories

```json
{
  "$schema": "http://cyclonedx.org/schema/bom-1.5.schema.json",
  "bomFormat": "CycloneDX",
  "specVersion": "1.5",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "components": [
    {
      "type": "library",
      "group": "org.example",
      "name": "mylibrary",
      "version": "1.0.0",
      "cpe": "cpe:/a:example:mylibrary:1.0.0",
      "purl": "pkg:maven/org.example/mylibrary@1.0.0",
      "externalReferences": [
        {
          "type": "advisories",
          "url": "https://example.org/security/advisories.json"
        }
      ]
    }
  ]
}
```

[comment]: # (!!! data-auto-animate)


## And more...

* Tooling for analysis and reporting
* Signing and Verification
* Conformance to legal requirements

etc.

[comment]: # (!!!)

## Are SBOMs supported on CPAN?

[comment]: # (!!! data-auto-animate)

## Are SBOMs supported on CPAN?

Not today.

[comment]: # (!!! data-auto-animate)

## Are SBOMs supported on CPAN?

Not today.

But we would like to change this.

[comment]: # (!!! data-auto-animate)


### What can I do?


Join the CPAN Security WG!

* If you work with & **care about security**
* …Have **tuits** or a **security commons** aware employer
* …Enjoy getting your **ducks in a row** 🦆🦆

Note:

* Do you have a **security background** or care about the Toolchain?
* Do you have **time to volunteer**?
* Is your employer willing to **dedicate a percentage of your time** to improve our security commons?

We need volunteers!


[comment]: # (!!!)

### Find us!

ircs://irc.perl.org#cpan-security

https://security.metacpan.org/

https://github.com/CPAN-Security/

mailto:cpan-security@perl.org


Note:

[comment]: # (!!!)

# Thanks!

* Salve J. Nilsen

🦆🦆🦆🦆🦆🦆


Note:

Thanks!
