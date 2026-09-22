# Orange County Estate Plans — private preview

Unpublished private preview of a practice website. This branch is for review only. It is not a live site, and nothing here accepts clients.

Orange County Estate Plans is a working label on this preview. It is not presented as a verified trade name.

## Do not publish

- Do not merge this branch in order to update the public GitHub Pages site.
- Do not enable GitHub Pages, a custom domain, or any other host from this branch.
- Do not change DNS for OrangeCountyEstatePlans.com. Ownership and DNS are unverified.
- Do not connect the inquiry form to email, a form vendor, a spreadsheet, or a booking tool.
- Do not add a phone number, street address, map, or personal name to this preview.

`main` still has a separate self-assessment page (Business & Estate Check). This branch replaces that page with the practice preview. Leave `main` as it is until there is a separate decision to publish.

## Run locally

No install, no build, and no environment variables.

```bash
python3 -m http.server 8080
```

Open http://127.0.0.1:8080/

`index.html` is the homepage. `inquire.html` is the inquiry form. You can also open `index.html` directly in a browser.

## Nonfunctional contact points

- “Request a 15-minute introductory call” only opens `inquire.html`. It does not book a call.
- “Request an existing-plan review” only opens the same form with existing-plan review selected. It does not book a call.
- “Submit request (preview only)” stays in the browser and shows “Preview only — not sent.” It does not email, store, or transmit the answers.
- The page has no phone number, email address, street address, map, chat, or calendar.

The fee panel is labeled as a draft. The amounts are not approved as live prices.
