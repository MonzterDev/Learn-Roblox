---
template: course.html
---

## String Concatenation
We've learned what **strings** are and even made a few, but how can we combine them?

Imagine we wanted to print out `The answer to 5+5 is 10!`. Currently, we know we can print out the following string:
=== "Script"

    ``` lua
    print("The answer to 5+5 is 10!")
    ```

=== "Output"

    ``` text
    03:49:43.359  The answer to 5+5 is 10!  -  Server - Script:1
    ```

But what if we wanted to do the actual math of `5+5` because we didn't know that was equal to `10`? You might think we could type something like the following:
=== "Script"

    ``` lua
    print("The answer to 5+5 is" 5+5 )
    ```

=== "Output"

    ``` text
    Expected ')' (to close '(' at column 6), got '5'
    ```

That results in an error because we didn't group the **string** and **equation**. We can group these together by putting two periods (`..`) between them.
=== "Script"

    ``` lua
    print("The answer to 5+5 is" .. 5+5 )
    ```

=== "Output"

    ``` text
    03:49:43.359  The answer to 5+5 is10  -  Server - Script:1
    ```

We have connected the **string** and **equation**, but we still need to make two adjustments:

* Put a space between the string and equation
* Add an `!` to the end of the sentence

Putting a space is easy, we can simply insert a space after the word `is` and before the string ends.
We can add the `!` to the end by making it a **string** and **combining** it with the **equation**.
=== "Script"

    ``` lua
    print("The answer to 5+5 is " .. 5+5 .. "!")
    ```

=== "Output"

    ``` text
    03:49:43.359  The answer to 5+5 is 10!  -  Server - Script:1
    ```

??? error "Malformed Number"

    If you're getting the error `Malformed Number` it's because your combiners `..`s are touching the numbers apart of the equation.
    To avoid this you should always add a space to the right and left of your combiners `..`s whenever you use them. It also helps with readability!

## What we Learned

!!! question "What we Learned"

    * How to combine strings
