# FlinT Web

The shared website for **FlinT Spark**, **FlinT OS** and **FlinT Desktop**, by DeeTech Labs.
Extracted from [FlinT OS](https://github.com/DeeTech-Labs/FlinT-OS/tree/main/site).
The firmware and companion remain in their own repositories.

## Pages

- `index.html` — ecosystem overview
- `spark.html` — device and hardware documentation
- `os.html` — firmware and developer overview
- `desktop.html` — companion, supported features and availability
- `changelog.html` / `desktop-changelog.html` — product release histories

## Preview and validation

```sh
python3 sync_changelog.py
python3 tools/check_site.py
python3 -m http.server 8080
```

Open http://localhost:8080. No build tools or third-party packages are required.

## Release histories

`changelogs/` contains snapshots from the product repositories; run
`python3 sync_changelog.py --fetch` to refresh them from their `main` branches.
Without `--fetch`, generation works offline. The deployment refreshes both
changelogs on each push, manual run and daily schedule. Product repositories
remain the source of truth; their code is not copied into this repository.

## Hosting

`.github/workflows/pages.yml` deploys only the public HTML/CSS/JS and assets to
GitHub Pages. Select **GitHub Actions** as the Pages source.
`CNAME` preserves `flint.deetech.ru`; the domain must belong to this repository's
Pages configuration before domain deployment. Existing DNS should point to
`deetech-labs.github.io`. HTTPS certificate issuance is managed by GitHub.

## License

Apache-2.0. Original FlinT OS site and branding © 2026 DeeTech Labs.
