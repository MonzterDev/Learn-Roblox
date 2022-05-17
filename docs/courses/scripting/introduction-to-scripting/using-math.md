---
template: course.html
---

Since we just learned about a few **Data Types**, let's start using the **number** type by doing some math! You can follow along within the **ServerScript** or **LocalScript** we created earlier.
It's **recommended** that you also type out these **math problems** to help with **memorizing** the content.


## Addition
Let's say we have **5 coins** and we do a task which **rewards** us with **3 coins**, we should have a **total** of **8 coins**.
=== "Script"

    ``` lua
    print(5+3)
    ```

=== "Output"

    ``` text
    03:49:43.359  8  -  Server - Script:1
    ```
## Subtraction
Lets say we have **10 coins** and we **purchase** something from the **shop** for **4 coins**, we should have a **total** of **6 coins**.
=== "Script"

    ``` lua
    print(10-4)
    ```

=== "Output"

    ``` text
    03:49:43.359  6  -  Server - Script:1
    ```

## Multiplication
Let's say we have **5 coins** and we do a task which **rewards** us with **3x** our **current coins**, we should have a **total** of **15 coins**.
=== "Script"

    ``` lua
    print(5*3)
    ```

=== "Output"

    ``` text
    03:49:43.359  15  -  Server - Script:1
    ```

## Division
Let's say we have **14 coins** and we **purchase** something from the **shop** which costs us **half** of our **current coins**, we should have a **total** of **7 coins**.
=== "Script"

    ``` lua
    print(14/2)
    ```

=== "Output"

    ``` text
    03:49:43.359  7  -  Server - Script:1
    ```

## Remainder
This is slightly different from the common arithmetic operations. The remainder is what is left over when one number is divided by another number.


Let's say we have **15 coins** and we want to know how much would be leftover if we **divided** our **current coins** by **4**, we should have a **total** of **3 coins** leftover. Considering how many times **4** can go into **15**: *4*, *8*, then *12*. We then have a **remainder** of **3 coins** because **12 + 3 = 15**. This might be a bit confusing, but don't worry at all. It's very uncommon to have scenarios where you'll want to use the **Remainder**.

=== "Script"

    ``` lua
    print(15%4)
    ```

=== "Output"

    ``` text
    03:49:43.359  3  -  Server - Script:1
    ```

## What we Learned

!!! question "What we Learned"

    * How to do calculations in Luau