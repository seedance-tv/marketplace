# Seedance for Codex

The Codex plugin marketplace for [Seedance](https://www.seedance.tv). It ships one plugin, [`seedance`](plugins/seedance),
which connects Codex to your Seedance canvas so you can make images, videos, music and edits from a Codex task.

| Install name | Display name | MCP server | Version |
| --- | --- | --- | --- |
| `seedance` | Seedance | `https://www.seedance.tv/mcp` | `1.0.0` |

The plugin is a remote HTTP MCP server. It holds no client ID, keys or local server: Codex registers itself and
signs you in through the server's OAuth metadata, and every person signs in with their own Seedance account.

## Install

### Let Codex do it

Paste this into a Codex task:

```text
Install the Seedance plugin so I can create images and videos here.

1. Add the marketplace: run `codex plugin marketplace add seedance-tv/marketplace --ref main`
2. Install the plugin: run `codex plugin add seedance@seedance`
3. In a new task, sign in to my Seedance account when asked

Tell me when it's ready to start creating.
```

### Or run it yourself

```bash
codex plugin marketplace add seedance-tv/marketplace --ref main
codex plugin add seedance@seedance
```

Then start a new Codex task and sign in to Seedance when Codex asks (or from the MCP connections list). The
repository is public, so no GitHub sign-in is needed.

## Use

Ask in plain words, for example:

- "Show my Seedance projects"
- "Make an 8-second product video from this photo with Seedance"
- "Write a 30-second story and turn it into a multi-shot video on my Seedance canvas"

Only starting a generation spends credits. Codex tells you what a run costs before it starts, and failed runs are
refunded automatically. You can see and disconnect connected apps at
[seedance.tv/connected-apps](https://www.seedance.tv/connected-apps).

## Update

```bash
codex plugin marketplace upgrade seedance
codex plugin add seedance@seedance
```

Start a new Codex task afterwards. Before sign-in the server answers `401` with `WWW-Authenticate: Bearer`, and both
OAuth well-known endpoints answer `200`; that is expected.

## Uninstall

```bash
codex plugin remove seedance
codex plugin marketplace remove seedance
```
