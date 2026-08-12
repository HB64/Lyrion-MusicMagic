# Lyrion-MusicMagic

The complete Lyrion Music Server MusicMagic (MusicIP) plugin, forked from `dev`/public 9.2, packaged as **MusicMagicCE**, for Lyrion **9.1.x**, with three extras not in stock 9.1:

- **Path Conversion** - configure a source/destination path prefix translation between what MusicIP reports and what Lyrion expects (useful when MusicIP runs under Wine, or on a different host/container than Lyrion).
- **Configurable host** - point MusicIP at a different host instead of always `localhost`.
- **Genre filters** - exclude specific genres from MusicIP mixes.

Named MusicMagicCE (not just "MusicMagic") because Lyrion's Additional Repositories installer won't list a plugin whose name matches the built-in MusicIP plugin, even if it's uninstalled.

## How to use it

In Lyrion, go to **Settings → Plugins → Additional Repositories** and add:

```
https://raw.githubusercontent.com/HB64/Lyrion-MusicMagic/main/public.xml
```

The plugin then shows up in your plugin list as **MusicMagicCE**, to install like any other - opt-in, doesn't touch anything else on your system.

Plugin metadata: [`install.xml`](MusicMagicCE/install.xml). Repository manifest: [`public.xml`](public.xml).

## `dev/`

Auto-synced mirror of the upstream MusicMagic plugin, kept up to date automatically. Reference only, doesn't affect the plugin above.

## Credits

[HB64](https://github.com/HB64)
