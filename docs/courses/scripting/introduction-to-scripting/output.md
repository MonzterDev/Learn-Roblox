---
template: course.html
---

## What is the Output
The **Output** is where the most important information will be displayed from our **scripts**! We'll constantly be using the **output** to view **errors** and **debug** our code.

You should see the **Output** tab at the bottom of your **Studio** window.

![Studio Output Tab](/img/courses/scripting/Studio-Output.png){ align=left, loading=lazy }

??? warning "Don't see the **Output** tab?"

    If you **do not** see the **Output** tab, click on the `VIEW` button at the top of **Studio**, then click the `🖼 Output` button to enable it.

## The Command Bar
The **Command Bar** can be used as another method of **running code** similar to **scripts**! The code written within the **command bar** is usually a **small task** or meant for **testing**.

You should see the **Command Bar** tab at the bottom of your **Studio** window, directly below the **Output** tab.

<img src="/img/courses/scripting/Studio-Command-Bar.png" alt="Studio Output Tab">

??? warning "Don't see the **Command Bar** tab?"

    If you **do not** see the **Command Bar** tab, click on the `VIEW` button at the top of **Studio**, then click the `🖼 Command Bar` button to enable it.

## Printing to the Output
What you're about to learn will be one of the most commonly used knowledge throughout your entire scripting journey! We can send a message to the **Output** by using the **Command Bar**.

**Type** the text below into your **Command Bar** and hit **enter**:
=== "Command Bar"

    ``` lua
    print("Hey, I did it!")
    ```

=== "Output"

    ``` text
    19:44:39.754  > print("Hey, I did it!") -  Studio
    19:44:39.755  Hey, I did it!  -  Edit
    ```
Upon hitting ++enter++, you should see a similar message appear in your **Output** as displayed in the **Output** tab above!

## Understanding the Output

The **Output** message is made up of a few components:

| Component | Example | Usage |
| -         | -       | -     |
| `Timestamp` | 19:44:39.755 | Indicates the time in the 24-hour format when the message was output |
| `Message` | Hey, I did it! | The information to be displayed in the Output |
| `Source` | Studio | The source of the print() call. Usually `Client` or `Server` |
| `Script Name` | Not Displayed | The name of the Script which triggered the message to be sent |
| `Line #` | Not Displayed | The line within a Script which triggered the message to be sent |

The **timestamp** will be different for you because the timestamp is based on your current time in the 24-hour format. Since I'm in the Eastern Standard Timezone the **Output** was triggered at `7:44:39.754PM`, which in the 24-hour format is `19:44:39.755`.

The **source** was **Studio** because we used the `print()` function in our **Command Bar**. Usually the **source** would be **Client** if you're using `print()` in a **LocalScript** or **Server** from a **ServerScript**.

Since we used the **Command Bar** instead of a **Script**, no `Line #` was displayed. Whenever there is output from a **Script** the last part of the output will be a number that indicates the line that caused the output.

Congratulations you can now call yourself a **scripter** as you just wrote your first line of code and used the `print()` function!

## What we Learned

!!! question "What we Learned"

    * Basic understanding of what the Output window is
    * How to view the Output window
    * What the Command Bar is
    * How to view the Command Bar
    * How information can be displayed in the Output window
    * Basic understanding of the format of an Output message
