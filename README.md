# libwinmedia-py
A Python port of libwinmedia, a tiny high-level media playback library for C++.

# Requirements & dependencies
This library DOES NOT depend on any Python library, that isn't included in standard library...

But it depends on C++ code, thus a .dll file (on Windows) or a .so file (on Linux) must be located in PATH

# Simple start
```py
import libwinmedia

# This creates a Player instance
player = libwinmedia.Player(1000, False)

# This creates media instance
media = libwinmedia.Media(1000, "https://archive.org/download/Kalimba.mp3_377/Kalimba.mp3")

# This provides player a media instance
# Normally this command autostarts playing, which you can change using autostart parameter
player.open(media, autostart=True) # autostart is default to True
```

When you stop using libwinmedia (before you stop program), I recommend disposing instance to free up some system resources
```py
player.dispose()
media.dispose()
```

## Setting parameters & getting current data
You can get parameters using setters & getters.

Example:
```py
>> player.volume
100
>> player.volume = 60
>> player.volume
60
```

Setters & getters in Player instance are:
- looping
- autoplay
- audio_balance
- rate
- volume
- position

# Documentation
This repository includes an example file, called example.py

In it, there is used almost every function this library provides...

Every function is documented (in code or in this file).

## Seek (change position)
Player instance provides 2 options for seeking (rewinding)

Position is in milliseconds, so if you want it in seconds, divide it by 1000

One is by using setter, eg.
```py
>> player.position = 1000
```

Second one is by using function
```py
>> player.seek(1000)
```
