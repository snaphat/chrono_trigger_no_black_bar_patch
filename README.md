# Chrono Trigger No Black Bar Patch
BPS patches to remove the bottom black bar in SNES Chrono Trigger.

# Patches
This table contains BPS patches for Chrono Trigger (USA) and Chrono Trigger (Japan) to remove the black bar at the bottom of the screen.

| Game                          | CRC      | BPS Patch                                                 |
|-------------------------------|:--------:|:---------------------------------------------------------:|
| Chrono Trigger (USA)           | 2d206bf7 | [bps](Chrono%20Trigger%20(USA).No%20Black%20Bar.bps)      |
| Chrono Trigger (Japan)         | 4d014c20 | [bps](Chrono%20Trigger%20(Japan).No%20Black%20Bar.bps)    |

## Video

[![
What Happens When You Remove the Bottom Black Bar in Chrono Trigger?](https://img.youtube.com/vi/PI3wsDg4YwQ/0.jpg)](https://www.youtube.com/watch?v=PI3wsDg4YwQ)

## How the Patch Works

This patch works by **removing the code** in **Chrono Trigger** that **sets the `INIDISP` register** before **scanline 212**. This register forces **vertical blanking**, which results in the black bar at the bottom of the screen.

### Technical Details

- **`INIDISP` Register:**
  The **`INIDISP` register** (`$2100`) forces **vertical blanking** in Chrono Trigger. This action shrinks the vertical display, generating the black bar at the bottom of the screen. The patch removes the code that sets this register both during the **field** and **combat screens**, which stops the forced vertical blanking and allows the full vertical display to be used without the black bar.

- **Artifacts:**
  Since the game was designed with the black bar, removing the forced vertical blanking can cause **artifacts**, such as:
  - **Garbage data** appearing beneath dialog boxes displayed at the bottom of the screen.
  - Occasionally, **8 rows of garbage** may appear at the bottom where the black bar would have been.
