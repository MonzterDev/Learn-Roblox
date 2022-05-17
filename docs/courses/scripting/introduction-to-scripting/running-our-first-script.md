---
template: course.html
---

## Hello World!

Upon opening the **Script** we created in the previous chapter, you should see the following line of code:
``` lua title="Script"
print("Hello world!")
```

If you remember back to our **Output** chapter, we used the `print()` function inside of our **Command Bar** to print the sentence "Hey, I did it!" to the **Output** window. Instead of using the **Command Bar**, we'll use a **Script** to print "Hello world!" to the **Output** window.

## Starting the Game

We now want to **start** our game, which we can do in multiple ways:

* Click the Play icon between the `FILE` and `HOME` buttons
* Switch to the `HOME` tab, then click the `Play` button
* Press ++f5++ which is the hotkey for starting the Game

<figure markdown>
  ![Start Game Button](/img/courses/scripting/Studio-Play-Buttons.png)
</figure>

## Viewing the Output

Upon starting the game, you should see the following appear in the **Output** window:
``` text title="Output"
  19:44:39.754  Hello world!  -  Server - Script:1
```

We've learned about the **Output** message format already, but let's review it with this usage.

| Component | Example | Usage |
| -         | -       | -     |
| `Timestamp` | 19:44:39.755 | Indicates the time in the 24-hour format when the message was output |
| `Message` | Hello world! | The information to be displayed in the Output |
| `Source` | Server | The source of the print() call |
| `Script Name` | Script | The name of the Script which tirggered the message to be sent |
| `Line #` | 1 | The line within a Script which triggered the message to be sent |

Additionally, if we click on `Hello world!` or `Script:1` within the **Output** window, it'll open the **script** and bring us to the line in the **script** which caused this to be displayed.

## Stopping the Game

We now want to **stop** our game, which we can do in multiple ways:

* Click the Stop icon between the `FILE` and `HOME` buttons
* Switch to the `HOME` tab, then click the `Stop` button
* Press ++shift+f5++ which is the hotkey for ending the Game

<figure markdown>
  ![Stop Game Button](/img/courses/scripting/Studio-Stop-Buttons.png)
</figure>

## Creating a Local Script

Rather than only using a **ServerScript**, let's create a **LocalScript** and once again output `Hello world!`.

1. Expand the **StarterPlayer** folder within the **Explorer** so you can see both **StarterCharacterScripts** & **StarterPlayerScripts**
2. Put your Mouse over the **StarterPlayerScripts** within the **StarterPlayer** folder
3. Click the :material-plus: icon to the right of the **StarterPlayerScripts** name
4. Search for "LocalScript" in the popup box
5. Click the ![Local Script](/img/icons/LocalScript.png)`LocalScript` button

<figure markdown>
  ![Created Local Script](/img/courses/scripting/Created-Local-Script.png)
</figure>

Upon opening the new **LocalScript** you should see the same code which was in our **ServerScript** earlier:
``` lua title="LocalScript"
print("Hello world!")
```

If we start our Game, we'll now see two lines in the **Output**, one from the **Server** and one from the **Client**:
``` text title="Output"
  03:15:31.496  Hello world!  -  Server - Script:1
  03:15:32.256  Hello world!  -  Client - LocalScript:1
```

## What we Learned

!!! question "What we Learned"

    * How to create different types of Scripts
    * How to start & stop our Game
    * Further understanding of the Output message format
