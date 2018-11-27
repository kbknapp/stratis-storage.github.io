# stratis-storage.github.io

This guide covers building this static site

## Pre-Reqs

This site is built with [`zola`](https://github.com/getzola/zola) which is a static site generator (SSG) written in [Rust](https://rust-lang.org) and based on [`hugo`](https://gohugo.io/)

`zola` is a single binary whose installation instructions are located [on the getzola.org installation page](https://www.getzola.org/documentation/getting-started/installation/).

## Building

First we clone the repo:

```
$ git clone https://github.com/kbknapp/stratis-storage.github.io
 [ ... ]

$ cd stratis-storage.github.io
```

Now just build the site:

```
$ zola build
Building site...
-> Creating 3 pages (2 orphan), 0 sections, and processing 0 images
Done in 84ms.
```

The site can now be served using only the contents of the `public/` directory.

## Editing

All pages are added to the `content/` directory as Markdown files.

### Posts

"bare" pages, or "posts", (i.e. ones in the base of the `content/` directory) are automatically added to the front page. Currently only a single "release note". To add additional files, use the "front matter" (the portions at the top of the file between `+++` lines) from the `relnotes-1.0.md` file as a template for new posts.

### "Static" (aka Orphan) Pages

Pages in subdirectories of the `content/` directory (such as the `content/static/` directory) are *not* automatically added to the front page and will need to be linked from some other page. These are also known as *orphan* pages. These are still markdown files that will be rendered into HTML files by `zola`.

### Static Content

Any content inside the `static/` directory (*not* `content/static/`) will be copied into the built site verbatim. For example, `static/imgs/stratis_d28445.jpg` -> `public/imgs/stratis_d28445.jpg`.

## Theming

The current theme in use is a customized version of [`hyde`](https://github.com/getzola/hyde) and can be found in `themes/hyde/`.

## Further Info

More information about how to use `zola` can be found on [getzola.org](https://www.getzola.org)
