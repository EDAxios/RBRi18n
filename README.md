**English** | [中文](README_zh.md)

# RBRi18n

A lightweight internationalization (i18n) plugin for **Richard Burns Rally (RBR)**. It hooks the game's text rendering to load translations and render CJK fonts with proper scaling.

![preview](preview.png)

## Features

- Multi-language support via `Language=zh|en` setting
- Per-plugin translation files (`RichardBurnsRally.zh.json`, `Weather.zh.json`, etc.)
- Configurable font family and sizes
- Resolution-aware font scaling (based on RBR's native 640×480)
- Widescreen/ultrawide centering support

## Installation

1. Copy `RBRi18n.dll` to your RBR `Plugins` directory
2. Create a `RBRi18n` folder in your RBR root directory
3. Place translation files (`.zh.json`, `.en.json`, etc.) in the `RBRi18n` folder

## Configuration

Add to `RichardBurnsRally.ini` in your game root:

```ini
[RBRi18n]
Language=zh

; Optional font settings (defaults shown)
FontFamily=SimHei
FontSizeSmall=7
FontSizeBig=8
FontSizeDebug=6
FontSizeHeading=8
FontSizeMenu=8
```

## Translation Files

Translation files use JSON format. Files are named `{source}.{lang}.json`:

```
RBRi18n/
├── RichardBurnsRally.zh.json  # Base game (Chinese)
├── Weather.zh.json            # Weather translations (Chinese)
├── Options.zh.json            # Options menu (Chinese)
├── TuneCar.zh.json            # Car tuning (Chinese)
└── ...
```

Example translation file:

```json
{
  "Options": "选项",
  "Quick Rally": "快速拉力赛"
}
```

All files matching `*.{lang}.json` are loaded and merged.

## Build from Source

### Prerequisites

- Windows
- Visual Studio with C++ tools (v143 toolset)
- Windows SDK 10.0

### Build

1. Open `RBRi18n.vcxproj` in Visual Studio (or add to a solution)
2. Select **Release | Win32**
3. Build

Output: `Release/RBRi18n.dll`

## Credits

- RBR API memory addresses and structs derived from [RBRAPI by MIKA-N](https://github.com/mika-n) (MIT-like license, see `RBR/RBRAPI.h`)
- [MinHook](https://github.com/TsudaKageworthy/minhook) for function hooking
- [nlohmann/json](https://github.com/nlohmann/json) for JSON parsing

## License

[MIT](LICENSE)
