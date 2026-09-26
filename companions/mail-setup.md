# Mail provider setup (Eraser + confirmation inbox)

Subject PII and credentials stay in private Eraser config / secret cards — never in this file.


After install / init, **ask which mailbox** will send opt-outs and receive confirmations. Configure Eraser (or manual drafts) accordingly.

#### A. Gmail

1. In the Google Account that will send opt-outs, turn on **2-Step Verification** if it is not already on.
2. Open [Google App Passwords](https://myaccount.google.com/apppasswords) (Account → Security → App passwords).
3. Create one for **Mail** (name it e.g. `Eraser`).
4. Copy the **16-character** password (spaces optional).
5. Give it to the agent only through the app’s **secure secret card** (environment variable such as `ERASER_GMAIL_APP_PASSWORD`) — **never paste into chat**, never commit to git, never put in this skill file.
6. SMTP: `smtp.gmail.com` port **587** STARTTLS. IMAP: `imap.gmail.com` port **993** SSL.
7. The agent writes credentials into `~/.eraser/config.yaml` under `email.smtp` / inbox with restricted file permissions, or injects them at send time from the env var.
8. **HARD unread:** Gmail API / connector — prefer `METADATA_ONLY`; restore `UNREAD` after any body fetch. Eraser IMAP must use BODY.PEEK.

If the user refuses an App Password, use **manual send mode** (`options.send_mode: manual`) instead.

#### B. Microsoft 365 / Outlook (work or personal outlook.com)

Many tenants disable basic auth / SMTP AUTH. Prefer **manual send mode** when the org blocks App Passwords or SMTP AUTH; otherwise:

1. **Consumer Microsoft account with 2FA:** Account → Security → App passwords — create one for Eraser if available.
2. **Work / school (Exchange Online):** ask an admin whether **SMTP AUTH** is enabled for the mailbox; org-issued app password or Conditional Access may block this path.
3. Typical SMTP: `smtp.office365.com` port **587** STARTTLS. IMAP: `outlook.office365.com` port **993** SSL.
4. If basic auth / SMTP AUTH / IMAP are blocked: set `options.send_mode: manual`. Have the agent create drafts via the Outlook / Microsoft 365 connector (or Outlook web); mark sent in Eraser with `eraser mark-sent` after the user sends. IMAP monitor may be unavailable — use Outlook / Grok connector **search** for broker replies instead of `eraser monitor`.
5. **HARD unread for Outlook connector:** prefer metadata / search. If reading a message marks it read, immediately mark unread again (mirror the Gmail restore rule).
6. If IMAP monitor is used, Eraser BODY.PEEK is still required.

#### C. Other IMAP (Yahoo, iCloud, custom)

Need the provider’s SMTP + IMAP host/ports and an app-specific password. If the provider does not offer app passwords or blocks SMTP, use **manual send mode** and a connected mail draft path when available.
