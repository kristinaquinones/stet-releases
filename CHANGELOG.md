# Changelog

Notable changes to the **stet** install packages distributed from this repository. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

This is the writer-facing install feed. It summarizes what's in the `stet.zip` you download. Versioning:

- **Stable releases** use semver (e.g. `0.1.1`).
- **Pre-releases** are cut after each merge to `main` and use a build-stamped tag `v0.1.0.{build}` (e.g. `v0.1.0.65`). They carry the same features as the current development line and are intended for testing and dogfooding.

For every published build, see [Releases](https://github.com/kristinaquinones/stet-releases/releases).

---

## Pre-release line — `0.1.0.x` (Milestone 2: audience, in progress)

Build-stamped pre-releases from `main`, beginning with the source-repo cutover (`v0.1.0.47`, 2026-06-15) through the latest build. These layer the Milestone 2 audience features on top of stable `0.1.0`.

### Added

- **Audience** — double opt-in subscribe form on posts. Send with built-in WordPress mail (no setup) or bring your own Postmark key, gated behind a verified test send.
- **Broadcast on publish** — per-post "Email subscribers when you publish" switch, plus "Send to subscribers" / "Send again" on published posts. Sends are batched through a background queue.
- **Subscriber dashboard** — **Stet → Subscribers** list with status filters (All, Pending, Confirmed, Unsubscribed), email search, and pagination.
- Admin actions on subscribers: confirm a pending address, resend confirmation, mark unsubscribed, re-subscribe, edit email, and remove one or many.
- **Add subscriber** modal and **Export CSV** (email, status, created_at, confirmed_at — no tokens).
- **Uninstall backup** — when the subscriber list is non-empty, a CSV is written to `uploads/stet-exports/` before plugin options are removed.

### Changed

- Settings gains an **Audience** card (confirmed count + View subscribers) and a provider control with bring-your-own-key validation hints.
- Published posts show **Details** when clean and **Save** + **Details** when dirty; unpublish and trash live in the More menu and Details panel.

### Fixed

- Broadcast retries resume from the last batch offset, so a failed send no longer re-mails subscribers who already received it.

### Security

- Subscriber confirm/unsubscribe tokens never appear in the list UI, AJAX responses, or CSV exports.
- Subscriber admin actions require the `manage_options` capability and a valid nonce.

---

## [0.1.0] — 2026-06-03 (Milestone 1)

First validated build: the calm writing experience.

### Added

- **One-switch writing mode** — admin stripped to Write, Drafts, and Settings; block editor off for posts; bundled theme applied. Fully reversible.
- **Markdown-first composer** — Markdown is the source of truth (stored in post meta); clean HTML compiled on save; live preview; autosave; Details panel for slug, category, and sharing fields.
- **Calm admin lists** — Drafts and Pages screens with trash via a confirm modal (reversible).
- **Permalink presets** — SEO-friendly post URL patterns in Settings, with prior structure backed up for reversal.
- **Bundled reading theme** — typography-first, responsive, comments off by default; light/dark, serif/sans, and writer-chosen palettes; category archives, optional search, pages index.
- **Easy sharing** — Open Graph and Twitter cards, per-post meta description and social image, clean URLs.
- **Clean uninstall** — posts and Markdown meta survive uninstall.

---

[0.1.0]: https://github.com/kristinaquinones/stet-releases/releases/tag/v0.1.0.47
