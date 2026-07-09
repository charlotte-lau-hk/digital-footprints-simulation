# Web Privacy & Digital Footprints

An interactive, client-side teaching tool that shows Hong Kong secondary school
students **what each part of the internet can see when you browse a web page** —
and how VPN, HTTPS, cookies, logins, and public-Wi-Fi attacks change the picture.

Built by **Charlotte Lau** for ICT / network security.

## Live demo

👉 https://charlotte-lau-hk.github.io/web-privacy-explorer/

## Two scenarios (tabs)

- **🏠 Home / general** — Device → ISP → VPN → Website
- **📶 Public Wi-Fi** — adds a Wi-Fi router hop, Wi-Fi security (Open vs
  WPA2/WPA3), and nearby attackers

## What students control

The device switches carry across both tabs:

- **Use VPN** — route traffic through a VPN server
- **Log in** — sign in to an account
- **Allow cookies** — let the site store an identifier
- **Secure connection** — HTTPS vs HTTP

On the **Public Wi-Fi** tab there are two more:

- **Wi-Fi security** — set by the network: Open / WPA2·WPA3
- **Attacker nearby** — None · 🕵️ Sniffer (passive) · 🎭 Fake AP (man-in-the-middle)

## What they see

- An animated diagram with colour-coded links: 🔒 encrypted (HTTPS / WPA2),
  🛡️ VPN tunnel, 🔓 plaintext (HTTP).
- Hover or tap any box — device, ISP, VPN, router, fake AP, website — for exactly
  what that party knows about you.
- **Sniffer mode** — the cursor becomes a 🕵️; move it over each link to see what
  an eavesdropper captures there. (WPA2 blocks the nearby stranger; HTTP exposes
  everything beyond the router.)
- **Fake AP mode** — the device joins the attacker's stronger-signal hotspot; the
  callout shows WPA2/WPA3 doesn't help, but a VPN keeps everything encrypted.
- A **"Can this website identify you?"** guess-and-reveal quiz.
- Two reference panels: **What each layer protects** (content vs digital
  footprint) and **Can a VPN really protect you?** (does vs does-not).

## Key teaching points

- HTTPS hides *content*, but the ISP / Wi-Fi still sees *which site* you visit
  (metadata).
- WPA2/WPA3 only protects the *radio hop* to the router — not beyond it, and not
  from a fake AP you willingly joined.
- A VPN is the strongest defence on hostile Wi-Fi (a sniffer or fake AP sees only
  a tunnel) — but it does **not** make you anonymous: cookies, logins, and your
  browser fingerprint still identify you.
- Nothing online is perfectly anonymous.

## Tech

A single `index.html` — pure HTML, CSS and JavaScript, no build step, no network
requests. Works fully offline. Bilingual (English / 繁體中文) with a light/dark
theme toggle.

All IP addresses are fake, taken from the range reserved for documentation
(RFC 5737).

## Licence

MIT — see [LICENSE](LICENSE).
