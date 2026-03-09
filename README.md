# RhythmBot
Open-source challenge: build a Python rhythm game bot utilzing ADB, with $10 reward to whoever first successfully completes it

**Full challenge**

Compatible with Windows 11

Create a bot that can capture an emulator(Bluestacks) screen utilizing ADB

Detect notes falling downwards, and determine when they hit the "hit line", and whether it's a tap, swipe, hold, or trace

Utilizing the detection, tapping at the correct time to hit/hold/swipe/trace the note exactly when it hits the hit line

Very low latency

Extremely fast reaction time

Preferablly with Auto calibration

Able to hit/hold/swipe/trace multiple notes at the same time

Must hit within **±41.7 ms** of the note coming into the hit line(so at the most 41.7 ms until the note hits the center of the hit line, or at the most of 41.7 ms after it's passed the hit line)

**Specs**

The screen is 1600x900 pixels

12 lanes

Hit lane y coordinate(This is the y coordinate of where the note needs to hit): **712**

Lane x coordinates(This is the center of each lane at the hit line): **222, 326, 432, 536, 641, 748, 850, 958, 1060, 1161, 1270, 1370**

Detect y coordinate(This is the highest coordinate you can look above the hit line, as the lanes stem outwards from the top): **651**

**Identifying Notes**
The images of the notes are within this repo, but I did some color detection to help out. There are a total of 8 notes, 4 with the same color, which is part of the challenge, but others have unique ones. Each color is in hex format, and goes from the bottom of the note to the top. There's bound to be some possible variency, but these were the closest parts of data that I could gather. The background is fairly dark, but has no unified color:

Tap note: First 3 colors: **#2c6289, #49b6d0, #49b6d0** Main color: **#e3effe** Last 3 colors: **#bfa7f3, #9d89cf, #573f7a**

Hold note: First 3 colors: **#228566, #46d49a, #42e5a7** Main color of note: **#d6f9ef**, General color of the hold line(the highlighted part that tells you to keep holding: **#6dc8b3**, Last 3 colors of the first hold note: **#6ed3c8, #44998e, #2d7466** First 3 colors of the last hold note(if it ends with a hold note, and not a swipe): **#156c4f, #329971, #43c791**, last 3 colors of the last hold note: **#91e9de, #7dcec9, #154549**

Swipe notes(these often are at the end of a hold note, there's an arrow, but those are detactched and harder to identify): First 3 colors: **#9c5f7a, #e99dc5, #fdacd9** Main color: **#fef1f3** Last 3 colors: **#fecad4, #f2bec6, #ab787e**

Trace notes: First 3 colors: **#06493d, #438974, #438974** Main color of note: **#5fe3b6**, General color of the hold line(the highlighted part that tells you to keep holding: **#519e88**, Last 3 colors of the first hold note: **#49bfad, #319481, #0e7569**

Golden notes(These can be any of the other four): First 3 colors: **#a1914c, #c4b554, #f3ec6b** Main color: **#fffbca** Last 3 colors: **#fecc80, #f6c379, #bb8c4b**
