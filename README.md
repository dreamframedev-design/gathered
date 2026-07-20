# Gathered Mahjong

A boutique mahjong house inspired by art, friendship, and the ritual of gathering.
Founded by Kelly, Jill, and Nha; artwork by Nha Vuu; site by Conner.

## What's here

| File | What it is |
|---|---|
| `index.html` | The door. A password splash page at the main URL; the house password unlocks the site. |
| `home.html` | The site behind the door. Animated hero, story, Collection No. 001 showcase, the mat, VIP waitlist. Fully self-contained. |
| `studio.html` | The founders' design studio. Invitation-only login, tile lab with artwork uploads, full-set preview, table scene, mat designer, version history, PNG sheet export. |
| `brand.html` | The house brand standard: marks, palette, letterforms, tile anatomy, voice. |

## The door

The main URL shows a splash gate. The house password (case-insensitive) is
`gathered2026`; correct entries are SHA-256 hashed, remembered in the browser,
and forwarded to `home.html`, which bounces locked visitors back to the door.
`home.html` carries `noindex` while gated. This is front-of-house protection
for a pre-launch, not security: anyone technical can read the files on a static
host. If it ever needs to be airtight, use hosting-level auth
(Netlify password / Cloudflare Access) instead. To change the password, put the
new SHA-256 hash in both `index.html` and `home.html`.

## Backend

Auth, design versions, artwork vault, and the waitlist live on Supabase
(project `oskadlvzfwrhhtglrtvu`, tables prefixed `gm_`, storage bucket `gathered`,
row-level security keyed to the founders allowlist). The publishable key in the
HTML is safe to ship; it grants nothing beyond what RLS allows.

Waitlist signups: table `gm_waitlist`, written by the site form, readable from the studio.

## Deploying

Static hosting is all it needs. Upload the three HTML files anywhere
(GoDaddy, Netlify, GitHub Pages). When gatheredmahjong.com is live, set it as
the Site URL in Supabase Auth settings so signup confirmation emails point home.

## House rules

No em dashes. Small is the point. The art gets the credit.
