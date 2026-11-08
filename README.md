# Dandies in the Wind

Static website for Jennifer R. Caldwell's personal coaching practice. Plain HTML and CSS, no build step.

## Files

- `index.html` home page with the intake form
- `thanks.html` page shown after the form is submitted
- `styles.css` all styling
- `images/` photos (JPG + WebP) and the social share image
- `favicon.svg` browser tab icon
- `CNAME` tells GitHub Pages to serve the site at dandiesinthewind.org

## Deploy on GitHub Pages

1. Create a new GitHub repo (e.g. `dandiesinthewind`) and push these files to the `main` branch.
2. In the repo: **Settings > Pages > Build and deployment**, set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Under **Custom domain**, enter `dandiesinthewind.org` and save.

## Point the domain at GitHub (in GoDaddy DNS)

In GoDaddy: **My Products > dandiesinthewind.org > DNS**.

1. Delete any existing `A` records for `@` and any `CNAME` for `www` that point to GoDaddy's website builder.
2. Add four `A` records for host `@`:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153
3. Add a `CNAME` record: host `www`, value `<your-github-username>.github.io`
4. **Do not touch the MX records.** Those deliver email to jennifer@dandiesinthewind.org.

DNS can take a few minutes to a few hours. Once GitHub shows the domain as verified, tick **Enforce HTTPS** in Settings > Pages.

After the new site is live, cancel the GoDaddy Website Builder plan (keep the domain and email).

## The intake form

The form posts to [FormSubmit](https://formsubmit.co), which emails each submission to jennifer@dandiesinthewind.org. No account needed.

**One-time activation:** the very first time anyone submits the form, FormSubmit sends a confirmation email to jennifer@dandiesinthewind.org. Click the activation link in it, and from then on every submission arrives as an email. Submit a test yourself right after launch so this happens before a real client fills it out.

Optional: after activating, FormSubmit gives you a random alias string. Replace the email address in the form's `action` with `https://formsubmit.co/<that-alias>` so Jennifer's address isn't visible in the page source.

Spam protection is a hidden honeypot field. If spam becomes a problem, change `_captcha` to `true` in `index.html`.
