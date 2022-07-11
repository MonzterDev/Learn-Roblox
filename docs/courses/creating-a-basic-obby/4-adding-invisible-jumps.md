Currently we only have basic Jumps, but lets add some invisible ones to spice things up!

## Creating the Invisible Jump

We already created some basics Jumps, and we want to create our new Jumps with the **same size** & **shape**. Rather than creating entirely new Jumps, we'll **duplicate** our existing ones

1. Duplicate one of our existing Jump Parts
2. Rename the new Jump to "InvisibleJump"
3. Position the new Jump to the **right** of our **2nd Spawn Location**
4. Rotate the new Jump 90 degrees by using `Ctrl + R`
5. Set the `Transparency` property of the new Jump to `1`

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Invisible-Jump.png" alt="Roblox Game showcasing the new setup with an Invisible Jump">

## Adding more Invisible Jumps

Lets add 4 more Invisible Jumps which lead to a new Spawn Location checkpoint!

1. Duplicate the existing InvisibleJump Part
2. Position the new InvisibleJump slightly infront of the previous InvisibleJump
3. Repeat this process 3 more times, until you have a total of 5 InvisibleJump Parts

!!! info

    If you're having trouble lining your InvisibleJump Parts up, you can set their Transparency to 0 so you can temporarily see them.

    Remember to set their Transparency back to 1 once you finish lining them all up!

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-5-Invisible-Jumps.png" alt="Roblox Game showcasing the 5 new Invisible Jumps">

## Adding another Checkpoint

Since we now have 5 new challenging Jumps for the Player to cross, lets add a new Checkpoint at the end of them!

1. Duplicate the existing SpawnLocation2 Part
2. Position it slightly further than the furthest InvisibleJump Part
3. Set the `BrickColor` property to `Really Red`
4. Set the `TeamColor` property to `Really Red`
5. Set the `Name` property to `SpawnLocation3`

## Creating the new Team

Remember, we should create a new Team Object each time we add a new Checkpoint.

1. Duplicate the `Lime Green` Team
2. Set the `TeamColor` property to `Really Red` (Must be the same color as the Checkpoint's `TeamColor`)
3. Set the `Name` property to `Really Red`

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Respawn-Location-3.png" alt="Roblox Game showcasing the 3rd Checkpoint">
