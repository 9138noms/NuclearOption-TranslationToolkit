# Nuclear Option — Translation Toolkit v3.0.2

Make your own Nuclear Option language mod. No programming needed — just edit a JSON.

## What's in this zip

| File | Purpose |
|------|---------|
| `LocalizationPatch.dll` | The translation plugin (drop into BepInEx/plugins) |
| `LocalizationPatchDropdown.dll` | Editor/dropdown translation addon |
| `en_template.json` | Template with **2,841 source strings** — copy, rename to your language code (e.g. `cs.json`), translate the right-hand values |
| `Pretendard-Regular.otf` / `Pretendard-Bold.otf` | Korean / Hangul + Hanja font |
| `Exo2-Regular.ttf` | Latin Extended-A/B (Czech, Polish, German umlauts, Turkish, Vietnamese) |
| `WDXLLubrifontSC-Regular.ttf` | Cyrillic (Russian, Ukrainian, Belarusian, Serbian, Bulgarian) |

## What's new in v3.0.2

- `en_template.json` regenerated from the **v3.0.1** Korean translation — **+141 source strings** vs v3.0.0/v3.0.1 toolkits, including ALL-CAPS variants used on the main menu (`SINGLEPLAYER`, `MULTIPLAYER`, `SETTINGS`, `ENCYCLOPEDIA`, `BACK`, `CONFIRM`, `CHANGELOG`, `EXIT`, `CONTROLS`, `FILTERS`, …) plus new strings introduced in 0.33.x (Argus / Cursor frigates, Alkyon AB-4, ATGM/AAA/MANPADS emplacements, Tactical Ballistic Missiles, mission editor multi-select, Camera Chase view).
- Earlier toolkits exported a 2,700-key template that silently dropped the ALL-CAPS variants — translators starting from those releases had main-menu buttons stay English even after a full translation pass.
- `LocalizationPatch.dll` unchanged from v3.0.1.

## Quick start

1. Install [BepInEx 5.x](https://github.com/BepInEx/BepInEx/releases) into your Nuclear Option install.
2. Launch the game once, then quit.
3. Create `BepInEx/plugins/LocalizationPatch/` and copy in:
   - `LocalizationPatch.dll`
   - `LocalizationPatchDropdown.dll`
   - your translated JSON (e.g. `cs.json`, `pl.json`)
   - the font file your language needs (see table below)
4. Create `BepInEx/config/com.noms.localizationpatch.cfg`:
   ```
   [General]
   Language = cs
   ```
   Or leave `Language = auto` — the plugin auto-detects 2- or 3-letter `<code>.json` files in the plugin folder. For longer codes (e.g. `zh_tw`, `pt_br`) set the value manually.
5. Launch the game. `F10` toggles the debug overlay; `Ctrl+F10` hot-reloads the JSON while you translate.

## Which font should I ship?

The plugin scans the plugin folder for any `.ttf` / `.otf` and picks the first one alphabetically. Drop in only the font your language needs.

| Script | Languages | Font in this zip |
|---|---|---|
| Latin (basic) | English | none — game default works |
| Latin Extended | Czech, Polish, German, Turkish, Vietnamese, Hungarian, Romanian | `Exo2-Regular.ttf` |
| Cyrillic | Russian, Ukrainian, Belarusian, Serbian, Bulgarian | `WDXLLubrifontSC-Regular.ttf` |
| Hangul + Korean Hanja | Korean | `Pretendard-Regular.otf` |
| Japanese (Kana + Kanji) | Japanese | Pretendard works for most kanji; consider Noto Sans JP for full coverage |
| **Traditional Chinese** | zh_tw | **Pretendard does NOT cover Traditional Chinese** — bring [Noto Sans TC](https://fonts.google.com/noto/specimen/Noto+Sans+TC) |
| **Simplified Chinese** | zh_cn | Same — bring [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC) |
| Thai | Thai | Bring a Thai font (e.g. Noto Sans Thai) |
| Arabic | Arabic | Bring an Arabic font (e.g. Noto Sans Arabic) |

> Tip: filename matters because of alphabetical pick order. If you ship two fonts in the same folder, the alphabetically-first one wins. Rename if needed.

## Want to publish your patch?

Open a PR against this repo or post your translated JSON as an issue — I'll help package and link to it from the main installer. Or ship it yourself on GitHub / Nexus.

## Existing translations (9 languages)

Korean · Russian · Ukrainian · Belarusian · German · Spanish · French · Portuguese · Norwegian
(Traditional Chinese in progress.)

One-click installer for the released ones:
https://github.com/9138noms/NuclearOption-LocalizationInstaller/releases/latest
