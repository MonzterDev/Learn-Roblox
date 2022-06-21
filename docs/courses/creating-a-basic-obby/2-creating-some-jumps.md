Lets add some **jumps** which lead to a new **checkpoint** for us to reach!

## Removing the Baseplate

We should delete the part called "Baseplate" from our Workspace, so a Player will fall to their death if they miss a jump!

1. Expand the Workspace Service inside of the Explorer
2. Click the Part named "Baseplate"
3. Right-Click and Click "Delete" OR press `Del` on your keyboard

Your Workspace should now look the same as the one below.
<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Cleaned-Workspace.png" alt="Roblox Workspace containing Camera, Terrain, & SpawnLocation">

## Creating a Jump Part

We'll create a simple Part, which will be a jump in our Obby. Once we create the Part with all the properties we like, we'll duplicate it and create more jumps!

### Adding a Part

1. Hover over Workspace and towards the right, click the `➕` Icon
2. Search for OR click "Part"

### Customizing the Part

1. Inside the Workspace, click the new Part object named "Part"
2. Set the `Anchored` property to `true` (Tick the box)
3. Resize the Part to be nearly as wide as the SpawnLocation
4. Move the Part away from the SpawnLocation requiring the player to jump to reach it
5. Rename the Part to "Jump"

!!! info

    * `Anchored` prevents the Part from being affected by gravity, so it will not fall down.
    * You can resize the part by going into the `MODEL` tab and selecting `Scale` OR press `Ctrl+3` on your keyboard
    * You can rename the part by Right-Clicking on the part and clicking "Rename" OR press `F2` on your keyboard

Your game should look similar to the image below.
<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Jump-1.png" alt="Roblox Game showcasing the SpawnLocation & Jump part near each other ">

## Adding more Jumps

We'll now add more Jumps to our game by using the Jump part we created.

1. Duplicate the Jump part
2. Move the new Jump further infront of the original Jump part
3. Repeat this 3 more times, until you have 5 Jumps

!!! info

    * You can duplicate the part by Right-Clicking on the part and clicking "Duplicate" OR press `Ctrl+D` on your keyboard

Your game should look similar to the image below.
<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Jumps.png" alt="Roblox Game showcasing the SpawnLocation & 5 Jumps ">

