# Agent Instructions & Integration Guide for Super-Keyboard

> [!IMPORTANT]
> This guide is specifically written for AI Coding Agents (Antigravity, Claude Code, Cursor, GitHub Copilot, OpenCode, Aider, Devin, etc.) tasked with inspecting, installing, extending, or troubleshooting the **Super-Keyboard** Kanata configuration.

---

## 1. Repository Overview

**Super-Keyboard** is a battle-tested, cross-platform ergonomic keyboard configuration powered by [Kanata](https://github.com/jtroo/kanata) (v1.7.0+ / tested on v1.12.0+). It transforms standard ANSI/ISO keyboards into a 3-layer ergonomic powerhouse:

1. **Base Layer (Home-Row Mods)**:
   - Left hand: `A` (Win / Cmd), `S` (Alt), `D` (Shift), `F` (Ctrl)
   - Right hand: `J` (Ctrl), `K` (Shift), `L` (Alt), `;` (Win / Cmd)
   - Spacebar: Tap for `Space`, Hold to activate **Layer 1**
   - CapsLock: Tap for `Escape`, Hold for `CapsLock`
2. **Layer 1 (Vim Navigation, Numbers & Dual-Action Home-Row Mods)**:
   - Activated momentarily while holding **`Spacebar`**.
   - Left hand numbers: `A` (1), `S` (2), `D` (3), `F` (4), `G` (5), `Q` (9), `W` (0).
   - Left hand dual-action home-row mods on hold: `A` (Win), `S` (Alt), `D` (Shift), `F` (Ctrl).
   - Right hand Vim navigation: `H` (Left), `J` (Down), `K` (Up), `L` (Right).
   - Navigation extremes: `T` (Home), `Y` (End), `E` (Escape).
   - Function row: `1`–`0` $\rightarrow$ `F1`–`F10`, `[` $\rightarrow$ `F11`, `'` $\rightarrow$ `F12`.
   - One-tap clipboard: `C` (Ctrl+C), `V` (Ctrl+V), `B` (Backspace), `N` (Delete), `M` (Ctrl+C).
   - Switch to Mouse Mode: Tap **`;`** while holding `Space`.
3. **Layer 2 (Hands-Free Modal Mouse Controller)**:
   - Toggled via `Space + ;`. Persistent—hands rest freely with zero buttons held.
   - Cursor movement: Inverted-T on left hand: `E` (Up), `S` (Left), `D` (Down), `F` (Right).
   - Mouse buttons: Right hand: `J` (Left Click), `K` (Right Click), `H` (Middle Click).
   - Scroll wheel: `W` (Wheel Down), `R` (Wheel Up).
   - Clipboard: `C` (Copy), `V` (Paste), `B` (Backspace), `N` (Delete), `M` (Copy).
   - Exit back to Base: Tap **`;`**.

---

## 2. File Index

| File | Purpose |
| :--- | :--- |
| [`config.kbd`](file:///E:/kanata/.config/kanata/config.kbd) | **Active Production Configuration**. Standard 3-layer layout with single Spacebar-Fn trigger. |
| [`config_dual_fn.kbd`](file:///E:/kanata/.config/kanata/config_dual_fn.kbd) | **Alternate Layout**. Includes dual triggers for Layer 3 (hold `x` or hold `.`). |
| [`assets/`](file:///E:/kanata/.config/kanata/assets) | High-resolution 2x Retina PNGs and XML-compliant SVGs for all layer visualizers. |
| [`README.md`](file:///E:/kanata/.config/kanata/README.md) | User-facing documentation, quickstart, and OS installation guides. |

---

## 3. Agent Operating Protocol (Applying Config to a User System)

When a user asks you to set up Kanata or install this configuration on their machine, follow this deterministic procedure:

### Step 1: Detect OS & Target Config Path
Identify the user's OS and copy `config.kbd` to their canonical configuration directory:
* **Windows**:
  - Target Path: `"$HOME\.config\kanata\config.kbd"` or `"$env:USERPROFILE\.config\kanata\config.kbd"`
  - System Binary: Check if `kanata.exe` is in `PATH` or located in `C:\kanata` / `E:\kanata`.
* **macOS**:
  - Target Path: `"~/.config/kanata/config.kbd"`
  - Requires Karabiner-Elements VirtualHIDDevice driver (`brew install --cask karabiner-elements`).
* **Linux**:
  - Target Path: `"~/.config/kanata/config.kbd"` (or `"/etc/kanata/kanata.kbd"` for system daemon).
  - User must belong to `input` and `uinput` groups.

### Step 2: ALWAYS Validate Syntax Before Running
Never start or reload Kanata without verifying the configuration:
```bash
# Windows / macOS / Linux
kanata --check -c <path_to_config.kbd>
```
Confirm the output states `[INFO] config file is valid` with exit code `0`.

### Step 3: Service Reload Protocol

#### 🪟 Windows (Scheduled Task or Background Process)
If Kanata runs via Windows Task Scheduler (`run kanata`):
```powershell
# 1. Stop existing process (critical: stopping task alone might leave child kanata.exe running)
Stop-ScheduledTask -TaskName "run kanata" -ErrorAction SilentlyContinue
Stop-Process -Name kanata -Force -ErrorAction SilentlyContinue
Start-Sleep -Milliseconds 500

# 2. Restart task
Start-ScheduledTask -TaskName "run kanata"
Get-ScheduledTask -TaskName "run kanata"
Get-Process -Name "kanata*" -ErrorAction SilentlyContinue
```

#### 🍏 macOS (Homebrew or launchd)
```bash
# If using brew services:
brew services restart kanata

# If running directly via sudo:
sudo pkill kanata || true
sudo kanata -c ~/.config/kanata/config.kbd &
```

#### 🐧 Linux (systemd user unit)
```bash
systemctl --user restart kanata.service
```

---

## 4. How to Extend & Customize the Configuration

When a user requests custom keys, shortcuts, or additional layers:

### 1. Adding a New Alias
Define aliases under `(defalias ...)`:
```lisp
(defalias
  ;; Format: name (action)
  my-shortcut C-A-t          ;; Ctrl + Alt + T (open terminal)
  my-macro    (macro g i t spc s t a t u s ret)
)
```

### 2. Adding a New Layer
1. Add the layer definition with matching source length:
```lisp
(deflayer my-new-layer
  _ _ _ _ _ _ _ _ _ _ _
  _ _ _ _ _ _ _ _ _ _
  _ _ _ _ _ _ _ _ _ _ _ _
  _ _ _ _ _ _
)
```
2. Use `_` (underscore) for transparent pass-through to the layer below.
3. Link the layer with `(layer-while-held my-new-layer)` for momentary hold or `(layer-switch my-new-layer)` for toggle.

### 3. Preserving Dual-Role Timing (Dwell Time Heuristics)
To prevent accidental modifier triggers during fast typing:
* Fast normal typing: `tap-time 150`, `hold-time 200`
* Shift modifier (pinky/ring): `dshift (tap-hold 150 140 d lshift)` (140ms hold time prevents missing capitals during rapid sequences).
* Long-press keys: `long-time 250` or `500` for Enter/CapsLock.

---

## 5. Critical Edge Cases & Troubleshooting

### ⚠️ Edge Case 1: PowerShell Here-String Variable Expansion
* **Problem**: In PowerShell, writing `@" ... $tap-time ... "@` expands `$tap-time` as an empty PowerShell variable, corrupting `config.kbd`.
* **Fix**: **Always use single-quoted here-strings** `@' ... '@` when writing Kanata configurations in PowerShell scripts.

### ⚠️ Edge Case 2: Windows Keyboard Driver Selection
* **`winIOv2` (Default)**: Uses Windows Low-Level Hooks (`LLHOOK + SendInput`). Requires zero driver installation and works out of the box on any Windows PC.
* **`wintercept`**: Requires installing the third-party Interception driver. Do NOT default to this unless the user explicitly requests it or has `interception.dll` installed.

### ⚠️ Edge Case 3: macOS Accessibility & Input Permissions
* On macOS, Kanata requires permission in **System Settings $\rightarrow$ Privacy & Security**:
  - `Input Monitoring` $\rightarrow$ enable `kanata` (or the Terminal / iTerm running it).
  - `Accessibility` $\rightarrow$ enable `kanata`.
* If keys do not register or throw permission errors, prompt the user to check these toggles.

### ⚠️ Edge Case 4: SVG Entity Escaping on Asset Regeneration
* If modifying keyboard diagram SVGs, **every string must be strictly XML-escaped**:
  - `<` $\rightarrow$ `&lt;`
  - `>` $\rightarrow$ `&gt;`
  - `&` $\rightarrow$ `&amp;`
  - `"` $\rightarrow$ `&quot;`
  - `'` $\rightarrow$ `&apos;`
* GitHub Camo and web browsers reject SVGs with XML parsing errors. Always validate with `xml.etree.ElementTree.parse(svg_path)` before committing.

### ⚠️ Edge Case 5: Dual-Hand Modifiers vs Vim Navigation Repeat
* On Layer 1, Left Hand keys (`A, S, D, F`) are tap-hold modifiers (`Win, Alt, Shift, Ctrl`).
* Right Hand keys (`H, J, K, L`) are **pure navigation keys** (`left, down, up, rght`).
* **Do NOT turn `H, J, K, L` into tap-holds on Layer 1**, as doing so breaks long-press continuous arrow repeat (scrolling down a document by holding `J`).
