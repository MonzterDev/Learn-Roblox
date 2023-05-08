## Benefits

* Makes your code much easier to understand for yourself and other Developers
* Provides a much better understanding of what you're doing and realize what you're working with
* Enables autocompletion in Roblox Studio

## What Types are Available

### Primitive

There are **8 primitive types**, but we’ll only cover the **5** you’ll likely ever use:

| Type      | Example Value                          |
| :---------- | :----------------------------------- |
| `nil` | |
| `string` | "Example" |
| `number` | 1 |
| `boolean` | true |
| `table` | {} |

### Roblox

Roblox offers many of its own custom types which can all be viewed [here](https://developer.roblox.com/en-us/api-reference). Here are a few commonly used types:

* Player
* Humanoid
* Workspace
* Part
* Model

## How to Enable Type Checking

While learning, it’s a good idea to use the **strict** type inferring mode, so we can spot possible issues!

You can enable **strict** mode by putting the following comment at the top of your script: `-!strict`

``` lua
--!strict
local test = 1
```

## Type Inferencing

Normally when we create a variable and assign a value to it, Studio is able to automatically know what type the variable is.

``` lua
local test = 1
```

With the example able, Studio is able to **infer** that **test** is a number.

## How to Specify the Type (Annotation)

To specify the type of something like a variable or a function’s argument we’ll use something called a **type annotation**.

Here's an example of using **type annotation**:

``` lua
local test: number = 10 -- Pointless since it's already inferred

local function testing(player: Player, amount: number)

end
```

When creating a **variable** or **argument**, simply put a **semicolon** (`:`) after the **name** and then put the **type**.

## Optional Parameters

What if we create a function and specify the parameter types, but maybe we don’t want to always pass through the second parameter when we call this function? We can use a **question mark** (`?`) **after** specifying the **parameter’s type** to indicate that parameter isn’t required!

``` lua
local function RenamePlayer(player: Player, name: string?)
	name = name or "Default"
	player.Name = name
end

RenamePlayer(player) -- Works
RenamePlayer(player, "test") -- Works
```

## Function Return Type

If we have a function which returns something, we can specify this by annotating it after listing the parameters!

``` lua
local function GetSum(num1: number, num2: number): number
	return num1 + num2
end
```

## Union Types

What if we have a variable, which could be a **different type** at multiple points? We can use a **bar** (`|`) to basically act as the word **or** when annotating types!

``` lua
local answer: boolean | string | number = "Yes"
answer = true
answer = 5
```

## Singleton Types

You can create types which are **very specific**!

``` lua
local test: "Yes" | "No" = "Yes"
local test2: 1 | 2 | 3 = 2
```

## Creating Custom Types

Creating a type is similar to creating a variable!

``` lua
type test = number
type test2 = number | string
```

## Getting Types from another Script

Sharing types amongst scripts is a common thing. Personally, I like to make one Module Script in the Replicated Storage where I store all my custom types!

You can use the **keyword** `export` to allow other scripts requiring the module to use those custom types.

``` lua title="ReplicatedStorage/Types.lua"
local Types = {}

export type Pet = {
	Name: string,
	Rarity: string
}

export type PlayerData = {
	Cash: number,
	Gems: number,
	Pets: {
		[string]: Pet
	}
}

return Types
```

``` lua title="ServerScriptService/PlayerData.server.lua"
local Types = require(ReplicatedStorage.Types)

local Template: Types.PlayerData = {
    Cash = 0,
    Gems = 0,
    Pets = {}
}
```

## Type Refinement

A common scenario I find myself in, is I’ll loop through some children within either a Gui or even a Folder in my Workspace. The children I’m looking for might be Parts, but within that same Folder could be Models or other objects. When doing this, **issues** can arise with **auto-completion**, because Studio doesn’t recognize what we looped through are parts.

``` lua
for _, possiblePart in Workspace.Parts:GetChildren() do
	if not possiblePart:IsA("Part") then continue end

	local part: Part = possiblePart
	part.BrickColor = BrickColor.new(1)
end
```

## Assigning a Type to a Module Variable

If you create a variable apart of a Module, you’ll realize that you cannot actually annotate its type. There is a workaround to this, which to be honest, I’m not a huge fan of and usually don’t use, but it is nice to know!

What we can do is create a local variable and annotate its type, then assign the Module variable to be the value of that local variable.

``` lua
local module = {}

local numbers: number = 0
module.Numbers = numbers

return module
```

## Other Resources

With this article, we went through most of the common and basic scenarios to help you understand **type checking**. There are other resources out there, which go into much more details and also touch on the same topics as well!

* [Luau Type Checking Article](https://luau-lang.org/typecheck)
* [Dev Forum Post "Type checking for beginners!"](https://devforum.roblox.com/t/type-checking-for-beginners/1027242)