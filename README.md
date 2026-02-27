# scrcpy on Windows — Mirror & Control Android (USB + Wi-Fi)

Lightweight tool to display and control Android devices from a PC.


Source:
https://github.com/Genymobile/scrcpy

---

## Requirements

- Android 5.0+
- USB cable (recommended)
- scrcpy Windows zip extracted to a folder
- (If needed) OEM USB driver for your phone brand (Samsung/Xiaomi/etc.)

---

## 1) Android Setup (One-Time)

1. **Settings → About phone → Software information**
2. Tap **Build number** 7 times (enter PIN if prompted)
3. Go back → **Developer options**
4. Enable **USB debugging**

---

## 2) Windows Setup (Correct Way to Run)

scrcpy is best run from a terminal so you can see errors.

1. Open the extracted **scrcpy** folder
2. Double-click:

```
open_a_terminal_here.bat
```

3. In the terminal that opens, run:

```bat
scrcpy
```

> Optional:  
> You can use `scrcpy-noconsole.vbs` to hide the console window, but use the terminal method for troubleshooting.

---

## 3) USB Connection (Best Performance)

1. Connect phone to PC via USB
2. Approve popup on phone:

```
Allow USB debugging
```

(You can select **Always allow from this computer**)

3. Run:

```bat
scrcpy
```

You can now control your phone using mouse and keyboard.

---

## 4) Wireless Connection (Quick Method)

⚠️ Requirements:

- Phone and PC on same Wi-Fi network
- First connection must be via USB

Steps:

1. Connect phone via USB
2. Open scrcpy folder
3. Run:

```
open_a_terminal_here.bat
```

4. In terminal:

```bat
scrcpy --tcpip
```

5. Allow debugging on phone
6. Disconnect USB cable
7. Run again:

```bat
scrcpy --tcpip
```

Notes:

- Wireless is more laggy than USB (normal)
- After reboot or network change you may need to repeat steps

---

## 5) Troubleshooting (Fast Checks)

Open terminal using `open_a_terminal_here.bat`.

### Check Device Detection

```bat
adb devices
```

If you see:

```
unauthorized
```

→ Unlock phone and accept debugging prompt.

### Restart ADB

```bat
adb kill-server
adb start-server
```

### Still Not Working

- Try another USB port/cable
- Install OEM USB drivers
- Reconnect device
- Enable USB debugging again

---

## 6) Useful Commands (You Will Need Later)

### Fullscreen

```bat
scrcpy -f
```

### Limit Resolution (Better Performance)

```bat
scrcpy --max-size 1024
```

### Limit FPS

```bat
scrcpy --max-fps 30
```

### Turn Phone Screen Off While Mirroring

```bat
scrcpy --turn-screen-off
```

### Keep Phone Awake

```bat
scrcpy --stay-awake
```

### Record Screen

```bat
scrcpy --record file.mp4
```

### Mirror Without Control

```bat
scrcpy --no-control
```

---

## 7) Daily Usage Tips

- Use **USB** for lowest latency
- Use `--turn-screen-off` to reduce heat and battery usage
- Create `.bat` scripts for repeated commands
- Keep scrcpy updated (frequent improvements)

---

## 8) Quick Start (TL;DR)

```bat
Enable USB debugging → Connect phone → open_a_terminal_here.bat → scrcpy
```

---

## Official Help

```bat
scrcpy --help
```

---
