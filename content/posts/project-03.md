+++
date = '2025-01-14T12:53:51-06:00'
draft = false 
title = 'Project 03'
+++


# Project-03 My blog projects
I have been writing technical blog posts, feel free to check them out!

Here's a link to my Blog for CSCI 0451 class taken during spring 2023: 
[My_Flabbergasted_CSCI_0451_Blog](https://xianzhiwang1.github.io/CS0451-page-site)

Here's a link to my other blog, which contains some miscellaneous items: 
[A Blog I started that I called My Very Own](https://xianzhiwang1.github.io/My-Very-Own-Blog)

I made those blog sites when I was a undergrad, and
I used quarto for those blog projects,
as well as my portfolio website itself.
It used to be organized as such:


### About this site
I have made this website using [quarto](https://quarto.org/docs/get-started/),
so basically, I write everything in markdown in a `main.md` file in the `projects`
directory, and after I am finished, I run a terminal command:
```sh
quarto render
```
while in the directory of this quarto project. The files that I edit
to make this website basically have the following directory structure: 
```sh
├── index.qmd
├── projects
│   ├── project-01
│   │   └── main.md
│   ├── project-02
│   │   └── main.md
│   ├── project-03
│   │   └── main.md
│   └── project-04
│       └── main.md
├── _quarto.yml
```
and after hitting that magic `quarto render`, it automatically
generates a `docs` directory that has a lot more stuff in it, 
and the directory structure looks like this:
```sh
├── docs
│   ├── about.html
│   ├── index.html
│   ├── listings.json
│   ├── projects
│   │   ├── project-01
│   │   │   └── main.html
│   │   ├── project-02
│   │   │   └── main.html
│   │   └── project-03
│   │       └── main.html
│   ├── search.json
│   ├── site_libs
│   │   ├── bootstrap
│   │   │   ├── bootstrap-dark.min.css
│   │   │   ├── bootstrap-icons.css
│   │   │   ├── bootstrap-icons.woff
│   │   │   ├── bootstrap.min.css
│   │   │   └── bootstrap.min.js
│   │   ├── clipboard
│   │   │   └── clipboard.min.js
│   │   ├── quarto-html
│   │   │   ├── anchor.min.js
│   │   │   ├── popper.min.js
│   │   │   ├── quarto.js
│   │   │   ├── quarto-syntax-highlighting.css
│   │   │   ├── quarto-syntax-highlighting-dark.css
│   │   │   ├── tippy.css
│   │   │   └── tippy.umd.min.js
│   │   ├── quarto-listing
│   │   │   ├── list.min.js
│   │   │   └── quarto-listing.js
│   │   ├── quarto-nav
│   │   │   ├── headroom.min.js
│   │   │   └── quarto-nav.js
│   │   └── quarto-search
│   │       ├── autocomplete.umd.js
│   │       ├── fuse.min.js
│   │       └── quarto-search.js
│   └── styles.css
├── favicon.ico
```
and that's where the magic happens.
Then all I need to do is check that
*deploy from `docs`* box on github,
so the github pages will know to get
everything it needs for the website 
from the `docs` folder.

### Transition to HUGO
as of Jan 2025, I'm learning
how to use HUGO to generate my web page.
The idea is the same: I write posts in markdown,
and let HUGO to do the heavy lifting to create 
the actual website. For me, it's a work in progress,
I always try to learn something new.




