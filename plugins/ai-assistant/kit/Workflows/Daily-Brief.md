# Daily Brief

Write a brief the user can read on their phone over coffee: what's on today, what those meetings need, which emails are still open, one first move, and an honest check on each goal. Use this for the scheduled Daily Brief, for "run my daily brief", and for "what am I forgetting?"

**When this runs as the scheduled task, ask nothing.** Make the best brief you can from what's available and note any gaps in the status line.

## Step 1 - Check what you can read

Check email and calendar as described in rule 2 of CLAUDE.md, and confirm `About-Me.md` and `This-Week.md` exist. In one short line, say what is available. If email or calendar is missing, still write the brief and say at the top which sections will be thinner.

## Step 2 - Gather

- **Read `This-Week.md` first.** It is the current truth for priorities, waiting-on items, reminders, and follow-ups. The brief should match it, not contradict it.
- Read `About-Me.md`: the goals (the Goal progress section is built from these), important people, and "How I like things".
- Calendar: today's events, in the user's time zone (America/Chicago unless the calendar says otherwise).
- Email: threads from the last 24 hours, read and unread, where the user is the next to reply or someone is waiting on them. Skip newsletters and notifications.
- If This-Week.md and the calendar disagree, don't silently pick one; note the mismatch in the brief.

## Step 3 - Prep meetings and draft clear replies

In light mode (the first brief during setup), skip this prep: list the meetings and mark each "Ask me to prep this one". Otherwise, for meetings today and tomorrow with people the user may not have context on, follow `Workflows/Meeting-Prep.md`. Only prep meetings that matter; skip routine ones and anything already prepped in `Meetings/`.

For each email where the user is next to reply and the reply is clear, create an email draft following Steps 5 and 6 of `Workflows/Email-Triage.md` (drafts only, never sent), and mark it "draft ready" in the brief. If a reply needs a decision only the user can make, say what's needed instead of drafting.

## Step 4 - Update This-Week.md

Before writing the brief, update `This-Week.md`:

- Keep everything the user wrote unless it is clearly done or out of date. Mark done items done with a one-line outcome.
- Replace [bracket] placeholders with real items when you have them.
- Priorities: one to three real outcomes for today. Don't dump the calendar here.
- Waiting on: add emails or commitments where someone is waiting on the user, or the user is waiting on someone. Who, what, since when.
- Reminders and Follow-ups: add dated items found in email, calendar, or notes.
- Set `Last updated:` to today's date.

## Step 5 - Write the brief

Copy `Workflows/Templates/Daily-Brief.html` and fill the copy. Never edit the template itself. The comment at the top of the template says how: replace every [bracket] marker, repeat each marked example row once per real item, set each count badge, and use a section's friendly empty line (or drop the card) when it has nothing. Before saving, delete the template's HTML comments and search the page for `[`; no placeholder text may remain.

Each section comes from one place:

- **First move:** one concrete action, under 15 minutes if possible. Add the heads-up line for a heavy day or a This-Week.md and calendar mismatch.
- **Today's schedule:** today's calendar events, with the next (or current) event tagged and any join link.
- **Goal progress:** one card per goal in About-Me.md, tagged Moving, Stalled, or Untouched, with one honest line.
- **Meeting prep:** meetings today and tomorrow from Step 3, linking to their pages in `Meetings/` and any file in `People/`.
- **To-do list:** today's priorities and things the user owes someone, from This-Week.md. Items set aside go in "Parked for now".
- **Email drafts for approval:** only the drafts created in this run, plus any reply that needs the user's decision. The "Open Gmail Drafts" link stays as is; with Outlook, change it to the Outlook drafts folder.
- **Waiting on others:** the This-Week.md waiting-on items where someone else owes the user.
- **Footer:** the build time and what was read, such as "Built 8:03 AM from your calendar and email." Say plainly if email or calendar could not be read.

**Goal progress is the point of the brief.** For each goal in About-Me.md, say honestly whether today's calendar or recent email moves it. If nothing has touched a goal in days, say so plainly. Tie the First move to a goal when you can.

Keep each line short. If the day is heavy, say so instead of faking calm. Plain language: "Sarah is waiting on the contract draft from Monday", not "Outstanding action item re: contract."

## Step 6 - Save the page and summarize in chat

Save the filled page twice:

- `Briefs/Daily-Brief.html`, replacing the previous one, so the latest brief is always in one place.
- `Briefs/YYYY-MM-DD Daily Brief.html`, a dated copy, using the user's local date.

Then reply in chat (rule 4 in CLAUDE.md):

- **When the user asked in a chat** ("show me my brief", "run my daily brief"): show the full brief in chat, every section in the same order as the page, in plain short lines. End with "Nothing was sent." and offer to open the page.
- **When this runs as the scheduled task:** a short chat note so the user can stay in Claude: the first move, today's meetings in one line, how each goal stands in a few words, drafts created, any gaps, and "Nothing was sent." Keep it to about five lines.

## Boundary

Read email, calendar, and files. Update This-Week.md and save the brief. Never send email, post, change a calendar event, or contact anyone. If the brief shows something the user needs to do (reply to Sarah, accept a meeting), flag it and stop.
