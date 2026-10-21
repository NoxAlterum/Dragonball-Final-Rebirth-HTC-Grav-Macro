# Dragon Ball Rebirth Macro

Made by NoxAlterum

## Quick start

1. **Unzip** the download. Right-click the zip, choose **Extract All...**, then **Extract**.
2. Open the extracted folder and double-click **Dragon Ball Rebirth Macro.exe**.
   The first time, Windows may show a blue box saying "Windows protected your PC". That's normal
   for programs that aren't from a big company: click **More info**, then **Run anyway**.
3. Press the green **Start** button, then click on Roblox and start the **Time Chamber training**
   or the **Gravity Chamber**. The macro plays it for you.

That's all. The message under the picture in the macro's window always tells you what to do next,
and if the window is in the way of the minigame it moves itself. Press **Stop** (or **F6**) to
stop.

---

## What it does

Plays two training minigames for you by watching the screen, and works out by itself which one is
open.

**Time Chamber training (rhythm).** Notes slide from left to right into two white rings, and the
macro presses each one as it reaches the middle of its ring:

| Note                                   | What the macro does                                        |
|----------------------------------------|------------------------------------------------------------|
| Mouse with a **red** left button       | Left click                                                 |
| Mouse with a **purple** right button   | Right click                                                |
| **Q** / **E** key                      | Presses Q / E                                              |
| Note with a long **red streak** behind | A number (usually 25) appears in the ring: the macro presses that note's button over and over (left click, right click, Q or E) until the number counts down to 0 |

**Gravity Chamber (sequence).** A row of six notes; the one to press has a white ring around it.
The macro presses that note's button (left/right click, or Q/E if you picked keyboard in the
minigame's settings). It waits for the ring to move to the next note, then presses that one,
round after round. Timing doesn't matter here (the ring's pulsing is just for show); only the
right button does, so every note is read twice before it's pressed.

It only reads the screen and presses keys/mouse buttons like you would. It doesn't touch the
game's files or memory.

- Finds the minigame by itself, on any monitor, at any resolution from **720p to 4K**
- Works with Windows display scaling from **100% to 200%** (and beyond)
- Measures how fast the notes are moving as they go, instead of assuming a fixed speed
- Corrects its own timing from the game's hit and miss flashes, and remembers what it learned
- Light and dark mode, a start/stop hotkey, and a live view of what it sees

---

## How to use

1. Open **Dragon Ball Rebirth Macro** and press **Start** (or the hotkey, **F6** by default).
2. Click on Roblox and start a minigame: the Time Chamber training or the Gravity Chamber. You can
   also press Start after the minigame has begun, even part-way through a round.
3. The macro finds the minigame and plays on its own. The message turns green and says which
   minigame it's playing. If it turns red, it says what to do (usually "Click on the Roblox
   window").
4. Press **F6** again (or **Stop**) to stop. Between minigames it simply waits, and it picks back
   up when the next one starts.

What the messages mean:

| Message | What to do |
|---|---|
| Open Roblox to get started | Open Roblox. |
| Ready - start the Time Chamber training or the Gravity Chamber in Roblox... | Start one of those minigames. |
| Playing the ... for you (green) | Nothing. Sit back. |
| Click on the Roblox window so the macro can play (red) | Click anywhere on the Roblox window. |
| That minigame has finished... | Start another one whenever you like. |

The strip at the top of the window shows what the macro sees. In the Time Chamber there's a box
around each note it's following, and `~` after a letter marks the start of a red streak. During a
streak the ring is circled orange with the number of presses so far, and turns green once the
game's counter reaches 0. In the Gravity Chamber the note it's about to press is circled: green
while it reads it, orange once it's pressed and waiting for the ring to move on.

### Tips

- **The macro window gets out of the way by itself.** The macro has to see the minigame, so if its
  window is covering it, the window moves up above the minigame. If there's no room (a small
  screen), it minimizes itself and comes back when the minigame is over.
- **Mouse clicks land wherever the cursor is.** When a minigame starts, the macro moves the
  cursor out of the way: between the two lanes in the Time Chamber, and over your character in
  the Gravity Chamber. That way a click can't hit the game's STOP button or this window. You can
  turn this off in the settings.
- Roblox has to be the active window. With "Only press while Roblox is the active window" on
  (the default), the macro never types Q/E into another program by accident.

---

## Automatic timing (Time Chamber)

Every PC has a little delay between the game drawing a frame and receiving a press, so the macro
presses slightly early. **Adjust automatically from hits and misses** (on by default) works out the
exact amount while you play:

- **On a hit**, the game turns the ring light green and a pale glow spreads out around it, at the
  moment it accepted the press. The macro compares that moment with when the note reached the
  middle of the ring and corrects by the difference. It corrects firmly for the first few hits,
  then in small steps, so it settles within a few milliseconds.
- **On a miss**, the screen flashes red. The flash's timing shows whether the press was early or
  late, and the macro steps its timing that way. If the misses continue, it tries a little either
  side until hits come back, then the hit measurements take over again.

The line under the message shows how many hits and misses it has seen and how far it has adjusted
the timing. When you stop, the learned timing is saved into
**Press early by (ms)**, so the next session starts already calibrated.

---

## Settings

| Setting | What it does |
|---|---|
| **Start/Stop hotkey** | Type a key (for example `f6`, `f8`, `ctrl+shift+s`) and press **Set**. Q and E can't be used, because the macro presses them itself. |
| **Press early by (ms)** | Makes up for the delay between the game drawing a frame and receiving a press. With automatic timing on, this is only the starting point, and it's updated with what was learned each time you stop. With it off, raise it if hits land late and lower it if they land early. |
| **Adjust automatically from hits and misses** | See [Automatic timing](#automatic-timing-time-chamber). |
| **Gravity Chamber pause (ms)** | How long to wait after the game takes a press before pressing the next note. The default is 50. Lower is faster; raise it if the game ever seems to drop presses. |
| **Only press while Roblox is the active window** | Skips presses while another window is in front. |
| **Move the mouse out of the way when a minigame starts** | See the tips above. |
| **Keep this window on top of the game** | Keeps the macro visible over a fullscreen or maximised Roblox window. |
| **Dark mode / Light mode** | Bottom-left button. |

Settings are saved in `dbr_config.json` next to the program. If that folder is read-only, they're
saved in `%APPDATA%\DragonBallRebirthMacro` instead.

---

## Accessibility

- Every control works from the keyboard: **Tab** moves between controls (with a visible focus
  outline), and **Space** or **Enter** presses buttons and ticks boxes.
- The start/stop hotkey works from inside the game, so you never need to switch windows.
- Text and buttons scale with Windows display scaling (Settings > System > Display > Scale), and
  the window still fits a 1080p screen at 200%. The window can also be resized.
- Both themes use high-contrast text colours (WCAG AA, 4.5:1 or better).

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Stays on "Ready - start the Time Chamber training or the Gravity Chamber" while one is open | Make sure the minigame is fully on screen and not covered by another window: both white rings in the Time Chamber, the row of notes in the Gravity Chamber. |
| Says "Open Roblox to get started" while Roblox is open | The macro looks for a window called "Roblox". Close and reopen Roblox. |
| "Click on the Roblox window so the macro can play" | Click anywhere on Roblox. The macro only presses keys while Roblox is the window in front, so it never types into another program. |
| "The game isn't responding to the presses" | No hit or miss followed the macro's presses. Click on Roblox so it's the window in front. |
| "Note(s) went grey: a button was misread" | In the Gravity Chamber a note goes grey when it's pressed with the wrong button. This shouldn't happen; if it does, please report it with a screenshot of the row. |
| Hits land a little late or early | Leave automatic timing on for a few notes; it corrects itself. With it off, change **Press early by (ms)** by about 10 at a time. |
| "Something went wrong (...) - trying again" | It keeps trying by itself. If the message stays, press Stop and then Start. |
| The hotkey doesn't work in game | Pick a different key. Some keys are taken by Roblox or by other programs. |
| Windows SmartScreen warns about the .exe | It's unsigned. Click **More info**, then **Run anyway**, or run the `.py` instead (see below). |

---

## Running from source

Needs Windows 10/11 and Python 3.10 or newer.

```
python -m pip install -r requirements.txt
python Dragon_Ball_Rebirth_Macro.py
```

## Building the .exe

Run `build_exe.bat`. It installs what's needed and creates `dist\Dragon Ball Rebirth Macro\` with
the .exe and this README, plus `dist\Dragon Ball Rebirth Macro.zip` of that folder, ready to share.
The .exe and window icon is `icon.ico`; replace it (or put an `icon.png` there instead) to change
it.

## Developer tools

`dev_tools/` has scripts that test the macro on screen recordings of the minigame, so you can
check changes without the game:

- `replay_test.py` runs a recording through the detection frame by frame. It reports every
  press, how far each one landed from the middle of its ring, and any note that was never
  pressed. Use `--height` to test other resolutions and `--auto` to also find the rings by
  itself.
- `live_sim.py` runs the full macro in real time against a recording played as if it were the
  screen. Nothing is actually pressed.
- `test_find_rings.py` and `test_ring_spread.py` check that the rings are found at every
  resolution, and how steadily. `test_find_gravity.py` does the same for the Gravity Chamber's
  row.
- `test_presser.py` checks the press timing edge cases.
- `test_tuner.py` plays the automatic timing against a simulated game with different amounts of
  lag, including lag far outside the hit window and lag that changes mid-game.
- `replay_test.py --tune --answers` also lists every hit and miss read off the recording.
- `screenshot_gui.py` and `benchmark.py` capture the window at any display scale and time the
  detection. `test_window_move.py` checks that the window gets out of the minigame's way.
