---
description: c-calculate
---

# Calculate

`c-calculate` is the most basic and frequently used CalcBot command. Simply run `c-calculate` \(or `c-c` for short\), followed by an expression to get the result:

```text
> c-calculate 0.45/240
0.001875

> c-calculate sin(2pi)
0

> c-calculate 0.279*3.11
0.86769
```

You can declare variables and use them within expressions. Use `c-calculate variables` to display your defined evariables, and `c-calculate delete` to delete them:

```text
> c-calculate x=5
5

> c-calculate x=x^2
25

> c-calculate y=6!
720

> c-calculate x+y
745

> c-calculate variables
x: 25
y: 720
ans: 745

> c-calculate delete x y
Sucessfuly deleted variables and functions:
x: 25
y: 720

> c-calculate x+y
`x` is not defined.
```

The special variable `ans` refers to the result of the last calculation you ran:

```text
> c-calculate 12+4
16

> c-calculate ans
16
```

You have access to these constants:

```text
> c-calculate pi
3.14159265358979

> c-calculate tau
6.28318530717959

> c-calculate e
2.718281828459045

> c-calculate phi
1.618033988749895

> c-calculate i
i

> c-calculate true
1

> c-calculate false
0
```

CalcBot supports complex numbers:

```text
> c-calculate sqrt(-16)
4i

> c-calculate (4i+2)^3
-16i-88

> c-calculate ans+16i+88
0
```

You can use prime notation with any function in order to get the estimated nth-order derivative of the function \(aka derivative at a point\):

```text
> c-calculate sin(0)
0

> c-calculate sin'(0)
1

> c-calculate cos(0)
1

> c-calculate cos'(0)
0
```

### Predefined functions

The `calculate` command features a large collection of predefined functions. You can find the full list at the [function reference](../reference/calculate.md).

### Custom functions

You can create custom functions for use in `calculate` and some other commands across CalcBot. You can define custom functions as if they were a variable. For example, here is a custom function that returns an approximation of the `sin` function:

```text
> c-calculate approxsin(x) = x - x^3/3! + x^5/5! - x^7/7!
approxsin(x) = x - x^3/3! + x^5/5! - x^7/7!
```

You can now use this function like any other function:

```text
> c-calculate approxsin(1)
0.841

> c-calculate sin(1)
0.841470984808
```

Custom functions can also have more than one [**parameter**](../reference/glossary.md#parameter):

```text
> c-calculate sumthree(a, b, c) = a + b + c
sumthree(a, b, c) = a + b + c

> c-calculate sumthree(3, 5, 7)
15
```

Custom functions can even have default / optional [**parameters**](../reference/glossary.md#parameter). In this example function, if a user does not provide any [**argument**](../reference/glossary.md#argument), `x` will by default be set to `5`:

```text
> c-calculate opt(x = 5) = if(x is 5, true, false)
opt(x = 5) = if(x is 5, true, false)

> c-calculate opt()
1

> c-calculate opt(5)
1

> c-calculate opt(10)
0
```

### Children commands

The `calculate` command also has a very large host of children commands. The most prominent are:

#### `c-calculate derivative` / `c-calculate integral` / `c-calculate numintegrate`

Self-explanatory:

```text
> c-calculate derivative x^2
2*x

> c-calculate integral 2x
x^2

> c-calculate derivative x^4+15x^3+45x^2+5x-66
4*x^3+45*x^2+90*x+5

> c-calculate integral 4*x^3+45*x^2+90*x+5
x^4+15*x^3+45*x^2+5*x

> c-calculate numintegrate 0 5 x x^2
41.666666666666667
```

#### `c-calculate limit`

Estimate the limit of an expression in terms of `x` as `x` approaches a certain value:

```text
> c-calculate limit 1 (x^2-1)/(x-1)
2

> c-calculate limit 4 (2x^3-128)/(sqrt(x)-2)
384

> c-calculate limit pi/4 sin(pi)
0

> c-calculate limit -∞ 1/x+5
5

> c-calculate limit 0+ 1/x
∞

> c-calculate limit 0- 1/x
-∞
```

#### Piecewise functions

CalcBot's limit command allows you to input piecewise functions. To enter a piecewise function, type the condition, followed by a colon \(`:`\), and the expression for that condition. For example:

```text
> c-calculate limit pi/2 0<=x<=pi : sin(x)
1
```

This computes the limit of a piecewise function defined in the region `0 <= x <= pi`, with the function `sin(x)`, as `x` approaches `pi/2`.

You can add more condition / function pairs after the first one by separating each condition / function pair with a colon \(`:`\):

```text
c-calculate limit pi 0<=x<=pi : sin(x) : pi<x<=10 : x/pi-1
0
```

Here, `0 <= x <= pi` is associated with the expression `sin(x)`, and `pi < x <= 10` is associated with the expression `x/pi-1`.

To summarize, this is the syntax for inputting piecewise functions:

```text
c-calculate limit <x approaches> <condition> : <expression> : <condition 2> : <expression 2> ...
```

#### `c-calculate mode`

Change the calculation mode of `c-calculate` to radians or degrees \(you can type `r` or `d` for short\):

```text
> c-calculate mode radian
Set calculation mode to radians

> c-calculate mode degree
Set calculation mode to degrees
```

#### `c-calculate newtonmethod`

Utilizes the [Newton-Raphson method](https://en.wikipedia.org/wiki/Newton%27s_method) to solve for roots of an expression equal to 0. There are a few caveats to this method, however: \(1\) the method requires that the derivative of the expression be calculable, which isn't possible for certain expressions; \(2\) the method can't reliably detect if there are no roots; \(3\) the results are an _approximation_ of the roots, which is why the precision of the result can sometimes be relatively awkward.

Despite this, Newton's method is still very powerful and can compute highly accurate approximations of roots if the conditions above are laid out.

```text
> c-calculate newtonmethod x 2 x^2+5x+6
-2

> c-calculate newtonmethod x -5.5 x^2+5x+6
-3
```

#### `c-calculate simplify`

Simplify an algebraic expression:

```text
> c-calculate simplify sqrt(1048)
2*sqrt(262)
```

Clicking the show steps button on the response message will display a list of steps taken to reach the result:

```text
> c-calculate simplify sqrt(1048)
sqrt(1048)
Start

sqrt(2*2*2*131)
Express constants with their prime factorization

2*sqrt(2*131)
Apply radical rule: sqrt(a^2) = a, a >= 0

2*sqrt(262)
Final
```

#### `c-calculate solvefor`

This is also a popular children command of CalcBot. Use it to algebraically solve for a variable in an equation. Note, that by not including an equal sign \(`=`\), CalcBot assumes the expression is equal to 0, like the first example below:

```text
> c-calculate solvefor x x^2+5x+6
-2, -3

> c-calculate solvefor y 3y+2=x
(1/3)*(x-2)

> c-calculate solvefor x y=log(2x-1)
(1/2)*(1+10^y)

> c-calculate solvefor c a+2b+c=-2
-2-2*b-a
```

#### `c-calculate tofraction`

This command accepts an expression / decimal number and converts it to a fraction. You can also use this command to simplify fractions. Enclose a number / section of numbers with parenthesis to specify that that section repeats, and / or enter a value for the fourth argument to return the result as a mixed fraction:

```text
> c-calculate tofraction 0.15
3/20

> c-calculate tofraction 0.(3)
1/3

> c-calculate tofraction 1.17 mixed
1 17/100

> c-calculate tofraction 0.(142857)
1/7

> c-calculate tofraction 65/100
13/20
```

