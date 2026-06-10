# Central Three — Website

Public marketing site for **Central Three** → https://centralthree.site

Single-file static site (`index.html`) with the animated emblem embedded.
No build step, no dependencies, nothing to install.

---

## Deploying (GitHub Pages)

1. Create the repo (e.g. `centralthree-site`) and upload everything in
   this folder, including the hidden `.gitignore`.
2. Repo **Settings → Pages** → Source: *Deploy from a branch* →
   Branch: `main`, folder: `/ (root)`.
3. The `CNAME` file in this folder tells Pages to serve the site at
   `centralthree.site`. Also enter the domain under
   **Settings → Pages → Custom domain** so GitHub registers it.
4. **Verify the domain** (Settings → Pages → verified domains — add the
   TXT record GitHub gives you at your registrar). This prevents
   domain-takeover attacks.
5. Once the certificate provisions, tick **Enforce HTTPS**.

## DNS records (at your domain registrar)

| Type  | Host | Value                     |
|-------|------|---------------------------|
| A     | @    | 185.199.108.153           |
| A     | @    | 185.199.109.153           |
| A     | @    | 185.199.110.153           |
| A     | @    | 185.199.111.153           |
| CNAME | www  | `<your-account>.github.io` |

⚠️ **Do not modify or delete the existing MX records** — they route
support@ / api@ and all aliases. They coexist fine with the records above.

Future app sites are CNAMEs too, each pointing at its own Pages repo:
`eat2night.centralthree.site`, `outdoors.centralthree.site`,
`healthyme.centralthree.site`.

## Repo rules

- This repo is the **public website only**. App source code, scripts
  with credentials, analytics configs, store certificates — all of that
  lives in separate **private** repos.
- Never commit secrets. The `.gitignore` blocks the common offenders,
  but it is a guardrail, not a guarantee — keys pasted *inside* an
  HTML or JS file will still go through. If a secret ever lands in a
  commit: rotate the key immediately; deleting the file does not remove
  it from git history.
- Write commit messages as if they're public. They are.

© 2026 Central Three LLC. All rights reserved — see `LICENSE`.
