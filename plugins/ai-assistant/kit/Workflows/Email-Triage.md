# Email Triage

Sort recent email into what needs a reply and what doesn't, and draft replies for the user to review and send. Use this for "go through my inbox", "what needs a reply?", or "draft replies". **You never send.** The Daily Brief also uses Steps 5 and 6 to draft its replies.

## Step 1 - Check what you can read

Check email (and calendar, for scheduling threads) as described in rule 2 of CLAUDE.md. Note whether the mail tool can create drafts, but never create a test draft. If email can't be read at all, tell the user how to connect it (Customize, then Connectors) and stop.

## Step 2 - Read the user's style

Read `About-Me.md`: "My email style" and "Working with me" under How I like things, and Important people. If "My email style" has real rules, follow them. If it is still empty, use the plain defaults in Step 5 and say so at the top of the review: "Drafts use plain defaults. Tell me what sounds off and I'll learn your style." Never scan the sent folder to guess.

## Step 3 - Pull recent threads

Default: threads with activity in the last 48 hours, read and unread (read mail can still need a reply), plus any older thread where the user is clearly next to reply. Honor any scope the user gives ("last 24 hours", "everything from this client"). Skip newsletters, marketing, automated notifications unless urgent, and threads where the user already replied and is waiting.

## Step 4 - Sort each thread

- **Reply needed:** the user is next to reply. Draft one (Step 5).
- **For your information:** worth knowing, no action. One line.
- **Done or no action:** resolved, or the user was only copied.
- **Ignored:** a newsletter or notification that slipped through. Count it and move on.

If everything looks like "Reply needed", the sorting is wrong; look again.

## Step 5 - Draft replies

For each "Reply needed" thread, write a draft that follows the user's email style from About-Me.md: their greeting, sign-off, usual length, punctuation habits, and never a phrase they said they don't use. Match warmth to the relationship; check the sender's file in `People/` if there is one.

With no style saved yet, use these defaults: direct and short, usually one to four sentences; no "Hope this finds you well", "Just circling back", or "I wanted to reach out"; no emojis or exclamation points unless the sender used them; echo the sender's greeting style; a plain sign-off like "Thanks,".

If a reply needs something only the user knows (a decision, a price, an attachment), say what's needed instead of drafting. Don't invent it, and don't save a placeholder draft.

## Step 6 - Save drafts and check them

For each complete draft:

- Create it as a draft reply in the original thread when the mail tool supports that. Keep the subject and the original recipients; add nobody new unless the user asked.
- Do **not** send, mark read, archive, label, or delete anything. Creating the draft is the only change allowed in the mailbox.
- Claim a draft was saved only when the mail tool confirms it. If saving fails, still show the draft in chat and mark it "Not saved", with the reason.
- If the mail tool can't create drafts (some Outlook setups), show the draft in chat and save it as `Briefs/YYYY-MM-DD Draft - [Name].txt`.

For Gmail, the Drafts folder is at https://mail.google.com/mail/u/0/#drafts (if more than one Google account is signed in, switch to the one connected to Claude). For Outlook, point to the Drafts folder in Outlook.

## Step 7 - Write the review

Fill `Workflows/Templates/Inbox-Review.md`. Show the full text of every draft in chat too, so the user can review without opening their mail. Near the top: "Email drafts created: [created]/[threads that need a reply]" and which style was used. End with "Nothing was sent."

Save the review as `Briefs/YYYY-MM-DD Inbox Review.html`, following `Workflows/Templates/Page-Style.md`. Reply in chat with the review itself (rule 4 in CLAUDE.md): the sorted threads in short lines and the full text of every draft, then the Drafts link, "Nothing was sent.", and an offer to open the saved page.

## When a draft doesn't sound like the user

Ask one or two short questions about what was off and save the answer under "My email style" in About-Me.md, as described in `Workflows/Capture.md`. The style gets better with each correction.
