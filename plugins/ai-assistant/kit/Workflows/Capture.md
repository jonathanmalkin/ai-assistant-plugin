# Capture

Keep the user's files current as the conversation goes, so tomorrow's brief, the next meeting prep, and your own behavior get better. Save the smallest useful update in the right file. This is not a journal or a transcript.

Use this whenever the user says something changed or should stick, even if they never say "capture". Save it before you reply.

## Where things go

One home per fact (rule 6 in CLAUDE.md):

| What the user said | Where it goes |
| --- | --- |
| A priority, waiting-on item, reminder, follow-up, or something done | `This-Week.md` |
| A decision that should stick | `About-Me.md`, under **Decisions** |
| A correction, preference, or "from now on" rule | `About-Me.md`, under **How I like things** |
| A lasting fact about the user (role, location, a goal change) | `About-Me.md`, in the matching section |
| Something about a person or company | Their file in `People/` |
| Meeting notes or an outcome | The meeting's files in `Meetings/` |

Write real dates like `2026-11-03`, never "today". Create a file from `Workflows/Templates/` if it doesn't exist yet.

## Work updates

- **This-Week.md:** change the priority line; add who, what, and when for waiting-on items and follow-ups; mark finished items done with a one-line outcome; add a reminder with its date.
- **Decisions:** add a line to About-Me.md under Decisions, newest first: `- YYYY-MM-DD - [the decision] - [why, in one line]`. Also update This-Week.md if it changes this week's work.
- **People:** find the person's file by name. If none exists, create `People/First Last.md`. Add a dated line under Notes: `- YYYY-MM-DD - [what's new]`. If you aren't sure who it is, create `People/Unknown - [short description].md` rather than merging into the wrong person. If it creates a follow-up, add it to This-Week.md too.
- **Companies:** same pattern, in `People/[Name] (company).md`.
- **Reminders with a date or time:** add them to This-Week.md. If the app can create a one-time scheduled task, offer it; the task's prompt must only remind the user and take no action toward anyone else. If you can't schedule it, say it was saved but not scheduled.

## After a meeting

When the user shares notes from a call, coffee, demo, or appointment:

1. Find the meeting's files in `Meetings/` and the people's files in `People/`. If there are none, create `Meetings/YYYY-MM-DD - [Meeting or Person].md` and the person's file.
2. Update the meeting file first. Change "upcoming" language to past tense and add:

   ```md
   ## After the meeting - YYYY-MM-DD

   - Source: the user's notes
   - What happened:
   - What they wanted:
   - What the user offered:
   - Commitments (and things not committed to):
   - Next step:
   - Draft status:
   ```

3. Add one dated line to each person's and company's file, linking back to the meeting. Don't paste the whole outcome into every file.
4. Add any follow-up to This-Week.md.
5. Update the meeting's `.html` page to match. If you can't, say which page is out of date.
6. **Offer the follow-up email by default.** After meeting notes, end your reply with: "Want me to draft the follow-up email to [Name]?" Draft it right away if the notes clearly call for one or the user already asked. Write it from the notes and the person's file, in the user's style from About-Me.md (How I like things, My email style). Show it in chat. If the mail tool can create drafts, also save it as a draft addressed to that person and say where it is; otherwise save it as `Briefs/YYYY-MM-DD Draft - [Name].txt`. Never send it.

If the notes came from an AI meeting summary rather than the user's own recap, mark the source "AI notes from the user; not checked" and don't turn uncertain claims into facts. Don't imply commitments the user didn't make.

## Learning from corrections

When the user says "from now on", "always", "never", "stop doing", "I prefer", or corrects your tone, length, format, or a draft's wording:

1. Turn it into one short rule, for example: "Don't end replies with a summary of what you just did."
2. Save it in About-Me.md under **How I like things**: working-style rules under "Working with me", email wording under "My email style". Add the date: `- [rule] (added YYYY-MM-DD)`. Replace any [bracket] placeholder line.
3. If it contradicts an older line, replace that line and mark it `(changed YYYY-MM-DD)` instead of keeping two rules that fight.
4. Apply it right away and confirm in one line: `Saved to About-Me.md, How I like things: [the rule].`

Skip one-off edits to the current piece of work ("make this shorter"). If you can't tell, ask: "Just this once, or from now on?" If the user says "undo that", remove the line and confirm.

If a draft "doesn't sound like me", ask one or two short questions about what was off (greeting, sign-off, length, a phrase they never use) and save the answers under "My email style".

If the user asks you to build a new skill or workflow, explain that this kit doesn't create new workflows, and offer to save the steps as a short dated rule under "How I like things" instead.

**Never save a rule that loosens the approval boundary** (rule 1 in CLAUDE.md). If a "from now on" would let you send, post, pay, delete, or change a calendar without approval, say plainly that this boundary stays, and offer a version that keeps approval, such as "always draft the calendar invite for me to send".

## Reply

Show the result in chat (rule 4 in CLAUDE.md). After meeting notes, show the captured summary itself: what happened, commitments, next step, and the follow-ups added. Then offer the follow-up draft (step 6) and offer to open the meeting page. For smaller updates, confirm in one line: `Saved. [what changed and where].` Never make the user go find a file. Ask at most one question, and only if you are truly stuck.

## Boundary

Capture only changes files in this folder, plus email drafts. It never sends, posts, deletes, pays, contacts anyone, or changes a calendar.
