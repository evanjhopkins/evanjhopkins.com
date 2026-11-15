# evanjhopkins.com

My public page — a single static `index.html`, served by GitHub Pages at
[evanjhopkins.com](https://evanjhopkins.com).

## How it's published

- The site is the repo root on `main`: `index.html` plus `CNAME`, which tells
  GitHub Pages the custom domain is `evanjhopkins.com`.
- Pages must be turned on once: **Settings → Pages → Source: Deploy from a branch
  → `main` / `(root)`**. After that, every push to `main` publishes automatically.

## DNS (Porkbun)

Domain nameservers are Porkbun's, so records are edited at
**porkbun.com → Account → Domain Management → DNS** (hover the domain, click
"DNS", or Details → DNS Records).

Porkbun's form fields map to GitHub's records like this — **Host** is just the
subdomain (`www`), never the full domain, and **Answer** is the target:

| Porkbun "Type"                 | Porkbun "Host" | Porkbun "Answer"      |
| ------------------------------ | -------------- | --------------------- |
| A - Address record             | *(blank)*      | 185.199.108.153       |
| A - Address record             | *(blank)*      | 185.199.109.153       |
| A - Address record             | *(blank)*      | 185.199.110.153       |
| A - Address record             | *(blank)*      | 185.199.111.153       |
| CNAME - Canonical name record  | www            | evanjhopkins.github.io |

Leave TTL at the default. Blank Host means the apex (`evanjhopkins.com`); don't
type `@` or the full domain there. Delete Porkbun's parking records first (an
apex A/ALIAS and a `www` CNAME pointing at `uixie.porkbun.com`, plus any `*`
wildcard) or the new records conflict.

Optional: add AAAA records `2606:50c0:8000::153` through `2606:50c0:8003::153`
at the apex for IPv6.

After DNS resolves, tick **Enforce HTTPS** in **Settings → Pages** (GitHub issues
the certificate once the domain points here).
