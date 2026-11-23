# Block Puzzle (Android, Kotlin + Jetpack Compose)

8x8 block puzzle (Block Blast style). Only ad: a single App Open Ad at startup.

## Open & run
1. Open this folder in Android Studio (Hedgehog or newer, JDK 17). Let Gradle sync (Studio will offer to create the Gradle wrapper; Gradle 8.2+).
2. Run on a device/emulator with Google Play services.

## Project structure
```
app/src/main/java/com/example/blockpuzzle/
  MainActivity.kt          screen switching (Splash -> Menu -> Game / Settings)
  BlockPuzzleApp.kt        AdMob init + early App Open ad load
  ads/AppOpenAdManager.kt  load + show-once App Open ad, AdConfig (unit ID)
  data/SettingsRepository  DataStore: highScore, selectedTheme, soundEnabled, vibrationEnabled
  game/Shapes.kt           25 piece shapes as Boolean grids
  game/GameEngine.kt       placement, line clears, fair piece generation
  game/GameViewModel.kt    state, scoring, combo, game over
  game/SoundManager.kt     ToneGenerator beeps
  ui/                      Theme (5 themes), Splash, Menu, Game, Settings, dialogs
```

## Before publishing (TODOs)
- `AndroidManifest.xml`: replace the test AdMob **App ID** (`ca-app-pub-3940256099942544~3347511713`).
- `ads/AppOpenAdManager.kt` (`AdConfig`): replace the test **App Open ad unit ID**.
- `app/build.gradle.kts`: change `applicationId`, set up release signing, bump `versionCode`.
- Replace the placeholder vector icon (`res/drawable/ic_launcher.xml`) with a proper adaptive icon.
- Add a privacy policy and complete Play Console Data safety + Ads declarations.
