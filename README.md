# Web Privacy & Digital Footprints

An interactive, client-side teaching tool that shows Hong Kong secondary school
students **what each part of the internet can see when you browse a web page**.

Built by **Charlotte Lau** as a teaching tool for ICT / network security.

## Live demo

👉 https://charlotte-lau-hk.github.io/web-privacy-explorer/

## What it does

Students flip switches on their own device and watch the network react in real time:

- **Use VPN** — route traffic through a VPN server
- **Log in** — sign in to an account
- **Allow cookies** — let the site store an identifier
- **Secure connection** — HTTPS vs HTTP

The animated diagram shows four parties — **your device → ISP → VPN → website** —
connected by colour-coded lines (encrypted, VPN tunnel, or plaintext). Hover or
tap any box to see exactly what that party knows: source/destination IP
addresses, whether it can read your content, and which digital footprints
(IP, cookie, login) the website can use to identify you.

A live verdict answers the key question: **"Can this website identify you?"**

## Teaching points

- HTTPS hides *content*, but the ISP still sees *which site* you visit (metadata).
- A VPN hides your IP from the website and your destination from the ISP — but
  you now trust the VPN provider instead.
- Cookies and logins still identify you **even with a VPN on**.
- Browser fingerprinting means "no cookies + VPN" is still not truly anonymous.

## Tech

A single `index.html` — pure HTML, CSS and JavaScript, no build step, no network
requests. Works fully offline. Bilingual (English / Traditional Chinese) with a
light/dark theme toggle.

All IP addresses are fake, taken from the ranges reserved for documentation
(RFC 5737 / RFC 3927).

## Licence

MIT — see [LICENSE](LICENSE).
