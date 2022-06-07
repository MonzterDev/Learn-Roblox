We'll cover most of the core concepts of **Luau** and **Roblox Development**.

## Variables

Variables are written in the following format: `local nameOfVariable = "valueOfVariable"`.

* **local** is the **scope** of the variable.
* **nameofVariable** is the **name** of the variable.
* **"valueOfVariable"** is the **value** of the variable.

### Types

A variable's type is based off its **value**. The **type** of a variable is important as it enables you to know how you can use that variable. For instance, you can only perform **math operations** on two **number** variables.

### Primitive Types

These types are standard **Luau** types, which are also commonly shared with other **programming languages**.

| Type | Example | Info |
| -         | -       | -     |
| `string` | "StringType" | Characters surrounded by `"`s |
| `number` | 10.5 | Any number including whole numbers & decimals |
| `boolean` | true | `true` or `false`, Similar to yes or no |
| `table` | { } | Array or Dictionary |
| `function` | function() | A function |
| `nil` | ` ` | It means "nothing" or "does not exist" |

There is also **userdata** & **thread**, but you'll likely never use these types.

#### String

You can **combine** two strings using two `.`s between the strings.
=== "Example"
    ``` lua
    local newString = "Hey I'm".." pretty cool!"
    print(newString)
    ```
=== "Output"
    Hey I'm pretty cool!

#### Number

You can do **math** with two numbers by using any **arithmetic symbols** between the numbers.
=== "Example"
    ``` lua
    local newMath = 5 + 10
    print(newMath)
    ```
=== "Output"
    15

#### Boolean

You can use a **conditional statement** to create a boolean.
=== "Example"
    ``` lua
    local newBool = 5 + 10 == 15
    print(newBool)
    ```
=== "Output"
    true

### Roblox Types

Roblox adjusts their plethora of custom **types** often, but you always view the most up to date list [here](https://developer.roblox.com/en-us/api-reference/data-types)!

<!-- | Type | Example | Info |
| -         | -       | -     |
| `Axes` | Axes.new() | Used for the ArcHandles class to control what rotation axes are currently enabled |
| `BrickColor` | BirchColor.new(1) | Provides a predefined list of named colors |
| `CatalogSearchParams` | CatalogSearchParams.new() | Specifying the parameters of a catalog search via `AvatarEditorService:SearchCatalog()` |
| `CFrame` | CFrame.new() | Short for "coordinate frame" describes a 3D position and orientation |
| `Color3` | Color3.new(255, 255, 255) | Describes a color using R, G and B components | -->

### Examples

#### Simple

``` lua
local numberVariable = 10
local stringVariable = "100"
local booleanVariable = true
local nilVariable = nil
local nilVariable2
local tableArrayVariable = {"2", 3, true}
local tableDictionaryVariable = {first = "2", 2 = "3rd", third = "two"}
```

#### Advanced

``` lua
local numberVariable = 1_000
local stringVariable = "100".." and two"
local booleanVariable = numberVariable == 1_000
local nilVariable = nil
local nilVariable2 = nilVariable or nil
```

## Conditional Statements