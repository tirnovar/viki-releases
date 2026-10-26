# VIKI

**VIKI is a local AI command center over an Obsidian vault.** It reads and writes your
notes directly on disk, answers questions about them, captures voice and text, tracks
tasks, projects and your day, and runs scheduled jobs (morning brief, mail triage,
weekly review) that write back into the vault. Speech-to-text and the voice run on your
Mac. Questions, job inputs and the weekly self-audit (on by default, with a sample of your
recent questions and answers; one switch turns it off) go to Anthropic through the Claude
Code CLI you sign in with; nothing else leaves the machine (see `PRIVACY.md` attached to
each release).

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
2. First launch: the app is not yet notarized by Apple (the release notes say when that
   changes), so macOS blocks it once. Open VIKI, click *Done* in the warning, then go to
   **System Settings → Privacy & Security** and click **Open Anyway** next to VIKI
   (macOS 15 and newer; right-click → Open no longer works there). On macOS 14,
   right-click → Open works too. Expect the same step after each update.
3. The five-step wizard asks for language and privacy consent, who you are, where the vault
   is (or creates one), optional integrations (macOS calendar or Microsoft 365, Telegram)
   and then checks that `claude` and Node.js are ready.

The full guide, from a clean Mac to the first scheduled job, is `ONBOARDING.md` attached
to every release. Updates: Settings → Info → *Check* compares your version with
`latest.json` here and links to the new DMG.

## Support

Settings → Info → *Export diagnostics* produces a zip (version, build, config without
secrets, redacted log) to attach to an
[issue](https://github.com/tirnovar/viki-releases/issues/new/choose) – a bug report or an
idea. Issues are public: look inside the zip before attaching it.

## About this repository

Only releases live here. The source code is in a private repository; VIKI is released
under the MIT License (`LICENSE`). `latest.json` on each release describes the newest
version for the in-app update check:

```json
{ "version": "1.0.0", "dmg_url": "https://github.com/tirnovar/viki-releases/releases/download/v1.0.0/VIKI_1.0.0_aarch64.dmg", "sha256": "…", "notes_url": "https://github.com/tirnovar/viki-releases/releases/tag/v1.0.0", "published_at": "2026-10-01T00:00:00Z", "min_macos": "14.0", "arch": "aarch64" }
```
