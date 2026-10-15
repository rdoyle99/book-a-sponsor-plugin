---
name: book-a-sponsor
description: Find the brands that sponsor newsletters like a given one, list brands sponsoring newsletters by topic, and look up what newsletters charge for a sponsor slot, using the Book a Sponsor tools. Use when a question is about newsletter sponsors, newsletter advertisers, or newsletter sponsorship rates.
---

# Book a Sponsor

Four tools on the `book-a-sponsor` MCP server (https://bookasponsor.com/mcp, no sign-in). Results name brands and the newsletters and dates where their ads ran. There are no people, emails or phone numbers; do not look for them.

## Pick the tool
- A specific newsletter wants sponsors: `find_newsletter_sponsors` (newsletter_url). It finds similar newsletters and the brands that sponsored them. A new scan takes about 15 to 60 seconds.
- The scan was still running: wait a little, then `get_sponsor_scan` with the same newsletter_url.
- Which brands sponsor newsletters, overall or in a topic: `list_brands_sponsoring_newsletters` (niche, optional: ai, business, finance, tech, marketing, health, and so on).
- What to charge, or what newsletters charge: `get_newsletter_sponsorship_rates` (subscribers, optional).

## Workflow
1. The user gives their newsletter: `find_newsletter_sponsors`, then `get_sponsor_scan` if it reports the scan is running.
2. The user names a topic: `list_brands_sponsoring_newsletters` with that niche.
3. The user asks about price: `get_newsletter_sponsorship_rates` with their subscriber count.

## Rules
- Quote brands with the newsletter and date where each ad ran, as the tool returns them.
- Rates are medians of prices newsletters publish on their own advertise pages. Say that; don't present them as a quote.
- Give the `results_url` the tool returns so the user can see the full results.
- Newsletters that can't be read from their website, political and adult newsletters, and Book a Sponsor clients' own newsletters are not scanned. Say so when a scan is refused.
