# Lesson 4: GitHub and your tools

**What he has at the end.** His own GitHub account, his `spcs-ai` folder backed up in a private repo, and two or three apps that fit his week.

**Time.** About 40 minutes. The apps at the end are optional and can wait for another day.

**New idea.** GitHub and a repo.

**Needs.** Lesson 3, because you create the account with him in his browser.

## Steps

### 1. Say why

**Say.** Explain *GitHub and a repo* in three lines. Tie it to him. His notes, his inbox skill and soon his proposals live in one folder on one laptop. Today that folder gets a backup with a memory.

**Wait.** His go-ahead. If he already has a GitHub account, skip to step 4.

### 2. Start the sign-up

**Do.** Open https://github.com/signup in his Chrome. Fill in his email. Suggest a username built from his name and check it's free.

**Say.** Offer the username and one alternative. Ask which he prefers.

**Wait.** His pick.

### 3. He finishes the sign-up

**Say.** The next three things are his. He types a password straight into the page (never into the chat), solves the puzzle, and enters the code GitHub emails him. Tell him to say "done" when he's on the GitHub home page. If he asks, suggest saving the password in his browser or in 1Password.

**Wait.** His "done".

### 4. Install the tools

**Say.** One line. You need two small tools so this computer can talk to GitHub, and what he'll see pop up.

**Do.** Install Git and GitHub's command line tool `gh`, unless the progress file says they're there.

- **Windows.** `winget install --id Git.Git` and `winget install --id GitHub.cli`.
- **Mac.** For Git, run `xcode-select --install`. A box asks him to install developer tools. He clicks Install, and it takes about ten minutes. For `gh`, use Homebrew if it's installed. Otherwise download the macOS installer from https://github.com/cli/cli/releases/latest and open it, and he types his Mac password into the installer.

**Wait.** The installs finish. While they run is a good time for step 7's question about his week.

### 5. Sign this computer in

**Do.** Run `gh auth login --web --git-protocol https`. Set his name and email with `git config --global user.name` and `git config --global user.email`.

**Say.** Show him the one-time code. A page opens in his browser. He pastes the code and clicks Authorize.

**Wait.** The sign-in completes. Check it with `gh auth status`.

### 6. His yes, back up the folder

**Say.** You'd like to put his `spcs-ai` folder in a private repo. Private means only he can see it. No keys or passwords are in it. Ask for his yes.

**Wait.** His yes.

**Do.** In `spcs-ai`, add a `.gitignore` with `kit/` in it. Check the folder holds no keys. Then run `git init`, commit everything, and `gh repo create spcs-ai --private --source . --push`. Open the repo page in his Chrome.

**Say.** Tell him to look at the page. That's his folder, saved, with today's date on it. From now on you save to it at the end of every lesson.

**Wait.** His reaction. Offer a stop here if he's been going a while.

### 7. Ask what would help most

**Say.** Remind him in one line what he told you about his week. Ask one question to fill the gap. For example, how many meetings he has in a normal week, or where his to-do list lives.

**Wait.** His answer.

### 8. Suggest two or three apps

**Do.** Match what he said against the table in START.md. Check each app's site for what it does today and what it costs.

**Say.** Two or three suggestions, one line each, with the reason drawn from his own words. "You said you leave meetings and forget who promised what. Granola writes the notes for you." Say which one you'd start with. Ask which he wants.

**Wait.** His pick. None is a fine answer.

### 9. Install what he picked

**Do.** Install each one the simplest way for his computer, as START.md describes. He creates any account himself, in the browser.

**Say.** For each app, one thing to try today. Keep it to a line.

### 10. Wrap up

**Do.** Commit and push the progress file. Update it first.

**Say.** Three short lines.

- What he has. A GitHub account, a private backup, and the apps he chose.
- What he learned. A repo is a folder with a memory, and GitHub keeps it safe.
- What to try. Open github.com, find his `spcs-ai` repo and click on `progress.md` to see your notes.

Then offer Lesson 5, or a stop.

## If something goes wrong

- **The username is taken.** Offer two more. Don't add random numbers.
- **GitHub's puzzle or email code fails.** That part is his. Wait, and suggest the "resend code" link.
- **The developer tools install on a Mac hangs.** Have him open Software Update, where it also appears.
- **`gh` can't be installed.** Git alone is enough. Create the private repo in the browser with him, then push with `git`, which opens a sign-in window.
- **He doesn't want any new apps.** Good. Move on.
