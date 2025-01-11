# Android Game Decompilation Guide
## Overview
This guide documents the process of extracting an Android game from its APK file, reconstructing it in Android Studio, and analyzing its core mechanics. The end result is a fully functional game with understood gameplay logic.

## Decompilation Process
1. Use [Java Decompilers](http://www.javadecompilers.com/apk) to extract the APK
2. Extract the decompiled output containing `sources` and `resources` directories

## Project Setup

### Core Components
- **Game Logic**: Copy game and menu activities from `\sources\com\classy\survivegame`
- **Configuration**: Import `AndroidManifest.xml` from `\resources`
  - Add and fix the activities in the manifest

### Resource Integration

1. **UI Elements**
   - Layout files: `\resources\res\layout`
   - Drawable assets: `\resources\res\drawable`

2. **String Resources**
   - Import URL string from `\resources\res\values`
   - Add to project's `strings.xml`
   - Note: Remove invisible character from URL string
  
## Game Mechanics

### Core Logic
The game operates on a sequence-based system determined by a player ID:

```
ID -> Integer Conversion -> Direction Mapping
```

### Direction Mapping
Each character in the ID translates to a movement:
- Modulo 4 (`% 4`) determines direction:
  - 0: Left  (`game_BTN_left`)
  - 1: Right (`game_BTN_right`)
  - 2: Up    (`game_BTN_up`)
  - 3: Down  (`game_BTN_down`)

### Victory Condition
Successful completion displays:
```
Survived in Pennsylvania.
```

## Development Outcomes
- Successfully rebuilt game in Android Studio
- Decoded core gameplay mechanics
- Achieved functional gameplay with original features
- Gained insights into game's architectural design
