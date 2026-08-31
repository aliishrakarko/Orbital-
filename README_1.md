# Orbital — Premium Android TV / Google TV Browser

Flagship glassmorphism browser designed for 10-foot UI.

## Features Implemented
- Glass capsule search with focus glow
- Quick Access shortcuts (editable, removable)
- Continue browsing history cards
- Floating translucent toolbar (auto-hide)
- WebView engine with hardware acceleration, JS, DOM storage, fullscreen video
- Tab manager overlay with large cards
- TV-optimized keyboard (D-pad navigable)
- Bookmark Room DB
- D-pad focus, scale + glow
- Remote keys: Back, DPAD, OK
- Keyboard shortcuts: Ctrl+L/T/W/R/D/F etc handled in MainActivity dispatch
- Permission dialogs, downloads via DownloadManager
- Custom error pages (offline)

## Build
1. Open in Android Studio Hedgehog+
2. Sync Gradle
3. Run on Android TV emulator API 31+ or real Google TV
   - MinSdk 21, Target 34, landscape locked, Leanback launcher
   - Banner included

## Architecture
Browser UI -> Browser Controller (ViewModel) -> Tab Manager -> WebView Manager -> Chromium WebView
StateFlow, MVVM, lifecycle-aware.

## TV UX Polish
- Focus: 150-250ms scale+glow
- Toolbar fade 300ms
- Never lose focus: fallback to search capsule
- Cursor mode: toggle in TV Experience settings (DPAD moves virtual pointer with acceleration)
- 1080p/4K scaling via dp, 60fps Compose

## Next steps to production APK
- Add adaptive icon: /res/mipmap/ic_launcher (generate with Image Asset)
- Enable Proguard
- Test YouTube fullscreen, back twice logic

Designed as: "What if a flagship browser were designed specifically for Google TV?"
