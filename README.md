# Gathered Mahjong

A boutique mahjong house inspired by art, friendship, and the ritual of gathering.
Founded by Kelly, Jill, and Nha; artwork by Nha Vuu; site by Conner.

## What's here

| File | What it is |
|---|---|
| `index.html` | The public site. Animated hero, story, Collection No. 001 showcase, the mat, VIP waitlist. Fully self-contained. |
| `studio.html` | The founders' design studio. Invitation-only login, tile lab with artwork uploads, full-set preview, table scene, mat designer, version history, PNG sheet export. |
| `brand.html` | The house brand standard: marks, palette, letterforms, tile anatomy, voice. |

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
