---
description: All available CalcBot commands (auto generated)
---

# `c-about`

View information about CalcBot.

* **Shorthand**: `c-about`
* **Aliases**: `about`

# `c-admin`

A set of commands only accessible to server admins.

* **Shorthand**: `c-adm`
* **Aliases**: `admin`, `adm`

## `c-admin channellist`

**Admin only**

Display all text channels and whether they are enabled or disabled.

* **Shorthand**: `c-adm cl`
* **Aliases**: `channellist`, `cl`

## `c-admin cleardeleted`

**Admin only**

Remove the specified amount of deleted messages stored with `c-recollect deleted`. The oldest messages are deleted, retaining the newest ones.

* **Shorthand**: `c-adm cd`
* **Aliases**: `cleardeleted`, `cd`
* **Syntax**:
	* `c-admin cleardeleted <amount>`

**Examples**:
```
c-admin cleardeleted 2
```

## `c-admin clearedited`

**Admin only**

Remove the specified amount of edited messages stored with `c-recollect edited`. The oldest messages are deleted, retaining the newest ones.

* **Shorthand**: `c-adm ce`
* **Aliases**: `clearedited`, `ce`
* **Syntax**:
	* `c-admin clearedited <amount>`

**Examples**:
```
c-admin clearedited 2
```

## `c-admin customratio`

**Admin only**

Create server-wide custom ratios for the unit conversion calculator. If there are collisions between user and server custom ratios, the user ratios will be used first.

* **Shorthand**: `c-adm c`
* **Aliases**: `customratio`, `custom`, `cus`, `cr`, `c`

### `c-admin customratio add`

Add a sever-wide custom ratio. View examples of custom ratios with `c-unitconvert customratio`.

* **Shorthand**: `c-adm c a`
* **Aliases**: `add`, `define`, `def`, `a`
* **Syntax**:
	* `c-admin customratio add <quantity> <ratio>`

**Examples**:
```
c-admin customratio add 1.008 g:H/mol
```

### `c-admin customratio delete`

Remove a previously added sever-wide custom ratio.

* **Shorthand**: `c-adm c d`
* **Aliases**: `delete`, `del`, `d`
* **Syntax**:
	* `c-admin customratio delete <quantity> <ratio>`

**Examples**:
```
c-admin customratio delete 1.008 g:H/mol
```

### `c-admin customratio edit`

Replace an existing server-wide custom ratio with another.

* **Shorthand**: `c-adm c e`
* **Aliases**: `edit`, `e`
* **Syntax**:
	* `c-admin customratio edit <quantity> <ratio> <new quantity> <new ratio>`

**Examples**:
```
c-admin customratio edit 1.008 g:H/mol 2.016 g:H2/mol
```

### `c-admin customratio view`

Display all server-wide custom ratios.

* **Shorthand**: `c-adm c l`
* **Aliases**: `view`, `list`, `v`, `l`

## `c-admin disablechannel`

**Admin only**

Set the specified text channels to `disabled` status, preventing CalcBot from sending messages in that channel. Type `all` to disable all channels (except for this one).

* **Shorthand**: `c-adm dc`
* **Aliases**: `disablechannel`, `disablech`, `dc`
* **Syntax**:
	* `c-admin disablechannel all`
	* `c-admin disablechannel <channel name | channel id>...`

**Examples**:
```
c-admin disablechannel all
c-admin disablechannel #general
```

## `c-admin enablechannel`

**Admin only**

Set the specified text channels to `enabled` status, allowing CalcBot to send messages in that channel. Type `all` to enable all channels.

* **Shorthand**: `c-adm ec`
* **Aliases**: `enablechannel`, `enablech`, `ec`
* **Syntax**:
	* `c-admin enablechannel all`
	* `c-admin enablechannel <channel name | channel id>...`

**Examples**:
```
c-admin enablechannel all
c-admin enablechannel #general
```

## `c-admin markchannel`

**Admin only**

Mark the specified text channels. Marked channels will be tracked for message deletions and edits for the `c-recollect` commands.

Note that all channels are unmarked by default.

* **Shorthand**: `c-adm mc`
* **Aliases**: `markchannel`, `markch`, `mc`
* **Syntax**:
	* `c-admin markchannel all`
	* `c-admin markchannel <channel name | channel id>...`

**Examples**:
```
c-admin markchannel all
c-admin markchannel #general
```

## `c-admin setprefix`

**Admin only**

Set the bot's prefix used to call commands. (default `c-`)

**This server's prefix: `c-`**

* **Shorthand**: `c-adm sp`
* **Aliases**: `setprefix`, `setp`, `sp`
* **Syntax**:
	* `c-admin setprefix <prefix>`

**Examples**:
```
c-admin setprefix c-
```

## `c-admin unmarkchannel`

**Admin only**

Unmark the specified text channels. Unmarked channels will **not** be tracked for message deletions and edits for the `c-recollect` commands.

Note that all channels are unmarked by default.

* **Shorthand**: `c-adm uc`
* **Aliases**: `unmarkchannel`, `unmarkch`, `um`, `uc`
* **Syntax**:
	* `c-admin unmarkchannel all`
	* `c-admin unmarkchannel <channel name | channel id>...`

**Examples**:
```
c-admin unmarkchannel all
c-admin unmarkchannel #general
```

# `c-anonreport`

This command functions the same as `c-report`, however your username will **not** be displayed in the #c-report channel on my [support server](https://discord.gg/3m7dK92).

* **Shorthand**: `c-arp`
* **Aliases**: `anonreport`, `anonrep`, `arp`
* **Syntax**:
	* `c-anonreport <message>`

**Examples**:
```
c-anonreport improve matrices
```

# `c-bar`

Use this module to create bar graphs. Use `c-bar quick` to quickly draw a graph with multiple columns, however these graphs will not be saved. Use `c-bar create` to create permanent bar graphs with additional options, such as showing extra analytic columns.

Note that the trigonometric functions are affected by the calculation mode (e.g, radians, degrees) that you set with `c-calculate mode`.

* **Shorthand**: `c-b`
* **Aliases**: `bar`, `b`

## `c-bar addcolumns`

Add the specified columns and amounts, separated by commas, to a bar graph you created with `c-bar create`. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b ac`
* **Aliases**: `addcolumns`, `addcol`, `ac`
* **Syntax**:
	* `c-bar addcolumns <graph id> <column name> : <amount>...`

**Examples**:
```
c-bar addcolumns 1 new column : 5
c-bar addcolumns 1 new column : 5, new column 2 : 5*2
```

## `c-bar axes`

Set the x-axis and y-axis names of a bar graph you created with `c-bar create`. If you would like to only provide a name for the y-axis, simply ignore the `<x axis name>` argument. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b axe`
* **Aliases**: `axes`, `axe`
* **Syntax**:
	* `c-bar axes <graph id> <x axis name>[, <y axis name>]`

**Examples**:
```
c-bar axes 1 x axis column, y axis column
c-bar axes 1 only x axis
c-bar axes 1 , only y axis
```

## `c-bar clearcolumns`

Remove the specified columns, separated by commas, from a bar graph you created with `c-bar create`. Column names are case-insensitive. CalcBot will ignore any nonexistent columns if you enter any. Use `c-bar list` for a list of graphs that you've created. To clear all columns from a graph, type `all` for the `<column names>...` argument.

* **Shorthand**: `c-b cc`
* **Aliases**: `clearcolumns`, `clearcol`, `cc`
* **Syntax**:
	* `c-bar clearcolumns <graph id> <column names>...`

**Examples**:
```
c-bar clearcolumns 1 column name, column name 2
```

## `c-bar create`

Create a new bar graph with the specified initial column(s) and amount(s). You may enter multiple columns and amounts separated by commas.

* **Shorthand**: `c-b a`
* **Aliases**: `create`, `init`, `add`, `cr`, `i`, `a`
* **Syntax**:
	* `c-bar create <initial column> : <initial amount>...`

**Examples**:
```
c-bar create column name : 500
c-bar create x : 0.5, y : 2
```

## `c-bar delete`

Remove a graph you created with `c-bar create`. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b del`
* **Aliases**: `delete`, `del`
* **Syntax**:
	* `c-bar delete <graph id>`

**Examples**:
```
c-bar delete 1
```

## `c-bar draw`

Render a bar graph you created with `c-bar create`. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b d`
* **Aliases**: `draw`, `d`
* **Syntax**:
	* `c-bar draw <graph id>`

**Examples**:
```
c-bar draw 1
```

## `c-bar increment`

Increment the specified column by `<amount>` of a bar graph you created with `c-bar create`. Column names are case-insensitive. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b inc`
* **Aliases**: `increment`, `incr`, `inc`
* **Syntax**:
	* `c-bar increment <graph id> <column name> : <amount>`

**Examples**:
```
c-bar increment 1 column name : pi
```

## `c-bar list`

View a list of bar graphs you created with `c-bar create`.

* **Shorthand**: `c-b v`
* **Aliases**: `list`, `view`, `l`, `v`

## `c-bar option`

Change an option of a bar graph you created with `c-bar create`. The options you can change are:

* `showExtras` - Add an extra **Average** and **Sum** column to your graph during rendering.

* **Shorthand**: `c-b o`
* **Aliases**: `option`, `op`, `o`
* **Syntax**:
	* `c-bar option <graph id> <option> <option's new value>`

**Examples**:
```
c-bar option 1 showExtras on
```

## `c-bar quick`

Quickly create a bar graph with multiple columns. You may enter multiple columns and amounts separated by commas.

* **Shorthand**: `c-b q`
* **Aliases**: `quick`, `q`
* **Syntax**:
	* `c-bar quick <column name> : <column amount>...`

**Examples**:
```
c-bar quick column : 50
c-bar quick column 1 : 100, column 2 : 200
```

## `c-bar renamecolumn`

Rename the specified column from a bar graph you created with `c-bar create`. Column names are case-insensitive. Use `c-bar list` for a list of graphs that you've created.

* **Shorthand**: `c-b rc`
* **Aliases**: `renamecolumn`, `renamecol`, `renc`, `rc`
* **Syntax**:
	* `c-bar renamecolumn <graph id> <old column name>, <new column name>`

**Examples**:
```
c-bar renamecolumn 1 old name, new name
```

# `c-calculate`

Evaluates a given expression, like `1 + 1`. You can declare variables by typing `variablename = [value]`. You can find extended documentation for this command [here](https://chillant.gitbook.io/calcbot/commands/calculate).

* **Shorthand**: `c-c`
* **Aliases**: `calculate`, `calc`, `c`
* **Syntax**:
	* `c-calculate <expression>...`

**Examples**:
```
c-calculate 1+1
c-calculate x=2
c-calculate 5sin(pi/2)
c-calculate 6!
c-calculate f(x)=x^2+5x+6
c-calculate f(2)
c-calculate cos'(0)
```

## `c-calculate arclength`

Calculates the arc length of a function / expression in terms of `x` from `x = a` to `x = b`. If the arc length of the expression could not be computed, an estimation will be provided and marked. If the symbolic integral happens to be computed incorrectly, you can force CalcBot to estimate the definite integral by typing `force` as the first argument.

* **Shorthand**: `c-c al`
* **Aliases**: `arclength`, `arcl`, `al`
* **Syntax**:
	* `c-calculate arclength [force] <a> <b> <expression>`

**Examples**:
```
c-calculate arclength 0 4 x*(x-4)
c-calculate arclength force 0 4 x*(x-4)
```

## `c-calculate defintegrate`

Calculates the definite integral of an expression. If the integral of the expression could not be computed, an estimation will be provided and marked. If the symbolic integral happens to be computed incorrectly, you can force CalcBot to estimate the definite integral by typing `force` as the first argument.

* **Shorthand**: `c-c nin`
* **Aliases**: `defintegrate`, `numintegrate`, `definteg`, `numinteg`, `din`, `nin`
* **Syntax**:
	* `c-calculate defintegrate [force] <low bound> <high bound> <variable> <expression>`

**Examples**:
```
c-calculate defintegrate 0 5 x x^2
c-calculate defintegrate force 0 5 x x^2
```

## `c-calculate delete`

Delete variables and functions defined with `c-calculate`.

* **Shorthand**: `c-c del`
* **Aliases**: `delete`, `del`
* **Syntax**:
	* `c-calculate delete <variable | function name>...`

**Examples**:
```
c-calculate delete x
c-calculate delete a b
```

## `c-calculate deleteall`

Delete all variables or all functions defined with `c-calculate`. Type `v` to delete all variables, and `f` to delete all custom functions.

* **Shorthand**: `c-c da`
* **Aliases**: `deleteall`, `delall`, `da`
* **Syntax**:
	* `c-calculate deleteall [v | f]`

**Examples**:
```
c-calculate deleteall v
c-calculate deleteall f
```

## `c-calculate derivative`

Calculates the derivative of a function / expression in terms of `x`.

* **Shorthand**: `c-c der`
* **Aliases**: `derivative`, `der`
* **Syntax**:
	* `c-calculate derivative <expression>`

**Examples**:
```
c-calculate derivative x^2
```

## `c-calculate distancetravelled`

Calculates the distance a function / expression in terms of `x` travels from `x = a` to `x = b`.

Distance travelled measures the total change in the value of the function in the given interval; it's essentially the opposite of displacement.

For example, the function `x^2` does not displace at all in the interval `x = -1` to `x = 1`, since the function starts and ends on the same spot (`y = 1`). However, the function travels a distance of two units in that interval: one unit from `x = -1` to `x = 0`, and one more unit from `x = 0` to `x = 1`.

* **Shorthand**: `c-c dt`
* **Aliases**: `distancetravelled`, `disttravelled`, `dt`
* **Syntax**:
	* `c-calculate distancetravelled <a> <b> <expression>`

**Examples**:
```
c-calculate distancetravelled 2 5 sin(x*pi/2)
```

## `c-calculate expand`

Expands a given expression.

* **Shorthand**: `c-c exp`
* **Aliases**: `expand`, `exp`
* **Syntax**:
	* `c-calculate expand <expression>`

**Examples**:
```
c-calculate expand (3x^2+2y)^5
c-calculate expand (x^3-3y^2)^4
```

## `c-calculate factor`

Factors a given expression. Support for multivariate polynomials is currently limited.

* **Shorthand**: `c-c fac`
* **Aliases**: `factor`, `fac`
* **Syntax**:
	* `c-calculate factor <expression>`

**Examples**:
```
c-calculate factor x^8+x^7+x^4+x^3
c-calculate factor 3*a*x+3*a*y+3*b*x+3*b*y
```

## `c-calculate integral`

Calculates the indefinite integral of an expression in terms of `x`.

* **Shorthand**: `c-c int`
* **Aliases**: `integral`, `int`
* **Syntax**:
	* `c-calculate integral <expression>`

**Examples**:
```
c-calculate integral x^2
```

## `c-calculate limit`

Estimates the limit of an expression in terms of `x` as `x` approaches the value set. This command returns `NaN` if the limit does not exist. For example, `c-calculate limit 1 (x^2-1)/(x-1)` estimates the limit of `(x^2-1)/(x-1)` as `x` approaches `1`, which is **2**.

Adding a `+` or `-` at the end of the approach argument will change the direction `x` approaches the value set (see examples).

To approach infinity, type any of the following for the `approach` argument: `infinity`, `inf`, `∞`

To input piecewise functions, separate the `x` conditions and function body with a colon (`:`). The condition is associated with the next function (see examples, or head [here](https://chillant.gitbook.io/calcbot/calculate#piecewise-functions)).

* **Shorthand**: `c-c lim`
* **Aliases**: `limit`, `lim`
* **Syntax**:
	* `c-calculate limit <approach> <expression>`

**Examples**:
```
c-calculate limit 1 (x^2-1)/(x-1)
c-calculate limit 4 (2x^3-128)/(sqrt(x)-2)
c-calculate limit pi/4 sin(pi)
c-calculate limit -∞ 1/x+5
c-calculate limit 0+ 1/x
c-calculate limit 0- 1/x
c-calculate limit pi 0<=x<=pi : sin(x) : pi<x<=10 : x/pi-1
c-calculate limit -3 -7<=x<=-3 : sqrt(7+x) : x>-3 : x^2-5
```

## `c-calculate mode`

View or set the angle calculation mode of the calculator. (default **radians**)

* **Shorthand**: `c-c mode`
* **Aliases**: `mode`

**Examples**:
```
c-calculate mode 
c-calculate mode r
```

## `c-calculate newtonmethod`

Use the Newton-Raphson method to **approximate** the roots of a function. This method subtracts the quotient of the expression and its derivative from an initial guess and repeats the process until a sufficiently precise value is reached. Read more about this method [here](https://en.wikipedia.org/wiki/Newton%27s_method "Newton-Raphson method").

The implementation of Newton's Method here iterates this method **10 times.** Therefore, the further the guess is to a root, the less accurate the result will be.

* **Shorthand**: `c-c nm`
* **Aliases**: `newtonmethod`, `nm`
* **Syntax**:
	* `c-calculate newtonmethod <variable> <initial guess> <expression>`

**Examples**:
```
c-calculate newtonmethod x 2 x^2+5x+6
```

## `c-calculate secantline`

Calculates the equation of the secant line that intersects `<expression>` (in terms of `x`) at `x = <start>` and `x = <end>`.

* **Shorthand**: `c-c sl`
* **Aliases**: `secantline`, `sl`
* **Syntax**:
	* `c-calculate secantline <start> <end> <expression>`

**Examples**:
```
c-calculate secantline 1 5 0.5^(-x)
c-calculate secantline 1 3 2/(x+3)
```

## `c-calculate secantmethod`

Use the secant method to **approximate** the roots of a function. This method is similar to the Newton-Raphson method, however the derivative is not needed to compute the roots, and thus may be more appropriate for highly complex functions. This method can also be thought of as a finite-difference approximation of the Newton-Raphson method. Read more about this method [here](https://en.wikipedia.org/wiki/Secant_method "Secant method").

The implementation of the secant method here iterates this method **10 times.** Therefore, the further the guesses are to a root, the less accurate the result will be.

* **Shorthand**: `c-c sm`
* **Aliases**: `secantmethod`, `sm`
* **Syntax**:
	* `c-calculate secantmethod <variable> <initial x_0> <initial x_1> <expression>`

**Examples**:
```
c-calculate secantmethod x 7 9 x^2+5x+6
```

## `c-calculate simplify`

Simplifies a given expression.

* **Shorthand**: `c-c s`
* **Aliases**: `simplify`, `simp`, `sim`, `s`
* **Syntax**:
	* `c-calculate simplify <expression>`

**Examples**:
```
c-calculate simplify 6x+11x+4y-2y
```

## `c-calculate solvefor`

Attempts to solve for a provided variable in the given expression. This command assumes that the expression given is equal to 0, unless if you specify one yourself (see the examples). Variables and functions are independent of `c-calculate`.

* **Shorthand**: `c-c sf`
* **Aliases**: `solvefor`, `solvef`, `sf`
* **Syntax**:
	* `c-calculate solvefor <variable> <expression | equation>`

**Examples**:
```
c-calculate solvefor x x^2+5x+6
c-calculate solvefor y 2y+3=2x
```

## `c-calculate stats`

Computes various descriptive statistics for two or more numbers, including the mean, median, mode, minimum, maximum, and others.

* **Shorthand**: `c-c st`
* **Aliases**: `stats`, `stat`, `st`
* **Syntax**:
	* `c-calculate stats <expression | number> <expression | number>...`

**Examples**:
```
c-calculate stats 1 2 4 5
c-calculate stats 3*6 11/2 5 5 100/9
c-calculate stats 1, 2, 5, 8, 9, 9, 40
```

## `c-calculate systemequations`

Attempts to solve the given system of equations. Variables and functions are independent of `c-calculate`.

* **Shorthand**: `c-c se`
* **Aliases**: `systemequations`, `systemeqs`, `syseq`, `se`
* **Syntax**:
	* `c-calculate systemequations <equation 1> <equation 2>...`

**Examples**:
```
c-calculate systemequations a+b+c=67 3a-2b=40 c+2a=44
```

## `c-calculate tangentline`

Calculates the equation of the tangent line that intersects `<expression>` (in terms of `x`) at `x = <at>`. If the derivative of `<expression>` could not be computed, an estimation will be provided and marked.

* **Shorthand**: `c-c tanl`
* **Aliases**: `tangentline`, `tanl`
* **Syntax**:
	* `c-calculate tangentline <at> <expression>`

**Examples**:
```
c-calculate tangentline 2 x^2
c-calculate tangentline 0 (x-4)(x+2)^2
```

## `c-calculate tofraction`

Convert an expression to a fraction, or reduce a fraction to its minimum. Entering the word "mixed" for the `mixed` argument will show the result in mixed fraction form (if possible).
You may specify repeating sections of a result by enclosing it in parenthesis:
```0.(142857) = 1/7```

* **Shorthand**: `c-c tf`
* **Aliases**: `tofraction`, `tofrac`, `tf`
* **Syntax**:
	* `c-calculate tofraction <expression> [mixed]`

**Examples**:
```
c-calculate tofraction 0.15
c-calculate tofraction 0.(3)
c-calculate tofraction 1.17 mixed
```

## `c-calculate tolatex`

Convert an expression to LaTeX.

* **Shorthand**: `c-c tl`
* **Aliases**: `tolatex`, `tolat`, `tl`
* **Syntax**:
	* `c-calculate tolatex <expression>`

**Examples**:
```
c-calculate tolatex sin(root(2, 16) / 4)
```

## `c-calculate variables`

Display all variables and functions defined in `c-calculate`.

* **Shorthand**: `c-c v`
* **Aliases**: `variables`, `functions`, `funcs`, `vars`, `v`

# `c-chemistry`

A module for various calculations related to chemistry.

* **Shorthand**: `c-ch`
* **Aliases**: `chemistry`, `chem`, `ch`

## `c-chemistry count`

Calculates the number of atoms of each element in a compound, given the mass of the compound in grams (g).

* **Shorthand**: `c-ch co`
* **Aliases**: `count`, `cou`, `co`
* **Syntax**:
	* `c-chemistry count <mass (grams)> <compound>`

**Examples**:
```
c-chemistry count 12.3 KClO3
c-chemistry count 54 Ba(OH)2
```

## `c-chemistry elementinfo`

Displays the properties of an element.

* **Shorthand**: `c-ch ei`
* **Aliases**: `elementinfo`, `eleminfo`, `einfo`, `elem`, `ei`
* **Syntax**:
	* `c-chemistry elementinfo <element name | symbol | atomic number>`

**Examples**:
```
c-chemistry elementinfo hydrogen
```

## `c-chemistry lookup`

Searches for chemical compounds that match the given constraints.

* **Shorthand**: `c-ch se`
* **Aliases**: `lookup`, `search`, `look`, `sear`, `lo`, `se`
* **Syntax**:
	* `c-chemistry lookup <formula | element name | symbol | atomic number>...`

**Examples**:
```
c-chemistry lookup sodium chloride
c-chemistry lookup alumin o
c-chemistry lookup B
c-chemistry lookup acid
```

## `c-chemistry mass`

Calculates the molar mass of a given compound in atomic mass units (grams per mole).

* **Shorthand**: `c-ch ma`
* **Aliases**: `mass`, `ma`
* **Syntax**:
	* `c-chemistry mass <compound>`

**Examples**:
```
c-chemistry mass H2O
```

## `c-chemistry oxidation`

Calculates the oxidation states of all elements in a given compound.

* **Shorthand**: `c-ch oxi`
* **Aliases**: `oxidation`, `oxi`
* **Syntax**:
	* `c-chemistry oxidation <compound> [expected charge]`

**Examples**:
```
c-chemistry oxidation NaCl
c-chemistry oxidation SO4 -2
```

# `c-clock`

Display the current time and date based on your locale and time zone settings.

* **Shorthand**: `c-cl`
* **Aliases**: `clock`, `cl`

# `c-dictionary`

Get the Google Dictionary entry of a word or phrase. You may also provide a [language code](https://chillant.gitbook.io/calcbot/commands/dictionary) for the second argument to search that language's dictionary.

**Note: CalcBot will not filter profanity or other words that might be considered offensive. Use with caution.**

* **Shorthand**: `c-def`
* **Aliases**: `dictionary`, `define`, `dict`, `def`
* **Syntax**:
	* `c-dictionary <word | phrase> [language]`

**Examples**:
```
c-dictionary hello
c-dictionary 안녕 ko
```

# `c-factor`

Lists the factors of a number.

* **Shorthand**: `c-fac`
* **Aliases**: `factor`, `fac`
* **Syntax**:
	* `c-factor <number>`

**Examples**:
```
c-factor 128
```

## `c-factor greatestcommonfactor`

Finds the greatest common factor of two or more numbers.

* **Shorthand**: `c-fac gcf`
* **Aliases**: `greatestcommonfactor`, `gcf`
* **Syntax**:
	* `c-factor greatestcommonfactor <number> <number>...`

**Examples**:
```
c-factor greatestcommonfactor 9 81
```

## `c-factor leastcommonmultiple`

Finds the greatest common factor of two or more numbers.

* **Shorthand**: `c-fac lcm`
* **Aliases**: `leastcommonmultiple`, `lcm`
* **Syntax**:
	* `c-factor leastcommonmultiple <number> <number>...`

**Examples**:
```
c-factor leastcommonmultiple 2 5 11
```

## `c-factor primefactorization`

Calculates the prime factorization of a number.

* **Shorthand**: `c-fac pf`
* **Aliases**: `primefactorization`, `primefac`, `pf`
* **Syntax**:
	* `c-factor primefactorization <number>`

**Examples**:
```
c-factor primefactorization 128
```

# `c-formula`

Calculates a value using one of various internally predefined formulas.
Running a formula will display a prompt for arguments. Enter each argument one-by-one (expressions supported); to leave an argument 'blank' (i.e. the value that will be calculated), type a non-evaluable expression (ex. `idk`). [Here](https://chillant.gitbook.io/calcbot/commands/formula) is a nice GIF showing the process.

For a full list of available formulas, run `c-formula list`.

* **Shorthand**: `c-fo`
* **Aliases**: `formula`, `fo`
* **Syntax**:
	* `c-formula <formula id>`

**Examples**:
```
c-formula tlos
```

## `c-formula list`

Show a list of available formulas.

* **Shorthand**: `c-fo l`
* **Aliases**: `list`, `l`
* **Syntax**:
	* `c-formula list [page num]`

## `c-formula mode`

View or set the angle calculation mode of the formula calculator. (default **radians**)

* **Shorthand**: `c-fo m`
* **Aliases**: `mode`, `m`

**Examples**:
```
c-formula mode 
c-formula mode r
```

# `c-graph`

Use this module to graph functions, equations, etc. Use `c-graph quick` to quickly graph multiple expressions, however these graphs will not be saved. Use `c-graph create` to create permanent graphs with additional options, such as showing function derivatives.

Note that the trigonometric functions are affected by the calculation mode (e.g, radians, degrees) that you set with `c-calculate mode`.

* **Shorthand**: `c-g`
* **Aliases**: `graph`, `g`

## `c-graph addexpressions`

Add the specified expressions, separated by commas, to a graph you created with `c-graph create`. CalcBot will ignore any already existing expressions if you enter any. Use `c-graph list` for a list of graphs that you've created.

* **Shorthand**: `c-g ae`
* **Aliases**: `addexpressions`, `addexp`, `ae`
* **Syntax**:
	* `c-graph addexpressions <graph id> <expressions>...`

**Examples**:
```
c-graph addexpressions 1 y=x^2, y=log(x, e)
c-graph addexpressions 1 y=x^2
```

## `c-graph addpoints`

Add the specified points, separated by commas, from a graph you created with `c-graph create`. CalcBot will ignore any already existing points if you enter any. Use `c-graph list` for a list of graphs that you've created.

* **Shorthand**: `c-g ap`
* **Aliases**: `addpoints`, `addp`, `ap`
* **Syntax**:
	* `c-graph addpoints <graph id> <points>...`

**Examples**:
```
c-graph addpoints 1 (e, 1)
c-graph addpoints 1 (0.5, 2), (e, 1)
```

## `c-graph clearexpressions`

Remove the specified expressions, separated by commas, from a graph you created with `c-graph create`. CalcBot will ignore any nonexistent expressions if you enter any. Use `c-graph list` for a list of graphs that you've created. To clear all expressions from a graph, type `all` for the `<expressions>...` argument.

* **Shorthand**: `c-g ce`
* **Aliases**: `clearexpressions`, `clearexp`, `ce`
* **Syntax**:
	* `c-graph clearexpressions <graph id> <expressions>...`

**Examples**:
```
c-graph clearexpressions 1 y=x^2, y=log(x, e)
c-graph clearexpressions 1 all
```

## `c-graph clearpoints`

Remove the specified points, separated by commas, from a graph you created with `c-graph create`. CalcBot will ignore any nonexistent points if you enter any. Use `c-graph list` for a list of graphs that you've created. To clear all points from a graph, type `all` for the <points>... argument.

* **Shorthand**: `c-g cp`
* **Aliases**: `clearpoints`, `clearp`, `cp`
* **Syntax**:
	* `c-graph clearpoints <graph id> <points>...`

**Examples**:
```
c-graph clearpoints 1 (e, 1)
c-graph clearpoints 1 all
```

## `c-graph create`

Create a new graph with the specified initial expression(s) and (optionally) point(s). You may enter multiple expressions and points separated by commas.

* **Shorthand**: `c-g a`
* **Aliases**: `create`, `init`, `add`, `cr`, `i`, `a`
* **Syntax**:
	* `c-graph create <initial expressions>... [: <initial points>...]`

**Examples**:
```
c-graph create y=x^2
c-graph create y=x^2, y=log(x, e)
c-graph create y=x^2, y=ln(x) : (e, 1)
```

## `c-graph delete`

Remove a graph you created with `c-graph create`. Use `c-graph list` for a list of graphs that you've created.

* **Shorthand**: `c-g del`
* **Aliases**: `delete`, `del`
* **Syntax**:
	* `c-graph delete <graph id>`

**Examples**:
```
c-graph delete 1
```

## `c-graph draw`

Render a graph you created with `c-graph create`. Use `c-graph list` for a list of graphs that you've created.

* **Shorthand**: `c-g d`
* **Aliases**: `draw`, `d`
* **Syntax**:
	* `c-graph draw <graph id>`

**Examples**:
```
c-graph draw 1
```

## `c-graph list`

View a list of graphs you created with `c-graph create`.

* **Shorthand**: `c-g v`
* **Aliases**: `list`, `view`, `l`, `v`

## `c-graph option`

Change an option of a graph you created with `c-graph create`. The options you can change are:

* `autoViewport` - Automatically move the viewport so that all points of interest are visible.
* `pointsOfInterest` - Draw points at function interceptions, as well as y-intercepts and x-intercepts.
* `expressionDerivatives` - Draw the derivative of each function.

* **Shorthand**: `c-g o`
* **Aliases**: `option`, `op`, `o`
* **Syntax**:
	* `c-graph option <graph id> <option> <option's new value>`

**Examples**:
```
c-graph option 1 pointsOfInterest on
c-graph option 1 expressionDerivatives false
```

## `c-graph quick`

Quickly graph an equation(s) / expression(s). You may enter multiple expressions separated by commas. Use the `c-graph quickviewport` command to change the zoom and positioning of the camera in the graph. As of now, this function supports expressions in the formats:
```
y=x
x=y
r=theta
```

* **Shorthand**: `c-g q`
* **Aliases**: `quick`, `q`
* **Syntax**:
	* `c-graph quick <expression>...`

**Examples**:
```
c-graph quick y=x^2
c-graph quick x-sqrt(y)=1
c-graph quick x*y=16
c-graph quick r=3sin(theta)
c-graph quick y>=x^2-4
```

## `c-graph quickviewport`

Change the viewport settings (zoom and positioning) of the `c-graph quick` command. For example, to change the center of the viewport, type `cam: (x, y)` with the position of the new center. To change the axes scale, type `x: [distance from center to side]` or `y: [distance from center to side]` to describe the scale you want. You may leave out any settings you don't want to change. Type `reset` to reset the settings to their defaults.

You may also type `xy: [value]` instead, which will set both the `x` and `y` settings to the same value at once. The first two examples below describe the **default** settings of the graph.

* **Shorthand**: `c-g qv`
* **Aliases**: `quickviewport`, `quickview`, `qv`
* **Syntax**:
	* `c-graph quickviewport <viewport settings>`

**Examples**:
```
c-graph quickviewport cam: (0, 0), x: 10, y: 10
c-graph quickviewport cam: (0, 0), xy: 10
c-graph quickviewport x: 300, y: 20
c-graph quickviewport cam: (pi, 0), x: 2pi
```

## `c-graph trace`

Trace every function defined on a graph you created with `c-graph create` at a given x location. This command will temporarily disable the `pointsOfInterest` option on the graph if it was already enabled.

* **Shorthand**: `c-g t`
* **Aliases**: `trace`, `t`
* **Syntax**:
	* `c-graph trace <graph id> <x location>`

**Examples**:
```
c-graph trace 1 pi/2
```

## `c-graph viewport`

Change the viewport settings (zoom and positioning) of a graph you created with `c-graph create`. For example, to change the center of the viewport, type `cam: (x, y)` with the position of the new center. To change the axes scale, type `x: [distance from center to side]` or `y: [distance from center to side]` to describe the scale you want. You may leave out any settings you don't want to change. Type `reset` to reset the settings to their defaults.

Note: You can set the `gx`, `gy` or `gxy` properties to 0, and CalcBot will automatically determine a grid scale.

**Properties**:
* `cam` = `(number, number)` = center of viewport
* `x`, `y` = `number` = axes scales
* `xy` = modifies both `x` and `y`
* `gx`, `gy` = `number` = grid scales
* `gxy` = modifies both `gx` and `gy`

* **Shorthand**: `c-g vp`
* **Aliases**: `viewport`, `vp`
* **Syntax**:
	* `c-graph viewport <graph id> <viewport settings>`

**Examples**:
```
c-graph viewport 1 cam: (0, 0), x: 10, y: 10
c-graph viewport 1 cam: (0, 0), xy: 10
c-graph viewport 2 x: 300, y: 20
c-graph viewport 2 cam: (pi, 0), x: 2pi
c-graph viewport 1 xy: 20, gxy: 2
```

# `c-help`

Get information on how to use a command. For example, to learn about `c-calculate stats`, run `c-help calculate stats`. All commands have aliases, which are alternative (always shorter) names for commands. You can find them in a command's help embed.

For a list of all commands, run `c-help commands`.

* **Shorthand**: `c-h`
* **Aliases**: `help`, `h`
* **Syntax**:
	* `c-help <command>`

**Examples**:
```
c-help 
c-help calculate stats
```

## `c-help commands`

View a list of available commands.

* **Shorthand**: `c-h l`
* **Aliases**: `commands`, `cmds`, `list`, `cmd`, `l`

# `c-link`

Access various useful links for CalcBot, such as online documentation or CalcBot's invite link.

* **Shorthand**: `c-link`
* **Aliases**: `link`

# `c-matrix`

A module for performing matrix math. A single matrix should be inputted using the following syntax:
```[<value>, <value>...] [<value>, <value>...] ...```
Each set of values enclosed in brackets represents a row in the matrix.

* **Shorthand**: `c-m`
* **Aliases**: `matrix`, `mat`, `m`

## `c-matrix determinant`

Computes the determinant of a matrix.

* **Shorthand**: `c-m det`
* **Aliases**: `determinant`, `deter`, `det`
* **Syntax**:
	* `c-matrix determinant <row 1> <row 2>...`

**Examples**:
```
c-matrix determinant [4, 5, 7, 1] [3, 1, 4, 2] [7, 6, 8, 5] [1, 8, 7, 8]
```

## `c-matrix gaussian`

Performs gaussian elimination on the given matrix, and returns the result in reduced row echelon form. This command can be used to find solutions to linear systems of equations.

* **Shorthand**: `c-m gau`
* **Aliases**: `gaussian`, `gauss`, `gau`
* **Syntax**:
	* `c-matrix gaussian <row 1> <row 2>...`

**Examples**:
```
c-matrix gaussian [2, 1, 7] [3, -2, -7]
```

## `c-matrix inverse`

Computes the inverse of a matrix.

* **Shorthand**: `c-m inv`
* **Aliases**: `inverse`, `inv`
* **Syntax**:
	* `c-matrix inverse <row 1> <row 2>...`

**Examples**:
```
c-matrix inverse [2, 5, 0, 8] [1, 4, 2, 6] [7, 8, 9, 3] [1, 5, 7, 8]
```

## `c-matrix multiply`

Multiplies two matrices.

* **Shorthand**: `c-m mul`
* **Aliases**: `multiply`, `mult`, `mul`
* **Syntax**:
	* `c-matrix multiply <matrix 1> <matrix 2>`

**Examples**:
```
c-matrix multiply [[1, -2, 1] [2, 1, 3]] [[2, 1] [3, 2] [1, 1]]
```

## `c-matrix rowechelon`

Reduces the matrix to row echelon form. If you would like the the **reduced** row echelon form instead, see the `c-matrix gaussian` command.

* **Shorthand**: `c-m ech`
* **Aliases**: `rowechelon`, `rowech`, `row`, `ech`
* **Syntax**:
	* `c-matrix rowechelon <row 1> <row 2>...`

**Examples**:
```
c-matrix rowechelon [-4, 3, 3, 7] [8, 7, 3, -9] [4, 3, 3, 2] [7, 3, 1, 1]
```

# `c-notmath`

A bunch of non-math related things. How dare you; go study for APUSH or something.

* **Shorthand**: `c-nm`
* **Aliases**: `notmath`, `nm`

## `c-notmath aegyo`

Bonus points on the test if you can type that second alias.

* **Shorthand**: `c-nm 애교`
* **Aliases**: `aegyo`, `애교`
* **Syntax**:
	* `c-notmath aegyo <string>`

**Examples**:
```
c-notmath aegyo please don't be mean to me, please?
```

## `c-notmath random`

Generate a random integer; boundaries are inclusive.

* **Shorthand**: `c-nm r`
* **Aliases**: `random`, `rand`, `r`
* **Syntax**:
	* `c-notmath random <max>`
	* `c-notmath random <min> <max>`

**Examples**:
```
c-notmath random 11
c-notmath random 4 11
```

## `c-notmath registeredtrademark`

Get your own custom brand name for free!

* **Shorthand**: `c-nm rt`
* **Aliases**: `registeredtrademark`, `reg`, `rt`
* **Syntax**:
	* `c-notmath registeredtrademark <string>`

**Examples**:
```
c-notmath registeredtrademark The Perfect Bite
c-notmath registeredtrademark [Brand name here]
```

## `c-notmath reverse`

No one will ever figure out your password now!

* **Shorthand**: `c-nm rev`
* **Aliases**: `reverse`, `rev`
* **Syntax**:
	* `c-notmath reverse <string>`

**Examples**:
```
c-notmath reverse !yadhtrib yppah
```

## `c-notmath scramble`

daw tbtlesr l armsreo/sec.
(If you can figure out what the unscrambled sentence is, hit me up)

* **Shorthand**: `c-nm sc`
* **Aliases**: `scramble`, `sc`
* **Syntax**:
	* `c-notmath scramble <letters>`

**Examples**:
```
c-notmath scramble invention
```

## `c-notmath sort`

Sorts a list of numbers / words in ascending / alphabetical order, numbers first. If a minus symbol (`-`) is provided for the first argument, the list will be sorted in descending order instead.

* **Shorthand**: `c-nm so`
* **Aliases**: `sort`, `so`
* **Syntax**:
	* `c-notmath sort <item>...`
	* `c-notmath sort - <item>...`

**Examples**:
```
c-notmath sort 9 5 28 12
c-notmath sort 5 11 this sentence is not in alphabetical order 2
```

## `c-notmath spacer`

The code for this command only takes up 49 characters, but is incredibly useful for sounding like the sloth from Zootopia or something like that.

* **Shorthand**: `c-nm sp`
* **Aliases**: `spacer`, `space`, `sp`
* **Syntax**:
	* `c-notmath spacer <string>`

**Examples**:
```
c-notmath spacer patience, mortal
c-notmath spacer he is the captain now
```

## `c-notmath title`

Converts text to title case. Prepositions and similar words will automatically be ignored.

* **Shorthand**: `c-nm t`
* **Aliases**: `title`, `t`
* **Syntax**:
	* `c-notmath title <string>`

**Examples**:
```
c-notmath title the great escape
c-notmath title what you should do in the event of apocalypse
```

## `c-notmath trademark`

Get your own custom brand name for free, although it has no legal meaning!

* **Shorthand**: `c-nm tm`
* **Aliases**: `trademark`, `tm`
* **Syntax**:
	* `c-notmath trademark <string>`

**Examples**:
```
c-notmath trademark The Perfect Bite
```

## `c-notmath trademarkinator`

I don't know why you would want to make the word "The" your custom brand name, but you do you.

* **Shorthand**: `c-nm tmor`
* **Aliases**: `trademarkinator`, `tminator`, `tmor`
* **Syntax**:
	* `c-notmath trademarkinator <string>`

**Examples**:
```
c-notmath trademarkinator The Perfect Bite, Over and Over Again
```

## `c-notmath uglify`

It'll sound like you're going through puberty.

* **Shorthand**: `c-nm ug`
* **Aliases**: `uglify`, `ug`
* **Syntax**:
	* `c-notmath uglify <string>`

**Examples**:
```
c-notmath uglify mock your friends, but only if they let you
```

## `c-notmath unscramble`

Finds words (up to 100) that can be spelt using the provided letters. The length of the input is used as the word length if not provided.

* **Shorthand**: `c-nm uns`
* **Aliases**: `unscramble`, `unsc`, `uns`
* **Syntax**:
	* `c-notmath unscramble <letters> [word length]`

**Examples**:
```
c-notmath unscramble itonnnive
```

# `c-polynomial`

A module for performing single-variable polynomial math. Polynomials are to be inputted with a syntax similar to:
```
Ax^2+Bx+C
```
Any amount of terms / degree can be used.

* **Shorthand**: `c-p`
* **Aliases**: `polynomial`, `poly`, `p`

## `c-polynomial divide`

Attempts to divide two polynomials using extended synthetic division.

* **Shorthand**: `c-p div`
* **Aliases**: `divide`, `div`
* **Syntax**:
	* `c-polynomial divide <polynomial 1> <polynomial 2>`

**Examples**:
```
c-polynomial divide 4x^4-16x^3+8x^2+12x x^2-x-1
c-polynomial divide 3672x^4-1962x^3-18987x^2+975x+3450 51x-23
```

## `c-polynomial factor`

Attempts to factor a polynomial with integers. This command will soon be replaced by `c-calculate factor`.

* **Shorthand**: `c-p fac`
* **Aliases**: `factor`, `fac`
* **Syntax**:
	* `c-polynomial factor <polynomial>`

**Examples**:
```
c-polynomial factor 4x^4-16x^3+8x^2+12x
c-polynomial factor 3672x^4-1962x^3-18987x^2+975x+3450
```

## `c-polynomial greatestcommonfactor`

Attempts to find the greatest common factor of a polynomial.

* **Shorthand**: `c-p gcf`
* **Aliases**: `greatestcommonfactor`, `gcf`
* **Syntax**:
	* `c-polynomial greatestcommonfactor <polynomial>`

**Examples**:
```
c-polynomial greatestcommonfactor 4x^4-16x^3+8x^2+12x
c-polynomial greatestcommonfactor 3672x^4-1962x^3-18987x^2+975x+3450
```

## `c-polynomial multiply`

Multiplies two polynomials.

* **Shorthand**: `c-p mu`
* **Aliases**: `multiply`, `multi`, `mu`
* **Syntax**:
	* `c-polynomial multiply <polynomial 1> <polynomial 2>`

**Examples**:
```
c-polynomial multiply x+3 x^2-x-1
c-polynomial multiply 12x+5 x^2+2
```

## `c-polynomial rationalroots`

Lists all potential rational roots of a polynomial given its first coefficient and the constant.

* **Shorthand**: `c-p rr`
* **Aliases**: `rationalroots`, `rr`
* **Syntax**:
	* `c-polynomial rationalroots <coefficient of (a)> <constant>`

**Examples**:
```
c-polynomial rationalroots 4 12
c-polynomial rationalroots 3672 3450
```

# `c-radical`

A module for working with radicals. Radicals should be inputted using the following syntax:
```
<coefficient>[<index>](<radicand>)
```
For example, `4[2](5)` means 4 times the square root of 5.

* **Shorthand**: `c-r`
* **Aliases**: `radical`, `rad`, `r`

## `c-radical approximate`

Approximates the given number into a radical with the given root using integers.

* **Shorthand**: `c-r a`
* **Aliases**: `approximate`, `approx`, `a`
* **Syntax**:
	* `c-radical approximate <number> <root>`

**Examples**:
```
c-radical approximate 1.4142135623730951 2
```

## `c-radical simplify`

Attempts to simplify a given radical.

* **Shorthand**: `c-r s`
* **Aliases**: `simplify`, `simp`, `sim`, `s`
* **Syntax**:
	* `c-radical simplify <radical>`

**Examples**:
```
c-radical simplify 4[2](8)
```

# `c-recollect`

Recollect previously deleted / edited messages. The last 15 deleted / edited messages are saved; administrators can clear the history with the `c-admin` commands.

**If you discover personal information of users when using `c-recollect` and are unable to clear this data (`c-admin`) for whatever reason, please notify me (POOLED#9848) on my [support server](https://discord.com/invite/3m7dK92) immediately.**

* **Shorthand**: `c-rc`
* **Aliases**: `recollect`, `rc`

## `c-recollect deleted`

Recollect the last deleted message, or provide an index to get that last deleted message; e.g. `c-recollect deleted 2` returns the 2nd-to-last deleted message.

* **Shorthand**: `c-rc d`
* **Aliases**: `deleted`, `d`
* **Syntax**:
	* `c-recollect deleted [index]`

**Examples**:
```
c-recollect deleted 
c-recollect deleted 2
```

## `c-recollect edited`

Recollect the last edited message, or provide an index to get that last edited message; e.g. `c-recollect edited 2` returns the 2nd-to-last edited message.

* **Shorthand**: `c-rc e`
* **Aliases**: `edited`, `e`
* **Syntax**:
	* `c-recollect edited [index]`

**Examples**:
```
c-recollect edited 
c-recollect edited 2
```

## `c-recollect mark`

Given a message link / ID, along with the ID of the channel it appears in (optional if in the same channel as the message), mark it as **important** to CalcBot. If the message is deleted or edited, CalcBot will capture the changes and make them visible in `c-recollect`. **The channel itself must be marked in order to mark messages within it.**

Note that all messages are marked automatically, except for messages that were sent before CalcBot restarted.

* **Shorthand**: `c-rc m`
* **Aliases**: `mark`, `m`
* **Syntax**:
	* `c-recollect mark <message link>`
	* `c-recollect mark <message id (in current channel)>`
	* `c-recollect mark <channel name | channel id> <message id>`

**Examples**:
```
c-recollect mark 123456789012345678
```

## `c-recollect unmark`

Given a message link / ID, along with the ID of the channel it appears in (optional if in the same channel as the message), unmark it as **important** to CalcBot. This means that CalcBot will no longer watch for changes to that message in `c-recollect`.

Note that all messages are marked automatically, except for messages that were sent before CalcBot restarted.

* **Shorthand**: `c-rc u`
* **Aliases**: `unmark`, `um`, `u`
* **Syntax**:
	* `c-recollect unmark <message link>`
	* `c-recollect unmark <message id (in current channel)>`
	* `c-recollect unmark <channel name | channel id> <message id>`

**Examples**:
```
c-recollect unmark 123456789012345678
```

# `c-regex`

A module to work with regular expressions.

* **Shorthand**: `c-re`
* **Aliases**: `regex`, `re`

## `c-regex match`

Displays all regular expression matches and groups against a string.

* **Shorthand**: `c-re m`
* **Aliases**: `match`, `m`
* **Syntax**:
	* `c-regex match /<regex>/ <string>`

**Examples**:
```
c-regex match /.+/ matches everything
```

## `c-regex replace`

Replaces all regular expression matches against a string with a substitution expression.

* **Shorthand**: `c-re r`
* **Aliases**: `replace`, `rep`, `r`
* **Syntax**:
	* `c-regex replace /<regex>/ /<substitution>/ <string>`

**Examples**:
```
c-regex replace /[aeiou]/ /o/ replace every vowel in this phrase with an o
```

# `c-regression`

A module that provides regression / data analysis for a set of points. Use it to determine a line of best fit, polynomial regression, etc.

There are two methods of inputting data. One way is by entering the points seperated by spaces / commas / etc.:
```(0, 0) (1, 1) (2, 4) (3, 9) (4, 16)```
The second way is by entering the list of x-coordinates and y-coordinates enclosed in brackets seperately:
```[0, 1, 2, 3, 4] [0, 1, 4, 9, 16]```

* **Shorthand**: `c-reg`
* **Aliases**: `regression`, `reg`

## `c-regression exponential`

Fits the input data to an exponential curve in the form `y=a*e^(b*x)`. See the help information for `c-regression` to learn how to input data.

* **Shorthand**: `c-reg e`
* **Aliases**: `exponential`, `expo`, `exp`, `e`
* **Syntax**:
	* `c-regression exponential <data>`

**Examples**:
```
c-regression exponential (0, 1) (1, 2) (2, 5) (3, 8)
c-regression exponential [0, 1, 2, 3] [1, 2, 5, 8]
```

## `c-regression linear`

Fits the input data to a straight line in the form `y=mx+b`. See the help information for `c-regression` to learn how to input data.

* **Shorthand**: `c-reg l`
* **Aliases**: `linear`, `lin`, `l`
* **Syntax**:
	* `c-regression linear <data>`

**Examples**:
```
c-regression linear (0, 0) (1, -1) (2, 5) (3, 8) (4, 5)
c-regression linear [0, 1, 2, 3, 4] [0, -1, 5, 8, 5]
```

## `c-regression logarithmic`

Fits the input data to a logarithmic curve in the form `y=a+b*ln(x)`. See the help information for `c-regression` to learn how to input data.

* **Shorthand**: `c-reg log`
* **Aliases**: `logarithmic`, `log`
* **Syntax**:
	* `c-regression logarithmic <data>`

**Examples**:
```
c-regression logarithmic (2, 1/2) (3, -3/2) (7, -6) (5, -4)
c-regression logarithmic [2, 3, 7, 5] [1/2, -3/2, -6, -4]
```

## `c-regression polynomial`

Fits the input data to a polynomial of the provided degree. See the help information for `c-regression` to learn how to input data.

* **Shorthand**: `c-reg p`
* **Aliases**: `polynomial`, `poly`, `p`
* **Syntax**:
	* `c-regression polynomial <degree> <data>`

**Examples**:
```
c-regression polynomial 2 (-5, 5) (-4, 4) (-3, 1) (-2, 1/2) (-1, 4)
c-regression polynomial 2 [-5, -4, -3, -2, -1] [5, 4, 1, 1/2, 4]
```

## `c-regression power`

Fits the input data to a power law curve in the form `y=a*x^b`. See the help information for `c-regression` to learn how to input data.

* **Shorthand**: `c-reg pow`
* **Aliases**: `power`, `pow`
* **Syntax**:
	* `c-regression power <data>`

**Examples**:
```
c-regression power (1/2, 3) (1, 4) (2, 1) (4, 1/2)
c-regression power [1/2, 1, 2, 4] [3, 4, 1, 1/2]
```

# `c-remind`

Set a reminder with an optional message for a specified interval. You can find the available time units with `c-unitconvert units`. You can view your reminders and their IDs with `c-remind view`. Check the **children commands** field above to see the various ways you can interact with reminders.

For reminders (set in servers) that are 2 minutes or longer, members can click the `Remind me` button on the reminder message in order to receive the reminder with you.

* **Shorthand**: `c-rem`
* **Aliases**: `remind`, `rem`
* **Syntax**:
	* `c-remind <quantity> <time unit> [message]`

**Examples**:
```
c-remind 10 min
c-remind 10 min stop watching youtube
```

## `c-remind at`

Set a reminder with an optional message that will be triggered at the specified time. This command supports both 24-hr and 12-hr times; if you include "AM" or "PM" for the third argument, the time will be interpreted as a 12-hr time.

**Make sure that you have correctly set your time zone settings with the `c-settings` command, or this command will not function properly.**

* **Shorthand**: `c-rem @`
* **Aliases**: `at`, `@`
* **Syntax**:
	* `c-remind at <hour>:<minute> [AM | PM] [message]`

**Examples**:
```
c-remind at 10:30 AM party time
c-remind at 22:00 stop watching youtube
```

## `c-remind delete`

Delete a specified reminder by its reminder ID. You can view your reminders and their reminder IDs with `c-remind view`.

* **Shorthand**: `c-rem d`
* **Aliases**: `delete`, `del`, `d`
* **Syntax**:
	* `c-remind delete <reminder id>`

**Examples**:
```
c-remind delete 4bxB
```

## `c-remind edit`

Change the interval of a specified reminder by its reminder ID. If the `[new message]` argument is left empty, it will **not** be changed. You can find the available time units with `c-unitconvert units`. You can view your reminders and their reminder IDs with `c-remind view`.

* **Shorthand**: `c-rem e`
* **Aliases**: `edit`, `e`
* **Syntax**:
	* `c-remind edit <reminder id> <new quantity> <new time unit> [new message]`

**Examples**:
```
c-remind edit 4bxB 10 sec
c-remind edit 4bxB 15 sec this is the new message :)
```

## `c-remind every`

Set a **recurring** reminder with an optional message that will be triggered at the specified time. Upon triggering, the reminder will automatically be renewed for the specified time interval. To avoid spam, the reminder interval must be **at least 1 minute.**

* **Shorthand**: `c-rem ev`
* **Aliases**: `every`, `ev`
* **Syntax**:
	* `c-remind every <quantity> <time unit> [message]`

**Examples**:
```
c-remind every 10 min
c-remind every 1 min level up
```

## `c-remind increment`

Increments a specified reminder by its reminder ID, allowing you to add or remove time from the reminder easily. The default time unit increment is **minutes**. You can find the available time units with `c-unitconvert units`. You can view your reminders and their reminder IDs with `c-remind view`.

* **Shorthand**: `c-rem i`
* **Aliases**: `increment`, `incr`, `inc`, `i`
* **Syntax**:
	* `c-remind increment <reminder id> <quantity> [time unit]`

**Examples**:
```
c-remind increment 4bxB 1
c-remind increment 4bxB 2.5 hr
c-remind increment 4bxB -10 min
```

## `c-remind pause`

Pause a specified reminder by its reminder ID. You can view your reminders and their reminder IDs with `c-remind view`.

* **Shorthand**: `c-rem p`
* **Aliases**: `pause`, `p`
* **Syntax**:
	* `c-remind pause <reminder id>`

## `c-remind recur`

Toggles the recurring status of a specified reminder. If the reminder is already set to recur, this command will disable its recurring status. If the reminder is not set to recur, you must also specify the time interval the reminder will recur with once it triggers.

* **Shorthand**: `c-rem rec`
* **Aliases**: `recur`, `rec`
* **Syntax**:
	* `c-remind recur <reminder id> [<quantity> <time unit>]`

**Examples**:
```
c-remind recur 4bxB
c-remind recur 4bxB 1 min
```

## `c-remind resume`

Resume a specified reminder by its reminder ID. You can view your reminders and their reminder IDs with `c-remind view`.

* **Shorthand**: `c-rem r`
* **Aliases**: `resume`, `res`, `r`
* **Syntax**:
	* `c-remind resume <reminder id>`

## `c-remind view`

View all of your active reminders.

* **Shorthand**: `c-rem l`
* **Aliases**: `view`, `list`, `v`, `l`

# `c-report`

Make a request for a feature you want to see added to the bot, or report a bug with one of CalcBot's commands. Reports are publicly visible at my support server, [here](https://discord.gg/3m7dK92).

* **Shorthand**: `c-rp`
* **Aliases**: `report`, `rep`, `rp`
* **Syntax**:
	* `c-report <message>`

**Examples**:
```
c-report improve matrices
```

# `c-scatter`

**This command is in development! Check back later if you'd like.**

Use this module to create scatter plots. Use `c-scatter quick` to quickly draw a graph with a set of data points, however these graphs will not be saved. Use `c-scatter create` to create permanent graphs with additional options and features, such as performing regression analysis and trend estimation.

Note that the trigonometric functions are affected by the calculation mode (e.g, radians, degrees) that you set with `c-calculate mode`.

* **Shorthand**: `c-sc`
* **Aliases**: `scatter`, `sca`, `sc`

# `c-sequence`

Predicts the next number in an arithmetic / geometric sequence. Extra commands are available for finding the sum of several terms of an expression, listing the terms of the sequence, etc., etc.

* **Shorthand**: `c-s`
* **Aliases**: `sequence`, `seq`, `s`
* **Syntax**:
	* `c-sequence <number> <number>...`

**Examples**:
```
c-sequence 1 3 6 10 15
```

## `c-sequence makearithmetic`

Given the first term and common difference of a sequence, or two values and where they lie in an arithmetic sequence, calculate the general formula for the arithmetic sequence. For example:
`c-sequence makearithmetic 1 4 4 15` = find the formula for a sequence whose first term is 4, and fourth term is 15

* **Shorthand**: `c-s ma`
* **Aliases**: `makearithmetic`, `ma`
* **Syntax**:
	* `c-sequence makearithmetic <first term> <common difference>`
	* `c-sequence makearithmetic <start location> <start value> <end location> <end value>`

**Examples**:
```
c-sequence makearithmetic 2 -2
c-sequence makearithmetic 1 4 4 15
```

## `c-sequence sum`

Calculates the sum of the terms from <start location> to <end location> of the given expression in terms of `n`.

* **Shorthand**: `c-s s`
* **Aliases**: `sum`, `s`
* **Syntax**:
	* `c-sequence sum <start location> <end location> <expression>`

**Examples**:
```
c-sequence sum 1 24 5n-3
```

## `c-sequence terms`

Displays the terms between the <start location> and <end location> of the given expression in terms of `n`. Up to 30 terms are shown at a time.

* **Shorthand**: `c-s t`
* **Aliases**: `terms`, `t`
* **Syntax**:
	* `c-sequence terms <start location> <end location> <expression>`

**Examples**:
```
c-sequence terms 1 5 3n+4
```

## `c-sequence toformula`

Calculates the formula for achieving the nth term of the sequence. This comand assumes that the sequence entered begins on the first term.

* **Shorthand**: `c-s tf`
* **Aliases**: `toformula`, `tf`
* **Syntax**:
	* `c-sequence toformula <number> <number>...`

**Examples**:
```
c-sequence toformula 1 3 6 10 15
```

# `c-settings`

A set of commands accessible to all users to customize CalcBot's behavior.

* **Shorthand**: `c-set`
* **Aliases**: `settings`, `setting`, `set`

## `c-settings calcin`

The `calc_in` setting determines how your input for `c-calculate` is parsed. This setting will also affect the input settings of certain commands across CalcBot, like `c-vector define`. These are the list of available modes:

* `dec` (default) - Decimal numbers are represented with a period / dot (`.`); function parameters are separated by commas (`,`)
* `com` - Decimal numbers are represented with a comma (`,`); function parameters are separated by periods / dots (`.`)

**Your current setting**: `{setting}`

* **Shorthand**: `c-set ci`
* **Aliases**: `calcin`, `ci`
* **Syntax**:
	* `c-settings calcin <mode>`

## `c-settings calcout`

The `calc_out` setting determines how results in `c-calculate` are formatted. This setting will also affect the results of certain commands across CalcBot, like `c-unitconvert`. These are the list of available modes:

* `auto` (default) - Displays all numbers as decimals, switching to scientific / imaginary notation as needed
* `scin` - Displays all numbers in scientific notation
* `frac` - Displays all numbers as a fraction
* `word` - Displays all numbers in word form

**Your current setting**: `{setting}`

* **Shorthand**: `c-set co`
* **Aliases**: `calcout`, `co`
* **Syntax**:
	* `c-settings calcout <mode>`

## `c-settings locale`

The `locale` setting determines how dates (in the `c-recollect` commands) are rendered. The default is `en-US`, signifying the English language as used in the USA. Here are examples and useful links to find your specific locale:

* `en-GB` - English as used in Great Britain
* `vi-VN` - Vietnamese language as used in Vietnam
* `ko-KR` - Korean language as used in South Korea
* [JavaScript locale syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl#Locale_identification_and_negotiation)
* [ISO 639-1 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
* [ISO 3166-1 alpha-2 country codes](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements)

**Your current setting**: `{setting}`

* **Shorthand**: `c-set loc`
* **Aliases**: `locale`, `loc`
* **Syntax**:
	* `c-settings locale <locale>`

## `c-settings timezone`

The `time_zone` setting is used to provide the time in the `c-clock` command and the functionality of the `c-remind at` command. The default is `+0`, the offset for Coordinated Universal Time. You can find the UTC offset of your current time zone with a quick [Google search](https://google.com/search?q=what%20is%20my%20time%20zone "Did it for you!").

**Your current setting**: `{setting}`

* **Shorthand**: `c-set tz`
* **Aliases**: `timezone`, `time`, `tz`
* **Syntax**:
	* `c-settings timezone <UTC time offset>`

# `c-unitconvert`

Convert a quantity from one unit / ratio to another.
CalcBot supports server-unique and user-unique custom ratios; run `c-unitconvert customratio` for more info.
Run `c-unitconvert units` to see a list of supported units.

**CalcBot uses the US customary measurement system.** You can read about its differences with the imperial system [here](https://en.wikipedia.org/wiki/Comparison_of_the_imperial_and_US_customary_measurement_systems).

* **Shorthand**: `c-uc`
* **Aliases**: `unitconvert`, `unco`, `uc`
* **Syntax**:
	* `c-unitconvert <quantity> <unit | ratio> <to unit | ratio>`

**Examples**:
```
c-unitconvert 18 sec min
c-unitconvert 14 mi/hr km/sec
```

## `c-unitconvert customratio`

Create custom ratios for the unit conversion calculator. Custom ratios are unique to the user who added them, and will be used automatically if possible.

This is an example of a custom ratio definition:
`1.008 g:H/mol`

This makes the unit `g:H` available as 1.008 of a mol, and the user who added it will be able to convert `g:H` to `mol`, and then to `atom`, and back again. As demonstrated by this example, you may use predefined units from `c-unitconvert units` in your custom ratios, and custom ratios will **take precedence over predefined ratios**.

* **Shorthand**: `c-uc c`
* **Aliases**: `customratio`, `custom`, `cus`, `cr`, `c`

### `c-unitconvert customratio add`

Add a custom ratio. View examples of custom ratios with `c-unitconvert customratio`.

* **Shorthand**: `c-uc c a`
* **Aliases**: `add`, `define`, `def`, `a`
* **Syntax**:
	* `c-unitconvert customratio add <quantity> <ratio>`

**Examples**:
```
c-unitconvert customratio add 1.008 g:H/mol
```

### `c-unitconvert customratio delete`

Remove a previously added custom ratio.

* **Shorthand**: `c-uc c d`
* **Aliases**: `delete`, `del`, `d`
* **Syntax**:
	* `c-unitconvert customratio delete <quantity> <ratio>`

**Examples**:
```
c-unitconvert customratio delete 1.008 g:H/mol
```

### `c-unitconvert customratio edit`

Replace an existing custom ratio with another.

* **Shorthand**: `c-uc c e`
* **Aliases**: `edit`, `e`
* **Syntax**:
	* `c-unitconvert customratio edit <quantity> <ratio> <new quantity> <new ratio>`

**Examples**:
```
c-unitconvert customratio edit 1.008 g:H/mol 2.016 g:H2/mol
```

### `c-unitconvert customratio view`

Display all created custom ratios.

* **Shorthand**: `c-uc c l`
* **Aliases**: `view`, `list`, `v`, `l`

## `c-unitconvert units`

Show a list of units supported by the unit conversion calculator.

* **Shorthand**: `c-uc u`
* **Aliases**: `units`, `unit`, `u`
* **Syntax**:
	* `c-unitconvert units [page num]`

# `c-vector2`

A module for math with two-dimensional vectors.

* **Shorthand**: `c-v2`
* **Aliases**: `vector2`, `vec2`, `v2`

## `c-vector2 calculate`

Evaluates a given vector expression, like `i + (0, 1)`. Your defined vectors are available for use in this command. A full list of documentation and functions you can use in this command can be found [here](https://chillant.gitbook.io/calcbot/reference/vector2).

* **Shorthand**: `c-v2 c`
* **Aliases**: `calculate`, `calc`, `c`
* **Syntax**:
	* `c-vector2 calculate <expression>`

**Examples**:
```
c-vector2 calculate i + (0, 1)
```

## `c-vector2 component`

Returns the provided vector in component form.

* **Shorthand**: `c-v2 comp`
* **Aliases**: `component`, `comp`
* **Syntax**:
	* `c-vector2 component <vector>`
	* `c-vector2 component <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 component 1 4 2 5
```

## `c-vector2 define`

Defines a vector that can be used in `c-vector2`'s children commmands. Expressions (as used in `c-calculate`) can be used to define the vector values, but there must be **no** spaces between any element of the expression, as they will be treated as arguments.
Use `c-vector2 list` to display all your defined vectors.

* **Shorthand**: `c-v2 def`
* **Aliases**: `define`, `def`
* **Syntax**:
	* `c-vector2 define <name> <x> <y>`
	* `c-vector2 define <name> <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 define x 2 2
c-vector2 define x 1 4 4 5
c-vector2 define x 3cos(45) 3sin(45)
```

## `c-vector2 definepolar`

Defines a vector given in polar form (magnitude and angle) that can be used in `c-vector2`'s children commmands. Expressions (as used in `c-calculate`) can be used to define the vector values, but there must be **no** spaces between any element of the expression, as they will be treated as arguments.
Use `c-vector2 list` to display all your defined vectors.

* **Shorthand**: `c-v2 dp`
* **Aliases**: `definepolar`, `defpolar`, `defp`, `dp`
* **Syntax**:
	* `c-vector2 definepolar <name> <m> <a>`

**Examples**:
```
c-vector2 definepolar x 4 135
c-vector2 definepolar x 3cos(45) 3sin(45)
```

## `c-vector2 delete`

Remove a previously defined vector.

* **Shorthand**: `c-v2 del`
* **Aliases**: `delete`, `del`
* **Syntax**:
	* `c-vector2 delete <name>`

**Examples**:
```
c-vector2 delete x
```

## `c-vector2 deleteall`

Delete all two-dimensional vectors defined with `c-vector2 define`. Type `y` as the first argument to confirm the deletion.

* **Shorthand**: `c-v2 da`
* **Aliases**: `deleteall`, `delall`, `da`
* **Syntax**:
	* `c-vector2 deleteall <y>`

**Examples**:
```
c-vector2 deleteall y
```

## `c-vector2 directionangle`

Returns the direction angle of the vector based on unit vector `i`. For example, unit vector `j`'s direction angle is 90 degrees.

* **Shorthand**: `c-v2 da`
* **Aliases**: `directionangle`, `dirangle`, `dirang`, `dang`, `dir`, `da`
* **Syntax**:
	* `c-vector2 directionangle <vector>`
	* `c-vector2 directionangle <x> <y>`
	* `c-vector2 directionangle <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 directionangle -2 2
```

## `c-vector2 dot`

Calculates the dot product of two vectors. Defined vectors are automatically temporarily converted to their component form for this calculation.

* **Shorthand**: `c-v2 dot`
* **Aliases**: `dot`
* **Syntax**:
	* `c-vector2 dot <vector 1> <vector 2>`
	* `c-vector2 dot <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 dot 1 0 0 1
```

## `c-vector2 list`

Display all vectors that were defined using `c-vector2 define` and `c-vector2 definepolar`.

* **Shorthand**: `c-v2 l`
* **Aliases**: `list`, `l`

## `c-vector2 magnitude`

Returns the magnitude of the provided vector.

* **Shorthand**: `c-v2 mag`
* **Aliases**: `magnitude`, `mag`
* **Syntax**:
	* `c-vector2 magnitude <vector>`
	* `c-vector2 magnitude <x> <y>`
	* `c-vector2 magnitude <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 magnitude 2 2
```

## `c-vector2 mode`

View or set the angle calculation mode of both two-dimensional / three-dimensional vectors. (default **degrees**)

* **Shorthand**: `c-v2 m`
* **Aliases**: `mode`, `m`

**Examples**:
```
c-vector2 mode 
c-vector2 mode r
```

## `c-vector2 unit`

Returns the unit vector of the provided vector.

* **Shorthand**: `c-v2 u`
* **Aliases**: `unit`, `u`
* **Syntax**:
	* `c-vector2 unit <vector>`
	* `c-vector2 unit <x> <y>`
	* `c-vector2 unit <x1> <y1> <x2> <y2>`

**Examples**:
```
c-vector2 unit 1 4 2 5
```

# `c-vector3`

A module for math with three-dimensional vectors.

* **Shorthand**: `c-v3`
* **Aliases**: `vector3`, `vec3`, `v3`

## `c-vector3 calculate`

Evaluates a given vector expression, like `i + j + k`. Your defined vectors are available for use in this command. A full list of documentation and functions you can use in this command can be found [here](https://chillant.gitbook.io/calcbot/reference/vector3).

* **Shorthand**: `c-v3 c`
* **Aliases**: `calculate`, `calc`, `c`
* **Syntax**:
	* `c-vector3 calculate <expression>`

**Examples**:
```
c-vector3 calculate i + j + k
```

## `c-vector3 component`

Returns the provided vector in component form.

* **Shorthand**: `c-v3 comp`
* **Aliases**: `component`, `comp`
* **Syntax**:
	* `c-vector3 component <vector>`
	* `c-vector3 component <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 component 1 4 6 2 5 1
```

## `c-vector3 crossproduct`

Calculates the cross product of two vectors. Defined vectors are automatically temporarily converted to their component form for this calculation.

* **Shorthand**: `c-v3 cp`
* **Aliases**: `crossproduct`, `cross`, `cr`, `cp`
* **Syntax**:
	* `c-vector3 crossproduct <vector 1> <vector 2>`
	* `c-vector3 crossproduct <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 crossproduct 1 0 2 2 0 1
```

## `c-vector3 define`

Defines a vector that can be used in `c-vector3`'s children commmands. Expressions (as used in `c-calculate`) can be used to define the vector values, but there must be **no** spaces between any element of the expression, as they will be treated as arguments.
Use `c-vector3 list` to display all your defined vectors.

* **Shorthand**: `c-v3 def`
* **Aliases**: `define`, `def`
* **Syntax**:
	* `c-vector3 define <name> <x> <y> <z>`
	* `c-vector3 define <name> <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 define x 2 2 4
c-vector3 define x 1 4 4 2 5 6
c-vector3 define x 3cos(45) 3sin(45) tan(45)
```

## `c-vector3 definepolar`

Defines a vector given in polar form (magnitude, inclination, azimuth) that can be used in `c-vector3`'s children commmands. Expressions (as used in `c-calculate`) can be used to define the vector values, but there must be **no** spaces between any element of the expression, as they will be treated as arguments.
Use `c-vector3 list` to display all your defined vectors.

* **Shorthand**: `c-v3 dp`
* **Aliases**: `definepolar`, `defpolar`, `defp`, `dp`
* **Syntax**:
	* `c-vector3 definepolar <name> <m> <i> <a>`

**Examples**:
```
c-vector3 definepolar x 4 135 45
c-vector3 definepolar x 3cos(45) 3sin(45) tan(45)
```

## `c-vector3 delete`

Remove a previously defined vector.

* **Shorthand**: `c-v3 del`
* **Aliases**: `delete`, `del`
* **Syntax**:
	* `c-vector3 delete <name>`

**Examples**:
```
c-vector3 delete x
```

## `c-vector3 deleteall`

Delete all three-dimensional vectors defined with `c-vector3 define`. Type `y` as the first argument to confirm the deletion.

* **Shorthand**: `c-v3 da`
* **Aliases**: `deleteall`, `delall`, `da`
* **Syntax**:
	* `c-vector3 deleteall <y>`

**Examples**:
```
c-vector3 deleteall y
```

## `c-vector3 directionangle`

Returns the direction angle of the vector about the specified axis (`x`, `y`, `z`).

* **Shorthand**: `c-v3 da`
* **Aliases**: `directionangle`, `dirangle`, `dirang`, `dang`, `dir`, `da`
* **Syntax**:
	* `c-vector3 directionangle <axis> <vector>`
	* `c-vector3 directionangle <axis> <x> <y> <z>`
	* `c-vector3 directionangle <axis> <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 directionangle x -2 2 0
```

## `c-vector3 dot`

Calculates the dot product of two vectors. Defined vectors are automatically temporarily converted to their component form for this calculation.

* **Shorthand**: `c-v3 dot`
* **Aliases**: `dot`
* **Syntax**:
	* `c-vector3 dot <vector 1> <vector 2>`
	* `c-vector3 dot <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 dot 1 0 2 2 0 1
```

## `c-vector3 list`

Display all vectors that were defined using `c-vector3 define` and `c-vector3 definepolar`.

* **Shorthand**: `c-v3 l`
* **Aliases**: `list`, `l`

## `c-vector3 magnitude`

Returns the magnitude of the provided vector.

* **Shorthand**: `c-v3 mag`
* **Aliases**: `magnitude`, `mag`
* **Syntax**:
	* `c-vector3 magnitude <vector>`
	* `c-vector3 magnitude <x> <y> <z>`
	* `c-vector3 magnitude <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 magnitude 2 2 6
```

## `c-vector3 mode`

View or set the angle calculation mode of both two-dimensional / three-dimensional vectors. (default **degrees**)

* **Shorthand**: `c-v3 m`
* **Aliases**: `mode`, `m`

**Examples**:
```
c-vector3 mode 
c-vector3 mode r
```

## `c-vector3 unit`

Returns the unit vector of the provided vector.

* **Shorthand**: `c-v3 u`
* **Aliases**: `unit`, `u`
* **Syntax**:
	* `c-vector3 unit <vector>`
	* `c-vector3 unit <x> <y> <z>`
	* `c-vector3 unit <x1> <y1> <z1> <x2> <y2> <z2>`

**Examples**:
```
c-vector3 unit 1 4 5 2 5 6
```