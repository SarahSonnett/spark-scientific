# Spark Scientific — website

Single-page static site for **Spark Scientific LLC**, served at
**https://sparkscientific.org/**. No build step, no dependencies — just
HTML, CSS, and SVG.

## Files

```
index.html          the whole site (one page)
css/style.css       all styling; brand colors defined at the top in :root
assets/favicon.svg  browser-tab icon (blue tile + orange spark)
assets/             put headshot.jpg and the logo PNG here
```

## Deploying

Upload the contents of this folder (not the folder itself) to your web
host's document root, preserving the `css/` and `assets/` subfolders.
`index.html` must end up at the top level so it loads at
`https://sparkscientific.org/`.

## Pointing all seven domains at sparkscientific.org

The other six domains (sparkscientificllc.org/.com/.net,
spark-scientific.net/.org, sparkscientific.net) should **301-redirect**
to `https://sparkscientific.org/` rather than serve copies of the site —
that consolidates search-engine ranking onto one domain.

Most registrars (Namecheap, GoDaddy, Cloudflare, etc.) offer this as
"domain forwarding" or "URL redirect" in the DNS settings — choose the
**permanent (301)** option and forward to `https://sparkscientific.org/`.
No hosting is needed for the redirect domains. The
`<link rel="canonical">` tag in `index.html` reinforces this for search
engines.

## Replacing the headshot

The site displays `assets/headshot.jpg`, a web-sized (1000px, ~140 KB)
copy of the original photo. To change it, overwrite that file with a
similarly sized JPEG — don't upload multi-MB originals, they slow the
page down. On macOS: `sips -Z 1000 -s format jpeg -s formatOptions 80
original.jpg --out assets/headshot.jpg`. The full-resolution original
(`AllisonBrownlowPhoto-Wolfe-57.jpg`) doesn't need to be uploaded to
the host.

## Enabling the contact form (later)

The mailto link works today. When you want a real form:

1. Sign up at https://formspree.io (free tier) with
   info@sparkscientific.org and create a form — you'll get an ID like
   `xkgwzabc`.
2. In `index.html`, find the `FUTURE CONTACT FORM` comment in the
   Contact section, replace `YOUR_FORM_ID` with your ID, and remove the
   comment markers around the `<form>`.

## Tweaking brand colors

All colors live in the `:root` block at the top of `css/style.css`
(orange `#F47B20`, blue `#1A7DC5`, sampled from the logo PNG). Change
them there and the whole site follows.
