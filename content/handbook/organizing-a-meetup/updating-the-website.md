---
author: PyLadies Vancouver
title: Updating the website
description: How the PyLadies Vancouver website is built and edited.
weight: 80
toc: true
---

The site is a [Hugo](https://gohugo.io/) project using the Hinode theme, in
[our GitHub repo](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io).
Changes go through a pull request and deploy automatically via Netlify once merged.

## Blog posts

Blog posts live in `content/blog/` as Markdown files with front matter (title, author,
date, description, tags, thumbnail). Event photos and banner images go in `assets/img/`.

### Banner images

A post's `thumbnail` banner is cropped to different aspect ratios in different places, so
export it at **21:9, ideally 2800x1200 pixels** (the largest size the site renders), and
keep the important content (text, logos, faces) **centered** so nothing gets cut off:

- **Post header:** cropped to 21:9 (ultra-wide)
- **Homepage blog card:** cropped to 16:9
- **Social sharing preview:** cropped to 2:1

A 21:9 image with centered content looks good in all three.

## Building locally

Build locally with the Hugo version the theme is pinned to: the newer Homebrew Hugo can
break the Hinode theme. Run the local dev server, check your changes, then open a pull
request.

## Events

Upcoming events are pulled live from our Luma calendar, which is embedded on the
[Events page](/events/) and the homepage. Once an event is published on Luma it appears on
the site automatically, with no code change needed per event.
