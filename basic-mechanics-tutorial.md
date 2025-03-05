# Basic Game Mechanics

## Arcade Tutorial @showdialog

During this tutorial you will learn how to create a simple MakeCode Arcade game with some basic game mechanics!


## Step 1 @fullscreen

**Welcome!** Let's make a simple game. Open the `||sprites:Sprites||` category and grab a `||sprites:set mySprite||` block and add it to your `||loops:on start||`.

```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
```

## Step 2

Click on the empty image oval, then click **Gallery** and select your hero sprite, click **Done**.
Click on **mySprite** and select **Rename variable**. Rename you sprite to an appropriate name, since mine is a duck, I'll name it duck.

```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
```

## Step 3

Open the `||controller:Controller||` category in the Toolbox and grab a `||controller:move mySprite with buttons||` block.
Change **mySprite** to your sprite's name (mine is duck).
Connect that block below your `||sprites:set mySprite||` block in the `||loops:on start||` block.



```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
```

## Step 4

Let's make it so our character can't move off the screen next.
Open the `||sprites:Sprites||` categroy in the Toolbox and grab a `||sprites: set mySprite stay in screen on||` block and place it below the `||controller:move mySprite with buttons||`.
Change **mySprite** to the name of your sprite.
Now when you move to the edge of the screen your sprite stays visible!

```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
duck.setStayInScreen(true)
```

## Step 5

Now let's make it so there is an enemy to avoid.
Make a new sprite using the `||sprites:set mySprite to sprite of kind Player||` block.
Pick an image from the Gallery and change the sprite's kind from **Player** to **Enemy**.
Rename your sprite to an appropriate name by clicking on **mySprite**, then **Rename variable**.
I named mine ghost.

```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
duck.setStayInScreen(true)
let ghost = sprites.create(img`
    ........................
    ........................
    ........................
    ........................
    ..........ffff..........
    ........ff1111ff........
    .......fb111111bf.......
    .......f11111111f.......
    ......fd11111111df......
    ......fd11111111df......
    ......fddd1111dddf......
    ......fbdbfddfbdbf......
    ......fcdcf11fcdcf......
    .......fb111111bf.......
    ......fffcdb1bdffff.....
    ....fc111cbfbfc111cf....
    ....f1b1b1ffff1b1b1f....
    ....fbfbffffffbfbfbf....
    .........ffffff.........
    ...........fff..........
    ........................
    ........................
    ........................
    ........................
    `, SpriteKind.Enemy)
```

## Step 6

Our enemy also needs to be able to move so let's give it a starting position by adding `||sprites:set mySprite position to||` block.
Change **mySprite** to your enemy sprite's name.
Get a `||sprites:set mySprite velocity||` block from `||sprites:Sprites||` and add it under the set position block.
Change **mySprite** to the name of your enemy sprite.
**Velocity** is speed and direction. If you change the number for vx and vy your enemy will move in different directions and speeds.

```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
duck.setStayInScreen(true)
let ghost = sprites.create(img`
    ........................
    ........................
    ........................
    ........................
    ..........ffff..........
    ........ff1111ff........
    .......fb111111bf.......
    .......f11111111f.......
    ......fd11111111df......
    ......fd11111111df......
    ......fddd1111dddf......
    ......fbdbfddfbdbf......
    ......fcdcf11fcdcf......
    .......fb111111bf.......
    ......fffcdb1bdffff.....
    ....fc111cbfbfc111cf....
    ....f1b1b1ffff1b1b1f....
    ....fbfbffffffbfbfbf....
    .........ffffff.........
    ...........fff..........
    ........................
    ........................
    ........................
    ........................
    `, SpriteKind.Enemy)
ghost.setPosition(0, 0)
ghost.setVelocity(50, 50)
```


## Step 7

Uh oh! Our enemy disapeared off the screen. What do we need to add to fix that?


```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
duck.setStayInScreen(true)
let ghost = sprites.create(img`
    ........................
    ........................
    ........................
    ........................
    ..........ffff..........
    ........ff1111ff........
    .......fb111111bf.......
    .......f11111111f.......
    ......fd11111111df......
    ......fd11111111df......
    ......fddd1111dddf......
    ......fbdbfddfbdbf......
    ......fcdcf11fcdcf......
    .......fb111111bf.......
    ......fffcdb1bdffff.....
    ....fc111cbfbfc111cf....
    ....f1b1b1ffff1b1b1f....
    ....fbfbffffffbfbfbf....
    .........ffffff.........
    ...........fff..........
    ........................
    ........................
    ........................
    ........................
    `, SpriteKind.Enemy)
ghost.setPosition(0, 0)
ghost.setVelocity(50, 50)
// @highlight
ghost.setStayInScreen(true)
```

## Step 8

Let's also make it so our enemy keeps moving around the screen after it reaches the edge.
Open ``||sprites:Sprites||` and grab a `||sprites:set mySprite bounce on wall||`.
Change **mySprite** to the name of your enemy sprite.
Now, you enemy should move on its own and bounce around the screen!


```blocks
let duck = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
controller.moveSprite(duck)
duck.setStayInScreen(true)
let ghost = sprites.create(img`
    ........................
    ........................
    ........................
    ........................
    ..........ffff..........
    ........ff1111ff........
    .......fb111111bf.......
    .......f11111111f.......
    ......fd11111111df......
    ......fd11111111df......
    ......fddd1111dddf......
    ......fbdbfddfbdbf......
    ......fcdcf11fcdcf......
    .......fb111111bf.......
    ......fffcdb1bdffff.....
    ....fc111cbfbfc111cf....
    ....f1b1b1ffff1b1b1f....
    ....fbfbffffffbfbfbf....
    .........ffffff.........
    ...........fff..........
    ........................
    ........................
    ........................
    ........................
    `, SpriteKind.Enemy)
ghost.setPosition(0, 0)
ghost.setVelocity(50, 50)
ghost.setStayInScreen(true)
ghost.setBounceOnWall(true)
```


## Step 9

But nothing happens when our enemy touchs the player sprite, so let's fix that next.
Grab a `||sprites:on sprite of kind player overlaps other sprite of kind player||` block from the `||sprites:Sprites||` category.
This block is a seperate event so it does not connect to the code we already have.
Change the second kind **Player** to **Enemy**.
Now, let's make it so the player loses a life when the enemy catches them.
Open the `||info:Info||` category and grab a `||info:change life by -1||` and place it inside the overlap event block.


```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
})
```

## Step 10
Test your game and let the enemy hit the player sprite.
What happened? The game instantly ended!
Because the two sprites are still touching the player continues to lose lives, so we need to move the enemy sprite away from the player sprite after they overlap.
We need to reset the enemy's position using the **set position** block.
Find your **set enemySprite position ** block, duplicate it (right-click or two-finger tap).
Put that block inside the overlap event block.
Test your game again, is it working better now?

```blcoks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    ghost.setPosition(0, 0)
})
```


## Step 11

Just avoiding an enemy isn't very much fun, so let's add something to collect!
In MakeCode Arcade we use the sprike kind *food* as a collectible item, it does not *have* to be a food item, but can be if you want!
Let's make a food sprite spawn into our game every few moments.
Go to the `||game:Game||` category and get a `||game:on game update every 500 ms||` event block.
This is another seperate event, so it will also not connect to your other code blocks.
You can change the **500** to the amount of milliseconds you want, consider how often you want the sprite to spawn. 500 ms is half a second.
Make another new sprite using the `||sprites:set mySprite of kind Player||` block.
Pick your sprite's image from the gallery and give it an appropriate name by renaming the variable.
Then change your sprite's kind from **Player** to **Food**.

```blocks
let taco: Sprite = null
game.onUpdateInterval(500, function () {
    taco = sprites.create(img`
        . . . . . . . e e e e . . . . . 
        . . . . . e e 4 5 5 5 e e . . . 
        . . . . e 4 5 6 2 2 7 6 6 e . . 
        . . . e 5 6 6 7 2 2 6 4 4 4 e . 
        . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
        . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
        . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
        e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
        e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
        e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
        e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
        e 5 e c 5 4 5 4 5 5 5 e e . . . 
        e 5 e e 5 5 5 5 5 4 e . . . . . 
        4 5 4 e 5 5 5 5 e e . . . . . . 
        . 4 5 4 5 5 4 e . . . . . . . . 
        . . 4 4 e e e . . . . . . . . . 
        `, SpriteKind.Food)
})
```


## Step 12

Grab a `||sprites:set mySprite postion||` block and place it below your food sprite block.
Change **mySprite** to the name of your food sprite.
We want our food sprite to appear in different locations each time it spawns so we will need to use **pick random**.
Open the `||math:Math||`` category and grab a `||math:pick random number from 0 to 10||` block and place it in the x 0 on the **set position** block.
Duplicate the **pick random** and place it in the y 0.
On the **pick random** for the x-coordinate use 10 to 150.
On the **pick random** for the y-coordinate use 10 to 110.
Using these cooridiate ranges will keep our food sprite visiable on the screen when they spawn.

```blocks
game.onUpdateInterval(500, function () {
    taco = sprites.create(img`
        . . . . . . . e e e e . . . . . 
        . . . . . e e 4 5 5 5 e e . . . 
        . . . . e 4 5 6 2 2 7 6 6 e . . 
        . . . e 5 6 6 7 2 2 6 4 4 4 e . 
        . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
        . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
        . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
        e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
        e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
        e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
        e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
        e 5 e c 5 4 5 4 5 5 5 e e . . . 
        e 5 e e 5 5 5 5 5 4 e . . . . . 
        4 5 4 e 5 5 5 5 e e . . . . . . 
        . 4 5 4 5 5 4 e . . . . . . . . 
        . . 4 4 e e e . . . . . . . . . 
        `, SpriteKind.Food)
    taco.setPosition(randint(10, 150), randint(10, 110))
})
```

## Step 13


Now we need to set up the interaction between our player sprite and our food sprite so the player can collect it.
For this we need to add another `||sprites:on sprite of kind Player overlaps otherSprite of kind Player||` event block.
Remember, this is a seperate event and therefore does not connect to any of our other code.
This time change the otherSprite's kind to **Food**.
When our player sprite touches the food sprite, the food sprite needs to get collected.
We can do this by destroying the food sprite that got touched!
Add a `||sprites:destroy mySprite||` block to the overlap event block.
Drag the **otherSprite** block from the overlap block into the **mySprite** section of the destroy block, this will make it so only the sprite that got touched gets destroyed.
We also want to get points when we collect our food sprites.
Add a `||info:change score by 1||` from the `||info:Info||` category under the `||sprites:destroy mySprite||` block in the overlap event block.
Test your game, you should be able to collect the food sprites as they appear!

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    sprites.destroy(otherSprite)
    info.changeScoreBy(1)
})
```


## Step 14

Did everything work? Great! You're ready to submit your project in Canvas!

**Bonus**
If you have time, add some additional features:
- Make the enemy steal the food sprites from the player using another sprites overlaps event
- Make it harder by having more enemies spawn every so often using another on game update ms
- add a countdown timer from the info category

```blocks
info.startCountdown(10)
```
