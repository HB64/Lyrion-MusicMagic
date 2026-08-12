# Lyrion-MusicMagic

A fork of Lyrion Music Server's built-in `Slim::Plugin::MusicMagic` (MusicIP) plugin, for Lyrion **9.1.x**.

## What this is

Two improvements to the MusicMagic plugin were contributed upstream from this project into Lyrion's `public/9.2` branch:

- **Path Conversion** ([PR #1629](https://github.com/LMS-Community/slimserver/pull/1629), merged) - lets you configure a source/destination path prefix translation between what MusicIP reports and what Lyrion expects. Useful when MusicIP runs under Wine (which reports Windows-style paths), or when MusicIP runs on a different host/container than Lyrion with a different mount layout.
- **Genre-filter bugfixes** ([PR #1633](https://github.com/LMS-Community/slimserver/pull/1633), pending review) - fixes a crash when `mix_genre_filter` holds a non-array value, and fixes an inverted genre-exclusion condition in `getMix()` that caused every mix to return zero songs unless a genre exclusion filter was explicitly configured.

The Lyrion maintainers only accept bugfixes into 9.1.x, not new features, so Path Conversion can't be backported into core 9.1. This repo carries both changes as a standalone fork of the plugin files, for anyone running Lyrion 9.1.x who wants them without upgrading to 9.2.

## How to use it

This is currently a **manual file replacement**, not an installable plugin via Lyrion's Plugin Manager. Copy the files under `Slim/Plugin/MusicMagic/` in this repo over the same-named files in your Lyrion 9.1.x installation (back up the originals first), then restart the server.

An `install.xml` is included for reference/metadata, but turning this into something installable directly through Lyrion's Plugin Manager would require repackaging it under a separate `Plugins::` namespace (since it currently shares the same package names as the built-in plugin it replaces) - not done yet.

## `dev/`

An auto-synced, read-only mirror of `Slim/Plugin/MusicMagic` from [LMS-Community/slimserver](https://github.com/LMS-Community/slimserver)'s `public/9.2` branch, updated weekly (or on demand) by [`.github/workflows/sync-upstream-musicmagic.yml`](.github/workflows/sync-upstream-musicmagic.yml). It's for reference only - changes there are never merged automatically into the plugin files above; a pull request is opened instead so any relevant upstream change can be reviewed and ported in manually.

## Credits

Path Conversion and the genre-filter fixes were developed and upstreamed by [HB64](https://github.com/HB64).
