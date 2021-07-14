---
description: Function reference for c-vector2 calculate
---

# Vector2

## Heads up!

This is the documentation for the `c-vector2` command. If you mean to read the information on `c-vector3`, go [here](vector3.md).

The term **vector** in this document will describe a **2D vector**.

## 2D vectors

A 2D vector is a representation of a point in two-dimensional space. You can express vectors in CalcBot with 2 or 4 components, which collectively express the magnitude and direction of the vector.

## General

### c-v2 c &lt;expression&gt;

Shorthand syntax for `c-vector2 calculate`.

```text
> c-v2 c i + j
(1, 1)
```

### c-v2 m \[r \| d\]

Shorthand syntax for switching trigonometric modes. `c-vector2` and `c-vector3` both share the same trigonometric mode.

```text
> c-v2 m r
Set vector mode to radians

> c-v2 m d
Set vector mode to degrees
```

## Operators

All operators from `c-calculate` are available for use in `c-vector2 calculate`:

### not n

Negates `n`. If `n` is a **truthy** value, false \(0\) is returned. Otherwise, true \(1\) is returned.

```text
> c-v2 c not true
0

> c-v2 c not false is true
1
```

### n!

Take the factorial of `n`. If `n` is a vector, this operation will throw an error.

```text
> c-v2 c 6!
720

> c-v2 c (1, 2)!
Cannot take factorials of vectors.
```

### a ^ b

Raise `a` to the power of `b`. If `b` is a vector, this operation will immediately throw an error. If `a` is a vector, but `b` is not an integer, this operation will also immediately throw an error. This operation will **not** return a complex number in any situation, unlike in `c-calculate`.

```text
> c-c 2 ^ 3
8

> c-v2 c (3i + j) ^ 3
(30, 10)

> c-v2 c -4 ^ (1/2)
NaN

> c-v2 c (3i + j) ^ (1/2)
Vectors cannot be raised to decimal powers.

> c-v2 c 2 ^ j
Vectors cannot be on the right side of the '^' operator.
```

### a \* b

Multiply `a` and `b`. When operating on two vectors, this operator returns the dot product of the two vectors.

```text
> c-v2 c 2 * 4
8

> c-v2 c (1, 2) * (5, 4, 1, 2)
-8
```

### a / b

Divide `a` by `b`. If `b` is a vector, this operation will immediately throw an error.

```text
> c-v2 c 15 / 5
3

> c-v2 c (1, 2) / 2
(0.5, 1)

> c-v2 c (1, 2) / (5, 4, 1, 2)
Vectors cannot be on the right side of the '/' operator.
```

### a % b

Divide `a` by `b` and return the remainder of the result. This is also known as modulus division, or remainder division. If either `a` or `b` is a vector, this operation will immediately throw an error.

```text
> c-v2 c 8 % 2
0

> c-v2 c (1, 2) % 2
Vectors cannot be used with the '%' operator.
```

### a + b

Add `a` and `b`.

```text
> c-v2 c 1 + 1
2

> c-v2 c (3, 4) + 2
(3, 4) + 2

> c-v2 c (3, 4) + (1, 2)
(4, 6)
```

### a - b

Subtract `b` from `a`.

```text
> c-v2 c 1 - 1
0

> c-v2 c (3, 4) - 2
(3, 4) - 2

> c-v2 c (3, 4) - (1, 2)
(2, 2)
```

### a is b

Returns true \(1\) if `a` is equal to `b`.

```text
> c-v2 c 3 is 1 + 2
1

> c-v2 c (1, 1) is (2 - 1, 1)
1
```

### a nis b

Returns true \(1\) if `a` is **not** equal to `b`.

```text
> c-v2 c 3 nis 1 + 2
0

> c-v2 c (3, 1) nis (2, 1)
1
```

### a ais b

Returns true \(1\) if `a` is **approximately** equal to `b`. The difference between them must be less than `1 * 10 ^ -6`. For vectors, this operator will compare the x and y components separately.

This operator is intended to be used when comparing the results of certain mathematical operations that produce slightly imprecise results \(like prime notation\).

```text
> c-v2 c 3.0000002 ais 3
1

> c-v2 c (3, 2) ais (2.9999999, 2)
1
```

### a anis b

Negates the behavior of the `ais` operator.

```text
> c-v2 c 3 anis 3
0

> c-v2 c (5, 2) anis (1, 0)
1
```

### a &gt; b

Returns true \(1\) if `a` is greater than `b`.

```text
> c-v2 c 3 > 2
1
```

### a &lt; b

Returns true \(1\) if `a` is less than `b`.

```text
> c-v2 c 3 < 2
0
```

### a &gt;= b

Returns true \(1\) if `a` is greater than or equal to `b`.

```text
> c-v2 c 3 >= 2
1

> c-v2 c 4 >= 4
1
```

### a &lt;= b

Returns true \(1\) if `a` is less than or equal to `b`.

```text
> c-v2 c 3 <= 2
0

> c-v2 c 4 <= 4
1
```

### a and b

Returns true if **both** `a` and `b` are **truthy** values.

```text
> c-v2 c 3 and 4
1

> c-v2 c 3 and 0
0
```

### a or b

Returns true if **either** `a` or `b` are **truthy** values.

```text
> c-v2 c 3 or 4
1

> c-v2 c 3 or 0
1

> c-v2 c 0 or 0
0
```

## Vector literals

### \(a, b\)

Syntax for a two-dimensional two-component vector.

```text
> c-v2 c (1, 2)
(1, 2)
```

### \(a, b, c, d\)

Syntax for a two-dimensional four-component vector. Vectors of this kind are implicitly converted to their component form when used with other operations during evaluation.

```text
> c-v2 c (1, 2, 5, 3)
(1, 2, 5, 3)
```

## Vector constants

These constants will always be available everywhere in all of `c-vector2`'s children commands.

* **`i`** = \(1, 0\)
* **`j`** = \(0, 1\)
* **`zero`** = \(0, 0\)

## Modified [Calculate](calculate.md) functions

All `c-calculate` functions as described [here](calculate.md) are available to use in `c-vector calculate`, and most of them will behave the same. Some functions have been modified for use with `c-vector calculate`, however:

### Trigonometric functions

All trigonometric functions will **not** operate with vector arguments.

### sqrt\(n\)

This function will **not** return a complex number in any situation, unlike in `c-calculate`.

```text
> c-v2 c sqrt(4)
2

> c-v2 c sqrt(-4)
NaN
```

### abs\(n\)

This function will behave as expected. If `n` is a vector, this function will return the vector with the absolute value of each of its components \(equivalent to `(abs(x(n)), abs(y(n)))`\).

```text
> c-v2 c abs(-4)
4

> c-v2 c abs((-2, -pi))
(2, 3.141592653589793)
```

### pow\(n, p\)

If `p` is a vector, this function will immediately throw an error. If `n` is a vector, but `p` is not an integer, this function will also immediately throw an error. Otherwise, this function behaves as expected, except that it will **not** return a complex number in any situation, unlike in `c-calculate`. This function is implicitly called when using the alternative syntax: `n ^ p`.

```text
> c-v2 c pow(2, 4)
16

> c-v2 c pow(3i + j, 3)
(30, 10)

> c-v2 c pow(3i + j, 1/2)
Vectors cannot be raised to decimal powers.

> c-v2 c pow(2, j)
Vectors cannot be on the right side of the '^' operator.
```

## Functions that return a number

Most of the functions below available in `c-vector calculate` are also exposed as children commands of `c-vector`.

### x\(v\)

Returns the `x` component of vector `v`.

```text
> c-v2 c x(2i + j)
2
```

### y\(v\)

Returns the `y` component of vector `v`.

```text
> c-v2 c y(2i + j)
1
```

### comp\(v\)

Returns the component of vector `v`.

```text
> c-v2 c comp((2, 2, 3, 3))
(1, 1)
```

### quad\(v\)

Returns the quadrant that vector `v`'s component's head lies in. If the head is on the x-axis, 5 is returned. If the head is on the y-axis, 6 is returned.

```text
> c-v2 c quad(2i + j)
1

> c-v2 c quad(j)
6
```

### dir\(v\)

Returns the direction angle of vector `v`, where the unit vector `i` \(1, 0\) is 0 degrees. For example, unit vector `j` \(0, 1\)'s direction angle is 90 degrees.

```text
> c-v2 c dir(2i + j)
26.56505117707799
```

### mag\(v\)

Returns the magnitude of vector `v`.

```text
> c-v2 c mag(2i + j)
2.23606797749979
```

### sqrmag\(v\)

Returns the squared magnitude of vector `v`. If you need to compare the magnitudes of two vectors, it will usually be more efficient to compare their squared magnitudes.

```text
> c-v2 c sqrmag(2i + j)
5
```

### angle\(v1, v2\)

Returns the smallest angle between vectors `v1` and `v2`. The returned value will always be between 0 and 180 degrees.

```text
> c-v2 c angle(2i + j, -4i + 6j)
97.12501634890181
```

### dot\(v1, v2\)

Returns the dot product of vectors `v1` and `v2`.

```text
> c-v2 c dot(2i + j, -4i + 6j)
-2
```

### dist\(v1, v2\)

Returns the distance between the heads of vectors `v1` and `v2`.

```text
> c-v2 c dist(2i + j, -4i + 6j)
7.810249675906654
```

## Functions that return a vector

### polar\(m, a\)

Returns a vector given its magnitude \(`m`\) and direction angle \(`a`\). This is equivalent to a vector defined as `(m * cos(a), m * sin(a))`.

```text
> c-v2 c polar(2, 90)
(0, 2)
```

### unit\(v\)

Returns the unit vector of vector `v`, that is, the vector with the same direction angle as `v` but with a magnitude of 1.

```text
> c-v2 c unit(2i + j)
(0.8944271909999159, 0.4472135954999579)
```

### lerp\(v1, v2, t\)

Returns a new vector linearly interpolated from vector `v1` to `v2` by a constant `t`. For example, `lerp(2i+j, -4i+6j, 0.5)` returns the midpoint between vectors `2i+j` and `-4i+6j`.

```text
> c-v2 c lerp(2i + j, -4i + 6j, 0.5)
(-1, 3.5)
```

### mid\(v1, v2\)

Returns the midpoint between vectors `v1` and `v2`. This will always perform more quickly than `lerp(v1, v2, 0.5)`.

```text
> c-v2 c mid(2i + j, -4i + 6j)
(-1, 3.5)
```

