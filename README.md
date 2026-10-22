# CLST plugin list

Public plugin index for the Caelestia Shell plugin browser.

The browser fetches:

```text
https://raw.githubusercontent.com/deeadly137/CLST-plugin-list/main/plugins.json
```

## Current plugins

- [plugin-desktop-pet](https://github.com/deeadly137/plugin-desktop-pet)
- [plugin-livewallpaper](https://github.com/deeadly137/plugin-livewallpaper)
- [plugin-nebula-widgets](https://github.com/deeadly137/plugin-nebula-widgets)

## Format

`plugins.json` is only a list of repositories. Each entry has exactly two fields:

| Field | Required | Description |
| --- | --- | --- |
| `id` | yes | Canonical plugin id, `author/name` from the plugin manifest, lowercased. |
| `repo` | yes | Git clone URL for the plugin repository. |

```json
{
    "schema": 2,
    "plugins": [
        {
            "id": "deeadly137/desktoppet",
            "repo": "https://github.com/deeadly137/plugin-desktop-pet.git"
        }
    ]
}
```

The browser reads the repository's `manifest.json` to get the display metadata: `name`, `author`,
`version`, `description`, `tags`, `icon`, `banner`, and `logo`. `banner` and `logo` may be relative
paths inside the repository or absolute URLs; relative paths are resolved against the manifest.
`image` is still accepted as a legacy alias for `banner`.

The id in the list must match the id derived from the repository's manifest (`author/name`,
lowercased). If it does not match, the browser treats the repository as a different plugin and uses
the id declared by the manifest.

## Adding a plugin

1. Publish the plugin repository publicly with a valid `manifest.json` at its root.
2. Add one `{ "id", "repo" }` object to `plugins.json`.
3. Open a pull request.
