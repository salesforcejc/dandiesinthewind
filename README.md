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

The intake form is a Microsoft Form owned by Jennifer's personal Microsoft account, embedded in `index.html` (the `intake-form-embed` iframe). Every response is saved in Microsoft Forms (View responses), and an email notification is sent for each one.

To change the questions, edit the form at forms.office.com; the site updates automatically. If the form grows or shrinks a lot, adjust the iframe `height` in `styles.css`.
