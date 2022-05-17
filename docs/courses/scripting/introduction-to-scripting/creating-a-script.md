---
template: course.html
---

## What is a Script

Similar to the **Command Bar** we used to run our code in the previous chapter, **Scripts** are the primary way of running code!

There are **3 types** of **Scripts**:

| Types | Description |
| ----------- | ------------------------------------ |
| ![Server Script](/img/icons/Script.png) `Server Script` | Controlled and ran by the **server** aka **our game**  |
| ![Local Script](/img/icons/LocalScript.png) `Local Script` | Controlled and ran by the **client** aka **the player** |
| ![Module Script](/img/icons/ModuleScript.png) `Module Script` | Controlled by either the **server** or **client** |

!!! note

    * **Server Scripts** are also commonly referred to as just **Scripts**
    * **Module Scripts** are more complex, so we won't be incorporating or discussing them much until later in the course

## Where Do We Put Scripts

Before we create a **script** we should get a general understanding of where to put our **Local** & **Server** scripts.

### What are Services

If we look inside of our **Explorer** we can many **Services** listed. Each **service** provides some usage for us, especially when scripting.

<figure markdown>
  ![Services with the Explorer](/img/courses/scripting/Explorer-Services.png)
</figure>

Here are a few examples that should make it easier to understand **Services**:

* **Workspace**: Contains any objects that are to be rendered in the 3D world
* **Players**: Contains Player objects for presently connected clients to a Roblox game server
* **Lighting**: Controls the environmental lighting in a game

If you look inside the **Workspace** service within your **Explorer** you should see a few parts which include the `Baseplate` & `SpawnPoint` You can see these parts displayed directly in your Game's world currently.

Whenever a player joins our game, the **Players** service will generate and hold a **Player** object with that specific player's data. This is extremely useful in scripting.

You can also think of **Services** as a **Folder**. You expanded the **Workspace** service and saw a few parts inside of it, you could also do the same with **Lighting** and see objects inside of it as well.

### Which Services Should Contain Scripts

While you could store a **Server Script** in nearly any service and it would still function, the **ServerScriptService** is the primary service for this.

**Local Scripts** on the other hand need to be **loaded** by a **client** aka **player** to run. The **ServerScriptService** cannot be accessed by **players**, so you wouldn't normally store a **Local Script** there. The **StarterPlayer/StarterPlayerScripts** service is the primary service to store **Local Scripts** as that is its purpose. The **Workspace**, **StarterPack**, & **StarterGui** services are also commonly used to hold **Local Scripts**.

The table reflects what we talked about above.

| Services | Script Types |
| ----------- | ------------------------------------ |
| `Workspace` | ![Local Script](/img/icons/LocalScript.png) Local |
| `ServerScriptService` | ![Server Script](/img/icons/Script.png) Server |
| `StarterGui` | ![Local Script](/img/icons/LocalScript.png) Local |
| `StarterPack` | ![Local Script](/img/icons/LocalScript.png) Local |
| `StarterPlayer/StarterPlayerScripts` | ![Local Script](/img/icons/LocalScript.png) Local |

## Creating a Server Script

1. Put your Mouse over the **ServerScriptService** within the **Explorer**
2. Click the :material-plus: icon to the right of the **ServerScriptService** name
3. Search for "Script" in the popup box
4. Click the ![Server Script](/img/icons/Script.png)`Script` button

<figure markdown>
  ![Create Script popup](/img/courses/scripting/Creating-a-Script.png)
</figure>

Within **ServerScriptService** you should see the new **Server Script** which is named `Script`.

<figure markdown>
  ![Created Script](/img/courses/scripting/Created-Script.png)
</figure>

## What we Learned

!!! question "What we Learned"

    * Basic understanding of what a Script is
    * The 3 types of Scripts
    * Where Scripts can be stored
    * Very basic understanding of a Service
    * How to create a Script
