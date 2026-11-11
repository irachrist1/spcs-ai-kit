# Lesson 2: Email from our domain

**What you'll have at the end:** a real email delivered from an @spcstech.com address, sent by your agent after your yes, and the know-how to write from that address in Gmail too.

**Time:** about 30 minutes, plus waiting on one thing from your co-founder if it isn't ready yet.

## Why this lesson

Clients take email from @spcstech.com more seriously than from a Gmail address. We get this for free, without Google Workspace, and agents can send from it too. That's how proposals and outreach go out under our name.

## How it works

Three free services, each with one job:

| Job | Service | What it does |
| --- | --- | --- |
| Receive | Cloudflare Email Routing | Forwards mail sent to an @spcstech.com address to a normal inbox |
| Send | Resend | Sends mail from @spcstech.com. Free up to 100 a day and 3,000 a month |
| Write | Gmail "Send mail as" | Lets you write from @spcstech.com inside your normal Gmail |

The domain's settings live with your co-founder. You only need two things from your co-founder, both through 1Password:

1. **The SPCS sending key.** A key is like a password that lets a program use a service. This one can only send email, and only from spcstech.com.
2. **Your own address,** if you want one (for example yourname@spcstech.com), with its mail forwarded to your inbox.

## Steps (for the agent)

### 1. Get the key safely

Check whether 1Password is installed and whether its command line tool `op` is available (`op --version`). If not, install it (on a Mac, `brew install 1password-cli`), then turn on **Settings, Developer, Integrate with 1Password CLI** in the 1Password app so `op` can use the app's sign-in.

Ask your person to find the shared item for the SPCS sending key in 1Password and tell you its exact name and vault. Don't ask them to paste the key. You'll read it straight from 1Password, so it never appears in the chat.

Test that you can read it without printing it:

```bash
op read "op://<vault>/<item>/credential" >/dev/null && echo "key found"
```

If the item doesn't exist yet, write the message they should send their co-founder ("Can you share the Resend sending key for spcstech.com with me in 1Password?") and move on to step 4, then come back.

If they don't use 1Password, open a new empty text file at `~/.config/spcs/resend-key` in their text editor, have them paste the key there and save, then lock it down with `chmod 600`. Never read the key back into the chat.

### 2. Draft the first email

The first email goes to your person's own inbox, so you can confirm it arrived. Draft it with them, from `SPCS <info@spcstech.com>` to their own address, with a short subject and body in their voice.

**Your yes:** show the sender, recipient, subject and full body. Wait.

### 3. Send it

```bash
RESEND_API_KEY="$(op read 'op://<vault>/<item>/credential')" \
curl -s -X POST https://api.resend.com/emails \
  -H "Authorization: Bearer $RESEND_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"from":"SPCS <info@spcstech.com>","to":["THEIR_ADDRESS"],"reply_to":"info@spcstech.com","subject":"...","text":"..."}'
```

A reply with an `id` means Resend accepted it. Then search their inbox through the email connector and confirm it arrived, and whether it landed in spam. If it did, have them mark it "not spam".

Explain what just happened in two lines. The agent asked Resend to send as SPCS, Resend checked the key, and the domain's settings prove to Gmail that the email really comes from spcstech.com.

### 4. Write from Gmail as SPCS (optional, but useful)

So your person can also write from the address themselves:

1. Gmail, **Settings, See all settings, Accounts and Import, Send mail as, Add another email address.**
2. Name "SPCS" (or their name), address `info@spcstech.com` or their own address.
3. SMTP server `smtp.resend.com`, port 465, SSL, username `resend`, password is the sending key. Have them copy it from 1Password into this box themselves.
4. Gmail sends a confirmation code to the address. That mail is forwarded to whoever the address points at. For `info@`, that's the co-founder, so write them the message asking for the code.

Then have them send one email from Gmail as SPCS, to themselves, and check it arrives.

### 5. A real one

**Your yes:** ask if there's a real email they've been meaning to send under the SPCS name, like a follow-up to a client or a partner. Draft it, show it in full, and send only after their yes. Check the `id` came back.

### 6. Wrap up

Three short lines: what they now have, what they learned (receive, send and write are three separate jobs; keys come from 1Password, never the chat), and the limit to remember (100 emails a day).

Note the result in the progress file. Offer Lesson 3.

## If something goes wrong

- **"Domain not verified" or 403 from Resend:** the key is for a different domain, or it was revoked. Ask the co-founder for a fresh one.
- **The email lands in spam:** normal for the first few. Mark it "not spam", and keep emails plain, with no attachments, for the first week.
- **No reply comes in:** replies to `info@` go to the inbox it forwards to. For their own address, the co-founder sets the forwarding in Cloudflare.
