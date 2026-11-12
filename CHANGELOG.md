# Changelog

All notable changes to the `vscode-rn-asset-lens` extension will be documented in this file.

## [1.1.0] - 2026-11-12

### Added
- **Find Duplicate Images (`rn-asset-lens.findDuplicateImages`)**:
  - Scans workspace assets using MD5 hashing to detect redundant and duplicate image files.
  - Interactive report panel with thumbnail preview, wasted storage calculation, "Find in Code", "Reveal", and "Delete" actions.
- **Audit Image Bit Depth & Color Space (`rn-asset-lens.auditColorDepth`)**:
  - Inspects PNG, JPEG, and WebP byte headers for bit depth and color channels.
  - Detects CMYK JPEGs that cause crashes / rendering failures on React Native Android.
  - Detects 16-bit PNGs/JPEGs that cause memory spikes and decoding errors on mobile devices.
  - Displays color space and bit depth badges in image Hover Tooltip.
  - Real-time diagnostic warnings when requiring CMYK or 16-bit images in code.
- **ESM Import Support**:
  - Supports both `require('./...')` and `import img from './...'` for hover previews, gutter icons, and path diagnostics.

## [1.0.0] - 2026-11-06

### Initial Release & Gutter Preview
- **Editor Gutter Thumbnail Preview**:
  - Automatically displays image thumbnail icons right in the editor margin (gutter next to line numbers) for `require('./assets/image.webp')` and `<IconComponent name="..." />`.
  - Hovering directly over the gutter icon also shows the quick preview tooltip.
- **Offline Icon Explorer & QuickPick**:
  - Over 15,000+ vector icons across 15 popular families (Ionicons, Material Community, Material Icons, Feather, Lucide, FontAwesome, AntDesign, Octicons, Entypo, etc.).
  - Webview panel with real-time fuzzy search, family tabs, live size & color customization.
  - Keyboard QuickPick shortcut (`Cmd+Shift+I` / `Cmd+Alt+I`).
  - Automatic JSX component generation & smart import merging (Expo `@expo/vector-icons`, `react-native-vector-icons`, `lucide-react-native`).
- **Image Hover Tooltip Preview**:
  - Instant preview for `require('./path/to/image.png')` and `source={{ uri: 'https://...' }}`.
  - Image dimensions (Width × Height px) and formatted file size (KB/MB).
  - React Native density scale variants detection (`@1x`, `@2x`, `@3x`) with comparative table.
  - Quick action links: Open File, Reveal in Finder/Explorer.
- **Asset Path Diagnostics & QuickFix**:
  - Real-time warning on missing or mistyped asset paths.
  - QuickFix (`Cmd+.`) suggests similar existing files in the directory.
- **IntelliSense & Definition Provider**:
  - `Cmd+Click` on `require('./assets/...')` jumps directly to the asset.
  - Auto-completion for asset paths inside `require('...')`.
  - Auto-completion for icon names inside `<IconComponent name="..." />`.
- **Status Bar Integration**:
  - Convenient status bar quick menu item.
