# StartPad

![StartPad Preview](https://raw.githubusercontent.com/frankh93/StartPad/main/preview.png)

A native, macOS Launchpad-style fullscreen application launcher for Windows 11 built as a [Windhawk](https://windhawk.net/) mod. **StartPad** replaces the default Windows Start menu with a fluid, paginated app grid featuring drag-and-drop organization, interactive folders, customizable visual styling, and instant search.

---

## ✨ Features

### 🚀 Seamless Start Replacement
- **Native Hooking**: Intercepts Explorer's internal `XamlLauncher::ShowStartView` symbol directly in `twinui.pcshell.dll`, guaranteeing that the original Windows 11 Start menu never flickers or opens behind it.
- **Universal Triggers**: Opens reliably with:
  - The **Windows Key**
  - **Ctrl + Esc**
  - Left-clicking the taskbar **Start button** on any monitor.
- **Smart Click Dismissal**: Clicking outside open popup menus (such as the context menu, power menu, or options menu) safely dismisses the menu without accidentally closing the launcher.

### 📄 Paginated Grid & Fluid Physics
- **Horizontal Pagination**: Browse installed software across clean pages rather than scrolling through an endless vertical list.
- **Multiple Ways to Flip Pages**:
  - Click and drag anywhere to swipe.
  - Scroll the mouse wheel (vertical or horizontal tilt).
  - Click the bottom pagination dots.
  - Use **Page Up** / **Page Down** or navigate across grid edges with the arrow keys.
- **Predictable 2D Keyboard Navigation**: Seamlessly navigate row-by-row and column-by-column with the **Arrow keys** or **Tab**. Moving past the leftmost or rightmost column on a row automatically turns to the previous or next page.

### 📁 Drag-and-Drop & Folder Management
- **Drag-and-Drop Reordering**: **Click and hold** (~320 ms) any icon to pick it up, drag it to any grid slot, or hold it near the left/right screen edges to move it between pages.
- **Create Folders**:
  - **Drag & Drop**: Drag an app onto another app icon to automatically bundle them into a folder.
  - **Menu Selection Mode**: Choose **Create folder** from the search bar menu, click to select multiple apps with checkmarks, and click the **Done (`✓`)** button (or press **Enter**) to generate a folder.
- **Center-Out Folder Expansion**: Folders expand smoothly from the center of the screen with eased spring transitions.
- **Inline Renaming**: When inside a folder, press **F2** or click the header title directly to rename it. Pressing **F2** while selecting a folder on the main grid also opens it directly in rename mode.
- **Ungrouping & Removal**: Drag an icon outside an open folder window to return it to the main grid, or right-click any folder and select **Ungroup folder**.
- **Persistent Storage**: All custom icon arrangements, folders, and visibility rules are saved automatically per user profile using Windhawk's native mod storage API (`Wh_GetModStoragePath`).

### 🔍 Instant Search & Application Control
- **Type-to-Search**: Start typing immediately when StartPad opens—no need to click the search bar first.
- **Focus Indicator**: An always-visible blinking cursor shows active search focus, even on an empty query.
- **Search in Hidden Apps**: A toggleable option inside the search bar menu allows search queries to find and launch apps that you have hidden from the main grid (displayed with normal opacity in search results).
- **Run as Administrator**: Launch any highlighted application with elevated privileges using **Ctrl + Shift + Enter** or via the right-click menu.
- **App Context Menu**: Right-click any app icon to **Open**, **Run as administrator**, **Open file location**, or **Hide**.

### 🛠️ App Visibility & Maintenance
- **Hide Distracting Apps**: Right-click any shortcut and choose **Hide** to tuck away utilities, background updaters, or unwanted tools.
- **Batch Visibility Editor**: Access **Edit hidden apps** from the search menu to toggle visibility badges across all installed programs simultaneously.
- **Automatic Uninstaller Filtering**: Cleans out junk shortcuts pointing to `unins000.exe`, `uninstall.exe`, and related maintenance links automatically.
- **Reset Layout**: Restore the default alphabetical grid at any time through the options menu.

### 🎨 Visuals, Theming & Legacy Fixes
- **Adaptive Blurred Backdrop**: Freezes a multi-pass blurred screenshot of your current desktop with adjustable blur strengths (Off, Light, Medium, Strong) and darkness tinting.
- **Two Visual Styles**:
  - **MacOS Style**: Clean glass search pill with squircle folder sheets.
  - **Windows 11 Fluent**: Acrylic-inspired search box with active system accent striping.
- **Legacy Icon Border Cleanup**: Automatically detects low-resolution Win32 executables (such as 7-Zip) that Windows normally displays with an awkward 1px gray border box and empty padding, stripping the frame and smoothly upscaling the icon content using bilinear interpolation.
- **Selection Card Styling**: Highlighted icons feature a semitransparent card enclosing both the icon and label, accompanied by smooth font enlargement on hover.
- **Integrated Power Menu**: Bottom-right power button aligned with the pagination dots for quick access to **Lock**, **Sign out**, **Sleep**, **Shut down**, and **Restart**.
- **Multilingual Support**: Fully localized interface strings for English, Spanish, French, German, Italian, Portuguese, Russian, Chinese, Japanese, and Korean.

---

## ⚖️ How StartPad Differs from Fullscreen Start

Both **StartPad** and Rafael Mendes's **[fullscreen-start](https://github.com/RafaelMendes1407)** hook Explorer's `XamlLauncher::ShowStartView` to replace the Start menu with a fullscreen grid. Because both mods intercept the same low-level function, **they cannot be enabled simultaneously**.

| Feature | StartPad | Fullscreen Start (`fullscreen-start`) |
| :--- | :--- | :--- |
| **Grid Architecture** | **Horizontal Pages** with pagination dots and page-swipe physics | **Single Vertical Scrolling** list |
| **App Organization** | **Folders** (drag-and-drop & multi-select creation, center-out animation, renaming) | Flat alphabetical list |
| **Custom Positioning** | **Drag-and-Drop** persistent layout reordering | Automatic alphabetical sort |
| **Hiding Apps** | Right-click hiding, batch edit mode, search in hidden apps | Fixed uninstaller exclusions |
| **Rendering Backend** | High-performance GDI/AlphaBlend DIB pipeline | Direct2D / DirectWrite |
| **Visual Styles** | **macOS Launchpad** and **Windows 11 Fluent** styles | macOS-inspired acrylic styling |
| **Quick Actions** | Integrated power menu (Sleep, Shut Down, Restart, Lock) | Standard window dismissal |
| **Context Menus** | Run as administrator, Open file location, Hide, Ungroup | Left-click launch only |

---

## ⌨️ Controls & Shortcut Cheat Sheet

| Input | Action |
| :--- | :--- |
| **Windows Key / Ctrl + Esc** | Open / Close StartPad |
| **Type alphanumeric keys** | Search applications |
| **Backspace / Ctrl + Backspace** | Delete character / Delete previous word |
| **Arrow Keys / Tab** | Navigate icon selection (flips pages at edges) |
| **Enter** | Launch selected app / Confirm search result |
| **Ctrl + Shift + Enter** | Run selected app as Administrator |
| **Click and Hold (~320ms)** | Pick up app or folder to drag and reorder |
| **F2** | Rename selected folder |
| **Esc** | Clear search query $\rightarrow$ Exit editing mode $\rightarrow$ Close folder $\rightarrow$ Close StartPad |
| **Mouse Wheel / Page Up / Page Down** | Switch pages |
| **Click outside grid** | Close StartPad |

---

## 🔧 Installation

1. Install **[Windhawk](https://windhawk.net/)** if you haven't already.
2. Open the Windhawk application and go to the **Mods** tab.
3. If installing locally:
   - Click **Create Local Mod** in the top-right corner.
   - Replace the template code with the contents of `startpad.wh.cpp`.
   - Click **Compile**.
4. Enable the mod and configure your desired grid columns, rows, icon sizes, and background blur in the **Settings** tab.

---

## 📄 Credits & License

- Core Start view interception techniques (`XamlLauncher::ShowStartView` hook, `kShowMethodKeyboard` / `kShowFlagKeyboard` flag detection, and secondary Explorer process filtering) adapted from **[Fullscreen Start (Launchpad style)](https://github.com/RafaelMendes1407)** by **Rafael Mendes**, licensed under the MIT License (Copyright (c) Rafael Mendes).
- Developed by **Frankh93**.
- Released under the **[MIT License](LICENSE)**.
