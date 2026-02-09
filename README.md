# Nuclear Option - Translation Toolkit

Create your own language mod for Nuclear Option. No programming required — just translate a JSON file and drop it in the game folder.

![BepInEx](https://img.shields.io/badge/BepInEx-5.x-blue) ![Game](https://img.shields.io/badge/Nuclear%20Option-Steam-black)

## How It Works

The `LocalizationPatch.dll` plugin automatically detects and loads any language JSON file placed alongside it. You just need to:

1. Translate the English template to your language
2. Drop the DLL + your translated file into the game's plugin folder
3. Play the game in your language

## Quick Start

### Step 1: Translate

1. Open `en_template.json` in any text editor
2. Rename it to your language code (e.g., `tr.json` for Turkish, `ja.json` for Japanese)
3. Translate the **values** (right side) — do NOT change the **keys** (left side)

Example:
```json
{
    "Play": "Jouer",
    "Settings": "Paramètres",
    "New Mission": "Nouvelle Mission"
}
```

### Step 2: Install

1. Install [BepInEx 5.x](https://github.com/BepInEx/BepInEx/releases) into your Nuclear Option game folder
2. Run the game once to generate the BepInEx folder structure
3. Copy these files into `[Game Folder]\BepInEx\plugins\`:
   - `LocalizationPatch.dll`
   - Your translated `.json` file (e.g., `tr.json`)
   - `Pretendard-Regular.otf` (only needed for non-Latin scripts like Korean, Japanese, Chinese, Russian, Thai, Arabic)

### Step 3: Play

Launch the game. Your translation will be applied automatically.

## Language Codes

Use standard ISO 639-1 codes for your file name:

| Code | Language | Code | Language |
|------|----------|------|----------|
| `ko` | Korean | `pt` | Portuguese |
| `de` | German | `it` | Italian |
| `ru` | Russian | `pl` | Polish |
| `es` | Spanish | `nl` | Dutch |
| `fr` | French | `ar` | Arabic |
| `tr` | Turkish | `th` | Thai |
| `ja` | Japanese | `vi` | Vietnamese |
| `zh` | Chinese | | |

Any 2-3 letter code works — the plugin auto-detects it.

## Translation Tips

- There are ~1,400 strings to translate
- You don't have to translate everything — untranslated strings will show in English
- Keep formatting markers like `\n` (newline) intact
- Some strings contain game-specific terms — when unsure, keep the English original
- Test in-game regularly with `F10` to see your progress

## In-Game Controls

| Key | Function |
|-----|----------|
| `F10` | Toggle translation status panel |
| `Ctrl+F10` | Reload translation file (hot-reload while game is running) |

## Font Support

- **Latin-script languages** (German, French, Spanish, Turkish, etc.): No extra font file needed
- **Non-Latin scripts** (Korean, Russian, Japanese, Chinese, Thai, Arabic): Include `Pretendard-Regular.otf` in the plugins folder

## Configuration

After first run, a config file is created at `BepInEx\config\com.yuulf.localizationpatch.cfg`:

| Setting | Default | Description |
|---------|---------|-------------|
| Language | auto | Set to `auto` to detect from JSON filename, or specify a language code manually |

## Distributing Your Translation

Once your translation is complete, you can share it with others by packaging:
- `LocalizationPatch.dll`
- Your `xx.json` translation file
- `Pretendard-Regular.otf` (if needed for your script)
- A README with install instructions

## Files Included

| File | Description |
|------|-------------|
| `LocalizationPatch.dll` | The universal translation plugin (v2.0.0) |
| `en_template.json` | English template with all ~1,400 translatable strings |
| `Pretendard-Regular.otf` | Font file for non-Latin scripts |
| `Pretendard-Bold.otf` | Bold font variant |
