# Lesson 3: Claude in your browser

**What he has at the end.** Claude working in his own Chrome while he watches, and his junk senders blocked for good by filters Claude set up.

**Time.** About 25 minutes.

**New idea.** Claude in Chrome.

**Needs.** Lesson 2, for the list of junk senders.

## Steps

### 1. Say why

**Say.** Explain *Claude in Chrome* in three lines. Connect it to yesterday. The junk senders are archived, and they'll be back tomorrow. Stopping them needs a settings page in his email, and that's a browser job.

**Wait.** His go-ahead.

### 2. Get Chrome, if it's missing

Skip this step if the progress file says Chrome is installed. Edge works too, so use it if he has Edge and no Chrome.

**Say.** One line. You'll install Google Chrome, and what he'll see.

**Do.** On Windows, `winget install --id Google.Chrome`. On a Mac, use Homebrew if it's there (`brew install --cask google-chrome`). If it isn't, open https://www.google.com/chrome/ in his browser and guide him through the download, one click at a time.

**Wait.** Chrome is open.

### 3. Add the extension

**Do.** Try to use the browser. If a box appears titled "Claude wants to use your browser", tell him to click **Install extension** and follow it. If no box appears, open the [Claude extension page](https://chromewebstore.google.com/detail/claude/fcoeoabgfenejglbffodgkkbkcdhcgfn) in Chrome.

**Say.** One instruction at a time. Click **Add to Chrome**. Click **Add extension**. Sign in with the same Claude account he uses in the app.

**Wait.** His "done".

### 4. Show him it works

**Do.** Open https://spcstech.com in a new tab through the extension and read the page.

**Say.** Tell him to look at Chrome. One line on what you see on the page, so he knows you're reading it. Mention that the first time you touch a site, a box asks him to allow that site.

**Wait.** His reaction. This is a good moment for a light check.

### 5. His yes, the filter plan

**Do.** Take the junk senders from the progress file.

**Say.** Show the list, shortest form. For each, the plan is a filter that skips the inbox. Where a sender has a working unsubscribe link, you'll unsubscribe too. Ask if any sender should stay.

**Wait.** His yes.

### 6. Do the first one slowly

**Do.** In Gmail, open Settings, then Filters and Blocked Addresses, and create the first filter (from that sender, skip the inbox). In Outlook, create a rule that moves the sender's mail out of the inbox.

**Say.** Narrate it in two lines while he watches. If Gmail asks him to sign in or confirm, that part is his.

**Wait.** He's seen it. Ask if you should do the rest the same way.

### 7. Do the rest

**Do.** Create the remaining filters. Then open the filter list and count them.

**Say.** One line with the result. "Eleven senders will never reach your inbox again."

### 8. Wrap up

**Do.** Add the filter rule to the `clean-inbox` skill (new junk senders go on a list for him to approve as filters). Update the progress file.

**Say.** Three short lines.

- What he has. Claude in his browser, and the filters.
- What he learned. Connectors are the fast doors, and the browser reaches everything else. Passwords and "prove you're human" puzzles stay with him.
- What to try. Ask you to do one small browser chore he's been putting off, like downloading a statement or filling in a form.

Then offer Lesson 4, or a stop.

## If something goes wrong

- **The extension isn't detected.** Have him quit Chrome completely and open it again, then try once more. Check the extension is signed in to the same Claude account as the app.
- **The connection drops mid-job.** Open a new tab and try again. If that fails, have him turn the extension off and on at `chrome://extensions`.
- **A page shows a login or a puzzle.** Stop and hand it to him. Never ask for a password in the chat.
- **Archiving failed in Lesson 2.** Do it now, in Gmail, with the list you kept.
