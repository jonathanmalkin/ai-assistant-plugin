# AI Assistant plugin for Claude

A personal assistant built as plain files, shipped as a plugin.

Every weekday at 8:00 AM it writes you a Daily Brief: today's meetings, the emails waiting on you, one first move, and an honest check on each of your goals. It preps you for meetings, remembers people and decisions, learns your preferences when you correct it, and drafts follow-up emails. It reads freely and drafts freely. It never sends, posts, deletes, buys, or changes your calendar without your OK on that exact action.

## Start as files, ship as a plugin

The assistant started as a folder, the AI Assistant Kit, that people download and add to a Claude chat. There is no code in it. `CLAUDE.md` is the map and the rules, `Workflows/` holds the steps in plain English, and a few Markdown files hold what the assistant knows about you. That folder is still the product: you can open any file and read exactly what your assistant does.

The plugin is how the folder gets shipped. Install it once, type **set me up**, and it copies the files into a folder you choose, then runs setup. To give a whole team the same assistant, share one marketplace. When you improve a workflow, bump the version, and everyone gets the change with **update my assistant**, without losing their own profile, people, or notes.

## Install

**Claude Code**

```
/plugin install ai-assistant --marketplace jonathanmalkin/ai-assistant-plugin
```

On older versions, run `/plugin marketplace add jonathanmalkin/ai-assistant-plugin`, then `/plugin install ai-assistant@jonathanmalkin`.

**Claude desktop app:** open **Customize**, then **Plugins**, and add the marketplace `jonathanmalkin/ai-assistant-plugin`. Then install **ai-assistant**.

## Use

1. Connect your email and calendar under **Customize**, then **Connectors** (Gmail and Google Calendar, or Outlook / Microsoft 365).
2. Start a new chat or task, add a folder (an empty one such as `Documents/My Assistant` is fine), and set permissions to **Auto**.
3. Type **set me up** and answer two questions: your name and a name for your assistant, then your top two or three goals for the next 90 days.

Setup fills in your profile, finds the people on today's and tomorrow's calendar, schedules the Daily Brief, and shows your first brief in the chat. Then try:

- "Prep me for my meeting with [name]."
- "Here are my notes from my meeting with [name]: ..."
- "From now on, [how you like things]."
- "Go through my inbox."

The Daily Brief runs while the Claude desktop app is open and the computer is awake.

## What's inside

- `plugins/ai-assistant/kit/`: the assistant's files, copied into your folder at setup.
- `plugins/ai-assistant/skills/`: five small skills (setup, daily-brief, meeting-prep, capture, email-triage). Each one points Claude at `CLAUDE.md` and the matching workflow in your folder.

## Make it yours

Fork this repo and edit the Markdown in `plugins/ai-assistant/kit/Workflows/`. Bump `version` in `plugins/ai-assistant/.claude-plugin/plugin.json`, and anyone using your marketplace can update. Personal preferences belong in each person's `About-Me.md`, which updates never touch.

Made by [Jonathan Malkin](https://opendoorlearningai.com), AI Educator in Austin.
