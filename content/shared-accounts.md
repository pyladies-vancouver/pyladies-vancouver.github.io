+++
title = "Shared Accounts in 1Password"
type = "docs"
weight = 66
eyebrow = "Runbooks"
lead = "A list of what the organizing team keeps in 1Password, so you know where to look before asking someone for a login. This page names the items only: the passwords and codes themselves stay in 1Password."
+++

## What's in the vault

| Item | What it holds |
| --- | --- |
| **PyLadies Vancouver Bluesky** | Login information for our [Bluesky account](https://bsky.app/profile/pyladiesvancouver.bsky.social) |
| **PyLadies Vancouver Mastodon** | Login information for our [Mastodon account](https://fosstodon.org/@pyladies_vancouver) |
| **PyLadies Vancouver Instagram** | Login information for our [Instagram account](https://www.instagram.com/pyladiesyvr), plus its two-factor authentication code |

{{% callout tone="warn" title="Never put a password on this page" %}}
This site is public. List the name of an item and what it is for, never the login itself.
{{% /callout %}}

## Signing in to Instagram

Instagram asks for a two-factor authentication (2FA) code when you sign in. The code
comes from 1Password, not from a text message.

{{% checklist key="sa-instagram-2fa" %}}
Sign in with the username and password from the Instagram item in 1Password.
If Instagram says it sent the code by SMS, change the method and choose the code from an authentication app.
Enter the number shown on the Instagram item in 1Password.
{{% /checklist %}}

The number in 1Password changes every 30 seconds, so enter the one showing right now.

## Keeping this list current

When you add an item to 1Password, or remove one, update the table above to match.
See [Contributing to the Website](/contributing/) for how to make the change.
