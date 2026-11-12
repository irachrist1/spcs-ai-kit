# Lesson 1: Meet your agent

**What he has at the end.** Claude connected to his email and calendar, a short list of what needs him today, and one reply written by Claude waiting in his Drafts.

**Time.** About 35 minutes. This is the whole first session. It installs nothing.

**New ideas.** Agent, the Code tab, a command, a connector, a draft and a send, a chat and its notes. Each is in ideas.md. One per message, at the step that names it.

## Steps

### 1. Say hello

**Say.** Who you are, in one line. What he'll have by the end of today (you'll have read his inbox and written a reply for him to check). That it takes about half an hour and he can stop any time. Then ask what to call him.

**Wait.** His name.

### 2. Explain what an agent is, and warn him about the box

**Say.** Explain *agent* in two or three lines. Then say you'd like to show him the difference straight away by looking at his computer yourself. Tell him a box will pop up asking him to allow it, and that he should click Allow.

**Wait.** His go-ahead.

### 3. Look at the computer

**Do.** Find out the system, its version and which apps are installed. On a Mac, `sw_vers` and `ls /Applications`. On Windows, `winget list`, or list the Start menu apps. Check for Chrome, Git, GitHub's `gh`, Homebrew (Mac), 1Password, Notion, Granola, Wispr Flow and Obsidian. Keep the full list for the progress file. Don't show it to him.

**Say.** One line about his computer, so he sees you looked. "You're on a MacBook with Chrome already installed, which we'll use later." Then explain *the Code tab*, tied to what just happened. In Chat you'd have had to ask him. Here you looked.

**Wait.** A light check that it makes sense.

### 4. Explain the box he just clicked

**Say.** Explain *a command*. What he allowed a moment ago was one. Tell him "always allow" is fine for looking and reading, and that you'll say so when a box deserves a careful read.

**Do.** While he reads, create `spcs-ai/progress.md` and `spcs-ai/CLAUDE.md` in his home folder. Put this in `CLAUDE.md`, so any new chat opened in that folder knows what to do:

```
I'm learning to use AI agents with the SPCS AI kit, one lesson at a time.
At the start of every chat, read kit/START.md and progress.md in this folder, then carry on from where progress.md says we stopped.
Start with one short line on where we are and what's next.
```

Don't explain the files yet. That comes in step 8.

**Wait.** Nothing. Go to the next step in the same message with one bridging line, since this step asks him nothing.

### 5. Ask about his week

**Say.** Ask what a normal work week looks like for him, and where he loses the most time.

**Wait.** His answer. Then reflect it back in one line that shows you listened, and note it in the progress file. If email is part of it, say that's what you'll fix first. If it isn't, say you'll start with email anyway because it's the fastest way to see an agent work, and come to his answer after.

### 6. Ask which email

**Say.** Ask which email address he uses for SPCS work, and whether it's Gmail or Outlook.

**Wait.** His answer.

### 7. Connect his email

**Say.** Explain *a connector*. Then walk him through it, one click per message if he needs it.

- Click the **+** next to the box where he types to you.
- Choose **Connectors** (it may say **Add connectors**), then find **Gmail**. For Outlook, it's **Microsoft 365**.
- Click **Connect**, pick his SPCS work account when Google asks, and allow it.

**Wait.** His "done". Then ask him to do the same for **Google Calendar** and **Google Drive**. He knows the clicks now, so one message covers both.

### 8. Pick up in a new chat, if you need to

**Do.** Check whether you can now see the mail and calendar tools. If you can, skip to step 9 and explain *a chat and its notes* at the wrap.

If you can't, update the progress file with everything so far and the exact next step ("Lesson 1, step 9").

**Say.** New connectors show up in a new chat. Explain *a chat and its notes*. Then give him the three moves. Start a new chat in the Code tab, choose the `spcs-ai` folder in his home folder, and say "let's continue".

**Wait.** He arrives in the new chat. The new chat reads the progress file and carries on from step 9.

### 9. Check which account you're in

**Do.** Search his mail for something recent and list one upcoming event. Work out which account each connector is signed in to. Connectors are often signed in to a personal or old address without anyone noticing.

**Say.** "I'm in k…@gmail.com and I can see your calendar. Is that the account you use for SPCS?"

**Wait.** His yes. If it's the wrong account, have him disconnect it on the same screen and connect the right one.

### 10. Do the first job

**Do.** Read the last three days of his inbox and today's and tomorrow's calendar. Find the few things that need him. A person waiting on a reply, a decision, a meeting to prepare for.

**Say.** At most five lines, most urgent first, one line each. Who, what they want, by when. Nothing about newsletters or receipts. Then ask which one he'd like you to write a reply to.

**Wait.** His pick.

### 11. Write the reply as a draft

**Say.** Ask what he wants to say, in a sentence. If he's unsure, suggest an answer and let him correct it.

**Do.** Write the reply the way START.md says, in his voice. Read two or three emails he sent before, so it sounds like him. Save it as a **draft** on that thread. Don't send it.

**Say.** Explain *a draft and a send*. Ask him to open Drafts in his email, read it, and tell you if it sounds like him.

**Wait.** His reaction. Fix what he asks. Sending it is his choice, and he presses send himself.

### 12. Wrap up

**Do.** Confirm the draft exists. Update the progress file.

**Say.** Three short lines.

- What he has. Email, calendar and Drive connected, and a reply in Drafts that he didn't type.
- What he learned. An agent does the work, connectors are the doors, and nothing leaves without his yes.
- How to come back. Code tab, the `spcs-ai` folder, "let's continue".

Then offer Lesson 2, which empties his inbox down to what needs him in about 30 minutes. Or a stop.

## If something goes wrong

- **No + button or no Connectors.** Try **Customize** in the sidebar, then **Connectors**. If there's nothing there either, the app may be out of date or he's on a free plan. Have him update the app and check the plan.
- **He uses Outlook.** Connect **Microsoft 365**. Everything else is the same.
- **The connector is in the wrong account.** Disconnect it and connect again, picking the right account on Google's screen.
- **You can't save a draft.** Show him the reply in the chat and have him paste it into a reply himself. Note it in the progress file. Lesson 3 gives you his browser, which fixes it.
- **He has very little email.** Use the calendar. Prepare him for his next meeting with a short note on who's in it, and save that as a draft to himself.
