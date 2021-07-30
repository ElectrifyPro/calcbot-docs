---
description: Function reference for c-calculate
---

# Calculate

## General

### c-c &lt;expression&gt;

Shorthand syntax for `c-calculate`.

```text
> c-c 11 * 2
22
```

### c-c m \[r \| d\]

Shorthand syntax for switching trigonometric modes.

```text
> c-c m r
Set calculation mode to radians

> c-c m d
Set calculation mode to degrees
```

### deg, rad

Special modifiers that provide a shortcut for converting values between degrees and radians.

```text
> c-c m r
Set calculation mode to radians

> c-c sin(90)
0.893996663600557

> c-c sin(90 deg)
1

> c-c sin(pi/2 rad)
1

> c-c 45 deg
0.785398163397448

> c-c m d
Set calculation mode to degrees

> c-c cos(pi)
0.998497149863863

> c-c cos(pi rad)
-1

> c-c cos(180 deg)
-1

> c-c pi/4 rad
45
```

### 0b...

Prefix for writing numbers in binary notation.

```text
> c-c 0b1111
15
```

### 0o...

Prefix for writing numbers in octal notation.

```text
> c-c 0o77
63
```

### 0x...

Prefix for writing numbers in hexadecimal notation.

```text
> c-c 0xffffff
16777215

> c-c 0xFFFFFF
16777215
```

### a'n

\*\*\*\*[**Radix**](glossary.md#radix) notation. This allows you to express a number `n` in any base `a`, from 1 to 64.

```text
> c-c 2'10000110000
1072

> c-c 8'2060
1072

> c-c 25'1hm
1072

> c-c 32'11g
1072

> c-c 47'mC
1072
```

## Operators

CalcBot supports the following operators, and evaluates them in the order listed:

### not n

Negates `n`. If `n` is a [**truthy**](glossary.md#truthiness) value, false \(0\) is returned. Otherwise, true \(1\) is returned.

```text
> c-c not true
0

> c-c not false is true
1
```

### ~n

Invert the bits of `n`. The fractional part of `n` will be truncated if there is any.

```text
> c-c ~255
-256

> c-c ~~255
255
```

### n!

Take the factorial of `n`. For example,  `6!` is equivalent to `6 * 5 * 4 * 3 * 2 * 1`.

```text
> c-c 6!
720
```

### a ^ b

Raise `a` to the power of `b`.

```text
> c-c 2 ^ 3
8
```

### a \* b

Multiply `a` and `b`.

```text
> c-c 2 * 4
8
```

### a / b

Divide `a` by `b`.

```text
> c-c 15 / 5
3
```

### a % b

Divide `a` by `b` and return the remainder of the result. This is also known as modulus division, or remainder division.

```text
> c-c 8 % 2
0
```

### a + b

Add `a` and `b`.

```text
> c-c 1 + 1
2
```

### a - b

Subtract `b` from `a`.

```text
> c-c 1 - 1
0
```

### a &lt;&lt; b

Shift all the bits in `a` to the left `b` times. For example, `1 << 3` is equal to `2 ^ 3`. After shiting by 3 bits, the resulting binary is `1000`, equivalent to `8`.

```text
> c-c 1 << 3
8

> c-c (5 << 2) + 5
25
```

### a &gt;&gt; b

Shift all the bits in `a` to the right `b` times. Bits at the end of the number will get discarded.

```text
> c-c 8 >> 3
1

> c-c 25 >> 3
3
```

### a is b

Returns true \(1\) if `a` is equal to `b`.

```text
> c-c 3 is 1 + 2
1

> c-c not false is true
1
```

### a nis b

Returns true \(1\) if `a` is **not** equal to `b`.

```text
> c-c 3 nis 1 + 2
0

> c-c re(3i + 2) nis im(3i + 2)
1
```

### a ais b

Returns true \(1\) if `a` is **approximately** equal to `b`. The difference between them must be less than `1 * 10 ^ -6`. For complex numbers, this operator will compare the real and imaginary components separately.

This operator is intended to be used when comparing the results of certain mathematical operations that produce slightly imprecise results \(like prime notation\).

```text
> c-c 3.0000002 ais 3
1

> c-c 3i + 2 ais 2.9999999i + 2
1
```

### a anis b

Negates the behavior of the `ais` operator.

```text
> c-c 3 anis 3
0

> c-c 5i + 2 anis i
1
```

### a &gt; b

Returns true \(1\) if `a` is greater than `b`.

```text
> c-c 3 > 2
1
```

### a &lt; b

Returns true \(1\) if `a` is less than `b`.

```text
> c-c 3 < 2
0
```

### a &gt;= b

Returns true \(1\) if `a` is greater than or equal to `b`.

```text
> c-c 3 >= 2
1

> c-c 4 >= 4
1
```

### a &lt;= b

Returns true \(1\) if `a` is less than or equal to `b`.

```text
> c-c 3 <= 2
0

> c-c 4 <= 4
1
```

### a & b

Compares the bits of `a` and `b` one by one. If both bits have a value of `1`, the corresponding bit in the new number will also be `1`.

```text
> c-c isodd(n) = n & 1
isodd(n) = n & 1

> c-c isodd(7)
1

> c-c 0b111 & 0b010
2
```

### a \| b

Compares the bits of `a` and `b` one by one. If either bit has a value of `1`, the corresponding bit in the new number will also be `1`.

```text
> c-c 0b1100 | 0b0011
15

> c-c 178 | 0
178
```

### a && b

Returns true if **both** `a` and `b` are **truthy** values.

```text
> c-c 3 && 4
1

> c-c 3 && 0
0
```

### a \|\| b

Returns true if **either** `a` or `b` are **truthy** values.

```text
> c-c 3 || 4
1

> c-c 3 || 0
1

> c-c 0 || 0
0
```

### a = b

Assigns the value of `b` to the [**symbol**](glossary.md#symbol) `a`. If `a` isn't a valid symbol, this operation will thrown an error.

```text
> c-c x = y = 100
100

> c-c x + y
200

> c-c 3x + 4 = 0
Variable names can only consist of letters and underscores.
```

## Control flow functions

### bool\(v\)

Returns true \(1\) if `v` is a [**truthy**](glossary.md#truthiness) value. Otherwise, false \(0\) is returned.

```text
> c-c bool(3i)
1

> c-c bool(0)
0
```

### if\(cond, true\_exp, false\_exp = NaN\)

Returns the value of `true_exp` if `cond` resolves to a [**truthy**](glossary.md#truthiness) value. Otherwise, `false_exp` is returned. If `cond` resolves to a [**falsy**](glossary.md#truthiness) value but `false_exp` was not provided, NaN is returned.

```text
> c-c x=5
5

> c-c if(x > 2, 2x, x)
10
```

### loop\(exp, start, end, step = 1, accum\_exp = cur + acc\)

Evaluates `exp` where the special variable `ind` represents the current index of the loop. `ind` will be initially set to `start`; then it will increment by `step` until it reaches `end`, at which point the loop will break and return the value of `acc`.

If `step` is not provided, it will be set to either 1 or -1 depending on the values of `start` and `end`.

`accum_exp` is an expression that contains two special variables, `cur` and `acc`. `cur` represents the current value of `exp`, while `acc` represents the combined values of all old values of `cur`. Therefore, you can set `accum_exp` to, for example, get the sum of a sequence `exp` bounded by `start` and `end`. See the examples below for various ways you can utilize `accum_exp`.

```text
> c-c loop(ind, 0, 5, 1)
5

> c-c loop(2ind, 0, 5, 1)
10

> c-c loop(3ind+1, 11, 22, 2, cur * acc)
12075581440
```

### try\(exp, error\_exp\)

Returns the value of `exp`. If an error is generated while evaluating `exp`, `error_exp` will be returned instead.

```text
> c-c try(circle(3i - 2), 1)
1

> c-c try(6^2, 2)
36

> c-c try(circle(3i - 2), (3i)!)
The `!` operator's left argument must be of type `number`.
```

## Summation and product

### sum\(exp, variable, start, end\)

Returns the summation of `exp`, evaluated from when `variable = start` to `variable = end`. Both bounds are _inclusive_.

```text
> c-c sum(n, n, 1, 100)
5050

> c-c sum(n^n/n, n, 1, 6)
8477
```

### product\(exp, variable, start, end\)

Returns the product of `exp`, evaluated from when `variable = start` to `variable = end`. Both bounds are _inclusive_.

```text
> c-c product(n, n, 1, 10)
3628800

> c-c 10!
3628800
```

## Substitution

### subst\(exp, variable, value\)

Substitutes `value` for the `variable` in the given expression. For example, `subst(x^2+5x+6, x, 0)` substitutes `0` for `x` in the expression `x^2+5x+6`, giving `6`.

```text
> c-c subst(x^2+5x+6, x, 0)
6

> c-c subst((y+5)(y-2), y, -5)
0
```

## Trigonometric functions

### sin\(angle\), cos\(angle\), tan\(angle\)

Returns the sine, cosine, or tangent of the angle.

```text
> c-c sin(pi/2)
1

> c-c cos(pi/2)
0

> c-c tan(pi/4)
1
```

### csc\(angle\), sec\(angle\), cot\(angle\)

Reciprocal functions of `sin(angle)`, `cos(angle)`, and `tan(angle)` respectively. For example, `csc(angle) = 1 / sin(angle)`.

```text
> c-c csc(pi/2)
1

> c-c sec(pi/4)
1.414213562373095

> c-c cot(pi/4)
1
```

### asin\(value\), acos\(value\), atan\(value\)

Inverse functions of `sin(angle)`, `cos(angle)`, and `tan(angle)` respectively.

```text
> c-c asin(1)
1.5707963267948966

> c-c acos(0)
1.5707963267948966

> c-c atan(1)
0.7853981633974483
```

### **atan2\(y, x\)**

Two-argument inverse tangent function.

```text
> c-c atan2(-2, 1)
-1.1071487177940904
```

### acsc\(value\), asec\(value\), acot\(value\)

Inverse functions of `csc(angle)`, `sec(angle)`, and `cot(angle)` respectively.

```text
> c-c acsc(1)
1.5707963267948966

> c-c asec(sqrt(2))
0.7853981633974484

> c-c acot(1)
0.7853981633974483
```

### sinh\(value\), cosh\(value\), tanh\(value\)

Returns the hyperbolic sine, cosine, or tangent of the value.

```text
> c-c sinh(e/2)
1.8179831047980461

> c-c cosh(e/2)
2.074864470111516

> c-c tanh(e/2)
0.8761936651700128
```

### csch\(value\), sech\(value\), coth\(value\)

Reciprocal functions of `sinh(value)`, `cosh(value)`, and `tanh(value)` respectively. For example, `csch(value) = 1 / sinh(value)`.

```text
> c-c csch(e/2)
0.5500601173689602

> c-c sech(e/2)
0.48195919030135675

> c-c coth(e/2)
1.1413001939542262
```

### asinh\(value\), acosh\(value\), atanh\(value\)

Inverse functions of `sinh(value)`, `cosh(value)`, and `tanh(value)` respectively.

```text
> c-c asinh(1/2)
0.48121182505960347

> c-c acosh(3/2)
0.9624236501192069

> c-c atanh(1/2)
0.5493061443340548
```

### acsch\(value\), asech\(value\), acoth\(value\)

Inverse functions of `csch(angle)`, `sech(angle)`, and `coth(angle)` respectively.

```text
> c-c acsch(1/2)
1.4436354751788103

> c-c asech(1/2)
1.3169578969248166

> c-c acoth(1/2)
-1.5707963267948966i + 0.5493061443340548
```

## Degree / radian conversion

### dtr\(degree\)

Returns the given value converted to radians.

```text
> c-c dtr(180)
3.141592653589793
```

### rtd\(radian\)

Returns the given value converted to degrees.

```text
> c-c rtd(pi)
180
```

### circle\(value\)

Returns the specified portion of one full revolution of a circle. For example, `circle(0.5)` returns half of a full revolution. If the current trigonometric mode is degrees, this function returns `value * 360`; otherwise, if it is radians, this function returns `value * 2 * pi`.

```text
> c-c m d
Set calculation mode to degrees

> c-c circle(0.5)
180
```

## Exponential / logarithmic functions

### scientific\(a, b\)

Returns `a * 10 ^ b`.

```text
> c-c scientific(5.1262, 4)
51262
```

### exp\(x\)

Exponential function with base `e`. Returns `e ^ x`.

```text
> c-c exp(2)
7.3890560989306495
```

### log\(x, y = 10\)

Logarithmic function with base `10` by default.

```text
> c-c log(10)
1

> c-c log(8, 2)
3
```

### ln\(x\)

Inverse function of `exp(x)`. Equivalent to the logarithmic function with base `e`, or `log(x, e)`.

```text
> c-c ln(e)
1
```

## Root / power functions

### sqrt\(n\)

Returns the square root of `n`.

```text
> c-c sqrt(16)
4

> c-c sqrt(-4)
2i
```

### cbrt\(n\)

Returns the cube root of `n`.

```text
> c-c cbrt(27)
3
```

### root\(n, i\)

Returns the `i`th root of `n`. For example, `root(16, 2)` is equal to `sqrt(16)`.

```text
> c-c root(16, 2)
4

> c-c root(729, 6)
3
```

### pow\(n, p\)

Returns `n` raised to the `p` power. This function is implicitly called when using the alternative syntax: `n ^ p`.

```text
> c-c pow(16, 1/2)
4

> c-c pow(2, 3)
8

> c-c pow(27, 1/3)
3
```

## Complex numbers

### re\(z\)

Returns the real part of complex number `z`.

```text
> c-c re(3i + 2)
2
```

### im\(z\)

Returns the imaginary part of complex number `z`.

```text
> c-c im(3i + 2)
3
```

### arg\(z\)

Returns the argument of complex number `z`.

```text
> c-c arg(3i + 2)
0.9827937232473291
```

### conj\(z\)

Returns the complex conjugate of `z`.

```text
> c-c conj(3i + 2)
-3i + 2
```

## Sequences

### fib\(n\)

Returns the `n`th term of the Fibonacci sequence.

```text
> c-c fib(8)
21
```

## Miscellaneous functions

### erf\(z\)

Returns an approximation of the error function of `z`.

```text
> c-c erf(0.5)
0.5204999077232427
```

### erfc\(z\)

The complementary error function.

```text
> c-c erfc(0.3)
0.6713732158964137

> c-c 1-erf(0.3)
0.6713732158964137
```

### rand\(\)

Returns a random number from 0 \(inclusive\) to 1 \(non-inclusive\).

```text
> c-c rand()
(results will vary)
```

Here is a custom function implementation that will generate random integers from a selected minimum and maximum, inclusively:

```text
> c-c randint(min, max = false) = if (max is false, floor(rand() * (min + 1)), floor(rand() * (max - min + 1)) + min)
Custom function created

> c-c randint(15, 35)
(random integer from 15 to 35, inclusive)
```

### factorial\(n\)

Returns the factorial of `n`. This function is implicitly called when using the alternative syntax: `n!`

```text
> c-c factorial(6)
720
```

### gamma\(n\)

Returns the gamma function of `n` using Lanczos's approximation.

```text
> c-c gamma(5)
24

> c-c gamma(3i + 4)
-1.511251952289958i - 1.1294284935320542
```

### ncr\(n, k\)

Combinations function. Returns the coefficient of the term `x ^ k` in the polynomial expansion of the binomial `(1 + x) ^ n`. This is also the number in row `n` column `k` of Pascal's triangle.

```text
> c-c ncr(8, 2)
28
```

### npr\(n, r\)

Permutations function. Computes the number of ways to obtain an ordered subset of `r` elements from a set of `n` elements.

```text
> c-c npr(8, 2)
56
```

### abs\(n\)

Returns the absolute value of `n`.

```text
> c-c abs(-4)
4

> c-c abs(4)
4
```

### lerp\(v1, v2, t\)

Returns a value linearly interpolated from`v1` to `v2` by a constant `t`. For example, `lerp(0, 10, 0.5)` returns the midpoint of `0` and `10`.

```text
> c-c lerp(0, 10, 0.5)
5
```

### invlerp\(v1, v2, v\)

Calculates the linear parameter that produces the interpolant `v` from `v1` to `v2`.

```text
> c-c invlerp(0, 10, 5)
0.5
```

### siground\(n, d\)

Returns `n` rounded to `d` significant digits.

```text
> c-c siground(3.1567, 2)
3.2
```

### round\(n, s = 1\)

Returns `n` rounded to the nearest `s`, integer by default.

```text
> c-c round(0.45)
0

> c-c round(0.5)
1

> c-c round(0.15, 0.25)
0.25
```

### ceil\(n, s = 1\)

Returns `n` rounded up to the next `s`, integer by default.

```text
> c-c ceil(0.45)
1

> c-c ceil(0)
0

> c-c ceil(0.26, 0.25)
0.5
```

### floor\(n, s = 1\)

Returns `n` rounded down to the next `s`, integer by default.

```text
> c-c floor(0.65)
0

> c-c floor(1)
1

> c-c floor(0.74, 0.4)
0.4
```

### min\(a, b\)

Returns the lesser value of `a` and `b`.

```text
> c-c min(1, 3)
1
```

### max\(a, b\)

Returns the greater value of `a` and `b`.

```text
> c-c max(1, 3)
3
```

### gcf\(a, b\)

Computes the greatest common factor of `a` and `b`.

```text
> c-c gcf(35, 7)
7
```

### lcm\(a, b\)

Computes the least common multiple of `a` and `b`.

```text
> c-c lcm(4, 5)
20
```

### clamp\(n, l, r\)

Returns `n`, clamped to the given range set by `l` \(left, negative\) and `r` \(right, positive\)

```text
> c-c clamp(0.5, 5, 6)
5

> c-c clamp(4.2, 4, 5)
4.2

> c-c clamp(9, 1, 2)
2
```

### sign\(n\)

Returns the polarity of `n`.

```text
> c-c sign(pi)
1

> c-c sign(0)
0

> c-c sign(-pi)
-1
```

### size\(n\)

Returns the amount of bits in the binary representation of `n`. The fractional part of `n` will be truncated if there is any.

```text
> c-c size(0b1111)
4

> c-c size(255)
8
```

