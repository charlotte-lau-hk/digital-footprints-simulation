# TODO / ideas for discussion

## Eavesdroppers / sniffers  — *proposed, not yet built*

Charlotte's idea: add sniffers that can capture traffic at different points —

- a **LAN sniffer** near the user (e.g. someone on the same Wi-Fi),
- an **internet sniffer** with access to router / backbone data,
- a **sniffer on the website's LAN** (near the server).

### Recommendation — do it, but as an *overlay*, not as 3 more boxes

Adding three more party boxes would crowd the diagram and overwhelm S1–S3
students. A cleaner design that teaches the *same* point:

> A sniffer is just **a passive reader sitting on one link**. What it can read is
> decided entirely by that link's colour (encrypted / tunnel / plaintext) — which
> is the lesson the line colours already teach.

So the sniffers map one-to-one onto the segments we already draw:

| Sniffer            | Sits on link            | Sees when HTTPS        | Sees when HTTP            |
|--------------------|-------------------------|------------------------|---------------------------|
| LAN (same Wi-Fi)   | device ↔ ISP            | domain/IP + metadata   | **everything** (content)  |
| Internet / backbone| ISP ↔ VPN/website       | domain/IP + metadata   | **everything**            |
| Website LAN        | at/near the server      | content (it's decrypted here) | content            |

With a **VPN on**, the LAN and backbone sniffers on the tunnel segments see only
encrypted tunnel traffic → the "encryption is important" point lands hard.

### Proposed implementation (Phase 2)

- One toggle in the controls: **"Show eavesdroppers 👂"**.
- When on, draw a small 👂/🕵️ marker hovering over each active segment.
- Hover/tap a marker → a callout in the *same style* as the node callouts,
  listing exactly what that sniffer captures for the current switch settings
  (reuse the per-segment `segClass()` logic — no new rules needed).
- Keep it off by default so the base diagram stays calm.

This keeps the tool honest ("even HTTPS isn't invisible to the endpoint / the
site's own network") without turning the diagram into spaghetti.

### Open questions for Charlotte
1. Should the website-LAN sniffer be included? It makes the subtle point that
   HTTPS protects data *in transit* only — powerful, but one more thing to explain.
2. Introduce sniffers in the same lesson, or as a separate "advanced" mode?

---

## Other backlog ideas
- A short "scenario" preset menu (e.g. *public Wi-Fi + HTTP login* → password exposed).
- Optional packet-inspection popup showing a mock HTTP request vs an encrypted blob.
- A print/worksheet mode for classroom handouts.
