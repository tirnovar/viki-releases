# VIKI

**VIKI is a local AI command center over an Obsidian vault.** It reads and writes your
notes directly on disk, answers questions about them, captures voice and text, tracks
tasks, projects and your day, and runs scheduled jobs (morning brief, mail triage,
weekly review) that write back into the vault. Speech-to-text and the voice run on your
Mac. Questions and job inputs go to Anthropic through the Claude Code CLI you sign in
with; nothing else leaves the machine (see `PRIVACY.md` attached to each release).

## Requirements

| | |
|---|---|
| **Mac** | macOS 14 or newer on Apple Silicon (M1 and later). Intel Macs are not supported. |
| **Claude Code CLI** | `claude` signed in to your own Anthropic account. VIKI has no API key of its own. |
| **Obsidian** | your vault editor; VIKI creates a fresh vault from its template or uses an existing one. |
| **Node.js** (optional) | renders Dataview and Bases blocks inside VIKI. |

## Install

1. Download the newest `VIKI_<version>_aarch64.dmg` from
   [Releases](https://github.com/tirnovar/viki-releases/releases/latest) and drag VIKI to
   Applications.
2. First launch: right-click → Open (the app is not yet notarized; the release notes say
   when that changes).
3. The five-step wizard asks for language and privacy consent, who you are, where the vault
   is (or creates one), optional integrations (Microsoft 365, Telegram) and then checks
   that `claude` and Node.js are ready.

The full guide, from a clean Mac to the first scheduled job, is `ONBOARDING.md` attached
to every release. Updates: Settings → Info → *Check* compares your version with
`latest.json` here and links to the new DMG.

## Support

Settings → Info → *Export diagnostics* produces a zip (version, build, config without
secrets, redacted log) to attach to a post in
[Discussions](https://github.com/tirnovar/viki-releases/discussions).

## About this repository

Only releases live here. The source code is in a private repository; VIKI is released
under the MIT License (`LICENSE`). `latest.json` on each release describes the newest
version for the in-app update check:

```json
{ "version": "1.0.0", "dmg_url": "https://github.com/tirnovar/viki-releases/releases/download/v1.0.0/VIKI_1.0.0_aarch64.dmg", "sha256": "…", "notes_url": "https://github.com/tirnovar/viki-releases/releases/tag/v1.0.0", "published_at": "2026-10-01T00:00:00Z", "min_macos": "14.0", "arch": "aarch64" }
```
