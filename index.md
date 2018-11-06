## Hi, I am learning Pygame and I am horrible!

I just deleted a repo on GitHub because I realised it did not look that good, so yeah... anyways after fiddeling around I got something working and had mistaken it for the repo on Github and ???? you know I replaced instead of deleted the thing which made me so happy, and now I will have to do it again, and this time I will document it!

### Lets go!

The recourses that I used are here: 
  [Scroll all the way down to putting it all together!!! (click)](https://www.pygame.org/docs/tut/MoveIt.html)
  Note: While the stuff in the box is all done in the python [IDLE (whoa! I learned something today!!!)](https://docs.python.org/2/library/idle.html) we can still use most of whats there as a refference for our little project!
  

```markdown
screen = pygame.display.set_mode((640, 480))
```
Ok, first line we can probably integrate into the project, so we will do just that!

Create a new directory, in my case its going to be pygame and lets get cracking!

```markdown
# Open a terminal in the new directory and type
git init 
# use your texteditor of choice
atom game.py 
```
Ok first things first!

```markdown
# in game.py
import sys
import pygame

pygame.init()

while 1:
  break

pygame.quit()
```
Those two imports at the beginning can be usefull, especially pygame, but sys you sometimes need without even knowing, I highly suggest you import sys everywhere because of print, you can use print in any class and it will be displayed on the console which is very usefull when debugging, or just finding the mistake, whatever you call it!

That brings us to the next topic, the structure of our code! Well, for our entrypoint of our little game, or for this little framework, its not an engine, allthough we are technically building engine tech, but I want to bridge the gap, you want to get a game finished after all!

Also, I am way focused on getting a map going that is scrollable with your input! Because if we can cover these topics you will know how to do the rest!

Add the line as I allready tolled you! We will keep the script nature of the entry point like this, no main needed. Also, there will be no need for a tilemap, we will work with single image files. 

```markdown
# in game.py
import sys
import pygame

pygame.init()

# this is the way pygame teaches you to use pygame.display, and I dont know any better!
screen = pygame.display.set_mode((640, 480))

while 1:
  break

pygame.quit()
```
phew ok, we will load in an image, like so

```markdown
bkgTile = pygame.image.load('bkgTile.png')
```

Nothing to worry here, the newest version of pygame supports a lot more image data formats and it will not spazz out when coordinates are negative, keep this in mind when moving forward... or not, no worries!

Add the line to game.py like so, and create your background tile for your game!

```markdown
# in game.py
import sys
import pygame

pygame.init()

# this is the way pygame teaches to use pygame.display, and I dont know any better!
screen = pygame.display.set_mode((640, 480))
# you can add a folder for all the graphics ;)
bkgTile = pygame.image.load('bkgTile.png')

while 1:
  break

pygame.quit()
```
Heres a tip I found out by accident, if you dont specify any background color, which is not necessary at all then pygame will choose a color from your tile and just use that, and I think it uses the color which is more prevelant in the image, so yeah, maybe that might be helpfull in the future for other stuff, but not now! I havent tested it for other collors by the way, but it was a curious enough color that led me believing just that!

## Lets just draw something tiled!

Lets create a tiled background just from this image file alone, I suggest you make the size something between 32 and 64, can be larger can be smaller, but stick to one size, this will make the process infinately easier, but nobody is stopping you!

What I mean is, if you choose the size of a single tile in the beginning you will not encounter any problems later on, we will be mainly hardcoding the game's structure and layout through code so having some predictible dimensions helps in that regard!

But if I am really honest, we can probably make it so that we just have to change the size variable(s) to change the dimensions of a single tile, by adding a tile count for width and height of the ground tile displayed, which is just the number of tiles displayed in the positive x and y axis we then create a tiled image displayed on the screen!

Ok so lets start!

```markdown
# in game.py
import sys
import pygame

pygame.init()
# we will organize our code a little bit before it gets too messed up
# make sure your image size is the same as the size we use to calculate the position of the tile!!!
size = 32
width = 20 
height = 30
# when we want to move eveything else should move too, right?
cameraMoveX = 0
cameraMoveY = 0
# we will need position variables that exist when the gameloop has completed one cycle, just to keep the structure simple you guys!
x = 0
y = 0

# this is the way pygame teaches to use pygame.display, and I dont know any better!
screen = pygame.display.set_mode((640, 480))
# you can add a folder for all the graphics ;)
bkgTile = pygame.image.load('bkgTile.png')

while 1:
  for x in width:
    screen.blit(bkgTile, (size*x, size*y))
  x = 0
  y = y +1
# call me crazy, the thing up there works!
# its time for some event handling
for event in pygame.event.get():
  if event.type == pygame.QUIT:
    sys.exit()

pygame.quit()

```
dont compile for now, you wont get stuff done, you will just delay the point where there is just nothing more to add! Very important! You are wasting engergy on trying to get it to work when you dont even have anything yet, thats not making you happy, deal with it when the time is ripe!

Tip #1: Allways code with refference, meaning use GOOGLE, or DOCKUMENTATION in every step and just dont care about compile errors, first we punch it in then we care about its internals! Especially starting out and with smaller tiny projects, it will make you more efficient! Who cares if you have to look stuff up! You are fine! Just stop! Get help!


### to be continued!


