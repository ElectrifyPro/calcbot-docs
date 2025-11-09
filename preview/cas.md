---
description: Introduction to `cas-rs`, the upcoming new computer algebra system
---

# Introduction

`cas-rs` is the new computer algebra system that will eventually power CalcBot,
including the `c-calculate` command, and practically every other command that
involves math. It's designed to be significantly faster, more accurate and more
feature-rich than the current system. Even if you don't need or use the new
features, you'll still benefit from very fast calculations.

## What's the `-rs` for?

`-rs` is often added to the names of projects written in the
[**Rust**](https://www.rust-lang.org/) programming language. You can browse all
the code for `cas-rs` [here on GitHub](https://github.com/ElectrifyPro/cas-rs).

All you really want to know is that Rust makes `cas-rs` **_really fast_**.

## Usage

You can try `cas-rs` right now in CalcBot by enabling [preview
mode](preview/introduction.md), then using the `c-calculate` command as normal.
It will function just like the previous `c-calculate`, but your input is fed to
`cas-rs` instead of the current system, except the calculation will be
noticeably faster.

```text
> c-calculate 0.45/240
0.001875

> c-calculate sin(2pi)
0

> c-calculate 0.279*3.11
0.86769
```

## Improvements over the current system

`cas-rs` introduces many new features and bug fixes that make calculations much
easier and more powerful.

### Better errors

When an error occurs in `cas-rs`, you'll now get a neat diagram explaining
exactly what went wrong, and in most cases, how to fix it. Here's an example:

```
> c-calculate log()
Error: missing required argument #1 for the `log` function
   ╭─[input:1:1]
   │
 1 │ log( )
   │ ──┬─ ─
   │   ╰───── this function call
   │
   │ Help: the `log` function takes 2 argument(s); there are 0 argument(s) provided here
   │
   │ Note: function signature: `log(n: Complex, base: Complex (optional))
```

Compare this to the current system's error message:

```
> c-calculate log()
log()
     
The first argument of the `log` function must be of type `number` or `complex`.
Evaluated to: undefined
```

### Lists

Lists are a new type of data in `cas-rs`, which let you group multiple values
together in a sequence. Lists are created using square brackets `[]`, with
values inside, separated by commas:

```text
> c-calculate list = [1, 2, 3, 4, 5]
[1, 2, 3, 4, 5]
```

Perhaps the most useful feature of lists is that you can perform operations on
all elements of a list at once. For example, to convert multiple temperatures
from Celsius to Fahrenheit in one go:

```text
> c-calculate c = [0, 20, 37, 100]
[0, 20, 37, 100]

> c-calculate f = c * 9/5 + 32
[32, 68, 98.6, 212]
```

This extends to nested lists as well, allowing you to simulate operations on
matrices, and more:

```text
> c-calculate matrix = [[1, 2], [3, 4]]
[[1, 2], [3, 4]]

> c-calculate 2matrix
[[2, 4], [6, 8]]
```

### Conditionals

`cas-rs` introduces conditional expressions, which let you choose between two or
more values based on various conditions. This was previously possible with the
`if` function, but the new syntax is significantly more readable and
programming-like. For example, to calculate whether a year is a leap year or
not:

```text
> c-calculate year = 2024
2024

> c-calculate isleapyear = {
    if year % 400 == 0 {
        true
    } else if year % 100 == 0 {
        false
    } else if year % 4 == 0 {
        true
    } else {
        false
    }
}
true
```

The old way of doing this using the `if` function was much more difficult to
read. See for yourself:

```text
> c-calculate year = 2024
2024

> c-calculate isleapyear = if(year % 4 == 0, if(year % 100 == 0, if(year % 400 == 0, true, false), true), false)
1
```

### Functions

Functions let you encapsulate a piece of logic or calculation, and reuse it
multiple times. In `cas-rs`, functions are now truly real functions! They can
span multiple lines and contain complex logic, including anything introduced
here.

### Loops

`cas-rs` introduces loops, which let you repeat a block of code / calculation
multiple times.

A `for` loop runs a calculation a specific number of times. Here's an example
of a function that performs Newton's method to solve a given equation. It uses
_prime notation_ (`f'(guess)`), which has actually existed in CalcBot for a
while:

```text
> c-calculate newton(f, guess) = {
    for i in 0..10 {
        guess -= f(guess) / f'(guess)
    }
    guess
}; newton(f(x) = x^2 + 5x + 6, 0)
-2
```

`for in in 0..10` means "repeat the following code 10 times, with `i` taking
values from 0 to 9". The loop variable `i` can be used within the

### Summation and product notation

There is a new syntax for computing the sum or product of a sequence, using the
`sum` and `product` keywords. This was previously possible using the `sum` and
`product` functions, however the new syntax is more concise and easier to read.

```text
> c-calculate sum n in 1..=100 of n
5050
```

### Assignment actually works

Function and variable assignment was actually very broken in the current system. The system to detect assignments was very fragile and could warp the input in unexpected ways. Try this in `c-calculate`:

```text
> c-calculate 3 / (8) == 3 / 8
ERROR: `3 /` cannot be used as a function name.

> c-calculate (35-b)+b+(32-b)==78
ERROR: `(35-b)+b+` cannot be used as a function name.
```

`cas-rs` fixes this, so you can now assign variables and functions and use them within expressions.

```text
```
