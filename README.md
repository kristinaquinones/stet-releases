# stet releases

Install packages for **[stet](https://stet.blog)** — *WordPress, minus everything that isn't writing.*

This repository is the public **install feed** for stet. It distributes the ready-to-install plugin zip. **No source code is published here** — stet is developed in a separate private repository.

- **Download:** grab `stet.zip` from the [Releases page](https://github.com/kristinaquinones/stet-releases/releases).
- **No GitHub account required.** Releases are public; anyone can download.

---

## What is stet?

*stet* is the proofreader's mark for "let it stand" — leave the writing alone.

stet is a self-hosted WordPress plugin that flips a cluttered install into a calm writing space in one switch. It strips the admin down to writing, turns off the block editor, drops you into a Markdown-first composer, ships a clean reading theme, and gives you a way to keep an audience without leaving the platform you already own. Everything is reversible.

> **Status:** prototype / free build. Pre-releases are published after each merge to `main`. The latest pre-release is fine for testing and dogfooding.

---

## Requirements

- Self-hosted WordPress (a site where you can upload plugins or place files in `wp-content/plugins/`).
- Ability to upload plugins in **wp-admin**, or SFTP/file access to the server.

---

## Install

1. Download **`stet.zip`** from the [Releases page](https://github.com/kristinaquinones/stet-releases/releases). The latest pre-release is fine for testing.
2. In wp-admin: **Plugins → Add New → Upload Plugin**.
3. Choose `stet.zip`, click **Install Now**, then **Activate**.
4. Open **Stet → Settings** and turn on writing mode when prompted.

Then follow the in-product getting-started flow to publish your first post.

---

## Upgrade

### From the dashboard (optional, recommended)

In **Stet → Settings → Advanced**, turn on **Check GitHub for stet updates**. stet checks this public repository when you click **Check now** (or open **Dashboard → Updates**). Nothing installs until you confirm.

- **Stable only (default):** clean semver tags like `0.1.1`.
- **Include pre-releases:** build-stamped dogfood builds like `0.1.0.65` after each merge to `main`.

No GitHub login is required. If your host shares an IP with many sites, GitHub may rate-limit unauthenticated checks — you can add an optional personal access token in the same settings section. Your posts, Markdown source, and subscriber data stay in the database across upgrades.

### Manual zip upload

Download a newer `stet.zip` and upload it the same way (**Plugins → Add New → Upload Plugin**). WordPress replaces the plugin folder; your content is preserved.

Pre-release zips carry a build-stamped version (e.g. `0.1.0.65`). After upload, confirm the **Plugins** screen shows that version rather than plain `0.1.0`.

---

## Version scheme

- **Stable releases** — clean semver (e.g. `v0.1.1`). Published as normal releases.
- **Pre-releases** — build-stamped `v0.1.0.{build}` (e.g. `v0.1.0.65`), cut automatically after each merge to `main`. Marked as pre-release on GitHub.

See the [Changelog](CHANGELOG.md) for what's in each notable build.

---

## Help and documentation

Writer-facing guides (install, writing mode, composer, audience, broadcasts) live with the project at **[stet.blog](https://stet.blog)**.

---

## License

stet is released under the [PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0). Personal and nonprofit blogging use is fine; **commercial use** — selling copies, selling support as the product, or running a paid service built on this code — is not permitted without permission from the copyright holder. Full terms are in [`LICENSE`](LICENSE) here and bundled inside each `stet.zip`.

The project **may switch to GPLv2-or-later in the future** if distribution plans change (for example, listing on the WordPress.org plugin directory).

---

Copyright © Kristina Quinones — [stet.blog](https://stet.blog)
