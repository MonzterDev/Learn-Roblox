Replication is one of the most important systems to understand when Developing on Roblox or any network-based games!

## What is Replication

"The goal of replication is to ensure that all of the players in the game have a consistent model of the game state." - [0fps.net](https://0fps.net/2014/02/10/replication-in-networked-games-overview-part-1/#:~:text=The%20goal%20of%20replication%20is,games%20ultimately%20follow%20from%20it.)

The best example of replication is the default Character system in Roblox. Whenever a player moves around, their movements are sent to the **game's server** and then to all other players. This allows each player to see each other's movements in real-time!

``` mermaid
graph LR
  A[Player1] --> B{Server};
  B --> C[Player2];
  B --> D[Player3];
  B --> E[Player4];
```

## Examples of Replication

Roblox has quite a few systems which automatically replicate for us!

### Leaderstats

Do you know that little leaderboard you see at the top right corner of many games? That's referred to as the leaderstats.

The process of adding a Player to the leaderstats goes as follows:

1. Create a Folder named "leaderstats" and parent it to the Player
2. Create a NumberValue, give it a name, and parent it to the leaderstats Folder

Once you've done this, you can change the **value** of the NumberValue at any time, and that will be replicated to all players. See, you're not handling the replication, you're just modifying the value of an object and Roblox handles the rest.

### Workspace

Whenever a player joins the game, all the contents of the Workspace are replicated to the player. If you make any changes to the Workspace from the server, such as deleting or adding an object, this will automatically be replicated to all current and future players.

### Services

Many Services will instantly replicate their contents to the player upon joining and continue replicating to them as well.

* Workspace
* Players
* Lighting
* ReplicatedFirst
* ReplicatedStorage
* StarterGui
* StarterPack
* StarterPlayer
* SoundService
* Chat

## How to Replicate Ourselves

First, let's quickly lay out the basics of networking on Roblox. If you want a more thorough explanation, you can check out our [Networking article](#)!

Roblox has two **Remote** objects which enable communication between the Client (Player) & Server:

* **RemoteEvent**: Server -> Client | Client -> Server
* **RemoteFunction**: Server -> Client -> Server | Client -> Server -> Client

Now that we understand the basics, let's create a scenario that would require replication.

### Replication Usage Scenario

Let's say we have a Wave Defense game and we want to display the current wave to every player. For further clarification, we want to also notify the player of the current wave, each time it increases.

Currently, only the Server knows what the current wave is because it's stored and handled within a script there.

Let's say the script below is a current example of our script which handles the waves.

``` lua title="Waves"
local wave = 1

while true do
    wave += 1
    task.wait(5)
end
```

This example shows that every 5 seconds the wave will increase by 1.

If we want to replicate the wave to each player, we must use a **RemoteEvent**. Using the **RemoteEvent** we can notify all players of the current wave, each time it increases. And upon a player joining, we want to notify them of the current wave as well.

``` lua title="Waves"
local Players = game:GetService("Players")

local WaveRemote = ReplicatedStorage.Remotes.WaveRemote

local wave = 1

while true do
    wave += 1
    WaveRemote:FireAllClients(wave)
    task.wait(5)
end

Players.PlayerAdded:Connect(function(player)
    WaveRemote:FireClient(player, wave)
end)
```

From the client, we must then listen to the **RemoteEvent** and we'll be notified each time the wave has been changed.

## Conclusion

Replication is a relatively simple concept to understand once have you a good understanding of networking. You've likely already done some form of replicating but didn't realize it was even called something specific.


When I first began fully understanding replication was when I began using [ProfileService](https://github.com/MadStudioRoblox/ProfileService). This naturally stores each player's data inside a table, rather than the NumberValue or other Value Objects I was using. It opened my eyes to realizing what Roblox automatically does for me.