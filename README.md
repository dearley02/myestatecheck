# myestatecheck

A thirteen-question self-assessment. Someone answers questions about their
family, home, business, and paperwork, and gets back a plain-language summary
of what an attorney would want to look at, an illustration of what California
statutory probate fees would run, and an option to request a call.

Live at: https://dearley02.github.io/myestatecheck/

## Publishing

This repository is a single static page. No build step, no dependencies.

1. Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)`
4. Save. The site is live in about a minute.

To point a custom domain at it later, add the domain under Settings → Pages →
Custom domain and create a CNAME record at your registrar per GitHub's
instructions.

## Configuration

Near the bottom of `index.html`:

```js
var CONFIG = { firmName: "", tagline: "", phone: "",
               email: "derekaearley+estatecheck@gmail.com",
               formEndpoint: "", familyPlan: 4000, ownerPlan: 6500,
               individualPlan: 2750 };
```

| Key | Effect |
|---|---|
| `email` | Submissions open the visitor's mail client addressed here. |
| `formEndpoint` | If set to a form-service URL, submissions POST there as JSON instead of opening a mail client. |
| `firmName`, `tagline` | Deliberately blank in this version. Setting them adds a header identity. |
| `familyPlan`, `ownerPlan`, `individualPlan` | Drive which package is recommended. No dollar figure is shown to the visitor. |

## How data is handled

While someone answers, nothing is stored, logged, or transmitted. No
analytics, no cookies, no local storage. The only outbound request before
submission is the webfont load from Google Fonts.

On submit, with `email` set, the visitor's own mail client opens with their
answers in the body; the data path is an ordinary email from them to the
configured address. With `formEndpoint` set instead, answers are POSTed to
that third-party service, which then holds them. The page states which of
these applies, and the questionnaire's sensitive answers are attached only
if the visitor leaves the consent box checked.

## Status and caveats

- This is an unbranded test version. No firm name appears anywhere.
- **Not yet reviewed by a licensed attorney.** That review should happen
  before the tool is used with anyone who is not a test participant.
- The configured email address is visible in page source, which is required
  for the mail link to function, and this repository is public.
- Statutory fee figures were verified against California Probate Code
  sections 10800 and 10810 in September 2026. Re-check before relying on them.

## License

Proprietary, all rights reserved. See `LICENSE.md`.
