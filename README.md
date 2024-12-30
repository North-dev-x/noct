The following syntax is "incredibly difficult with little to no hand-holding."
This is due to a low level of abstraction from the actual processes that you're calling with the commands.

I mostly made the command syntax this complicated for fun, as a mental exercise.
I call it "North's Overly Complicated Terminal" or NOCT.

The following is a reference for all of the commands, and all of the syntax types used in executing commands.
#### Syntax Reference

##### Command
Defined as any characters following a `:`.
Must **ALWAYS** be the first token of a command.
```diff
- :perms
- :help
- :debug
```
##### String 
Defined as any of the following:
```lua
'this is a string'
"this is also a string"
'meow'
```
##### Option
An option is any characters following a `-` or `--`.
```bash
--noalt
-remote
```

##### Number 
A number is, well, a number.
```lua
10
20
30
40
```
##### Target
The name of a player in the server.
```lua
xAbruptum
funwillpanda2
ChillyDedM8
```

##### General Info
In this documentation:
`<...Type>` will refer to any number of parameters of that type.
`<Type?>` will refer to optional parameters.
`<...Type?>` will refer to any number of parameters, that are optional.

#### Command List
##### :help
Permission Level: Helper

`:help`

Returns a list of all commands and their permission levels.

##### :perms
Permission Level: Helper

`:perms`

Returns your current permission level.

##### :debug
Permission Level: Head Moderator

`:debug`

Teleports you to the debug area.

##### :ban
Permission Level: Moderator

`:ban <...Target>`

Bans the given target(s) from the game.

`:ban -remote <...Number>`

Bans the given UserID(s) from the game.

`:ban -noalt`

The `-noalt` option will cause the Ban API to not automatically search for the user's alts. 
This is only useful in very specific situations.

##### :unban
Permission Level: Moderator

`:unban <...Number>
`
Unbans the given UserID(s) from the game.

##### :wipe
Permission Level: Moderator

`:wipe <...Target>
`
Wipes the given target(s), setting their lives to 0.

##### :silver
Permission Level: Moderator

`:silver <Target?> <Number?>`

Gives the given target(or yourself) the given number (or 5000) of silver.

Examples:
```lua
:silver xAbruptum 30 
:silver -- gives 5k silver to yourself
:silver 60000 -- gives 60k silver to yourself
```

##### :ff
Permission Level: Moderator

`:ff`

Gives you a forcefield.

##### :unff
Permission Level: Moderator

`:unff`

Removes your forcefield.

##### :restore
Permission Level: Junior

`:restore <...Target>`

Restores the given targets.

##### :heal
Permission Level: Moderator

`:heal <Target?>`

Heals yourself, or the given target, to full HP.

##### :givetrinket
Permission Level: Helper

`:givetrinket <...String> <Number?> <Target?>`

Gives the target(or yourself), all of the listed trinkets. (given as string literals)
If a number is passed, it gives you that number of trinkets.-

##### :gate
Permission Level: Head Moderator

`:gate <String>
`
Teleports you to the specified gate location, given as a string literal

##### :giveskill
Permission Level: Head Moderator

`:giveskill <...String> <Target?>`

Gives yourself, or the given target, all of the listed skills.

##### :setname
Permission Level: Head Moderator

`:setname <String> <Target?>`

Sets you or the given target's name to the given string literal.

##### :join
Permission Level: Helper

`:join <Number>
`
Teleports you to the given UserID's server if they are playing the game.

##### :re
Permission Level: Helper

`:re <...Target?> 
`
Respawns you, or the given targets.

##### :globalmsg
Permission Level: Head Moderator

`:globalmsg <String>
`
Replicates the given string as a global message to all running game servers.

##### :goto
Permission Level: Moderator

`:goto <Target>
`
Teleports you to the given target.

##### :bring
Permission Level: Moderator

`:bring <Target>`

Teleports the given target to you.

---
