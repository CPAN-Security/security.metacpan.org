# Contributing to CPANSec

Thank you for caring about the security of the Perl and CPAN ecosystems and distributions!

To join the conversation you can connect to one of [our channels listed on our website](https://security.metacpan.org/).
Share with us if you are interested in working on any specific topics or efforts, and let's take it from there!


# How to contribute changes to the CPANSec website itself

This website runs on GitHub Pages, and uses Ruby's _Jekyll_ gem for generating static pages.

## Installing `ruby` and `gem`

```
apt install ruby gem
```

## Installing Jekyll

```
gem install jekyll bundler
```

## Installing website dependencies

```
bundler install
```

## Testing the website

```
bundler exec jekyll serve
```
