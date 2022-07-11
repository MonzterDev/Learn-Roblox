Whenever a player passes through a certain amount of Jumps, we should add a Checkpoint, which will change their respawn location if they fall.

## Creating a new Spawn Location

### Adding the Spawn Location

Similar to how we added our first Jump Part, we'll do the same process to add a Spawn Location Part!

1. Hover over Workspace and towards the right, click the `➕` Icon
2. Search for OR click "SpawnLocation"

### Customizing the Spawn Location

1. Position the new Spawn Location part towards the end of our current Jumps
2. Set the `BrickColor` property to `Lime Green`
3. Set the `AllowTeamChangeOnTouch` property to `true`
4. Set the `Neutral` property to `false`
5. Set the `TeamColor` property to `Lime Green`
6. Set the `Name` property to `SpawnLocation2`

Whenever a Player touches the Spawn Location part, their Team will be changed to our define `TeamColor` which is `Lime Green`. When we set `Neutral` to `false`, this now only allows Players of the defined `TeamColor` to respawn at that location.

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Respawn-Location-2.png" alt="Roblox Game showcasing the new SpawnLocation">

## Setting up the Player's Team

Since we just added another SpawnLocation, we must assign the Player a default **Team**, and modify the first SpawnLocation.

**Teams** are a basic service provided by Roblox, which allows us to easily group Players together and do certain things for each team, like set their respawn location.

1. Within the **Explorer** locate the **Teams** Service
2. Add a new Team Object to the **Teams** Service
3. Set the `AutoAssignable` property to `true`
4. Set the `TeamColor` property to `White`
5. Set the `Name` property to `White`

<img src="/img/courses/creating-a-basic-obby/Roblox-Studio-Obby-Teams-Service.png" alt="Roblox Studio Teams Service">

## Modifying the Origianl Spawn Location

Since we've setup the default **Team**, we must modify the original SpawnLocation Part which will set the Player's first respawn location.

1. Select the original SpawnLocation Part
2. Set the `Neutral` property to `false`
3. Set the `TeamColor` property to `White`

!!! important

    The default **Team**'s `TeamColor` must match the **SpawnLocation**'s `TeamColor`, otherwise no spawn location will be set for the Player

## Adding Additional Teams

Each time we add a new Checkpoint, we should add a new Team since it's displayed in the Leaderstats for everyone to see. Lets add a new Team for our first Checkpoint.

1. Add a new Team Object to the **Teams** Service
2. Set the `AutoAssignable` property to `false`
3. Set the `TeamColor` property to `Lime Green` (Must be the same color as the Checkpoint's `TeamColor`)
4. Set the `Name` property to `Lime Green`
