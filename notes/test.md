---
toc: true
type: page
title: Test page
mastodon: { username: sjn, instance: chaos.social }
---

* https://kramdown.gettalong.org/quickref.html
* https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax


# H1

<!-- Does not work -->
{::warning}
don't break it!
{:/warning}


!!! note this is a note

!!! danger do not try this danger sign

> **Note:** more notes

> [!NOTE]
> test note

## H2

> A citation


### H3

; term
; definition


### H3

[Foo*bar]:../docs/glossary.md#author 'title (with parens)'
[Foo*baz]:../docs/glossary.md#maintainer 'Someone who maintains a project'

We make a link with [Foo*bar] in it


#### H4

[Foo*bar]{: #foo-id}
: definition with [Foo*baz] in it

### H3

<details>

<summary>Click me</summary>
  
### Heading

1. Foo
2. Bar
   * Baz
   * Qux

### Some Javascript

```js
  function logSomething(something) {
    console.log('Something', something);
  }
```

</details>

<details>

<summary>Click me</summary>

| Header 1 | Header 2 |
| -------- | -------- |
| Row 1    | Row 1    |
| Row 2    | Row 2    |
  
</details>


## H2

Here is a simple footnote[^1]. No mention of SBOM.

[^1]: My ref.


## H2

A named footnote[^foo].

[^foo]: New ref with foo, but no HTML.


### H3

This is an HTML
example.

----

*[HTML]: Hyper Text Markup Language
*[SBOM]: Software Bill of Materials – a common machine-readable set of standards for storing and communicating metadata

----

## Github variables

Found on https://jekyll.github.io/github-metadata/site.github/

### public_repositories

{% for repository in site.github.public_repositories %}
* [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}

### Edit this

[Edit this page]({{ site.github.repository_url }}/{{ page.path }})


### Debug

<pre>
    site: {{ site.google | jsonify | escape }}
    page: {{ page | jsonify | escape }}
    layout: {{ layout | jsonify | escape }}
    content: {{ content | jsonify | escape }}
    paginator: {{ paginator | jsonify | escape }}
</pre>
