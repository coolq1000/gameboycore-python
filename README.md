Gameboy Core Python
===================

![img] (https://ci.appveyor.com/api/projects/status/hatnihg8ii76hc27?svg=true)
![img] (https://img.shields.io/pypi/v/gameboycore.svg)
![img] (https://readthedocs.org/projects/gameboycore-python/badge/?version=latest)

* Python Bindings for [GameboyCore] (https://github.com/nnarain/gameboycore)  

Hello fellow developers!  
GameboyCore is a python gameboy emulator, it is a library that makes the emulation process a whole lot easier.



# Installation,

`using pypi:`
    pip install gameboycore

Usage,
------

Using gameboycore is as easy as py!  
Here are some examples:

Example #1 (Video: Yes, Audio: No, Input: No.) Description:( A basic example ):

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

def updateScreen():
    if pygame.event.poll().type == pygame.QUIT: pygame.quit(); sys.exit()
    pygame.display.flip()
    clock.tick()

core.registerScanlineCallback(drawScanline)
core.registerVBlankCallback(updateScreen)

clock = pygame.time.Clock()

while True:
    fps = clock.get_fps()
    core.update(2048) # Number of `steps` the emulated Z80 cpu makes.
    pygame.display.set_caption(str(int(fps)))
```

Example #2 (Video: Yes, Audio: No, Input: Yes.) Description:( Another basic example ):

```python

```

More examples may come, documentation is still under heavy development.

<sub>gameboycore was originally and currently created and maintained by Nnarain, documentation created by Rohan (coolq).</sub>
<sub>Last updated 1/7/2017.</sub>
