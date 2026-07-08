+++
title = "Meetup Runbooks"
type = "docs"
weight = 60
eyebrow = "Runbooks"
lead = "The behind-the-scenes steps we follow to run a meetup, from finding a date to publishing the recap. The stages overlap and the timeline flexes, but this is the general order. Checklist progress is saved in your browser, so you can close the tab and pick up where you left off."
+++

## Before you start

{{% callout tone="warn" title="Always CC vancouver@pyladies.com" %}}
CC **vancouver@pyladies.com** on any communication with venues, vendors, and speakers. It
keeps the whole organizing team in the loop and means nothing depends on a single
person's inbox: as long as that address is copied, you're good to go.
{{% /callout %}}

For the principles behind these steps, what we ask of hosts, how we support speakers,
and how to get involved, see the [Handbook](/handbook/).

## Where things live

Here's where everything lives and what we use it for.

| What | Where | Used for |
| --- | --- | --- |
| **Website** | [github.com/pyladies-vancouver/pyladies-vancouver.github.io](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io) | Our site, built with [Hugo](https://gohugo.io/) and the Popular theme, deployed via Netlify |
| **Luma** | [luma.com/pyladiesvancouver](https://luma.com/pyladiesvancouver) | RSVPs and event pages (our primary platform) |
| **Meetup** | [meetup.com/pyladies-vancouver](https://www.meetup.com/pyladies-vancouver/) | Announcing events; we point people to Luma to RSVP |
| **Sessionize** | [sessionize.com/pyladies-vancouver-meetup](https://sessionize.com/pyladies-vancouver-meetup/) | Call for proposals and managing speaker info |
| **PyLadies Vancouver donations** | [Donate](https://psfmember.org/civicrm/contribute/transact/?reset=1&id=60) | Supporting our local chapter |
| **Email** | vancouver at pyladies dot com | Getting in touch with the organizers |
| **Slack** | [#city-vancouver via slackin.pyladies.com](https://slackin.pyladies.com) | Where organizers and volunteers coordinate |

We also share updates on
[LinkedIn](https://linkedin.com/company/pyladies-vancouver),
[Instagram](https://www.instagram.com/pyladiesyvr),
[Mastodon](https://fosstodon.org/@pyladies_vancouver), and
[Bluesky](https://bsky.app/profile/pyladiesvancouver.bsky.social).

## Pick a date and venue

We aim to confirm a date and a venue host first, since the venue is usually the longest
lead time.

### What we need from a venue

The bare minimum we need from a venue host is **a space that fits our group and a
projector/AV setup** for the talks. The PyLadies organizer still handles all the
coordination. See [Host a venue](/host/) for what we ask
of hosts.

Food (often pizza) is **optional**: appreciated but not required, and it can be covered by
a separate sponsor who isn't the venue host.

### Hosting agreements

Most venues ask us to sign an **event hosting agreement** covering booking lead time,
setup and cleanup responsibilities, access procedures, and a cancellation policy. Read it
carefully: agreements often require a host contact or volunteer to be confirmed weeks in
advance, and the booking can be cancelled if that isn't arranged in time.

{{% callout tone="warn" title="Venue access details are private" %}}
Door codes, alarm procedures, and day-of contacts are sensitive and are kept in a private
organizer document, shared only with the team running that specific event, never
published on this site.
{{% /callout %}}

## Speakers and call for proposals

We collect talk submissions through **Sessionize**. Our call for proposals lives at
[sessionize.com/pyladies-vancouver-meetup](https://sessionize.com/pyladies-vancouver-meetup/).

### Talk formats we accept

- **Lightning talks**: 5 minutes
- **Standard talks**: 15–30 minutes
- **Workshops**: up to 2 hours

No experience is necessary to speak: we welcome first-time and seasoned speakers alike.
Point prospective speakers to the [Speak at our meetup](/speak/)
guide.

### Working with Sessionize

Once talks are accepted and speakers confirm, Sessionize holds the session titles,
abstracts, and speaker bios. Organizers can pull this data from the Sessionize API to fill
in the event page and recap, instead of retyping it: there are read-only API endpoints for
sessions and speakers.

{{% checklist key="rb-speakers" %}}
Confirm each speaker's talk title, abstract, and bio before publishing the event.
Collect a headshot for the event page and promotion.
Keep vancouver@pyladies.com CC'd on speaker communications.
{{% /checklist %}}

## Create the Luma event

We publish each event on **Luma**, which handles RSVPs, reminders, and a subscribable
calendar. Build the description from the confirmed Sessionize talk and speaker details,
using the [Luma event template](#luma-event-template) below as your starting point.

### Tips

- **Luma's API requires a paid Luma Plus plan**, so on the free tier we create events
  through the web editor. Luma supports Markdown, so the template pastes in directly.
- Luma supports only two heading levels (`#` and `##`), so keep the description to those.
- Add the speaker photo(s) from Sessionize as the event/cover image.
- Double-check the date, start/end time (leave room for cleanup), location, and capacity.

Once published, the event appears on our [Events page](/events/) and homepage through the
embedded Luma calendar. Also add a page for it under `content/events/` on the website,
see [Updating the website](#updating-the-website).

## Luma event template

Paste this into the Luma event description (it's Markdown) and fill in the talk and speaker
details from Sessionize. Adjust the agenda times to match the program. Luma supports only
two heading levels (`#` and `##`).

````markdown
Join PyLadies Vancouver for our meetup at **[VENUE]**!

# [TALK TITLE] by [SPEAKER NAME]

[TALK ABSTRACT]

**About [SPEAKER NAME]**

[SPEAKER BIO]

[Speaker links]

## Agenda

- **6:00 PM**: Doors open, food & mingling
- **6:15 PM**: PyLadies intro & community updates
- **6:20 PM**: [TALK TITLE] ([SPEAKER NAME])
- **7:00 PM**: Fundraiser, swag & wrap-up
- **7:45 PM**: Event ends

## Support PyLadies Vancouver

Help us keep our meetups running: [donate to PyLadies Vancouver](https://psfmember.org/civicrm/contribute/transact/?reset=1&id=60)
to support the costs of organizing community events like this one.

We'll also be selling PyLadies tote bags in support of **PyLadies Vancouver**, and we'll
have conference swag to share!

## Thank you to our venue host: [VENUE]

Thank you to [VENUE] for providing the space for this meetup!

## Getting in

[Arrival and building-access instructions for attendees: which floor, how to be buzzed
in, parking and transit notes.]

## House rules

Please stay within the designated event areas. Photos of our event and attendees (with
their consent) are welcome. All attendees must follow the
[PyLadies Code of Conduct](https://www.pyladies.com/CodeOfConduct/).
````

### Other fields to set on Luma

- **Title**, **date/time** (leave room for cleanup before the venue's hard stop)
- **Location** and **capacity**
- **Cover image**: the speaker photo from Sessionize

## Announce the event

Once the Luma event is live, announce it on **Meetup** and across **all of our social media
channels**, pointing everyone to Luma to RSVP.

{{% checklist key="rb-announce" %}}
Post the event on [Meetup](https://www.meetup.com/pyladies-vancouver/).
Post on [LinkedIn](https://linkedin.com/company/pyladies-vancouver).
Post on [Mastodon](https://fosstodon.org/@pyladies_vancouver).
Post on [Instagram](https://www.instagram.com/pyladiesyvr).
Post on [Bluesky](https://bsky.app/profile/pyladiesvancouver.bsky.social).
{{% /checklist %}}

People can also
[subscribe to our Luma calendar](https://api.luma.com/ics/get?entity=calendar&id=cal-EefnU0O5BifyHgg)
to get upcoming events in their own calendar app automatically.

## On the day

On the day, the organizing team runs the show:

{{% checklist key="rb-dayof" %}}
Doors & check-in: welcome attendees as they arrive.
PyLadies intro & community updates: kick things off and share announcements.
Introduce the speaker(s) and keep the program on time.
Q&A after each talk.
Fundraising: tote bag sales, conference swag, and pointing people to donate.
{{% /checklist %}}

Follow the venue's access and conduct rules throughout, and make sure everyone is aware of
the [PyLadies Code of Conduct](https://www.pyladies.com/CodeOfConduct/). Day-of venue access
details live in the private organizer document for that event.

## Wrap-up and recap

### Wrap up the venue

After the event, reset the space to how we found it:

{{% checklist key="rb-wrapup" %}}
Return furniture to its original arrangement.
Clean up tables, dishes, and any food.
Sort garbage, recycling, and compost per the venue's rules.
Follow the venue's closing/security checklist exactly.
{{% /checklist %}}

Following the wrap-up steps carefully is what keeps us welcome to come back. The specific
closing steps for each venue are in that event's private organizer document.

### Publish a recap

Write up a recap as a [blog post](/blog/): a thank-you to the speaker and venue, photos
from the event, and a note about what's coming next. This is also a good place to list
other Python and open source events worth knowing about. See
[Updating the website](#updating-the-website) for how to add a post.

## Updating the website

The site is a [Hugo](https://gohugo.io/) project using the **Popular** theme, in
[our GitHub repo](https://github.com/pyladies-vancouver/pyladies-vancouver.github.io).
Changes go through a pull request and deploy automatically via Netlify once merged.

The full guide (setting up locally, writing blog posts, adding events, banner image
sizes, shortcodes) lives in [Contributing to the Website](/contributing/). The short
version for organizers running a meetup:

- **When the Luma event is published**, add a page for it in `content/events/`. That
  powers the "Next meetup" section on the homepage and the upcoming/past lists on the
  [Events page](/events/), alongside the embedded Luma calendar.
- **After the event**, publish the recap as a blog post in `content/blog/`.
