# Lesson 7: Work that runs itself

**What he has at the end.** His inbox cleaned and a short brief written every weekday morning, before he sits down.

**Time.** About 25 minutes.

**New idea.** A routine.

**Needs.** Lesson 2, and a few days of saying "clean my inbox" himself. If he hasn't used the skill yet, suggest he does that for a few days first, so the routine copies a habit that already works.

## Steps

### 1. Say why

**Say.** Explain *a routine* in three lines. Tie it to him. He's been asking for a clean inbox each morning. From tomorrow it's done before he asks.

**Wait.** His go-ahead.

### 2. Agree what the morning looks like

**Say.** Ask what time he starts work. Then propose the brief in one line. What needs him in his inbox, what's on his calendar today, and anything due this week.

**Wait.** The time, and anything he wants added or dropped. Keep the brief to what he'll read in one minute.

### 3. Set it up

**Do.** Create a scheduled task that runs every weekday, about 30 minutes before he starts, in the `spcs-ai` folder. The simplest way is to create it yourself from this chat. Its instructions are short.

```
Run the clean-inbox skill.
Then write today's brief, in ten lines or fewer. What needs me in my inbox, most urgent first.
What's on my calendar today, and what I should prepare. Anything due this week.
Save it as briefs/YYYY-MM-DD.md in this folder. Never send anything. Drafts only.
```

**Say.** Where to find it. In the Code tab's sidebar, under **Scheduled**. Some versions of the app call it **Routines**. One line on the limit. It runs on this computer, so the Claude app must be open and the laptop awake. If the laptop was asleep, it runs once when he opens it.

**Wait.** He's found it in the sidebar.

### 4. His yes, run it once now

**Say.** You'll run it now so he can see what tomorrow looks like. Boxes will pop up for the things it does. For reading mail, archiving and saving drafts, he chooses "always allow", so tomorrow's run doesn't wait for him. Nothing in it sends.

**Wait.** His go-ahead.

**Do.** Run it. Watch for anything that stalls. Read the brief it wrote and check it against the inbox.

**Say.** Show him the brief. Ask what he'd change.

**Wait.** His edits. Update the task's instructions.

### 5. Offer one more, and only one

**Say.** If Lesson 6 is done, suggest a second routine. Every Monday morning, hunt for new opportunities and have the best three waiting. Ask if he wants it. Don't offer a third. Too many routines and he stops reading them.

**Wait.** His answer. Set it up the same way if yes.

### 6. Wrap up

**Do.** Update the progress file with each routine, when it runs and where its output goes.

**Say.** Three short lines.

- What he has. A morning that starts with a clean inbox and a brief.
- What he learned. A routine is a skill on a timer. It can draft and tidy, and it never sends.
- What to do tomorrow. Open the Claude app with his coffee and read the brief.

Then offer Lesson 8, or a stop. Suggest he lives with the routine for a week or two first.

## If something goes wrong

- **You can't create the task from the chat.** Guide him through it. Code tab, **Scheduled** in the sidebar, **New task**, name it, paste the instructions, choose the `spcs-ai` folder and **Weekdays**.
- **A run is stuck.** It's waiting on a box nobody clicked. Open the run under **Scheduled**, answer the box with "always allow", and it finishes.
- **He wants it to run with the laptop closed.** That's a cloud task. It can't read files on his computer, so it suits jobs that only need his connectors. Set it up at https://claude.ai/code/routines with him, and have it leave the brief as a draft email to himself.
- **The brief is too long.** Cut it. Three things that need him beat ten things that might.
