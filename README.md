# Kaltura Moodle Plugin Mirror

This repository mirrors a single plugin split from the upstream
[kaltura/moodle_plugin](https://github.com/kaltura/moodle_plugin) monorepo.

## Branch structure

| Branch | Contents |
|--------|----------|
| `main` | Only this README and the GitHub Actions workflow |
| `MOODLE_405_STABLE` | The plugin code, kept in sync with upstream |

## How it works

A workflow (`.github/workflows/sync-upstream.yml`) runs automatically every
Monday at 06:00 UTC. It can also be triggered manually from the **Actions** tab
in GitHub.

When it runs it:

1. Clones the `MOODLE_405_STABLE` branch of
   `github.com/kaltura/moodle_plugin`.
2. Uses `git subtree split` to extract only the subdirectory for this plugin.
3. Force-pushes the resulting commit to the `MOODLE_405_STABLE` branch of
   this repository.

No code lives on `main` — all plugin code is on `MOODLE_405_STABLE`.
