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
- **image** is the banner. It displays at a **16:9** aspect ratio on the post header and
  the blog cards, so export it at 16:9 (for example, 1600x900 pixels or larger). It is
  also the social sharing preview, which platforms crop to roughly 2:1, so keep text,
  logos, and faces centered.
- Images go in `static/img/` and are referenced as `img/filename.png`.
- For announcement and recap posts, speaker names, bios, photos, and the schedule can be
  fetched from Sessionize if the CFP ran there; see
  [Fetching speakers and the schedule from Sessionize](#fetching-speakers-and-the-schedule-from-sessionize).

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
- **speakers** is a list of speaker profile pages in `content/speakers/`, referenced by
  filename (for example `speakers = ["daniel-chen"]`), and renders their profile cards on
  the event page. The Sessionize importer creates these profiles. A plain
  `speaker = "Name"` string also works for names without a profile page, which is how the
  pre-2025 Meetup-era events are written.
- **image** is optional and does not appear on the events list or the event page; it is
  only used as the social sharing preview when the event page is linked. 16:9 with
  centered content works well.
- **venueWanted = true** shows a "Venue wanted" badge while you're still looking.
- **meetupUrl** records the original Meetup page for events from our Meetup era. Our 72
  past Meetup events (2015-2025) were imported this way. To link back to Meetup on the
  event's detail page, add a button in the body:

```
{{</* button url="https://www.meetup.com/pyladies-vancouver/events/123/" label="View this event on Meetup" variant="outline" icon="fa-brands fa-meetup" */>}}
```

The events list intentionally shows no external links; each row links to the event's own
page, and the linkback to Meetup lives there.

### Fetching speakers and the schedule from Sessionize

When a meetup's CFP ran through Sessionize, the speaker names, titles, bios, photos, and
the session schedule can be fetched instead of typed up by hand. The Popular theme ships
an import script,
[`scripts/sessionize-import.py`](https://github.com/Mariatta/hugo-theme-popular/blob/main/scripts/sessionize-import.py),
that converts a Sessionize event's public JSON into the theme's content model:

```
python3 sessionize-import.py --site .
```

- Our **embed ID** (`c44c13ew`) is stored in `popular-import.toml` at the repo root, so
  the command above needs no flags; it resolves to
  `https://sessionize.com/api/v2/c44c13ew/view/All`. Embed IDs come from the Sessionize
  organizer dashboard under **API / Embeds**; creating one there makes the endpoint
  public, and no authentication is needed. Note this is different from our CFP page
  (`sessionize.com/pyladies-vancouver-meetup`), which is only for submitting talks.
- Because the theme is installed as a Hugo Module, the script is not in this repo's tree.
  It is on disk in Hugo's module cache
  (`~/Library/Caches/hugo_cache/modules/filecache/modules/pkg/mod/github.com/!mariatta/hugo-theme-popular@v<version>/scripts/`
  on macOS), or grab it from the theme repo link above. Plain Python, no installs needed.
- It never overwrites existing files (pass `--force` to allow it), and `--dry-run` shows
  what it would write.
- Speaker photos come through as Sessionize-hosted URLs. For blog posts, download the
  headshots into `static/img/` (as `img/speaker_<name>.jpg`) and reference the local
  copies instead, so posts stay self-contained.

## Organizer and author photos

- **Organizer cards** (`content/organizers/`, the `photo` field) display as a **square
  (1:1)**, so use a square photo, at least 600x600 pixels, with the face centered.
- **Author photos** (`content/authors/`, shown on blog posts) and **persona shortcode
  photos** render as small circles, so a square photo with the face centered works here
  too; 300x300 pixels is plenty.
- Like banners, photos go in `static/img/` and are referenced as `img/filename.jpg`.

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

See the [theme's README](https://github.com/Mariatta/hugo-theme-popular#readme) for the
full syntax of each.

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
