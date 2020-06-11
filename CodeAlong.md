# Retro Games: Simple Platformer Code-Along
Learn about MakeCode Arcade and add some code to start building a platformer game!

## MakeCode Arcade Introduction
Play through the [jumpy platformer](https://arcade.makecode.com/71044-22408-12308-23475) for an idea of what is possible with MakeCode Arcade. This editor uses block-based code (or JavaScript) to create retro games. The games can even be ported to physical devices. It may take a long time to build something like the jumpy platformer, but getting started with a simple platformer is not as difficult!

Go to https://arcade.makecode.com/#editor to start working on a new MakeCode Arcade project. The editor looks like this:

![](https://i.imgur.com/qE7JRFy.png)

### Page Sections
- **Game Preview:** This pane on the left is where the developer can test out the game.
- **Block Selection:** This pane in the middle is where the blocks live. They can be dragged to the **Code** section to create the program.
- **Code:** This pane on the right is where the code for the program lives. Drag blocks from the **Block Selection** section into this section to create code.

## Setting a Background Color
For the first block of the game, set the background color.

1. In the **Block Selection** section, click on "Scene" and find the `set background color to` block  
    ![](https://i.imgur.com/DIxGkJy.png)
1. Click on the `set background color to` block, and drag it into the `on start` block  
    ![](https://i.imgur.com/7mUHPf3.png)
1. Click on the blank spot in the background color block, and select a color for the background  
    ![](https://i.imgur.com/EBSSte0.png)
1. The game preview should automatically update, and the background should be the proper color!

## Creating the Main Character
The first thing the game needs is a main character for the player to control!

1. In the **Block Selection** section, in the "Sprites" category, click and drag the red `set mySprite to` block under the background color block  
    ![](https://i.imgur.com/TK6AUAx.png)
1. In the `set mySprite to` block, click the drop-down arrow on `mySprite`, and click "Rename variable..."  
    ![](https://i.imgur.com/DvJnknn.png)
1. Set the variable name to "Main Character"
    - _Note: If the main character has a name, this could be their name instead! Just make sure to use the name when referencing the `Main Character` sprite_
1. Click on the blank space next to "sprite" in the `set sprite` block to open the Sprite Editor  
    ![](https://i.imgur.com/kudM2w5.png)
1. Draw a sprite image for the main character, and then click the green "Done" button in the bottom right
1. The game preview should automatically update, and the main character sprite should appear!

### _Side-Note: Variables_
In computer science, **variables** are containers for data. In MakeCode Arcade, variables can hold things like sprites, images, hit points, the player's score... almost anything!

## Moving the Main Character
The main character should be able to move left and right, as in any other platformer.

1. From the "Controller" category, click and drag a red `move mySprite with buttons +` block under the `set sprite` block  
    ![](https://i.imgur.com/97MwAaU.png)
1. In the `move` block, click the drop-down arrow on `mySprite`, and select `Main Character`
1. In the game preview, notice that it is possible to move left and right, but also up and down
1. To prevent the main character from moving up and down, click the `+` in the `move` block, and set the `vy` to `0`
    - This sets the _vertical speed_ of the main character sprite to `0`
1. Test out the game in the game preview again, and verify that the main character only moves left and right!

### _Side-Note: The Cartesian Plane - Up, Down, Left, Right_
The MakeCode Arcade screen is a lot like a Cartesian plane. The **x** axis moves left and right (horizontally), and the **y** axis moves up and down.

## Creating a Game Map
Now the main character can move, but they won't have much to do without a map!

1. In the "Scene" category, under the "Tiles" header, click and drag a `set tilemap to` block to right under the `set background color` block  
    ![](https://i.imgur.com/LPZlxa3.png)
1. Click the blank spot in the `set tilemap to` block to open the Tilemap Editor

![](https://i.imgur.com/M8kOvQQ.png)

1. In the bottom left, set the **Map Size** to `16`x`8`
    - Zoom out if necessary using the magnifying glass icons in the bottom right
1. In the **Tile Selector** section, select a tile for the ground
1. In the **Current Map** section, draw ground covering the bottom part of the map  
    ![](https://i.imgur.com/NLoxb1h.png)
1. Select the **Wall Editor** tool  
    ![](https://i.imgur.com/k761HmG.png)
1. Draw over the ground with the wall editor - this will make the ground stop the main character from falling  
    ![](https://i.imgur.com/0ON40yM.png)
1. Click the "Done" button, and see the map appear in the game preview!

## Adding Gravity
Now that the main character has somewhere to land, add gravity to the game!

1. In the "Sprites" category, click and drag a `set mySprite x to 0` block under the existing blocks in `on start`  
  ![](https://i.imgur.com/fo4305C.png)
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. Click the drop-down arrow next to `x` and select `ay (acceleration y)`
1. Change the `0` to `400`
    - This will make the main character accelerate downward (fall)
1. Notice that in the updated game preview, the main character can move to the right off the screen - the camera does not follow the sprite
1. In the "Scene" category, scroll down to find a `camera follow sprite` block, and click and drag it under the existing blocks in `on start`
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. Play the game in the game preview and verify that the main character falls, and the camera follows them!

## Making the Main Character Jump
In almost every platformer, the main character has the ability to jump.

1. In the "Controller" category, click and drag an `on A button pressed` into the **Code** section
1. Click the drop-down arrow next to `A` and select `up`  
    ![](https://i.imgur.com/mPPXEEM.png)
1. In the "Sprites" category, click and drag a `set mySprite x to 0` block into the `on up button pressed` block
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. Click the drop-down arrow next to `x` and select `vy (velocity y)`
1. Change the `0` to `-200`
    - This will make the main character star moving upward (jump)
1. In the game preview, notice that the main character can jump multiple times, which should not be possible

### Single Jump
The main character should only be able to jump when they are on the ground.

1. In the "Logic" category, click and drag an `if true then` block into the `on up button pressed` block
1. In the "Scene" category, scroll down to "Collisions" and click and drag an `is mySprite hitting wall left` into the `true` in the `if` block
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. Click the drop-down arrow next to `left` and select `bottom`
1. Click and drag the `set Main Character vy to -200` block into the `if` block
1. Play the game preview and verify that the main character can only jump when they are on the ground!

![](https://i.imgur.com/gfnc4yS.png)

### _Side-Note: Conditionals_
In computer science, **conditionals** let the program do different things depending on the current situation. In this example, the main character can only jump _if_ they are on the ground. Conditionals are incredibly useful for creating dynamic programs!

## Winning the Game
For this to be an actual game, there should be a way to win!

1. Find the `set tilemap to` block, and click on the tilemap to open the Tilemap Editor  
    ![](https://i.imgur.com/wqw8HfF.png)
1. In the Tile Selector section on the left, find a good tile for the winning tile
    - The player will win the game if the main character overlaps with this tile
1. Select the tile, and select the pencil tool  
    ![](https://i.imgur.com/5MLnNgZ.png)
1. Place the winning object tile somewhere on the tilemap
1. Click the green "Done" button in the lower right to exit the Tilemap Editor
1. Back in the code, in the "Scene" category, scroll down to Tiles and find the `on sprite of kind Player overlaps at location` block
1. Click and drag the `overlaps` block to a blank spot in the **Code** section
1. Click the drop-down arrow next to `overlaps` and select the winning object tile
1. In the "Game" category, click and drag a `game over` block into the `overlaps` block
1. Click the `LOSE` switch to flip it to `WIN`
1. Play the game in the game preview to verify that reaching the winning object will win the game!

![](https://i.imgur.com/SJvBqML.png)

## Losing the Game
The game will not be very interesting if there is no way to lose. Add an obstacle that will end the game for the player.

1. Find the `set tilemap to` block, and click on the tilemap to open the Tilemap Editor
1. In the Tile Selector section on the left, click on "My Tiles"  
    ![](https://i.imgur.com/CWzSDP3.png)
1. Click the "+" to create a new tile for an obstacle  
    ![](https://i.imgur.com/9I6lDav.png)
1. In the Tile Editor, draw an obstacle that will end the game (e.g. spikes, fire, an enemy)
1. Place the obstacle tile in several places on the tilemap
1. Click the green "Done" button in the lower right to exit the Tilemap Editor
1. Back in the code, in the "Scene" category, click and drag another `overlaps` block into the **Code** section
1. Click the drop-down arrow next to `overlaps` and select the obstacle tile
1. In the "Game" category, click and drag a `game over` block into the new `overlaps` block
1. Click the `+` on the `game over` block to reveal additional options
1. Click the drop-down arrow next to `confetti` and select a new game-ending animation (like `melt`)
1. Play the game in the game preview to verify that touching an obstacle will lose the game!

![](https://i.imgur.com/AN7mNnx.png)

## Code
At this point, the project should look something like this: https://makecode.com/_b6V3sP1w5DgL

## OPTIONAL CHALLENGE: Adding an Animation
In most platformers, the main character will animate whenever they move. Add a basic two-frame animation to the main character sprite!

### Creating the Animation
The first step to animate a sprite is creating the actual frames for the animation.

1. In the **Block Selection** section, click "Advanced" and then click "+ Extensions" at the bottom
1. Click the `animation` extension to load it into the project  
    ![](https://i.imgur.com/qpQap5M.png)
1. In the new "Animation" category, click and drag a red `set anim to` block into the `on start` block
1. Change the `1000` in the `set anim to` block to `200`
1. In the "Animation" category, click and drag a green `add frame to anim` block into the `on start` block at the bottom
1. From the `set Main Character to sprite` block, click and drag the sprite image into the blank spot after `add frame`  
    ![](https://i.imgur.com/DzodVFj.png)
1. In the "Animation" category, click and drag another `add frame to anim` block into the `on start` block at the bottom
1. From the `set Main Character to sprite` block, click and drag the sprite image into the next blank spot after `add frame`
1. Click the image in second `add frame` block to open the Image Editor
1. Edit the image so it will become the second frame of the Main Character walking animation
1. From the "Animation" category, click and drag an `attach animation anim` block into the `on start` block at the bottom
1. Click the drop-down arrow next to `mySprite` and select `Main Character`

![](https://i.imgur.com/OFjGAzS.png)

>Note: Nothing will change after creating the animation. It needs to be activated first!

### Activating the Animation
The main character should only animate while walking. Add code to activate the animation whenever the player moves the main character.

1. In the "Game" category, click and drag a purple `on game start` block into the **Code** section
1. In the "Logic" category, click and drag an `if` block into the `on game start` block
1. In the "Logic" category, click and drag a `0 = 0` block into where the `true` is in the `if` block
1. In the "Sprites" category, click and drag a `mySprite x` block into the first `0` in the `0 = 0` block
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. Click the drop-down arrow next to `x` and select `vx (velocity x)`
    - This `if` block will be **true** if the main character has no horizontal speed (i.e. they are standing still)
1. In the "Sprites" category, scroll down and click and drag the `set mySprite image to` block into the `if` block
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. From the original `set Main Character to sprite` block, click and drag the sprite image into the next blank spot after `set Main Character image to`
1. Click the `+` at the bottom of the `if` block to add an `else` section
1. From the "Animation" category, click and drag an `activate animation` block into the `else`
1. Click the drop-down arrow next to `mySprite` and select `Main Character`
1. In the game preview, move the main character and verify that the animation activates only when the character is moving!

![](https://i.imgur.com/yGf644g.png)