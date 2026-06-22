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
date, description, tags, thumbnail). Event photos go in `assets/img/`.

## Building locally

Build locally with the Hugo version the theme is pinned to — the newer Homebrew Hugo can
break the Hinode theme. Run the local dev server, check your changes, then open a pull
request.

## Events

Upcoming events are pulled live from our Luma calendar, which is embedded on the
[Events page](/events/) and the homepage. Once an event is published on Luma it appears on
the site automatically — no code change needed per event.
