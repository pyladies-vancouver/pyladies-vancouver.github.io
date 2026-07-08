+++
title = "Contributing to the Website"
type = "docs"
weight = 70
eyebrow = "Contributing"
lead = "How to add blog posts, events, and pages to vancouver.pyladies.com. Anyone can contribute: you don't need special access, just a GitHub account and a pull request."
+++

## How the site works

The site is a [Hugo](https://gohugo.io/) project using the **Popular** theme (bundled in
`themes/popular`), in
[our GitHub repo](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io).
Changes go through a pull request and deploy automatically via Netlify once merged. Every
pull request gets a Netlify deploy preview, so you (and reviewers) can see the rendered
result before merging.

The theme uses plain CSS: no SCSS, npm, or Hugo modules. A standard Hugo install
(v0.126.0 or newer) is all you need.

## Getting set up

1. Fork and clone the repo, or create a branch if you have access.
2. Run the local dev server:

```sh
hugo server
```

3. Open http://localhost:1313/ and edit files under `content/`. The browser reloads as
   you save.
4. When it looks right, open a pull request against `main`.

### New to git and GitHub?

Contributing to this website is a great way to get started in open source: the changes
are small and low-stakes, the workflow (fork, branch, pull request, review) is exactly
what you'll use on any other open source project, and a friendly organizer reviews every
pull request. Some good resources for learning the tools:

- [Git "Hello World" on GitHub Docs](https://docs.github.com/en/get-started/start-your-journey/hello-world):
  create a repo, branch, commit, and open your first pull request
- [GitHub Skills](https://skills.github.com/): free, hands-on interactive courses
- [Pro Git](https://git-scm.com/book): the definitive git book, free to read online
- [First Contributions](https://github.com/firstcontributions/first-contributions): a
  practice repo for making your very first pull request
- [Open Source Guides: How to Contribute](https://opensource.guide/how-to-contribute/):
  the bigger picture of contributing to open source

Stuck on a git problem?
[Open an issue](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io/issues)
describing where you're stuck and we'll help you through it. Working in the open like
this is normal in open source, and no question is too basic.

## Writing a blog post

Blog posts live in `content/blog/` as Markdown files:

```yaml
---
authors: ["mariatta"]
title: "Recap: our amazing workshop"
date: 2026-07-15
description: "One or two sentences shown on the blog cards and in search results."
tags: ["meetup", "events", "pyladies", "vancouver"]
image: img/my-banner.png
---
```

- **authors** refers to author profiles in `content/authors/` by filename. First time
  writing? Add yourself: copy `content/authors/mariatta.md` and fill in your name, role,
  bio, and links. One-off guest writers can use `guestAuthors` in the post instead.
- **image** is the banner. It displays at a **16:9** aspect ratio on the post header, the
  homepage blog card, and social sharing previews, so export it at 16:9 (for example,
  1600x900 pixels or larger) and keep text, logos, and faces centered.
- Images go in `static/img/` and are referenced as `img/filename.png`.

## Adding an event

Each meetup gets a small page in `content/events/`. Future-dated events show under
**Upcoming** on the [Events page](/events/) and power the "Next meetup" section on the
homepage; once the date passes, they move to **Past** automatically.

```toml
+++
title = "August meetup: something wonderful"
date = 2026-08-10T18:00:00-07:00
description = "One or two sentences shown on the event row."
image = "img/august-banner.png"
tags = ["meetup", "talks"]

venue = "Venue name"
address = "123 Street, Vancouver"
time = "6:00 PM"
speaker = "Speaker Name"
rsvp = "https://luma.com/pyladiesvancouver"
+++

A short description of the event. Link to the announcement blog post if there is one.
```

Field notes:

- **date** is the event start time, with the Vancouver UTC offset (`-07:00` in summer,
  `-08:00` in winter). It controls the upcoming/past split.
- **rsvp** shows an RSVP button; use it for upcoming events only.
- **venueWanted = true** shows a "Venue wanted" badge while you're still looking.
- **meetupUrl** records the original Meetup page for events from our Meetup era. Our 72
  past Meetup events (2015-2025) were imported this way. To link back to Meetup on the
  event's detail page, add a button in the body:

```
{{</* button url="https://www.meetup.com/pyladies-vancouver/events/123/" label="View this event on Meetup" variant="outline" icon="fa-brands fa-meetup" */>}}
```

The events list intentionally shows no external links; each row links to the event's own
page, and the linkback to Meetup lives there.

## Shortcodes you can use

The theme ships shortcodes for use in any Markdown page:

- `button`: a styled link, as in the example above. Variants: `primary`, `secondary`,
  `outline`, `ghost`, `dark`.
- `callout`: an info/tip/warn box. Use the `{{%/* callout */%}}` form so the body renders
  as Markdown.
- `persona`: a speaker or person card with photo, name, and bio.
- `checklist`: a tick-box list that remembers progress in the visitor's browser (used in
  the [Runbooks](/runbooks/)).
- `badge`: a small label like "Confirmed".

See `themes/popular/README.md` for the full syntax of each.

## Site configuration

Menus, brand colours, the footer, and social links all live in `hugo.toml` under
`[params]`. Most content contributions never need to touch it.

## Questions and ideas

We work in the open, so the default place for anything website related is
[GitHub issues](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io/issues):
questions, bug reports, typos you don't have time to fix yourself, and ideas for new
content are all welcome there. Issues keep the discussion public and searchable, so the
next contributor benefits from the answer too.

For the meetup-organizing side of things, see the [Meetup Runbooks](/runbooks/); for ways
to participate beyond the website, see the [Handbook](/handbook/). You can also say hi in
the **#city-vancouver** channel on the [PyLadies Slack](https://slackin.pyladies.com).
