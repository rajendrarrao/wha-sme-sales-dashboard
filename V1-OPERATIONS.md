# WHA Virtual Sales Director — V1 operations

## Current status
- Static GitHub Pages dashboard deployed from index.html.
- Auditable seed activity at data/activity.json; not automatically synchronised.
- No live Gmail, Google Calendar, WhatsApp, or prospect database integration in the public page.
- Never store Gmail OAuth credentials, prospect private email addresses, access tokens, or private customer information in this public repository.

## Zero-cost implementation plan
1. Use a private automation repository or private scheduled runner for GitHub Actions, within account free quotas.
2. Connect Gmail and Calendar with least-privilege OAuth and store tokens in private secrets, never the public dashboard repository.
3. Import the existing WHA prospect workbook into a private data store; deduplicate and enforce DND before every outreach.
4. Research public sources using permitted methods; verify company, trigger, named buyer and attributable direct email. Do not fabricate addresses or scrape protected LinkedIn pages.
5. Gmail send: check existing correspondence and suppression; send personalised one-service email; record returned Gmail message ID; apply WHA SME Outreach label; mark as sent only on success.
6. Calendar: check availability and invite only after buyer confirms a slot. Escalate hot prospects.
7. Publish an aggregate, non-sensitive JSON feed to data/activity.json after every successful run; keep personally identifying details private.
8. Send daily Gmail executive summaries with researched, qualified, confirmed sends, replies, meetings, skips and next actions. Set alerts for positive replies.
9. Monitor Gmail quotas and GitHub Actions limits. Stop safely on errors; never mark blocked sends as delivered.

## Acceptance tests
- Duplicate recipient blocked; opt-out suppressed; generic inbox not counted as named buyer.
- Gmail-confirmed send increments count once; blocked attempt increments blocked only.
- Replies and meeting bookings require source evidence.
- Dashboard reports last-sync timestamp and stale-data warning.
- No secrets or private prospect contact data in public GitHub Pages assets.

## Revenue goal
- Target 20 qualified new sends per weekday and 5 confirmed meetings per 15-day period; these are goals, not guaranteed results.
