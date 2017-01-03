Gameboy Core Python
===================

.. image:: https://ci.appveyor.com/api/projects/status/hatnihg8ii76hc27?svg=true
    :target: https://ci.appveyor.com/project/nnarain/gameboycore-python

.. image:: https://img.shields.io/pypi/v/gameboycore.svg
    :target: https://pypi.python.org/pypi/gameboycore

.. image:: https://readthedocs.org/projects/gameboycore-python/badge/?version=latest
    :target: http://gameboycore-python.readthedocs.io/en/latest/?badge=latest

Python Bindings for `GameboyCore <https://github.com/nnarain/gameboycore>`_

Hello fellow developers!

GameboyCore is a python gameboy emulator, it is a library that makes the emulation process a whole lot easier.



# Installation,

`using pypi:`
    pip install gameboycore

# Usage,

Using gameboycore is as easy as py!  
Here are some examples:

```python
import gameboycore, pygame, sys

core = gameboycore.GameboyCore()
core.open("game.gb")

pygame.init()

w,h = 320,288
screen = pygame.display.set_mode((w,h))

def drawScanline(scanline,line):
    for i in range(len(scanline)):
        pixel = scanline[i]
        screen.fill((pixel.r,pixel.g,pixel.b),(i*w/160,line*h/144,w/160,h/144))

while True:
    core.update(2048) # Number of `steps` the emulated Z80 cpu makes.
    pygame.display.update()
```
