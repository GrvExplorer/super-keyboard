# ⚡ super-keyboard: Advanced Kanata Configuration

A modern, high-performance, cross-platform keyboard configuration powered by [Kanata](https://github.com/jtroo/kanata). Designed to maximize typing efficiency, eliminate pinky fatigue, and keep hands anchored to the home row at all times.

---

## 🌟 Key Highlights

* **Home-Row Modifiers (HRM)**: `Ctrl`, `Alt`, `Shift`, and `Win`/`Cmd` accessible right beneath your home-row fingers on hold.
* **Dual-Function Spacebar (Layer 1)**: Tap for standard `Space`; hold to unlock Vim-style arrow navigation, brackets, math symbols, numbers, and one-tap Copy/Paste.
* **Modal Mouse Controller (Layer 2)**: Toggle hands-free mouse mode (`Space + ;`) to steer the cursor with smooth acceleration, left/right click, drag-and-drop, and scroll. Tap `;` to return to typing.
* **Integrated Function Keys (`F1` – `F12`)**: Hold `Space` and tap top-row numbers for instant access to function keys (`F1` through `F12`) without awkward hand stretching.
* **Dual-Trigger Function Alternative**: Includes a standalone alternate configuration (`config_dual_fn.kbd`) utilizing dual bottom-row triggers (`x` and `.`).

---

## 🗺️ Layer Architecture & Keyboard Maps

### Layer 0: Base Layer (Home-Row Mods)

Tap a letter to type normally. Hold a home-row key to activate a system modifier:

```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│  1  │  2  │  3  │  4  │  5  │  6  │  7  │  8  │  9  │  0  │  [  │     │
├─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│   Q    │  W  │  E  │  R  │  T  │  Y  │  U  │  I  │  O  │  P  │        │
├────────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴────────┤
│  Esc/Caps │  A  │  S  │  D  │  F  │  G  │  H  │  J  │  K  │  L  │  ;  │ ' │
│   [Caps]  │ WIN │ ALT │ SHFT│ CTRL│     │     │ CTRL│ SHFT│ ALT │ WIN │   │
├─────┬─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│     │   Z    │  X  │  C  │  V  │  B  │  N  │  M  │  ,  │  .  │  /  │     │
└─────┴────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┘
                                 │  Space / │
                                 │ [Layer 1]│
                                 └──────────┘
```

| Physical Key | Tap Action | Hold Action |
| :--- | :--- | :--- |
| **`Caps`** | `Escape` | `Caps Lock` |
| **`A`** / **`;`** | `a` / `;` | **Left GUI (Win/Cmd)** / **Right GUI** |
| **`S`** / **`L`** | `s` / `l` | **Left Alt** / **Right Alt** |
| **`D`** / **`K`** | `d` / `k` | **Left Shift** / **Right Shift** |
| **`F`** / **`J`** | `f` / `j` | **Left Ctrl** / **Right Ctrl** |
| **`Space`** | `Space` | **Hold $\rightarrow$ Activates Layer 1** |

---

### Layer 1: Navigation, Numbers & Symbols (Space Held)

Hold **`Space`** to transform the keyboard into a productivity console:

```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│ F1  │ F2  │ F3  │ F4  │ F5  │ F6  │ F7  │ F8  │ F9  │ F10 │ F11 │     │
├─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│   9    │  0  │ Esc │  ;  │ Home│ End │  [  │  ]  │  -  │  =  │        │
├────────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴────────┤
│ Enter/Caps│  1  │  2  │  3  │  4  │  5  │ Left│ Down│ Up  │Right│ Mouse│F12 │
│           │     │     │     │     │Enter│  ◄   │  ▼  │  ▲  │  ►  │ Mode │    │
├─────┬─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│     │        │     │Copy │Paste│ Bksp│ Del │  M  │     │     │     │     │
│     │        │     │CtrlC│CtrlV│     │     │     │     │     │     │     │
└─────┴────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┘
                                 │ Backspace│
                                 └──────────┘
```

#### Key Bindings Summary:
* **Vim Navigation Arrows**: `H` (Left), `J` (Down), `K` (Up), `L` (Right).
* **Editing Shortcuts**:
  * `C` $\rightarrow$ **Copy** (`Ctrl + C`)
  * `V` $\rightarrow$ **Paste** (`Ctrl + V`)
  * `B` $\rightarrow$ **Backspace**
  * `N` $\rightarrow$ **Delete**
  * `E` $\rightarrow$ **Escape**
  * `T` / `Y` $\rightarrow$ **Home** / **End**
* **Brackets & Math**:
  * `U` $\rightarrow$ `[` &nbsp;|&nbsp; `I` $\rightarrow$ `]` &nbsp;|&nbsp; `O` $\rightarrow$ `-` &nbsp;|&nbsp; `P` $\rightarrow$ `=`
* **Left-Hand Numbers**: `A` (1), `S` (2), `D` (3), `F` (4), `G` (5).
* **Function Keys (`F1` – `F12`)**:
  * Top numbers `1` – `0` $\rightarrow$ `F1` – `F10`
  * `[` $\rightarrow$ `F11` (Fullscreen)
  * `'` $\rightarrow$ `F12` (Inspect / Developer Tools)
* **Mouse Layer Toggle**: Tap **`;`** while holding `Space` to enter **Layer 2 (Mouse Mode)**.

---

### Layer 2: Modal Mouse Controller (Hands-Free Mouse Mode)

Enter with **`Space + ;`**. Once entered, release all keys; both hands are completely free to navigate without holding any modifiers.

```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│     │     │     │     │     │     │     │     │     │     │     │     │
├─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│        │WhlUp│Up ▲ │WhlDn│     │     │     │     │     │     │        │
├────────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴────────┤
│           │     │Lft ◄│Dn ▼ │Rgt ►│     │MidClk│L-Clk│R-Clk│     │ EXIT │   │
│           │     │     │     │     │     │      │     │     │     │ (;)  │   │
├─────┬─────┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴─────┤
│     │        │     │Copy │Paste│ Bksp│ Del │  M  │     │     │     │     │
│     │        │     │CtrlC│CtrlV│     │     │     │     │     │     │     │
└─────┴────────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┘
```

#### Mouse Controls:
* **Cursor Steering (Left Hand inverted-T)**:
  * `E` $\rightarrow$ Up
  * `S` $\rightarrow$ Left
  * `D` $\rightarrow$ Down
  * `F` $\rightarrow$ Right
  *(Configured with smooth linear acceleration for pixel-level precision and rapid screen transit)*.
* **Clicks & Dragging (Right Hand)**:
  * `J` $\rightarrow$ **Left Click** (`mlft`) — hold down to drag-and-drop or select text.
  * `K` $\rightarrow$ **Right Click** (`mrgt`).
  * `H` $\rightarrow$ **Middle Click** (`mmid`).
* **Scroll Wheel**:
  * `W` $\rightarrow$ Scroll Up
  * `R` $\rightarrow$ Scroll Down
* **Quick Text Actions**:
  * `C` $\rightarrow$ Copy (`Ctrl + C`)
  * `V` $\rightarrow$ Paste (`Ctrl + V`)
  * `N` $\rightarrow$ Delete (`del`)
  * `B` $\rightarrow$ Backspace (`bspc`)
* **Exit Mouse Mode**:
  * Tap **`;`** to immediately return to **Layer 0 (Base)**.

---

## 💻 How to Install Kanata

### 🪟 Windows Installation

#### Method 1: Direct Binary Download (Recommended)
1. Download the latest release binary `kanata.exe` from the [official Kanata Releases page](https://github.com/jtroo/kanata/releases).
2. Place `kanata.exe` in a convenient directory (e.g. `C:\kanata` or `E:\kanata`).
3. Add that directory to your system `PATH` so `kanata` can be called from any terminal.

*(Note: The standard Windows binary uses low-level hooks (`LLHOOK` + `SendInput`) and works out of the box with zero extra drivers).*

#### Method 2: Package Managers
```powershell
# Using Winget
winget install jtroo.kanata

# Or using Scoop
scoop bucket add extras
scoop install kanata
```

---

### 🍏 macOS Installation

Kanata requires the virtual keyboard driver from Karabiner to inject keypresses on macOS.

#### 1. Install Driver and Kanata via Homebrew
```bash
# Install Karabiner VirtualHIDDevice driver
brew install --cask karabiner-elements

# Install Kanata
brew install kanata
```

#### 2. Grant macOS System Permissions
1. Open **System Settings** $\rightarrow$ **Privacy & Security**.
2. Under **Input Monitoring**, enable **kanata** (or your terminal application).
3. Under **Accessibility**, enable **kanata**.

#### 3. Run Kanata
On macOS, Kanata requires root privileges to grab raw keyboard devices:
```bash
sudo kanata -c ~/.config/kanata/config.kbd
```

To auto-start Kanata on login as a system daemon:
```bash
sudo brew services start kanata
```

---

## 📦 How to Use This Configuration

### 1. Clone this Repository
```bash
# macOS / Linux default config directory
git clone https://github.com/GrvExplorer/super-keyboard.git ~/.config/kanata

# Windows default config directory
git clone https://github.com/GrvExplorer/super-keyboard.git "$HOME\.config\kanata"
```

### 2. Validate the Configuration
Run Kanata in validation mode to verify syntax:
```bash
kanata --check -c ~/.config/kanata/config.kbd
```

### 3. Start Kanata
```bash
# Windows
kanata -c "C:\Users\<YourUser>\.config\kanata\config.kbd"

# macOS
sudo kanata -c ~/.config/kanata/config.kbd
```

---

## 📁 Configuration Flavors

* **`config.kbd` (Active Default)**: Option B layout. Places `F1`–`F12` directly on the physical number row while holding `Space`.
* **`config_dual_fn.kbd` (Alternate)**: Option A layout. Features a dedicated Layer 3 activated by dual triggers: holding `x` (left hand) or holding `.` (right hand).

---

## ⚙️ Timing Variables (`defvar`)

Calibrated for natural human keystroke ergonomics (average typing dwell time is ~70–120ms):

```lisp
(defvar
  tap-time 150   ;; Double-tap window for repeating the tap action (ms)
  hold-time 200  ;; Hold duration required to activate modifiers/layers (ms)
  long-time 250  ;; Extended hold time for outer fingers (Ring/Pinky)

  ;; Mouse movement acceleration
  ms-t 10        ;; Interval between mouse movements (ms)
  ms-at 800      ;; Duration to linearly ramp up to max speed (ms)
  ms-min 3       ;; Starting speed (pixels)
  ms-max 25      ;; Maximum transit speed (pixels)

  ;; Mouse scroll wheel
  scr-t 50       ;; Scroll event interval (ms)
  scr-d 120      ;; Distance per notch (120 is 1 Windows notch)
)
```

---

## 🚀 Windows Auto-Start Setup (Headless)

To run Kanata silently in the background on Windows startup without a console window:

1. Open **Task Scheduler** (`taskschd.msc`).
2. Create a new task named **`run kanata`**:
   * **General**: Check *Run only when user is logged on*.
   * **Triggers**: *At log on of any user*.
   * **Actions**:
     * **Program/script**: `conhost`
     * **Arguments**: `--headless kanata -c "E:\kanata\.config\kanata\config.kbd"`
   * **Conditions**: Uncheck *Stop if the computer switches to battery power*.

---

## 🛑 Emergency Exit

Kanata has a built-in safety combo to terminate immediately:
* Press **`Left Control + Space + Escape`** simultaneously to exit Kanata and restore default keyboard behavior.

---

## 👤 Author & Acknowledgments

* Created and maintained by **Gaurav Verma** ([@GrvExplorer](https://github.com/GrvExplorer)).
* Inspired by the ergonomic concepts in [tannerr-dev/kanata-config](https://github.com/tannerr-dev/kanata-config) and [jtroo/kanata](https://github.com/jtroo/kanata).
