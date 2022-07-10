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

We can use **conditionals** to perform an action based on a specified scenario.

Conditionals are written in the following format:

``` lua
local number = 10
if number == 10 then -- Can be thought of as 10 = 10
    print(true)
elseif number < 15 then -- Can be thought of as 10 is less than 15
    print(true)
else -- Can be thought of as any other 'condition' besides the previous two
    print(false)
end
```

Conditionals are read from top to bottom. For example, first `number == 10` is read, since this is true `print(true)` will run, and nothing more will happen. If we want `number < 15` to be checked, we must use a number between `11` and `14` so that `number == 10` will NOT be true.

### Rational Operators

We commonly use **rational operators** to create conditionals.

``` lua
if 10 == 10 then -- Can be thought of as 10 = 10 (True)
    print(true)
end
```

| Symbol | Name | Example | Result |
| -         | -       | -     | -   |
| `==` | Equal to | if 1 == 2 | False |
| `~=` | Not Equal to | if 1 ~= 2 | True |
| `<` | Less than | if 1 < 2 | True |
| `<=` | Less than or Equal to | if 1 <= 2 | True |
| `>` | Greater than | if 1 > 2 | False |
| `>=` | Greater than than or Equal to | if 1 >= 2 | False |

### Logical Operators

We can also use **logical operators** to create slightly more complex conditionals.

``` lua
if not 10 == 10 or not 1 == 1 then -- Can be thought of as 10 ~= 10 or 1 ~= 1 (False)
    print(true)
end
```

| Symbol | Name | Example | Result |
| -         | -       | -     | -   |
| `not` | Opposite | if not 1 == 2 | True |
| `or` | Either | if 1 == 2 or 1 == 1 | True |
| `and` | And | if 1 == 1 and 1 == 2 | False |
