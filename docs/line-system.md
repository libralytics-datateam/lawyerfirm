# LINE and booking

How the public site connects to LINE and the consultation calendar. This file has no secrets. Channel secrets, LIFF secrets, and the firm mailbox login stay in LINE Developers, LINE Official Account Manager, and Google.

## Pieces

- **LINE Official Account `@918ujhum`.** Add link: https://line.me/R/ti/p/@918ujhum. The rich menu and the automatic reply are set in LINE Official Account Manager. They are not files in this repo.
- **LIFF app.** LIFF ID `2012228617-Hxvy7UGE`. Endpoint `https://lawfirmtable.com/liff/`. The page is `liff/index.html`. Inside the LINE app it can post the intake text into the chat. Outside LINE it shows that text so the visitor can copy it, and a link back to the official account. The page itself switches among Thai, Japanese, and English.
- **Google Calendar booking page.** https://calendar.google.com/calendar/appointments/schedules/AcZssZ063b2G2D5iphuJqtga-YGXJfOtBQd3zanNZncXVShZCgmTxuK_nKR7gJxclo9_-zJiPci0DSMN
  The contact-section button “Book a free 30-minute consultation” and the booking button on the LIFF page both open this URL.
- **Firm Gmail auto-reply.** The automatic reply to mail sent to the firm is configured in Gmail. This site does not send that reply.

The contact section still prints the LINE handle as `@lawfirmtable`. That wording was left unchanged. The new “Add us on LINE” button uses `@918ujhum`.

## Deployment

`lawfirmtable.com` is served by Vercel over HTTPS. The domain CNAMEs to Vercel DNS, and responses include `server: Vercel` and HSTS. Vercel serves the files at the repo root, so `liff/index.html` is the page at `/liff/` once this tree is what production is serving.

This repo has no GitHub Actions workflow, no `vercel.json`, and GitHub Pages is off. GitHub has no deployment records for the repo, and the latest commit on `main` has no Vercel status check. Merging to `main` is not, from anything visible in the repo or on GitHub, enough to publish `/liff/`. The Vercel project still has to be deployed. Whether that project is also connected to GitHub in the Vercel dashboard could not be checked from here.

LINE only loads a LIFF endpoint over HTTPS. After deploy, `https://lawfirmtable.com/liff/` has to return this page. Before this change is deployed, that URL 404s.
