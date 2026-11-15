# evanjhopkins.com

My public page — a single static `index.html`, served by GitHub Pages at
[evanjhopkins.com](https://evanjhopkins.com).

## How it's published

- The site is the repo root on `main`: `index.html` plus `CNAME`, which tells
  GitHub Pages the custom domain is `evanjhopkins.com`.
- Pages must be turned on once: **Settings → Pages → Source: Deploy from a branch
  → `main` / `(root)`**. After that, every push to `main` publishes automatically.

## DNS (set at the registrar, e.g. Porkbun)

Delete any parking/default records first, then:

| Type  | Host | Value                                                      |
| ----- | ---- | ---------------------------------------------------------- |
| A     | @    | 185.199.108.153                                            |
| A     | @    | 185.199.109.153                                            |
| A     | @    | 185.199.110.153                                            |
| A     | @    | 185.199.111.153                                            |
| AAAA  | @    | 2606:50c0:8000::153                                        |
| AAAA  | @    | 2606:50c0:8001::153                                        |
| AAAA  | @    | 2606:50c0:8002::153                                        |
| AAAA  | @    | 2606:50c0:8003::153                                        |
| CNAME | www  | evanjhopkins.github.io                                     |

The AAAA records are optional. After DNS resolves, tick **Enforce HTTPS** in
**Settings → Pages** (GitHub issues the certificate once the domain points here).
