# NOCT REFERENCE

The following syntax is "incredibly difficult with little to no hand-holding."
This is due to a low level of abstraction from the actual processes that you're calling with the commands.

I mostly made the command syntax this complicated for fun, as a mental exercise.
I call it "North's Overly Complicated Terminal" or NOCT.

The following is a reference for all of the commands, and all of the syntax types used in executing commands.
## Syntax Reference

### Command
Defined as any characters following a `:`.
Must **ALWAYS** be the first token of a command.
```diff
- :perms
- :help
- :debug
```
### String 
Defined as any of the following:
```lua
'this is a string'
"this is also a string"
'meow'
```
### Option
An option is any characters following a `-` or `--`.
```bash
--noalt
-remote
```

### Number 
A number is, well, a number.
```lua
10
20
30
40
```
### Target
The name of a player in the server.
```lua
xAbruptum
funwillpanda2
ChillyDedM8
```

### General Info
In this documentation:
`<...Type>` will refer to any number of parameters of that type.
`<Type?>` will refer to optional parameters.
`<...Type?>` will refer to any number of parameters, that are optional.

## Command List
### :help
Permission Level: Helper

`:help`

Returns a list of all commands and their permission levels.




### :perms
Permission Level: Helper

`:perms`

Returns your current permission level.




### :debug
Permission Level: Head Moderator

`:debug`

Teleports you to the debug area.




### :ban
Permission Level: Moderator

`:ban <...Target>`

Bans the given target(s) from the game.

`:ban -remote <...Number>`

Bans the given UserID(s) from the game.

`:ban -noalt`

The `-noalt` option will cause the Ban API to not automatically search for the user's alts. 
This is only useful in very specific situations.




### :unban
Permission Level: Moderator

`:unban <...Number>
`
Unbans the given UserID(s) from the game.


### :wipe
Permission Level: Moderator

`:wipe <...Target>
`
Wipes the given target(s), setting their lives to 0.




### :silver
Permission Level: Moderator

`:silver <Target?> <Number?>`

Gives the given target(or yourself) the given number (or 5000) of silver.




Examples:
```lua
:silver xAbruptum 30 
:silver -- gives 5k silver to yourself
:silver 60000 -- gives 60k silver to yourself
```

### :ff
Permission Level: Moderator

`:ff`

Gives you a forcefield.




### :unff
Permission Level: Moderator

`:unff`

Removes your forcefield.




### :restore
Permission Level: Junior

`:restore <...Target>`

Restores 1 life to the given targets.




### :heal
Permission Level: Moderator

`:heal <Target?>`

Heals yourself, or the given target, to full HP.




### :givetrinket
Permission Level: Helper

`:givetrinket <...String> <Number?> <Target?>`

Gives the target(or yourself), all of the listed trinkets. (given as string literals)
If a number is passed, it gives you that number of trinkets.




### :gate
Permission Level: Head Moderator

`:gate <String>
`
Teleports you to the specified gate location, given as a string literal




### :giveskill
Permission Level: Head Moderator

`:giveskill <...String> <Target?>`

Gives yourself, or the given target, all of the listed skills.




### :setname
Permission Level: Head Moderator

`:setname <String> <Target?>`

Sets you or the given target's name to the given string literal.




### :join
Permission Level: Helper

`:join <Number>
`
Teleports you to the given UserID's server if they are playing the game.




### :re
Permission Level: Helper

`:re <...Target?> 
`
Respawns you, or the given targets.




### :globalmsg
Permission Level: Head Moderator

`:globalmsg <String>
`
Replicates the given string as a global message to all running game servers.




### :goto
Permission Level: Moderator

`:goto <Target>
`
Teleports you to the given target.




### :bring
Permission Level: Moderator

`:bring <Target>`

Teleports the given target to you.




---


Caffeine is a lightweight, concise, dynamically typed language for use inside of [computer cafe](https://www.roblox.com/games/107901904438609/computer-cafe)'s laptop.


## Hello World
To print to the screen, use `io.out`.
```lua
io.out("Hello, world!")
```

If you need to take command line arguments, create a main function.
```rust
fn main(argc, argv, flags) {
	let current = ""
	io.out(current)
	for i = 2,argc; {
		current ..= argv[i] .. " "
		io.out("\r" .. current)
	}
}
```
*a basic program to take all command line arguments given and output them*

## Types

Caffeine is dynamically-typed, with no support for static typing(yet!)

Typechecking must be done through the `is` and `not` keywords or the standard library's `type` function.
```python
if x is not str; {
	panic("Help!")
}

if type(x) != "str"; {
	return
}
```

Caffeine contains the following types by default.

**str**    : A string (sequence of characters)
**num** : A 64-bit double-precision floating point number.
**bool** : A true or false boolean value.
**tbl**    : A Lua-style table.
**fn**     : A function pointer
**any**   : Any of the above.
**null**   : None of the above.


## Variables

Variables can be declared in two ways:
`const` for constant values
`let` for mutable variables

Variables shadow other variables within their scope, so watch out and try to give variables unique names.

```rust
const PI = math.pi

let answer = 42

do {
	let answer = 3
	io.out(answer) --3
}

io.out(answer) -- 42

PI = 44 -- Compile-time exception: Attempt to change constant 'PI'
```

Variable identifiers(the name) must begin with an alphabetic character or underscore, and can contain any number of alphanumeric characters or underscores

## Operators

There is no operator overloading outside of receiving metatables from interoperating with Lua code, which is a rare use case.


| Name                            | Syntax              | Types | Notes                                                                                                | Example                     |
| ------------------------------- | ------------------- | ----- | ---------------------------------------------------------------------------------------------------- | --------------------------- |
| Addition                        | `a + b`<br>`a += b` | num   |                                                                                                      | `4 + 2 == 6`                |
| Subtraction                     | `a - b`<br>`a -= b` | num   |                                                                                                      | `4 - 2 == 2`                |
| Negation                        | `-a`                | num   |                                                                                                      | `-3 == 0 - 3`               |
| Multiplication                  | `a * b`<br>`a *= b` | num   |                                                                                                      | `2 * 2 == 4`                |
| Division                        | `a / b`<br>`a /= b` | num   | `b` being zero causes a runtime error                                                                | `10 / 2 == 5`               |
| Modulus<br>(remainder division) | `a % b`<br>`a %= b` | num   | `b` being zero causes a runtime error                                                                | `2 % 2 == 0`                |
| Logical And                     | `a and b`           | any   | Non-null values are always truthy                                                                    | `(true and false) == false` |
| Logical Or                      | `a or b`            | any   | Non-null values are always truthy                                                                    | `(true or false) == true`   |
| Logical Not                     | `!a`                | any   | If a value is truthy it will become `false`<br>If a value is falsy(null/false) it will become `true` | `!false` = true             |
| Equality                        | `a == b`            | any   | Equality checking is a boolean expression                                                            | `(2+2 == 4) == true`        |
|                                 |                     |       |                                                                                                      |                             |



## Structs

User-defined data structures can be added via the `struct` keyword.

Structs can contain any number of fields of any type, and fields can have default values.
```rust
struct SomeStruct {
	some_field: str;
	other_field: any;
	field_with_default = "This is a default value!";
}
```

#### Instantiation
A struct can be instantiated with the following syntax.
```rust
let instance = SomeStruct {
	some_field = "Hello!";
	other_field = true;
}
```

You can also create a custom constructor using method implementation.
```rust
impl SomeStruct {
	fn new(value) {
		return SomeStruct {
			some_field = value;
			other_field = null;
		}
	}
}

let instance = SomeStruct.new("Hello!")
```

#### Method implementation
Implement methods on a struct using the `impl` keyword.

```rust
impl SomeStruct {
	fn some_method(self) {
		io.out(self.some_field)
	}
}

instance:some_method() -- Hello!
```





