# Lesson 5: Email from our domain

**What he has at the end.** An email delivered from an @spcstech.com address, sent by Claude after his yes.

**Time.** About 30 minutes, plus a wait if Tonny hasn't shared the key yet.

**New idea.** A key.

**Needs.** Lesson 1. Lesson 3 helps for the optional Gmail step.

## Background (for the agent)

Clients take email from @spcstech.com more seriously than from a Gmail address. SPCS gets this free, without Google Workspace, from three services with one job each.

| Job | Service | What it does |
| --- | --- | --- |
| Receive | Cloudflare Email Routing | Forwards mail sent to an @spcstech.com address to a normal inbox |
| Send | Resend | Sends mail from @spcstech.com. Free up to 100 a day and 3,000 a month |
| Write | Gmail "Send mail as" | Lets him write from @spcstech.com inside his normal Gmail |

Tonny holds the domain's settings. Two things come from him, both through 1Password. The SPCS sending key, and an address of his own if he wants one (like hisname@spcstech.com), with its mail forwarded to his inbox.

Don't walk him through this table. He needs one sentence of it, at step 1.

## Steps

### 1. Say why

**Say.** Two lines. Proposals and outreach land better from @spcstech.com than from Gmail, and after today you can send from it for him. It needs one thing from Tonny, a key.

**Wait.** His go-ahead.

### 2. Explain the key, and get 1Password

**Say.** Explain *a key*. It reaches him through 1Password, so you'll set that up first. Ask if he already uses 1Password.

**Wait.** His answer.

**Do.** If 1Password isn't installed, install the app the simplest way for his computer. He creates or signs in to his account himself. Then install its command line tool `op` (`brew install 1password-cli` on a Mac with Homebrew, `winget install --id AgileBits.1Password.CLI` on Windows, or the installer from https://developer.1password.com/docs/cli/get-started/). Guide him to turn on **Settings, Developer, Integrate with 1Password CLI** in the 1Password app, one click at a time.

### 3. Find the key

**Say.** Ask him to look in 1Password for an item shared by Tonny for sending SPCS email, and to tell you its exact name and the vault it's in. He must not paste the key itself.

**Wait.** The name and vault.

**Do.** Test that you can read it without showing it.

```bash
op read "op://<vault>/<item>/credential" >/dev/null && echo "key found"
```

**If the key isn't there yet.** Write the message for him to send Tonny, and offer to save it as a draft. "Can you share the Resend sending key for spcstech.com with me in 1Password? I'd also like my own @spcstech.com address, forwarded to my inbox." Note it in the progress file, stop the lesson here, and offer Lesson 6 meanwhile.

### 4. His yes, the first email

**Say.** The first email goes to his own inbox, so you can both see it arrive. Show it in full. From `SPCS <info@spcstech.com>`, to his address, a short subject and two lines of body. Ask for his yes.

**Wait.** His yes.

### 5. Send it and watch it land

**Do.** Send it. The key is read straight from 1Password and never shown.

```bash
RESEND_API_KEY="$(op read 'op://<vault>/<item>/credential')" \
curl -s -X POST https://api.resend.com/emails \
  -H "Authorization: Bearer $RESEND_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"from":"SPCS <info@spcstech.com>","to":["HIS_ADDRESS"],"reply_to":"info@spcstech.com","subject":"...","text":"..."}'
```

A reply with an `id` means Resend accepted it. Search his inbox through the connector and confirm it arrived. If it landed in spam, have him mark it "not spam".

**Say.** Tell him to check his inbox. Then two lines on what happened. You asked the sending service to send as SPCS, it checked the key, and the domain's settings prove to Gmail that the mail is from spcstech.com.

**Wait.** He's seen it.

### 6. His yes, one that counts

**Say.** Ask if there's an email he's been meaning to send under the SPCS name, like a follow-up to a client or a partner.

**Wait.** His answer. If there's none today, skip to the wrap.

**Do.** Draft it with him. Show the sender, the recipient, the subject and the full body. Send only after his yes for that exact message. Check the `id` came back.

### 7. Wrap up

**Do.** Update the progress file. Push it if Lesson 4 is done.

**Say.** Three short lines.

- What he has. Email from @spcstech.com, sent by his agent.
- What he learned. A key is a password for a program, and it lives in 1Password, never in a chat.
- What to remember. 100 emails a day, and every one needs his yes.

Mention in one line that you can also set up Gmail so he writes from @spcstech.com himself, whenever he wants it. Then offer Lesson 6, or a stop.

## Optional, later. Writing from Gmail as SPCS

Do this when he asks for it. It's easiest with Claude in Chrome.

1. In Gmail, open **Settings, See all settings, Accounts and Import, Send mail as, Add another email address.**
2. Name "SPCS" or his own name. Address `info@spcstech.com` or his own SPCS address.
3. SMTP server `smtp.resend.com`, port 465, SSL, username `resend`. The password is the sending key. He copies it from 1Password into the box himself.
4. Gmail sends a confirmation code to that address. For `info@`, the code goes to Tonny, so write him the message asking for it.

Then he sends one email from Gmail as SPCS to himself, and you check it arrives.

## If something goes wrong

- **"Domain not verified" or 403 from Resend.** The key is for a different domain, or it was revoked. Write him the message asking Tonny for a fresh one.
- **The email lands in spam.** Normal for the first few. Mark it "not spam", and keep emails plain, with no attachments, for the first week.
- **No reply comes in.** Replies to `info@` go to the inbox it forwards to. For his own address, Tonny sets the forwarding in Cloudflare.
- **He won't use 1Password.** Open a new empty text file at `~/.config/spcs/resend-key` in his text editor. He pastes the key there and saves. Lock it with `chmod 600` on a Mac. Never read the key back into the chat.
