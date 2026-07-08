---
authors: ["mariatta"]
title: "July meetup: AI agents and LLMs, plus Python and PyLadies news"
date: 2026-06-23
description: "Join PyLadies Vancouver on July 6 for two talks on AI agents and LLMs, plus a roundup of Python and PyLadies news: award winners, open CFPs, and upcoming conferences."
tags: ["python", "pyladies", "vancouver", "meetup", "events", "ai"]
image: img/julyblogbanner.png
---

We're excited to announce our next PyLadies Vancouver meetup on **Monday, July 6, 2026**,
hosted at **Improving Vancouver**! This month we have **two talks** on AI agents and large
language models. Come for the talks, stay for the community, and the pizza 🍕. Read on for
the details, plus a roundup of Python and PyLadies news.

## Our July meetup

### RSVP on Luma

Spots are limited, so please RSVP through our Luma calendar:

{{< button url="https://luma.com/pyladiesvancouver" label="RSVP on Luma" icon="fa-solid fa-calendar" >}}

We handle RSVPs through [Luma](https://luma.com/pyladiesvancouver) now, and you can also
[subscribe to our Luma calendar](https://api.luma.com/ics/get?entity=calendar&id=cal-EefnU0O5BifyHgg)
to get future events in your own calendar app.

### The talks

**What Happens When Your Agent Has to Wait for a Human, by Melanie Warrick**

You built an agent in Python. It reasons, calls tools, handles its own steps, and then it
hits a step that needs a human to approve something. What happens to your agent's state
while it waits? Melanie shows how **durable execution** with Temporal keeps the loop alive
through crashes and long waits, with a short live demo.

**A Practical Introduction to Generative AI and Large Language Models, by Daniel Chen**

How do large language models actually work, and why can the same prompt give different
answers? Daniel, a Data Science Lecturer at UBC, gives a practical introduction to
generative AI and LLMs, and how to use them effectively in Python-based data science
workflows.

### Thank you to our venue host: Improving Vancouver

A big thank you to [Improving Vancouver](https://improving.com/locations/vancouver/) for
hosting us **and providing pizza** for the evening! Improving Vancouver is an IT consulting
and software development firm specializing in application development, data engineering, and
AI solutions. We're grateful for their support of the local Python community.

### Support PyLadies Vancouver

PyLadies Vancouver is run entirely by volunteers, and donations help us keep our meetups
free and welcoming. If you're able, please consider chipping in:

{{< button url="https://psfmember.org/civicrm/contribute/transact/?reset=1&id=60" label="Donate to PyLadies Vancouver" variant="secondary" icon="fa-solid fa-heart" >}}

Love our PyLadies Vancouver tote bags? For a **minimum donation of $25**, you can pick up
one of these at a future meetup!

<figure style="max-width:20rem;margin:1.5rem auto;text-align:center">
  <img src="/img/pyladiesvancouver-tote.jpg" alt="PyLadies Vancouver tote bag" loading="lazy" style="width:100%;aspect-ratio:1/1;object-fit:cover;border-radius:12px">
  <figcaption style="font-size:.85rem;color:#5b6b76;margin-top:.5rem">PyLadies Vancouver tote bag</figcaption>
</figure>

## PyLadies news

We're one of many PyLadies chapters! If you're travelling, or know Pythonistas elsewhere,
here are a few other active chapters worth following:

- **[PyLadies Toronto](https://www.meetup.com/pyladies-toronto/)**: talks and social
  meetups
- **[PyLadies Boston](https://www.meetup.com/pyladies-boston/)**: monthly "Grab a Byte"
  virtual lunches and talk previews with Boston Python
- **[PyLadies Montreal](https://www.meetup.com/pyladies-montreal/)**: a fellow Canadian
  chapter, led by Denny Perez (one of this year's Outstanding PyLady Award winners!)

You can find your nearest chapter on the [PyLadies website](https://pyladies.com/locations/).

It's been a wonderful season for PyLadies recognition, and we want to shine a light on
members of our global PyLadies community. Congratulations to the 2026
[Outstanding PyLady Award](https://pyladies.com/blog/Celebrating-the-Winners-of-the-Outstanding-PyLady-Awards-for-2026/outstanding-pylady-winners/)
recipients: María José Molina-Contreras, Denny Perez, and Fay Shaw! And among this year's
[PSF Community Service Award](https://www.python.org/community/awards/psf-awards/)
recipients, we're especially celebrating these PyLadies: Inessa Pawson (PyLadies SWFL),
María José Molina-Contreras (PyLadies en Español), Micaela Reyes (PyLadies Manila), and
Sarah Kuchinsky (PyLadies Silicon Valley). 🎉

{{% callout tone="tip" title="Know someone who deserves recognition?" %}} You can nominate community members for awards,
too! If you know a PyLady doing great work,
[nominate them for an Outstanding PyLady Award](https://pyladies.com/blog/Nominate-a-PyLady-for-the-Outstanding-PyLadies-Award/outstanding-award-nominations/).
Or [let us know](mailto:vancouver@pyladies.com) and we can nominate as a group, which makes
the nomination even stronger.
{{% /callout %}}

## Python news

### What the Python core team is discussing

A peek at the [Python core team's development forum](https://discuss.python.org/c/core-dev/23):

- **[Updated guidelines for using AI tools when contributing to CPython](https://discuss.python.org/t/updated-guidelines-for-using-ai-tools-when-contributing-to-cpython/107462)**:
  timely for this month's theme! CPython refreshed its guidance on AI-assisted
  contributions. The gist: contributors stay responsible for everything they submit, should
  review AI output carefully and explain changes in their own words, and keep contributions
  focused. Thoughtful AI-assisted work is welcome; unreviewed AI output is not.
- **[Community perspectives on the JIT](https://discuss.python.org/t/community-perspectives-on-the-jit-experiences-expectations-and-concerns/107737)**:
  an active thread gathering experiences, expectations, and concerns about Python's
  experimental JIT compiler, following a
  [Steering Council announcement on the JIT project](https://discuss.python.org/t/an-announcement-from-the-steering-council-regarding-the-jit-project/107638).
- **[Reverting the incremental GC in Python 3.14 and 3.15](https://discuss.python.org/t/reverting-the-incremental-gc-in-python-3-14-and-3-15/107014)**:
  the most active recent thread, on rolling back the incremental garbage collector after
  reports of memory pressure.
- **[Repr output of t-strings](https://discuss.python.org/t/repr-output-of-t-strings/107653)**:
  polishing the brand-new t-string literals ([PEP 750](https://peps.python.org/pep-0750/))
  that landed in Python 3.14.

On the release front, **Python 3.14.6** shipped on June 10, and **Python 3.15** has reached
feature freeze, with its release candidate expected in August.

### From the Python Software Foundation

A couple of updates from the PSF worth your attention:

- **[PSF Strategic Plan 2026 draft: open for community feedback](https://pyfound.blogspot.com/2026/06/psf-strategic-plan-2026-draft-open-for.html)**:
  the PSF is asking the community to review its draft strategic plan and weigh in on whether
  the goals and direction feel right. The feedback window closes **June 25, 2026** (end of
  day, anywhere on Earth), so don't wait!
- **[PSF Board election dates for 2026](https://pyfound.blogspot.com/2026/06/psf-board-election-dates-for-2026.html)**:
  four board seats are open. Nominations open July 28, and voting runs September 1-15. If
  you're a Contributing, Supporting, or Fellow member, affirm your voting intention by
  August 25 to take part.

### Python AI libraries to explore

Since this month's talks are all about agents and LLMs, here are some Python libraries
worth a look if you'd like to build your own:

- **[Pydantic AI](https://ai.pydantic.dev/)**: an agent framework "the Pydantic way," with
  type-safe, structured outputs
- **[LangGraph](https://github.com/langchain-ai/langgraph)**: for building stateful,
  multi-step agent workflows
- **[smolagents](https://github.com/huggingface/smolagents)**: Hugging Face's lightweight
  library for agents that write and run code
- **[Temporal](https://temporal.io/)**: durable execution to keep agents alive through
  crashes and long waits (exactly what Melanie's talk is about!)

### Calls for proposals: your talk could be next

Two friendly conferences have **open calls for proposals** right now, and both are great
places to give a first talk:

- **[SeaGL](https://seagl.org/)** (Seattle GNU/Linux Conference): CFP open until **June 30,
  2026** (closing soon!). A free, welcoming conference, October 23-24, 2026 at the University
  of Washington, with online participation. [Submit a talk to SeaGL](https://pretalx.seagl.org/2026/cfp).
- **[PyBay](https://pybay.org/)** (San Francisco): CFP open until **July 12, 2026**. October
  3, 2026 at the UCSF Mission Bay Conference Center. [Submit a talk to PyBay](https://sessionize.com/pybay2026).

{{% callout tone="tip" title="Your talk could be next" %}}
If you've been thinking about speaking, this is your sign! We're happy to help you
brainstorm or review a proposal, so [reach out](mailto:vancouver@pyladies.com).
{{% /callout %}}

### Upcoming regional Python conferences

PyLadies are active as speakers and organizers across the Python conference circuit, so
you'll find familiar faces from our community on stage at events like these. They're
welcoming places to attend, learn, and one day give your own talk. Here are some coming up:

- **[SciPy 2026](https://www.scipy2026.scipy.org/)**: Minneapolis, USA · July 13-19, 2026,
  with talks from Naty Clementi (PyLadies DC) and Inessa Pawson (PyLadies SWFL)
- **[PyOhio 2026](https://www.pyohio.org/2026/)**: Cleveland, USA · July 25-26, 2026, with a
  keynote by Carol Willing (PyLadies San Diego)
- **[PyCon Latam 2026](https://www.pylatam.org/)**: Turrialba, Costa Rica · August 20-23,
  2026, with a keynote by Georgi Ker (PyLadies Bangkok)
- **[DjangoCon US 2026](https://2026.djangocon.us/)**: Chicago, USA · August 24-28, 2026
- **[PyBay 2026](https://pybay.org/)**: San Francisco, USA · October 3, 2026
- **[PyBeach 2026](https://2026.pybeach.org/)**: Santa Monica, USA · October 24, 2026

See you on July 6! 🐍
