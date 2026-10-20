---
name: setup
description: Set up the AI assistant in the user's folder, or update its files. Use when the user says "set me up", "get started", "run setup", "install my assistant", "update my goals", or "update my assistant", and when another ai-assistant skill finds no CLAUDE.md in the folder yet.
---

# Setup

This plugin ships the AI Assistant Kit: a folder of plain files. `CLAUDE.md` is the map and the rules, `Workflows/` holds the steps, and `About-Me.md`, `This-Week.md`, `People/`, `Meetings/` and `Briefs/` hold what the assistant knows. The files are the assistant. This skill copies them into the user's folder, then runs the kit's own setup.

## Where things are

- **The kit:** `${CLAUDE_PLUGIN_ROOT}/kit`. If that path did not expand, it is the `kit` folder two levels up from this skill's base directory.
- **The assistant folder:** the folder the user added to this chat, or the current working directory. Wherever the kit's files say "this folder", they mean the assistant folder.

If there is no folder to write to (a plain chat with no folder added), stop and say in plain words: "Add a folder to this chat first (an empty one is fine, for example Documents/My Assistant), then type: set me up."

## Step A - Put the files in the assistant folder

Copying files into the assistant folder counts as drafting under rule 1 of the kit's CLAUDE.md, so it needs no approval. Never copy anything anywhere else.

- **First time** (the assistant folder has no `CLAUDE.md`): copy everything in the kit into the assistant folder, keeping the folder structure. Never overwrite a file that already exists; list any you skipped. With a shell, `cp -Rn "<kit>/." "<assistant folder>/"` does this. Without one, read each kit file and write it. Then say one line: `Copied the assistant's files into [folder name].`
- **Update** (the user asked to update the assistant, and `CLAUDE.md` exists): replace `CLAUDE.md`, everything in `Workflows/`, and `Help/` with the kit's copies. Never touch `About-Me.md`, `This-Week.md`, `People/`, `Meetings/` or `Briefs/`. The user's own rules live in About-Me.md under "How I like things", so nothing personal is lost. Confirm in one line which files were refreshed, and stop there unless the user also asked to run setup.
- **Already set up** (`CLAUDE.md` exists and the user asked to set up or change their goals): copy nothing and go to Step B; the kit's setup handles a refresh.

## Step B - Run the kit's setup

Read `CLAUDE.md` in the assistant folder in full, then follow `Workflows/Setup.md` there, with two changes for the plugin:

- **Step 1, item 2:** the folder can have any name. If the files are missing because the copy failed, say what failed instead of asking for a folder named AI-Assistant-Kit.
- **Step 4, the scheduled task:** use the assistant folder, and set the prompt to exactly `Use the [folder name] folder. Read CLAUDE.md, then follow Workflows/Daily-Brief.md.` with the folder's real name.

Everything else runs as written: two questions in one message, then no more questions, files filled, people found, the Daily Brief scheduled, and the first brief shown in chat. Nothing is ever sent.
