# Scribewave plugins for Claude Code

## Airgap

Use [Scribewave Airgap](https://airgap.scribewave.com), the offline transcription app, from Claude Code:

- transcribe audio and video files on your computer;
- search and read your Airgap transcripts;
- propose corrections, which Airgap checks and you review in its editor;
- highlight words to check, or replace a misheard name everywhere;
- prepare meetings with `/airgap:prepare` and follow up with `/airgap:follow-up`.

**Privacy.** Audio never leaves your computer: Airgap transcribes it locally. Claude receives only the text it asks for, from the folders you share, and Airgap lists every request under Settings → AI assistants → Activity.

### Requirements

- Scribewave Airgap 0.1.17 or later, on macOS or Windows.
- In Airgap: **Settings → AI assistants → Allow AI assistants** on, and at least one folder shared.

### Install

```bash
claude plugin marketplace add scribewave/claude-plugins
```

```bash
claude plugin install airgap@scribewave
```

Then restart Claude Code. Inside Claude Code, `/plugin marketplace add scribewave/claude-plugins` and `/plugin install airgap@scribewave` do the same.

If Airgap isn't installed in `/Applications` on a Mac, set `AIRGAP_BIN` to the full path of its `scribewave-offline` binary before starting Claude Code. On Windows the plugin looks only in the per-user installer's folder (`%LOCALAPPDATA%\Scribewave Airgap`).

### Update

```bash
claude plugin marketplace update scribewave
```

```bash
claude plugin update airgap@scribewave
```

Or turn on auto-update for this marketplace under `/plugin` → Marketplaces.

### Help

Airgap's in-app help ("AI assistants") covers the settings and the editor. Questions and problems: airgap@scribewave.com.

---

This repository is generated from the Airgap source; changes made here directly are overwritten on the next publish.
