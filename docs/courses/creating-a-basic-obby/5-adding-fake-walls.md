Lets add some walls, which Player can walk through, to complement our Jump obstacles!

## Creating the Fake Wall

We'll create a basic wall, which the Player will think they must jump around it, but really they can walk right through it!

1. Create a new Part within the Workspace
2. Rename the new Part to "FakeWall"
3. Resize the wall so it's at least taller than the Player
4. Resize the wall to it's as wide as a Jump
5. Set the `Anchored` property of the Part to `true`
6. Set the `CanCollide` property of the Part to `false`
7. Set the `Transparency` property of the Part to `0.2`

!!! info

    Disabling collisions on a Part will allow other Parts (in this case a Player) to move through it!


<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Fake-Wall.png" alt="Roblox Game showcasing the Fake Wall">

## Adding Jumps

Lets use the 5 jumps between SpawnLocation and SpawnLocation2 to easily make jumps for our newest path!

1. Select the 5 jumps between SpawnLocation and SpawnLocation2
2. Duplicate these selected jumps using `Ctrl + D`
3. Move the duplicated jumps to the latest checkpoint

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Duplicated-Jumps.png" alt="Roblox Game showcasing the new Jumps">

## Inserting the Fake Wall

Now that we have our Jumps positioned, lets create more FakeWalls and add them between the Jumps!

1. Move the FakeWall between SpawnLocation3 and its first Jump
2. Duplicate the FakeWall and move it between the next Jumps
3. Repeat this proccess until all Jumps have a FakeWall between them

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Fake-Wall-Between-Jumps.png" alt="Roblox Game showcasing the Fake Walls positioned between the new Jumps">

## Adding the Next Checkpoint

1. Duplicate the existing SpawnLocation3 Part
2. Position it slightly further than the furthest Jump we just setup
3. Set the `BrickColor` property to `New Yeller`
4. Set the `TeamColor` property to `New Yeller`
5. Set the `Name` property to `SpawnLocation4`

Remember, we should create a new Team Object each time we add a new Checkpoint.

1. Duplicate the `Really Red` Team
2. Set the `TeamColor` property to `New Yeller` (Must be the same color as the Checkpoint's `TeamColor`)
3. Set the `Name` property to `New Yeller`

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Respawn-Location-4.png" alt="Roblox Game showcasing the 4th Checkpoint">
