# CLST plugin list

Public plugin index for the Caelestia Shell plugin browser.

The browser fetches:

```text
https://raw.githubusercontent.com/deeadly137/CLST-plugin-list/main/plugins.json
```

## Current plugins

- [plugin-desktop-pet](https://github.com/deeadly137/plugin-desktop-pet)
- [plugin-livewallpaper](https://github.com/deeadly137/plugin-livewallpaper)

## Format

`plugins.json` contains a single `plugins` array. Each entry has:

| Field | Required | Description |
| --- | --- | --- |
| `id` | yes | Canonical plugin id, `author/name` from the plugin manifest, lowercased. |
| `name` | yes | Display name shown in the browser. |
| `author` | yes | Plugin author. |
| `version` | no | Plugin version string. |
| `description` | no | Short description shown on the card. |
| `tags` | no | Array of tag strings. |
| `repo` | yes | Git clone URL for the plugin repository. |
| `path` | no | Subdirectory inside `repo` when the plugin lives in a monorepo. |
| `image` | no | Absolute URL to a preview image. |

## Adding a plugin

1. Publish the plugin repository publicly.
2. Add one object to `plugins.json`.
3. Open a pull request.

The id in the list must match the plugin's `manifest.json`.
