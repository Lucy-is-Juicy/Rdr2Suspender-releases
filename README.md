# Session Suspender (RDR2 Suspender)

Press one key and **Red Dead Redemption 2 / Red Dead Online** freezes for a few seconds, then comes back in an **empty (solo) session**.

- **Windows**: get it from the Microsoft Store → **[Session Suspender on Microsoft Store](https://apps.microsoft.com/detail/9PN0KD7SMDLJ)**
- **Linux / Steam Deck**: download it below

This repository has the Linux / Steam Deck downloads only.

---

## Linux / Steam Deck

Works with RDR2 running through Steam / Proton. It works in **Desktop Mode and Gaming Mode**. One file with nothing else to install, and no root access needed to freeze the game.

On a Steam Deck, do the install in **Desktop Mode** (STEAM button → Power → Switch to Desktop).

### Install: option A, one command (easiest)

Open **Konsole** (app menu, bottom-left → System → Konsole), paste this and press Enter:

```sh
curl -fsSL https://github.com/Lucy-is-Juicy/Rdr2Suspender-releases/releases/latest/download/install.sh | sh
```

It downloads the latest version, checks it is not damaged, installs it and asks *Allow keyboard access now?*. Answer **y** and type your password.

### Install: option B, download the file

1. Download **[session-suspender-linux-x64.tar.gz](https://github.com/Lucy-is-Juicy/Rdr2Suspender-releases/releases/latest/download/session-suspender-linux-x64.tar.gz)**.
2. Right-click it → **Extract** → **Extract archive here**.
3. Open the new **SessionSuspender** folder and double-click **session-suspender**. If asked, click **Execute** / **Run**.
4. A small icon appears next to the clock (bottom-right; click **^** if you can't see it). Click it and choose **Allow keyboard access…**, then type your password.

The folder also has a **README.txt** with the same steps in more detail.

### Then, for both options

1. **Restart** the computer / Steam Deck (only needed once, after allowing keyboard access).
2. Start RDR2 as usual and press **F9** when you want an empty session. The picture freezes for about 8 seconds (that is normal), then the game continues.

It starts by itself every time you turn the device on.

> **Steam Deck: "I don't have a password!"** Open Konsole, type `passwd`, press Enter, then type a new password twice. Nothing shows while you type, which is normal. Write the password down.

### Steam Deck: use the back buttons instead of F9

Click the tray icon (Desktop Mode) → **Steam Deck back button** → pick **L4**, **R4**, **L5** or **R5**, or **L4+R4** / **L5+R5** (hold one, press the other, so it never fires by accident). You don't need to change anything in Steam's controller settings, and it works in Gaming Mode.

Any other combination can be set in Konsole, for example:

```sh
~/.local/bin/session-suspender config button L5+A
```

Button names: `L4 R4 L5 R5 A B X Y L1 R1 L2 R2 L3 R3 Up Down Left Right View Menu QAM Steam`. Include at least one back button, because the game still reacts to the other buttons.

### Settings

Click the icon next to the clock (Desktop Mode): **Change hotkey…**, **Steam Deck back button**, **Duration** (default 8 seconds; try 10 if you land in the same session), **Start at login**, **Language** (English / Russian), **Exit**. Changes also apply in Gaming Mode.

### Problems?

| Problem | Fix |
|---|---|
| F9 does nothing | Click the tray icon and read the top line. *No keyboard access*: allow it and restart. *Hotkey service not running*: restart. |
| I land in the same session | Set **Duration** to 10 seconds. |
| Game stays frozen | Wait for the seconds to pass, or press F9 again. Still frozen? In Konsole: `~/.local/bin/session-suspender resume` |
| Can't find the icon | App menu → search **Session Suspender**. |

### Update / remove

- **Update**: run the command from option A again, or download and open the new file. Your settings are kept.
- **Remove**: in Konsole run `~/.local/bin/session-suspender uninstall`.

---

## Please read

- **Red Dead Online has anti-cheat.** Freezing the game might be noticed. Use it at your own risk.
- **Keyboard access**: allowing it adds your account to the `input` group, which lets programs on your account read the keyboard. That is what makes the hotkey work everywhere, including Gaming Mode.
- All downloads are on the **[Releases](https://github.com/Lucy-is-Juicy/Rdr2Suspender-releases/releases)** page. Each release includes a `.sha256` checksum.
