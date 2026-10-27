# ORYNVAL research waitlist page

Single static file: `index.html` (inline CSS/JS, no external scripts, fonts, analytics or trackers).
Two tiers, each posting to its own Google Form (owned by the tomelias2020 Google account; responses go to that form's linked Sheet):

| tier | form |
|---|---|
| Pilot early access | `https://docs.google.com/forms/d/e/1FAIpQLSfg0TL9M1j85u2iCa2MXMw4b2gD_Yy8_tPyrMWgzVbAzbsICw/viewform` |
| Research updates | `https://docs.google.com/forms/d/e/1FAIpQLSdS17euRFBVZay0ZhmuDdW9mM-IJFxt-EZcohNc6TV8Cd8BIQ/viewform` |

## How submission works
- `FORM_ENDPOINT` at the top of the `<script>` block maps each page field to a Google Forms `entry.<id>`.
- The page POSTs `application/x-www-form-urlencoded` to `/formResponse` with `fetch(..., {mode: "no-cors"})`. Google sends no CORS headers, so the browser cannot read the result; the page shows "Thanks — you're on the list." once the request is sent.
- Multiple-choice values on the page must match the form's option strings exactly (including en dashes), or Google drops the answer / rejects the response. If you edit options in the form, edit them in `index.html` too.
- Honeypot field `website`: if filled, nothing is sent.
- CSP allows only `https://docs.google.com` for `connect-src` / `form-action`.

## Hosting
GitHub Pages, branch `main`, folder `/` (root). `.nojekyll` disables Jekyll processing.

## Rules for this page
- No performance claims or numbers, no customers/partners/funding, no dates, no internal research names.
- Data deletion contact: tomelias2020@gmail.com.
