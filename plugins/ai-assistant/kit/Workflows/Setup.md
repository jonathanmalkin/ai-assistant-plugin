# Setup

Take the user from "I just added the folder" to "my first Daily Brief is in this chat" in one pass. This usually runs in a workshop while the instructor teaches, so the user is only half watching: **ask everything in your first message, then never stop to ask again.** Post one short line per step as you go.

By the end: `About-Me.md` and `This-Week.md` are filled in, the people found in the calendar (or email) have files in `People/`, a scheduled task named **Daily Brief** runs weekdays at 8:00 AM, and today's brief is saved and shown in chat.

**Boundary:** read freely, draft freely, write files in this folder. Never send email, post, delete, buy, or change a calendar event. Email drafts in the user's mailbox are the only thing created outside this folder, and nothing is ever sent.

## Step 1 - Check the folder

1. Confirm you have read `CLAUDE.md` in full. If not, read it now.
2. Confirm you can see `CLAUDE.md`, `About-Me.md`, `This-Week.md`, and `Workflows/` in the folder the user added. If you can't, stop and tell the user in plain words: "I can't see your kit folder. Add the folder named AI-Assistant-Kit (the one that has CLAUDE.md directly inside it), then type: Read CLAUDE.md and set me up." Point them to `Help/Troubleshooting.html` if they can open it.
3. Confirm you can write a file here by saving `Last updated:` with today's date in `This-Week.md`. If writing fails, say so and point to the troubleshooting sheet.
4. If `About-Me.md` already has the user's real name (setup ran before), this is a refresh: show the current name, assistant name, goals, and people in a few lines, ask what has changed in one message, update only what they change, then continue from Step 4.

## Step 2 - One message: two questions

Check these first. Never ask about them; use what you find:

- **Time zone:** America/Chicago (US Central), unless the calendar clearly reports a different one.
- **Email and calendar:** find whichever the user connected, Google or Microsoft (see rule 2 in CLAUDE.md). Note whether the mail tool can create drafts. Use the connected account; never ask for an email address.
- **Daily Brief time:** weekdays at 8:00 AM. The user can change it later.
- **People:** you find them yourself in Step 3. Never ask for them.

Then send **one** message with two numbered questions the user can answer in one reply:

1. **Your name, and a name for your assistant.**
2. **Your top 2 or 3 goals for the next 90 days, and the project that moves each one.**

In the same message, add one line: "While I build, I'll read your calendar and email and write files in this folder. Nothing is ever sent." If the chat is not on **Auto** and permission prompts appear, tell the user to choose "Always allow".

If email or calendar is not connected, say so in the same message: "Your [email/calendar] isn't connected. To connect it, open Customize, then Connectors. I'll carry on without it and note what's missing." Do not wait for it.

Wait for the one reply. Do not ask anything after this point. If an answer is missing, use a sensible default or leave the [bracket] placeholder, and move on.

## Step 3 - Fill the files and find the people

Fill from the user's answers and what you read. Never make anything up; leave a [bracket] placeholder where you have nothing.

- **`About-Me.md`:** their name exactly as they gave it (never the computer's account name), the assistant's name, their goals with the project for each, the time zone, and today's date in `Last updated:`. Fill "My business" and "Where I'm based" only if the calendar or an email signature makes it obvious. Under **Important people**, one line per person you found, linked to their People/ file. Leave "How I like things" and "Decisions" as they are.
- **`This-Week.md`:** today's date, and any priorities, waiting-on items, or follow-ups the goals, calendar, and email imply.
- **People, from the calendar:** read today's and tomorrow's events only. Keep meetings with at least one attendee from outside the user's own organization. Skip personal holds, all-company events, and events with no other attendees. Take up to **5** people.
- **If the calendar gives nobody:** use people waiting on a reply from the user in the last 14 days of email, up to **3**. Skip newsletters and notifications.
- **For each person:** a short `People/First Last.md` from `Workflows/Templates/Person.md`, with only what the calendar and recent email show. No web research yet. If the person's company matters, also create `People/[Company] (company).md` from `Workflows/Templates/Company.md`.
- **If both are empty:** create no People files, and in the recap say: "Tell me about one person anytime."

One line to the user: `Saved your profile, this week, and [N] people.`

## Step 4 - Schedule the Daily Brief

Create a scheduled task:

- **Name:** Daily Brief
- **When:** weekdays (Monday to Friday) at 8:00 AM, in the user's time zone (cron `0 8 * * 1-5`)
- **Folder:** this kit folder (AI-Assistant-Kit)
- **Prompt, exactly:** `Use the AI-Assistant-Kit folder. Read CLAUDE.md, then follow Workflows/Daily-Brief.md.`

If the app shows a confirmation, tell the user to click **Create**. Then tell them in one or two plain lines: the Daily Brief needs this folder to stay where it is, and the Claude desktop app must be open (and the computer awake) at 8:00 AM for it to run. If it misses a morning, they can ask "run my daily brief" anytime.

If scheduling is not available here, say so and give the steps: open **Scheduled** in the Claude sidebar, add a new task named Daily Brief, weekdays at 8:00 AM, choose this folder, and paste the prompt above. Then continue.

## Step 5 - Build today's brief now

Follow `Workflows/Daily-Brief.md` now, in this chat, in **light mode**, so every permission prompt happens while the user is in the room and the first brief is ready quickly. Light mode: list today's and tomorrow's meetings without web research or prep pages (the meeting prep card says "Ask me to prep this one"), and draft at most two clear email replies. Full prep happens when the user asks and in the 8:00 AM scheduled brief. One line per step. Skip its chat reply; Step 6 shows the brief.

## Step 6 - Recap, with the brief in chat

Show the result in chat (rule 4 in CLAUDE.md), in this order:

1. **Today's brief, in full,** in plain short lines, the same sections as the page.
2. **The people you found,** by name with one line each (or "Tell me about one person anytime." if none), so the user has a name ready for meeting prep.
3. A few lines, no more:
   - The assistant's name, and that the profile, this week, and people are saved.
   - Email and calendar status.
   - The Daily Brief runs weekdays at 8:00 AM while the app is open.
   - How many email drafts are waiting, if any, and that nothing was sent.
   - What to try next, as things they can type:
     - "Prep me for my meeting with [a person you found]."
     - "Here are my notes from my meeting with [name]:"
     - "From now on, [how you like things]."
   - The boundary in one line: I read and draft; you approve and send.
4. Offer to open the brief page.
