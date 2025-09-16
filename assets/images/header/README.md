# Header and teaser images that can be used in news and blog posts

Standard size: 1280x400 (please don't use other sizes!)
Teaser size: 512x160    (40% of standard size)

## To use in a news or blog post

```yaml
excerpt: "This post should [...]"
header:
  overlay_image: /assets/images/header/DEFAULT.IMG # Pick an image you like, or upload your own
  overlay_filter: 0.6 # same as adding an opacity of 0.6 to a black background
  caption: "Photo credit: [@sjn](https://github.com/sjn)" # Give proper credit!
  teaser: /assets/images/teaser/DEFAULT.IMG # Remember to add a resized image if you uploaded your own
  actions:
    - label: "Report a vulnerability"
      url: "/docs/report.html"

```

## Converting your own uploads

How to resize your own image

```bash
    # Install the convert(1) tool for batch resizing
    apt install imagemagick

    # Resize all JPG's added to the ../header/ dir to 40%, and place them in ../teaser/
    find ../header/ -mtime -1 -daystart -iname '*.JPG' \
       | while read f; do echo convert $f -resize 40% ${f/header/teaser}\; ; done \
       | sh -x
```


