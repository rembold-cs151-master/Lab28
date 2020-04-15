# Lab 28: Child's Play
##### April 15, 2020
---

We will be focusing on overriding Arcade's built in methods today to achieve drawing, animation, and mouse and keyboard control. Particular learning objectives will focus on:
- [ ] Creating a new game class that inherits from `arcade.Window`
- [ ] Overriding drawing and other useful methods to that class
- [ ] Getting and interpreting mouse clicks and typed keys

I'm letting you work in pairs today, so you can create your own groups on Github like last time if you want!

## Instructions
The goal for today is to create a simple clicking type game that might amuse a 4 year old, or maybe a cat (or maybe a college aged individual, I'm not judging!). The program will run be displaying a square on the screen. When the square is clicked, it will move to a different random part of the screen, and the process can be repeated. The program should not exit until the 'q' key is pressed.

#### Part A)
Create a class for your game that inherits from `arcade.Window`. Set up your `__init__` method to call the parent's `__init__` class to set up your usual window with some width, height, and title. You can also go ahead and define whatever background color you want your window to have here. Since you are going to be moving a target about the screen, I'd also suggest some other data attributes to define in the `__init__` method:
* `loc_x`: the x center location of your target. Start in the center of your window.
* `loc_y`: the y center location of your target. Start in the center of your window.
* `size`: the side length dimesions of your target. 100 is a good size.
* `color`: the color of your target. This ensures that if you want to change it, you'd only have to do so in one place. Choose whatever color makes your heart happy.
* `shrink`: a boolean toggle that will be initially `False` and we'll toggle it on or off to indicate if we want the target to be shrinking.

The go ahead and define a `on_draw` method with takes care of starting the render and then drawing a filled rectangle at the desired location, with the desired size and color.

Don't forget to actually *call* your class at the very bottom of your script. Then if you run it, you should get your box being drawn in the middle of the screen.
Create a class for the object that will represent your target. Initially include an `__init__` method and some sort of `draw` method to construct and actually draw the target to the screen. The target should be a 100 by 100 pixel square with some solid filled color. You can decide if you want its initial location to be passed in via arguments, always default to the middle of the screen, or be randomly assigned.

#### Part B)
Add a `on_key_press` method which will take care of closing and exiting the program if the 'q' key is pressed.

Now add as well a `on_mouse_press` method which will check to see if the location of a mouse-click is within the inside of your drawn square. If it is, set `self.shrink` to be `True` and print to the terminal "Good work!" so that you can be sure it is working. Test it a few times and make sure that clicking anywhere OUTSIDE the square gives you nothing, and clicking inside the square prints "Good work!" to the terminal.

#### Part C)
Now to make it more interesting! Add an `on_update` method which which first checks to see if `self.shrink` is `True`. If it is, then decrement the current size of your square by some amount (5 seems good).

The add code that checks to see if the size is smaller than 0. If it is, stop the shrinking, set the target back to the original size, and randomly move the target to some new location within the window. Using the random library will probably help with coming up with a new location for the target.

And now you can play!

Feel free to add any other features you might want! Maybe a score tracker for how many times you've clicked? Maybe you want changing colors? At this point, feel free to play around and add anything extra you might want or just turn it in as it is.
