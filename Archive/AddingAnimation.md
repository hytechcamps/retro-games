This challenge was originally added to the end of the [code-along](../CodeAlong.md) activity. 

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