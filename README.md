# StartPad

A lightweight, native **macOS-style fullscreen application launcher** built as a [Windhawk](https://windhawk.net/) mod to replace the default Windows 11 Start menu.

Inspired by Apple’s macOS Launchpad, **StartPad** provides an intuitive, distraction-free environment to browse, organize, and launch all your installed software with fluid animations and extensive customization.

---

## ✨ Features

### 🚀 Flawless Start Menu Integration
- **Direct Native Hook:** Intercepts Explorer's internal `ShowStartView` trigger directly in `twinui.pcshell.dll`, ensuring the native Windows Start menu never flickers or accidentally opens.
- **Universal Triggers:** Opens seamlessly via:
  - The **Windows Key**
  - **Ctrl + Esc**
  - Left-clicking the taskbar **Start button** (on any monitor).

---

### 🎨 Visuals & Theming
- **Adaptive Blurred Backdrop:** Takes an instant snapshot of your desktop and applies an adjustable multi-pass blur (Off, Light, Medium, or Strong) with custom tint darkness.
- **Multiple Visual Styles:**
  - **macOS Launchpad:** Clean glass search pill with rounded squircle folder containers.
  - **Windows 11 Fluent:** Acrylic search bar with an accent-colored bottom indicator.
- **Automatic System Theming:** Matches your active Windows light/dark theme and pulls your personalization accent color dynamically.
- **Fluid Spring Animations:** Smooth physics-based page sliding, folder opening/closing from center screen, and layered fade transitions.

---

### 🗂️ Grid Layout & Smart Scaling
- **Customizable Grid:** Configure any layout from 4 to 12 columns and 3 to 8 rows per page.
- **Intelligent Icon Sizing:** Scales icons smoothly from 50% to 150%, automatically pulling crisp, high-resolution assets.
- **Smart Legacy Icon Cleanup:** Automatically detects and strips the awkward gray square borders and empty padding often added by Windows to older Win32 icons (e.g., 7-Zip), upscaling the actual icon smoothly with bilinear interpolation.
- **Compact Selection Cards:** Features a sleek, semitransparent rounded card that wraps both the app icon and label, animating smoothly with an interactive title zoom on hover.

---

### 🔍 Instant Search & Quick Actions
- **Type-to-Search:** Simply start typing anytime StartPad is open—no need to click into the search box first.
- **Always-Active Focus Caret:** Clear visual cue in the search bar indicating ready-to-type status.
- **Deep Search Toggle:** Option to search across all applications, including hidden ones, directly from the search bar menu.
- **Instant Launch:** Press **Enter** to open the highlighted result, or **Ctrl + Shift + Enter** to run directly as administrator.

---

### 📁 Folders & Organization
- **Easy Drag-and-Drop:** Drag one application icon over another to create a folder instantly, or drag apps in/out to reorganize your grid.
- **"Create Folder" Selection Mode:** Select multiple apps using checkmarks directly from the search bar menu to quickly bundle them into a new folder without dragging.
- **Center-Out Folder Expansion:** Folders open directly from the center of the screen with smooth easing and inline name editing (**F2** or clicking the title).
- **Edit Hidden Apps Mode:** Easily hide background tools, updaters, or unwanted shortcuts via the options menu or directly through right-click.
- **Automatic Uninstaller Filtering:** Automatically cleans up shortcuts pointing to uninstallers (`unins000.exe`, `uninstall.exe`, etc.) to keep your launcher clutter-free.

---

### ⌨️ Navigation & Controls
- **Smart 2D Arrow Navigation:** Move smoothly across rows and columns using arrow keys; navigating past the outer edge seamlessly flips to the previous or next page.
- **Mouse & Touchpad Friendly:** Click-and-drag swipe support, mouse wheel page turning, and clickable bottom pagination dots.
- **Integrated Power Menu:** A dedicated power button aligned with the grid dots offers quick access to **Lock**, **Sign out**, **Sleep**, **Shut down**, and **Restart**.
- **Safe Click Dismissal:** Clicking outside open context menus dismisses only the menu, preventing accidental launcher closures.
- **Multilingual Support:** Localized interface strings for English, Spanish, French, German, Italian, Portuguese, Russian, Chinese, Japanese, and Korean.

---

## 🛠️ Installation

1. Install [Windhawk](https://windhawk.net/) if you haven't already.
2. Open Windhawk and navigate to the **Mods** tab.
3. Click **Create Local Mod** (or paste into your mod list).
4. Paste the contents of `winlaunchpad.cpp` and click **Compile**.
5. Enable the mod and customize your preferences via the **Settings** tab.