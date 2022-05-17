---
template: course.html
---

A **variable** can be thought of as a **container** for a value.

## Naming a Variable

We can create a variable by giving it a **name**. Certain **rules** must be followed when naming our **variables**:

* Cannot start with a number
* Cannot contain certain symbols (Example: `!`, `"`, `,` & many more)
* Cannot be certain reserved words (Example: `false` since that's the value of a boolean)

Let's create a few variables inside of our **Script**.
    ``` lua title="Script" linenums="1"
    variable1
    ImAVariable
    i_Am_A_Variable
    ```

### Camel Case

Whenever you decide on a name for your variable, you want to follow a strict **naming convention** throughout your entire project.

**Camel Case** is a naming convention in which a name is formed of multiple words, the **first letter** in the **first word** is **lowercase**, while the **first letter** in **each word after** the first is **capitalized**.
    ``` lua title="Example"
    variable1 = 10
    imAVariable = "Hi!"
    iAmAVariable = true
    ```

**Camel Case** is the most commonly used naming convention in Roblox projects. There are **no required** or **standard naming conventions**, but it's highly recommended you use the most common one.

## Assigning a Value to a Variable

Since we have already given our **variables** names, we can give them some **values** to store using the equal `=` symbol. In the **Data Types** chapter when we talked about multiple types of data that **variables** can hold. Lets **assign** a **variable** to each **type** of **data**.
    ``` lua title="Script" linenums="1"
    variable1 = 10
    imAVariable = "Hi!"
    iAmAVariable = true
    ```

Looking at each variable we can see that `variable1` is of the type `number` because its value is 10, `imAVariable` is of the type `string` because its value is a combination of characters surrounded by `"`s, and `iAmAVariable` is of the type `boolean` because its value is the word `true`. We forgot to include the `nil` type, but we can create another variable for that. When we create a variable with the value of `nil`, we're saying the variable doesn't have any value.
    ``` lua title="Script" linenums="1"
    variable1 = 10
    imAVariable = "Hi!"
    iAmAVariable = true
    imNothing = nil
    ```

!!! tip

    **Name** = **Value**

    The name of the variable is always on the left, while its value is always on the right and they're separated with an equals `=` sign between them.

## Printing Variables

We have now created a few **variables** which each hold their own **value**. Lets use these **variables** to **print** their **values** to the **Output** window! We can do this by putting each **variable** name into a **print** function.
=== "Script"

    ``` lua title="Script" linenums="1"
    variable1 = 10
    imAVariable = "Hi!"
    iAmAVariable = true
    imNothing = nil

    print(variable1)
    print(imAVariable)
    print(iAmAVariable)
    print(imNothing)
    ```

=== "Output"

    ``` text
    03:49:43.359  10  -  Server - Script:6
    03:49:43.359  Hi!  -  Server - Script:7
    03:49:43.359  true  -  Server - Script:8
    03:49:43.359  nil  -  Server - Script:9
    ```

We can see the value of each variable displayed in the **Output** window!

## Reassigning Variables

Rather than a **variable** only ever having one specific **value**, you can change the value to anything you want. Let's use our variable named `imNothing` and reassign its value to `10` after the `print` function call on line 9. We'll reassign its value and print it again.
=== "Script"

    ``` lua title="Script" linenums="1"
    variable1 = 10
    imAVariable = "Hi!"
    iAmAVariable = true
    imNothing = nil

    print(variable1)
    print(imAVariable)
    print(iAmAVariable)
    print(imNothing)

    imNothing = 10

    print(imNothing)
    ```

=== "Output"

    ``` text
    03:49:43.359  10  -  Server - Script:6
    03:49:43.359  Hi!  -  Server - Script:7
    03:49:43.359  true  -  Server - Script:8
    03:49:43.359  nil  -  Server - Script:9
    03:49:43.359  10  -  Server - Script:13
    ```

We can see that the first time we print the `imNothing` variable, `nil` is output, but once we **reassign** it to `10`, and print it again, `10` is now output.

## Scope

There are two types of **scopes** in Lua, **Global** and **Local**. Currently, all the variables we created are of the **global** scope, which **99.9%** of the time is **not** what you want.

### Local

Whenever we create a new variable, before typing the name, we should type the keyword `local`. Here's an example of how it should be written `local newVariable = 1`. We used the keyword `local` to specify the variable's **scope**.

There is more to **scope** than just including a **keyword** when creating a **variable**. Although we haven't learned about `if-statements`, `functions`, or `loops` yet, these will be commonly used while you code. When thinking about the **scope**, think of **containers** or **boxes** which can hold things inside of them.

<figure markdown>
  ![Local Scope Demonstration](/img/courses/scripting/Local-Scope-Demonstartion.png)
</figure>

Let's break apart the image above:

* We create `variable1` in **Container 0**
* We use `variable1` in **Container 0** with the `print()` function

* We then use an `if-statement` in **Container 0**, which now creates **Container 1**
* We create `variable2` in **Container 1**
* We use `variable1` & `variable2` in **Container 1** with the `print()` function

* We then use an `if-statement` in **Container 1**, which now creates **Container 2**
* We create `variable3` in **Container 2**
* We use `variable1`, `variable2`, & `variable3` in **Container 2** with the `print()` function

So remember, everytime we use an `if-statement`, we basically create a **container** inside of another **container**. The important lesson to understand is that each **container** can **access** **variables** that are **inside** the **same container** OR in **previous containers**!

That might seem confusing, but let's use the image to better understand:

* `variable1` is created in **Container 0** and can be used within **Container 0**, **Container 1** & **Container 2**
* `variable2` is created in **Container 1** and can be used within **Container 1** & **Container 2**, but **not Container 0**
* `variable3` is created in **Container 2** and can be used within **Container 2**, but **not Container 0** or **Container 1**

So **local variables** can be used within the same **container** they were created in and **containers** within their **container**. They **cannot** be used in **containers** outside of the one they were created in.

### Global

As originally stated, you most likely should **never** create **Global** scoped **variables**. With that being said, the reason you should learn about the **Global** scope is to get a better understanding and easily differentiate between **Local** & **Global**.

Instead of using the keyword `local` before the variable's name, you do not include any keywords. Here's an example of how it would be written `newVariable = 1`. Since we didn't specify the **local** scope with the `local` keyword, it's automatically assumed to be global.

<figure markdown>
  ![Global Scope Demonstration](/img/courses/scripting/Global-Scope-Demonstartion.png)
</figure>

The image above looks similar to the one we saw in the **Local** lesson, but this time we use **Global** scoped variables. The **containers** are the same, but instead of **variables** being only accessible from their **own containers** and **containers within** their **container**, they can now be accessed from **every container**!

This is why the `print()` functions no longer have yellow squiggly lines which indicate an error. The `print()` functions in **Container 0** are able to print `variable2` & `variable3`, which aren't created within **Container 0**.

You should almost **never** use **Global** scope on variables since they can be modified in more locations, it becomes **hard to keep track** of where **changes** are made. You might think the **Global** scope provides benefits over **Local**, which in some ways it does, but those do not outweigh the negatives.



## What we Learned

!!! question "What we Learned"

    * What a variable is
    * How to name a variable
    * Which naming convention to use for naming variables
    * How to give a variable a value
    * How to private a variable's value
    * How to reassign a variable to a different value
    * What a scope is
    * The different types of scopes
    * Which scope variables should almost always be