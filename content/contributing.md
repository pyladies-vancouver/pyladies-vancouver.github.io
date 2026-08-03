+++
title = "Contributing to the Website"
type = "docs"
weight = 70
eyebrow = "Contributing"
lead = "How to add blog posts, events, and pages to vancouver.pyladies.com. Anyone can contribute: you don't need special access, just a GitHub account and a pull request."
+++

## How the site works

The site is a [Hugo](https://gohugo.io/) project using the **Popular** theme, in
[our GitHub repo](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io).
Changes go through a pull request and deploy automatically via Netlify once merged. Every
pull request gets a Netlify deploy preview, so you (and reviewers) can see the rendered
result before merging.

The theme is a [Hugo Module](https://gohugo.io/hugo-modules/) pinned in `go.mod`, so
there is no `themes/` directory in the repo: Hugo downloads the theme for you on the
first build. You need both Hugo (v0.126.0 or newer) and [Go](https://go.dev/dl/)
installed. The theme's styling is plain CSS, so there is no SCSS or npm step.

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
- **Recap posts** have their own toolkit: the `photo` and `gallery` shortcodes for the
  photos from the night, and `pullquote` for lifting a line out of the post. See
  [Shortcodes you can use](#shortcodes-you-can-use), and note that `photo` crops to 4:3.
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

venueRef = "visst"       # or the flat venue/address pair below
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
- **venueRef** points at a venue page in `content/venues/` by filename (for example
  `venueRef = "visst"`). It links the venue, reuses its address and arrival notes, and
  feeds the event's location into the page's structured data (JSON-LD). Prefer it for
  places we return to. For a one-off spot, use the flat `venue = "Name"` and
  `address = "..."` pair instead. Override a venue's default arrival notes for one event
  with **venueNotes**, and add a check-in reminder with **checkin**.
- **cancelled = true** shows a "Cancelled" badge on the event and marks it cancelled in
  the structured data. Keep the page up so links still resolve.
- **online = true** marks the event as virtual in the structured data; the `rsvp` link is
  used as the location. Leave it off for in-person events.
- **price** and **currency** set a paid-event Offer in the structured data (for example
  `price = 10`). Events with no price are advertised as free. The site-wide default
  currency is set in `hugo.toml` under `[params.seo]`.
- **speakers** is a list of speaker profile pages in `content/speakers/`, referenced by
  filename (for example `speakers = ["daniel-chen"]`), and renders their profile cards on
  the event page. The Sessionize importer creates these profiles. A plain
  `speaker = "Name"` string also works for names without a profile page, which is how the
  pre-2025 Meetup-era events are written.
- **talks** lists the night's talks. It renders a Talks section on the event page and
  feeds the [talk archive](/talks/). Each entry needs a `title`; `speaker`, `recording`,
  and `slides` are optional:

```toml
[[talks]]
  title = "What Happens When Your Agent Has to Wait for a Human"
  speaker = "melanie-warrick"
  recording = "https://www.youtube.com/watch?v=..."
```

  Unlike the event-level `speaker` field above, `talks[].speaker` only accepts a
  `content/speakers/` filename: a plain name logs a build warning and renders no byline,
  so leave it out when the speaker has no profile page. For a single-talk meetup you can
  skip `talks` entirely and put `recording` and `slides` at the top level instead. Either
  way, a past event with a recording shows a "Recording available" cue on the events
  list. The `/talks/` archive itself is switched on by `content/talks/_index.md`.
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

## Venue pages

Places we return to get a page in `content/venues/`, which events point at with
`venueRef`. Alongside `title`, `description`, `address`, and `website`, a venue page
carries the access details shown in its "Getting there & access" section:

```toml
+++
title = "VISST"
description = "A non-profit, STEM-focused high school on West Broadway."
address = "1490 West Broadway, Vancouver"
website = "https://www.visst.ca/"

wheelchair = true
transit = "A short walk from the Broadway-City Hall SkyTrain station, plus several bus routes."
parking = "Metered street parking on West Broadway."
access = "Enter through the main doors on Broadway. The elevator is to the left."
+++
```

- **wheelchair = true** shows a "Wheelchair accessible" badge on the venue page and on
  every event held there.
- **transit** and **parking** are one-liners. **access** is a freeform Markdown note for
  anything else worth knowing: which door, the elevator, washrooms, a quiet space.
- **notes** are arrival instructions inherited by every event at that venue; a single
  event can override them with `venueNotes`.

Most of our venue pages have these fields commented out, waiting on confirmation. Please
don't guess at accessibility: ask the venue, then fill it in. Getting this wrong sends
someone to a building they can't get into.

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
- `photo`: a captioned figure, for recap posts. `src` and `alt` are both required, and a
  missing `alt` fails the build on purpose. Photos render at a **4:3** aspect ratio and
  are centre-cropped to fit, so export at 4:3, or keep faces and slides away from the
  left and right edges.
- `gallery`: wraps a run of `photo` shortcodes into a grid. There is no lightbox and no
  JavaScript; each photo links to its full-size image.
- `pullquote`: pulls a quote out of the surrounding text, with an optional `cite`. Use
  the `{{%/* pullquote */%}}` form so the quote renders as Markdown.
- `faq` and `question`: a frequently-asked-questions block. `faq` wraps a series of
  `question` shortcodes and also emits FAQ structured data for search engines.

See the [theme's README](https://github.com/Mariatta/hugo-theme-popular#readme) for the
full syntax of each.

## Site configuration

Menus, brand colours, the footer, and social links all live in `hugo.toml` under
`[params]`. Most content contributions never need to touch it.

`hugo.toml` also declares the site's extra outputs: `/llms.txt`, a plain-text summary of
the next meetup and our key pages for AI agents, and an iCalendar feed at
`/events/calendar.ics` that the events section opts into with `outputs` in
`content/events/_index.md`. Our [Luma calendar](https://luma.com/pyladiesvancouver)
remains the subscribe link we point people at.

## Questions and ideas

We work in the open, so the default place for anything website related is
[GitHub issues](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io/issues):
questions, bug reports, typos you don't have time to fix yourself, and ideas for new
content are all welcome there. Issues keep the discussion public and searchable, so the
next contributor benefits from the answer too.

For the meetup-organizing side of things, see the [Meetup Runbooks](/runbooks/); for ways
to participate beyond the website, see the [Handbook](/handbook/). You can also say hi in
the **#city-vancouver** channel on the [PyLadies Slack](https://slackin.pyladies.com).
