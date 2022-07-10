We'll cover the **TypeScript** version of common **Lua** components!

Checkout [**Roblox TypeScript**](https://roblox-ts.com/) to utilize **TypeScript** in your games!

## Variables

Instead of `local` you would use either `const` (short for **constant**) for variables which **do not** change or `let` for variables that do change.

You can use `let` for all variables, but it's best practice to use `const` when a variable does not change.

=== "Lua"

    ``` lua
    local name = "MyName"
    ```

=== "TypeScript"

    ``` ts
    const name = "MyName"
    let secondName = "MySecondName"

    secondName = "NewName" // This does work
    name = "NewName" // This does not work because it's a const
    ```

## Functions

* Rather than using the `local` keyword when creating a Function, you don't need to define any scope.
* Upon creating the Function, use curly braces `{}` to surround your code block.


=== "Lua"

    ``` lua
    local function TestFunction(name: string)
        print(true)
    end
    ```

=== "TypeScript"

    ``` ts
    function TestFunction(name: string) {
        print(true)
    }
    ```

### Arrow Functions

Basically a shorter way of writing out a function.

=== "Lua"

    ``` lua
    local function TestFunction(name: string)
        print(true)
    end
    ```

=== "TypeScript"

    ``` ts
    const TestFunction = (name: string) => {
        print(true)
    }

    TestFunction("Test") // Calls the function
    ```

## Conditions

=== "Lua"

    ``` lua
    local name = "MyName"
    if name == "MyName" then
        print(true)
    elseif name ~= "MyName" then
        print(false)
    else
        print(name)
    end
    ```

=== "TypeScript"

    ``` ts
    const name = "MyName"
    if (name === "MyName") {
        print(true);
    } else if (name !== "MyName") {
        print(false);
    } else {
        print(name);
    }
    ```

### Operators

| Symbol | Name | Example | Result |
| -         | -       | -     | -   |
| `===` | Equal to | if (1 === 2) {} | False |
| `!==` | Not Equal to | if (1 !== 2) {} | True |
| `<` | Less than | if (1 < 2) {} | True |
| `<=` | Less than or Equal to | if (1 <= 2) {} | True |
| `>` | Greater than | if (1 > 2) {} | False |
| `>=` | Greater than than or Equal to | if (1 >= 2) {} | False |


## Creating Instances

=== "Lua"

    ``` lua
    local folder = Instance.new("Folder")
    folder.Name = "Test"
    ```

=== "TypeScript"

    ``` ts
    const folder = new Instance("Folder")
    folder.Name = "Test"
    ```

## Method Calls

Use a `.` to call methods rather than `:`s.

=== "Lua"

    ``` lua
    local folder = Instance.new("Folder")
    folder:Clone()
    ```

=== "TypeScript"

    ``` ts
    const folder = new Instance("Folder")
    folder.Clone()
    ```

## Loops

### For

#### Simple

=== "Lua"

    ``` lua
    for count = 1, 5 do
        print(count)
    end
    ```

=== "TypeScript"

    ``` ts
    for (let count = 1; count <= 5; count++) {
        print(count)
    }
    ```

#### Advanced

=== "Lua"

    ``` lua
    for _, player in ipairs(Players:GetPlayers()) do
        print(player.Name)
    end
    ```

=== "TypeScript"

    ``` ts
    for (const player of Players.GetPlayers()) {
        print(player.Name);
    }
    ```

### While

=== "Lua"

    ``` lua
    while true do
        print(true)
    end
    ```

=== "TypeScript"

    ``` ts
    while (true) {
        print(true)
    }
    ```

### Iterables

Iterables are iterable objects like Tables or more specifically **Arrays** & **Dictionaries**.

It's important to know that a **Map** in **TS** is the equivalent to a **Lua Dictionary**!

=== "Lua"

    ``` lua
    for _, player in ipairs(Players:GetPlayers()) do
        print(player.Name)
    end
    ```

=== "TypeScript"

    ``` ts
    // Arrow Function
    Players.GetPlayers().forEach((player: Player) => {
        print(player.Name);
    });

    // Normal function
    Players.GetPlayers().forEach(function (player: Player) {
        print(player.Name);
    });
    ```

## Tables, Arrays, & Dictionaries

### Array

#### Creating

=== "Lua"

    ``` lua
    local example = {"test", 524, true}
    ```

=== "TypeScript"

    ``` ts
    const example = ["test", 524, true]
    ```

#### Writing Into

=== "Lua"

    ``` lua
    local example = {"test", 524, true}

    table.insert(example, "added!")
    ```

=== "TypeScript"

    ``` ts
    const example = ["test", 524, true]

    example.push("added!")
    ```

#### Reading From

=== "Lua"

    ``` lua
    local example = {"test", 524, true}

    print(example[1]) -- test
    ```

=== "TypeScript"

    ``` ts
    const example = ["test", 524, true]

    print(example[0]) // test
    ```

#### Removing Pair

=== "Lua"

    ``` lua
    local example = {"test", 524, true}

    table.remove(example, 1)

    print(example[1]) -- 524
    ```

=== "TypeScript"

    ``` ts
    const example = ["test", 524, true]

    example.remove(0)

    print(example[0]) // 524
    ```

#### Iterating

Unlike **Maps** and **Dictionaries**, arrays are iterated through in order.

=== "Lua"

    ``` lua
    local example = {"test", 524, true}

    for index, value in ipairs(example) do
        print(index, value) -- 1 test    2 524    3 true
    end
    ```

=== "TypeScript"

    ``` ts
    const example = ["test", 524, true]

    // Same as Lua example
    example.forEach((value, index) => {
        print(index, value) // 1 test    2 524    3 true
    });

    // Doesn't include the index
    for (const value of example) {
        print(value) // 1 test    2 524    3 true
    }
    ```

### Dictionaries

The closest thing to a dictionary in **TS** is a **Map**. These allow for storing **key-value** pairs, similar to Lua dictionaries.

#### Creating

When creating a Map, we must assert what the type of our **keys** and **value** will be.

Example: `new Map<string, any>()` | `new Map<number, string>()`

=== "Lua"

    ``` lua
    local example = {
        Key = 3,
        key2 = {},
        key3 = "NewKey"
    }
    ```

=== "TypeScript"

    ``` ts
    const example = new Map<string, any>([
        ["Key", 3],
        ["key2", {}],
        ["key3", "NewKey"],
    ])
    ```

#### Writing Into

=== "Lua"

    ``` lua
    local example = {
        Key = 3,
        key2 = {},
        key3 = "NewKey"
    }

    example["aNewKey"] = 100
    ```

=== "TypeScript"

    ``` ts
    const example = new Map<string, any>([
        ["Key", 3],
        ["key2", {}],
        ["key3", "NewKey"],
    ])

    example.set("aNewKey", 100);
    ```

#### Reading From

=== "Lua"

    ``` lua
    local example = {
        Key = 3,
        key2 = {},
        key3 = "NewKey"
    }

    print(example["Key"]) -- 3
    ```

=== "TypeScript"

    ``` ts
    const example = new Map<string, any>([
        ["Key", 3],
        ["key2", {}],
        ["key3", "NewKey"],
    ])

    print(example.get("Key")) // 3
    ```

#### Removing Pair

=== "Lua"

    ``` lua
    local example = {
        Key = 3,
        key2 = {},
        key3 = "NewKey"
    }

    example["Key"] = nil

    print(example["Key"]) -- nil
    ```

=== "TypeScript"

    ``` ts
    const example = new Map<string, any>([
        ["Key", 3],
        ["key2", {}],
        ["key3", "NewKey"],
    ])

    exampleMap.delete("Key")

    print(example.get("Key")) // nil
    ```

#### Iterating

Reminder: Dictionaries & Maps are unordered, meaning when iterating through them, it will not start from the first entry.

=== "Lua"

    ``` lua
    local example = {
        Key = 3,
        key2 = {},
        key3 = "NewKey"
    }

    for key, value in pairs(example) do
        print(key, value) -- "Key" 3   "key2" {}   "key3" "NewKey"
    end

    ```

=== "TypeScript"

    ``` ts
    const example = new Map<string, unknown>([
        ["Key", 3],
        ["key2", {}],
        ["key3", "NewKey"],
    ])

    // Same as Lua example
    for (const [key, value] of example) {
        print(key, value) // "Key" 3   "key2" {}   "key3" "NewKey"
    }

    // Using forEach instead of a For Of Loop
    example.forEach((value, key) => {
        print(key, value); // "Key" 3   "key2" {}   "key3" "NewKey"
    });

    // Another way of doing it
    for (const entry of example) {
        print(entry[0], entry[1]) // "Key" 3   "key2" {}   "key3" "NewKey"
    }
    ```

## Classes

### Creating

=== "Lua"

    ``` lua
    Example = {}
    Example.__index = Example

    function Example.new(player: Player)
        local self = setmetatable({}, Inventory)

        self.Player = player
        self.UserId = player.UserId
        return self
    end

    -- Create object
    local object = Example.new(player)
    ```

=== "TypeScript"

    ``` ts
    class Exmaple {
        player;
        userId;

        constructor(player: Player) {
            this.player = player
            this.userId = player.UserId
            return this
        }
    }

    // Create object
    const object = new Example(player)
    ```

### Methods

=== "Lua"

    ``` lua
    Example = {}
    Example.__index = Example

    function Example.new(player: Player)
        local self = setmetatable({}, Inventory)

        self.Player = player
        self.UserId = player.UserId
        return self
    end

    function Example:GetPlayerName()
        return self.Player.Name
    end

    -- Create object
    local object = Example.new(player)

    object:GetPlayerName()
    ```

=== "TypeScript"

    ``` ts
    class Exmaple {
        player;
        userId;

        constructor(player: Player) {
            this.player = player
            this.userId = player.UserId
            return this
        }

        GetPlayerName() {
            return this.player.Name
        }
    }

    // Create object
    const object = new Example(player)

    object.GetPlayerName()
    ```

## Services

You can get a **Service** similarly to the Lua method, by using the `.` operator on the `game` data model.

Alternatively you can use the [services package](https://www.npmjs.com/package/@rbxts/services).

=== "Lua"

    ``` lua
    local ReplicatedStorage = game:GetService('ReplicatedStorage')
    ```

=== "TypeScript"

    ``` ts
    const ReplicatedStorage = game.GetService('ReplicatedStorage')
    ```

=== "TypeScript (Alternative)"

    ``` ts
    import { ReplicatedStorage } from "@rbxts/services";
    ```

## Modules

Rather than creating a Table and attaching Variables and Functions to it, you create Functions and Variables like normal, then prefix them with the keyword `export`.

To use the Module in another Script, you **import** the Functions and Variables you want to use from the directory of the Module.

=== "Lua"

    ``` lua
    -- Module Script named Config within ReplicatedStorage
    local Config = {}

    Config.List = {"Example"}

    function Config.Print()
        print("Hey!")
    end

    return Config

    -- Requiring the Module Script in another Script
    local ReplicatedStorage = game:GetService('ReplicatedStorage')

    local Config = require(ReplicatedStorage.Config)

    print(Config.List)
    Config.Print()
    ```

=== "TypeScript"

    ``` ts
    // Module Script named Config within my Rojo Project folder called "Shared"
    // which is is synced to the ReplicatedStorage
    export const List = ["Example"];

    export function Print() {
        print("Hey!")
    }

    // Requiring the Module Script in another Script
    import { List, Print } from "shared/Config"

    print(List)
    Print()
    ```
