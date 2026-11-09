<div align="center">

# ⚡ Super-Keyboard: The Ultimate Ergonomic Kanata Setup

**Turn any standard laptop or mechanical keyboard into a \$400 custom ergonomic powerhouse.**

[![GitHub stars](https://img.shields.io/github/stars/GrvExplorer/super-keyboard?style=for-the-badge&logo=github&color=f59e0b)](https://github.com/GrvExplorer/super-keyboard/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-38bdf8?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/jtroo/kanata)
[![Powered by Kanata](https://img.shields.io/badge/Powered%20by-Kanata%20v1.7%2B-22c55e?style=for-the-badge)](https://github.com/jtroo/kanata)

<p align="center">
  <b>No more reaching across the desk for arrow keys.</b><br>
  <b>No more pinky gymnastics stretching for Ctrl and Alt.</b><br>
  <b>Control your entire mouse cursor, scroll wheel, and clicks directly from your home row.</b>
</p>

[Quick Start](#-quick-start--installation) • [Layer Visuals](#-interactive-layer-visuals) • [Why This Setup?](#-why-super-keyboard) • [Configuration Reference](#-layer-walkthrough--cheat-sheet)

</div>

---

## 💡 Why Super-Keyboard?

Repetitive strain injury (RSI), wrist pain, and slow typing often stem from two design flaws of traditional QWERTY keyboards:
1. **The Pinky Stretch**: Reaching down to `Ctrl` or up to `Backspace` strains the smallest finger on your hand thousands of times a day.
2. **The Mouse & Arrow Gap**: Moving your entire right arm off the keyboard just to nudge the mouse or move the text cursor breaks your focus and typing rhythm.

**Super-Keyboard solves this entirely in software using [Kanata](https://github.com/jtroo/kanata):**
* 🧠 **Home-Row Modifiers**: System modifiers (`Ctrl`, `Alt`, `Shift`, `Win`/`Cmd`) live comfortably beneath your resting fingers on hold.
* 🚀 **Spacebar Layer**: Holding `Space` transforms your right hand into a Vim navigation cluster and your left hand into numbers & symbols.
* 🖱️ **Full Mouse Control**: Toggle into hands-free mouse mode (`Space + ;`) to move the cursor with smooth acceleration, left/right click, and scroll—both hands completely relaxed.
* ⚡ **Zero Added Latency**: Fast typists type naturally with zero lag, thanks to calibrated 150ms/200ms human dwell-time heuristics.

---

## 🗺️ Interactive Layer Visuals

### 1. Base Layer (Home-Row Mods)
> **Tap** a key to type normally. **Hold** any home-row key to activate system modifiers.

<p align="center">
  <img src="assets/layer-0-base.svg" alt="Base Layer: Home Row Mods" width="860">
</p>

| Key | Tap | Hold (When pressed with other keys) |
| :--- | :--- | :--- |
| **`Caps Lock`** | `Escape` | `Caps Lock` |
| **`A`** &nbsp;/&nbsp; **`;`** | `a` &nbsp;/&nbsp; `;` | **Left GUI (Windows / Cmd)** &nbsp;/&nbsp; **Right GUI** |
| **`S`** &nbsp;/&nbsp; **`L`** | `s` &nbsp;/&nbsp; `l` | **Left Alt** &nbsp;/&nbsp; **Right Alt** |
| **`D`** &nbsp;/&nbsp; **`K`** | `d` &nbsp;/&nbsp; `k` | **Left Shift** &nbsp;/&nbsp; **Right Shift** |
| **`F`** &nbsp;/&nbsp; **`J`** | `f` &nbsp;/&nbsp; `j` | **Left Ctrl** &nbsp;/&nbsp; **Right Ctrl** |
| **`Spacebar`** | `Space` | **Hold $\rightarrow$ Activates Layer 1 (Navigation & Numbers)** |

---

### 2. Layer One: No More Pinky Keys
> Hold **`Spacebar`** to activate. Gives instant access to Vim arrows, brackets, math symbols, numbers, and Function keys (`F1`–`F12`).

<p align="center">
  <img src="assets/layer-1-space.svg" alt="Layer One: Navigation, Numbers & F-Keys" width="860">
</p>

* **Vim Navigation**: `H` (Left ◄), `J` (Down ▼), `K` (Up ▲), `L` (Right ►).
* **Navigation Extremes**: `T` $\rightarrow$ **Home**, `Y` $\rightarrow$ **End**, `E` $\rightarrow$ **Escape**.
* **Brackets & Symbols**: `U` $\rightarrow$ `[`, `I` $\rightarrow$ `]`, `O` $\rightarrow$ `-`, `P` $\rightarrow$ `=`.
* **One-Tap Editing**:
  * `C` $\rightarrow$ **Copy** (`Ctrl + C`)
  * `V` $\rightarrow$ **Paste** (`Ctrl + V`)
  * `B` $\rightarrow$ **Backspace**
  * `N` $\rightarrow$ **Delete**
* **Instant Function Row (`F1` – `F12`)**:
  * `Space + 1` through `Space + 0` $\rightarrow$ **`F1` through `F10`**
  * `Space + [` $\rightarrow$ **`F11`** (Fullscreen toggle)
  * `Space + '` $\rightarrow$ **`F12`** (Inspect / DevTools)
* **Enter Mouse Mode**: Tap **`;`** while holding `Space` to switch into **Layer 2 (Mouse Mode)**.

---

### 3. Layer Two: Use the Mouse!
> Enter with **`Space + ;`**. Once entered, you can let go of all keys—your hands are completely free to navigate without holding any buttons.

<p align="center">
  <img src="assets/layer-2-mouse.svg" alt="Layer Two: Hands-Free Mouse Controller" width="860">
</p>

* **Smooth Cursor Acceleration (Left Hand Inverted-T)**:
  * `E` $\rightarrow$ Cursor Up ▲
  * `S` $\rightarrow$ Cursor Left ◄
  * `D` $\rightarrow$ Cursor Down ▼
  * `F` $\rightarrow$ Cursor Right ►
* **Mouse Clicks & Dragging (Right Hand)**:
  * `J` $\rightarrow$ **Left Click** (`mlft`) — *hold down to select text or drag windows*
  * `K` $\rightarrow$ **Right Click** (`mrgt`)
  * `H` $\rightarrow$ **Middle Click** (`mmid`)
* **Scroll Wheel**:
  * `W` $\rightarrow$ Wheel Up
  * `R` $\rightarrow$ Wheel Down
* **Inline Clipboard Actions**:
  * `C` $\rightarrow$ **Copy** (`Ctrl + C`)
  * `V` $\rightarrow$ **Paste** (`Ctrl + V`)
  * `B` $\rightarrow$ **Backspace**
  * `N` $\rightarrow$ **Delete**
  * `M` $\rightarrow$ **Copy** (`Ctrl + C`)
* **Exit Mouse Mode**:
  * Tap **`;`** to return immediately to **Layer 0 (Base)**.

---

## 💻 Quick Start & Installation

### 🪟 Windows Setup

#### 1. Install Kanata
* **Via Winget / Scoop (Fastest)**:
  ```powershell
  winget install jtroo.kanata
  # or
  scoop install kanata
  ```
* **Or Manual Download**:
  Download `kanata.exe` from the [official Kanata Releases](https://github.com/jtroo/kanata/releases) and place it in your `PATH` or folder (e.g. `C:\kanata`).

#### 2. Clone the Super-Keyboard Config
```powershell
git clone https://github.com/GrvExplorer/super-keyboard.git "$HOME\.config\kanata"
```

#### 3. Test & Run
```powershell
# Validate syntax
kanata --check -c "$HOME\.config\kanata\config.kbd"

# Run Kanata
kanata -c "$HOME\.config\kanata\config.kbd"
```

#### 4. Auto-Start in Background (Headless)
To run silently on Windows login without an open command prompt:
1. Open **Task Scheduler** (`Win + R` $\rightarrow$ `taskschd.msc`).
2. Create Task:
   * **Name**: `run kanata`
   * **Triggers**: *At log on of any user*
   * **Action**:
     * Program: `conhost`
     * Arguments: `--headless kanata -c "C:\Users\<YourUser>\.config\kanata\config.kbd"`
   * **Conditions**: Uncheck *Stop if computer switches to battery power*.

---

### 🍏 macOS Setup

Kanata leverages the Karabiner VirtualHIDDevice driver to inject virtual keypresses on macOS.

#### 1. Install via Homebrew
```bash
# 1. Install driver
brew install --cask karabiner-elements

# 2. Install Kanata
brew install kanata
```

#### 2. Grant macOS Accessibility Permissions
1. Go to **System Settings** $\rightarrow$ **Privacy & Security**.
2. Under **Input Monitoring**, enable **kanata** (or your Terminal / iTerm2).
3. Under **Accessibility**, enable **kanata**.

#### 3. Clone & Run
```bash
git clone https://github.com/GrvExplorer/super-keyboard.git ~/.config/kanata

# Test / Validate syntax
kanata --check -c ~/.config/kanata/config.kbd

# Run directly (requires sudo on macOS for low-level device access)
sudo kanata -c ~/.config/kanata/config.kbd
```

#### 4. Auto-Start on Boot / Login (macOS)

Because Kanata requires root privileges to grab raw keyboard devices, choose either of the following setup options:

##### Option A: Homebrew Services (Recommended & Easiest)
If you installed Kanata via Homebrew, run:
```bash
# Start background service and enable launch on system boot
sudo brew services start kanata
```
*(To stop the background service: `sudo brew services stop kanata`)*

##### Option B: Custom `launchd` LaunchDaemon (Manual Binary / High Reliability)
If you installed the binary manually or prefer a standalone native daemon:

1. Create a `launchd` service file:
```bash
sudo tee /Library/LaunchDaemons/com.kanata.daemon.plist << 'EOF'
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.kanata.daemon</string>
    <key>ProgramArguments</key>
    <array>
        <!-- Use /opt/homebrew/bin/kanata on Apple Silicon or /usr/local/bin/kanata on Intel -->
        <string>/opt/homebrew/bin/kanata</string>
        <string>-c</string>
        <string>/Users/YOUR_USERNAME/.config/kanata/config.kbd</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>KeepAlive</key>
    <true/>
    <key>StandardOutPath</key>
    <string>/Library/Logs/kanata.out.log</string>
    <key>StandardErrorPath</key>
    <string>/Library/Logs/kanata.err.log</string>
</dict>
</plist>
EOF
```
*(Make sure to replace `/Users/YOUR_USERNAME/` with your actual macOS user home folder path).*

2. Register and start the daemon:
```bash
sudo chown root:wheel /Library/LaunchDaemons/com.kanata.daemon.plist
sudo chmod 644 /Library/LaunchDaemons/com.kanata.daemon.plist
sudo launchctl load -w /Library/LaunchDaemons/com.kanata.daemon.plist
```
*(To stop and unload the daemon: `sudo launchctl unload -w /Library/LaunchDaemons/com.kanata.daemon.plist`)*


---

## ⚙️ Ergonomic Tuning (`defvar`)

Every delay and acceleration curve in this configuration is finely tuned for human typing mechanics:

```lisp
(defvar
  tap-time 150   ;; 150ms: Quick double-tap window for repeating alpha characters
  hold-time 200  ;; 200ms: Ergonomic hold threshold before modifiers/layers activate
  long-time 250  ;; 250ms: Slightly longer dwell for weaker outer fingers (pinky/ring)

  ;; Mouse cursor acceleration
  ms-t 10        ;; 10ms update interval for butter-smooth 100fps motion
  ms-at 800      ;; 800ms linear acceleration ramp
  ms-min 3       ;; 3px initial precision speed (pixel-perfect targeting)
  ms-max 25      ;; 25px max transit speed (lightning-fast multi-monitor crossing)

  ;; Mouse scroll wheel
  scr-t 50       ;; Scroll interval
  scr-d 120      ;; 120 units = 1 standard mouse wheel detent
)
```

---

## 🛑 Emergency Kill-Switch

If you ever need to stop Kanata immediately and restore stock keyboard behavior:
* Press **`Left Control + Space + Escape`** simultaneously.

---

## 🤝 Contributing & Community

Contributions, bug reports, and layout suggestions are warmly welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/cool-layer`)
3. Commit your Changes (`git commit -m 'Add new symbol macro'`)
4. Push to the Branch (`git push origin feature/cool-layer`)
5. Open a Pull Request

---

## 📜 License & Credits

* Distributed under the **MIT License**. See `LICENSE` for details.
* Created and maintained by **Gaurav Verma** ([@GrvExplorer](https://github.com/GrvExplorer)).
* Special credit to [jtroo/kanata](https://github.com/jtroo/kanata) for the incredible engine and [tannerr-dev/kanata-config](https://github.com/tannerr-dev/kanata-config) for initial layer inspiration.
