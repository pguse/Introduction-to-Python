# Introduction to Pygame

Pygame is a graphics library for programming graphical applications in Python.  We are going to begin this introduction by drawing a single pixel on the screen.  To begin, we need to install the Pygame library.  In the terminal, type the following.

```
$ pip install pygame
```

You don't need to type the dollar sign.  It is just a marker for the command line.  The **pip **program should download Pygame to your computer.  If no error messages appear, Pygame should be installed.  To test this, enter the Python interpreter and import Pygame as follows.

![](/assets/importPygameTest.JPG)If there are no error messages, Pygame should be installed properly.

## A First Program

A computer screen is made up of an array of tiny dots called pixels.  We are going to  write a program to draw **one pixel**.  In the Visual Studio Code editor, type in the following program.  **Do not copy and paste**.  It is much better to type it out and correct your own syntax errors.

```
# first, let Python know we're using pygame
import pygame

# needed to draw pixels 
import pygame.gfxdraw

# make sure pygame gets set up
pygame.init()

# Set width and height of our screen we'll make next
screenWidth = 800
screenHeight = 800 

# create a screen to draw to with screenWidth and screenHeight
screen = pygame.display.set_mode((screenWidth, screenHeight)) 

# white is red, green, and blue light in equal amounts
# at maximum brightness (255 for Pygame)
white = (255,255,255) 

# black is an absence of light
black = (0,0,0) 

# Let's make something so we know when to stop
running = True

# Let's run while running is still true
while running: 

    # Fill the screen with black
    screen.fill(black) 

    # Draw a single white pixel in the middle of the screen
    pygame.gfxdraw.pixel(screen, screenWidth // 2, screenHeight // 2, white) 

    for event in pygame.event.get():
        # if you try to quit, let's leave this loop
        if event.type == pygame.QUIT: 
            running = False # lets loop finish 

    # this is how we update the screen we've been drawing on.
    pygame.display.flip()
```

## Colours

One thing you'll notice in the code above is that colours are defined using a set of 3 numbers.  These values represent the intensity of **Red**, **Green**, and **Blue **light in each pixel.  Each value can **range from 0 to 255**, with 0 representing 'off' and 255 representing full intensity.  The combination \(0,0,0\) represents **black **because all colours are off, while \(255,255,255\) represents **white **because all colours are fully on.  To investigate other colours using the RGB model of colour, click on this [link ](https://www.rapidtables.com/web/color/RGB_Color.html)or just do an internet search for 'RGB Color'.

## Creating a Line

To create a line, we can using a loop to plot lots of pixels with different x-coordinates as follows.

```
while running: 

    screen.fill(black) 

    # Our for loop, for the width of the screen
    for i in range(0, screenWidth):
      # Our pixel draw function uses i to know the current value
      pygame.gfxdraw.pixel(screen, i, screenHeight // 2, white) 

    for event in pygame.event.get():
        if event.type == pygame.QUIT: 
            running = False

    pygame.display.flip()
```

When you run this program you should see a horizontal white line positioned in the middle of the screen.

## Next Steps

* How would you plot a vertical line?
* How would you plot a diagonal line?  How would you plot the other diagonal line?

## Challenge

Modify the program so that it creates the following pattern.

![](/assets/challengePygameIntro.png)

