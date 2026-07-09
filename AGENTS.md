# AGENTS.md: working on the PyLadies Vancouver website

Instructions for AI agents (and new contributors) working in this repository.

## What this repo is

The [PyLadies Vancouver](https://vancouver.pyladies.com/) website: a
[Hugo](https://gohugo.io/) site using the
[Popular theme](https://github.com/Mariatta/hugo-theme-popular), deployed via Netlify on
merge to `main`.

## Read the site's own docs first

The full how-to guides are published site content. Read the relevant one before making
content changes; they are the source of truth and this file does not duplicate them:

- `content/contributing.md`: how to write blog posts and add events, image sizes and
  where images live, shortcodes, fetching speakers and the schedule from Sessionize,
  and the site configuration layout.
- `content/handbook.md`: the organizer handbook (ways to participate, how the
  community runs).
- `content/runbooks.md`: step-by-step runbooks for organizing a meetup, including the
  blog announcement and recap steps.

## Build and serve

```
hugo server        # local dev server
hugo               # one-off build
```

The theme is a **Hugo Module** pinned in `go.mod`/`go.sum`, so Go must be installed.
There is no `themes/` directory. Update the theme with
`hugo mod get github.com/Mariatta/hugo-theme-popular@vX.Y.Z` (versions follow the
theme's tags; see its CHANGELOG).

## Gotchas

- `buildFuture = true` in `hugo.toml` is required: upcoming meetups are future-dated
  pages in `content/events/` and power the events list and the homepage.
- The `[module]` table in `hugo.toml` must stay below the top-level keys
  (`enableRobotsTXT`, `buildFuture`, ...), or TOML silently swallows them into
  `[module]`.
- This site has **no analytics, on purpose**. Do not add analytics or suggest adding
  them.
- The `button` shortcode is a plain single tag with named args only:
  `{{</* button url="..." label="..." */>}}`. Do not self-close it and do not give it
  a body.
- Every image needs meaningful alt text.

## Writing style

- No em dashes anywhere; use a comma or a colon instead.
- Plain, concrete wording; no flowery adverbs (no "beautifully", "wonderfully", and
  the like).
