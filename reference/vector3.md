---
description: Function reference for c-vector3 calculate
---

# Vector3

## Heads up!

This is the documentation for the `c-vector3` command. If you mean to read the information on `c-vector2`, go [here](vector2.md).

The term **vector** in this document will describe a **3D vector**.

## 3D vectors

A 3D vector is a representation of a point in three-dimensional space. You can express vectors in CalcBot with 3 or 6 components, which collectively express the magnitude and direction of the vector.

## General

### c-v3 c &lt;expression&gt;

Shorthand syntax for `c-vector3 calculate`.

```text
> c-v3 c i + j + k
(1, 1, 1)
```

### c-v3 m \[r \| d\]

Shorthand syntax for switching trigonometric modes. `c-vector2` and `c-vector3` both share the same trigonometric mode.

```text
> c-v3 m r
Set vector mode to radians

> c-v3 m d
Set vector mode to degrees
```

## Operators

All operators from `c-calculate` and `c-vector2 calculate` are available for use in `c-vector3 calculate`:

### not n

Negates `n`. If `n` is a **truthy** value, false \(0\) is returned. Otherwise, true \(1\) is returned.

```text
> c-v3 c not true
0

> c-v3 c not false is true
1
```

### n!

Take the factorial of `n`. If `n` is a vector, this operation will throw an error.

```text
> c-v3 c 6!
720

> c-v3 c (1, 2, 1)!
Cannot take factorials of vectors.
```

### a ^ b

Raise `a` to the power of `b`. If `b` is a vector, this operation will immediately throw an error. If `a` is a vector, but `b` is not an integer, this operation will also immediately throw an error. This operation will **not** return a complex number in any situation, unlike in `c-calculate`.

```text
> c-v3 c 2 ^ 3
8

> c-v3 c (3i + j + k) ^ 3
(33, 11, 11)

> c-v3 c -4 ^ (1/2)
NaN

> c-v3 c (3i + j + k) ^ (1/2)
Vectors cannot be raised to decimal powers.

> c-v3 c 2 ^ (2k)
Vectors cannot be on the right side of the '^' operator.
```

### a \* b

Multiply `a` and `b`. When operating on two vectors, this operator returns the dot product of the two vectors. To compute the cross productof two vectors, see [cross\(v1, v2\)](vector3.md#cross-v-1-v-2).

```text
> c-v3 c 2 * 4
8

> c-v3 c (1, 2, 2) * (5, 4, 1, 2, 1, 3)
-5
```

### a / b

Divide `a` by `b`. If `b` is a vector, this operation will immediately throw an error.

```text
> c-v3 c 15 / 5
3

> c-v3 c (1, 2, 2) / 2
(0.5, 1, 1)

> c-v3 c (1, 2, 2) / (5, 4, 1, 2, 1, 3)
Vectors cannot be on the right side of the '/' operator.
```

### a % b

Divide `a` by `b` and return the remainder of the result. This is also known as modulus division, or remainder division. If either `a` or `b` is a vector, this operation will immediately throw an error.

```text
> c-v3 c 8 % 2
0

> c-v3 c (1, 2, 2) % 2
Vectors cannot be used with the '%' operator.
```

### a + b

Add `a` and `b`.

```text
> c-v3 c 1 + 1
2

> c-v3 c (3, 4, 2) + 2
(3, 4, 2) + 2

> c-v3 c (3, 4, 2) + (1, 2, 3)
(4, 6, 5)
```

### a - b

Subtract `b` from `a`.

```text
> c-v3 c 1 - 1
0

> c-v3 c (3, 4, 2) - 2
(3, 4, 2) - 2

> c-v3 c (3, 4, 2) - (1, 2, 3)
(2, 2, -1)
```

### a is b

Returns true \(1\) if `a` is equal to `b`.

```text
> c-v3 c 3 is 1 + 2
1

> c-v3 c (1, 1, 0) is (2 - 1, 1, 0)
1
```

### a nis b

Returns true \(1\) if `a` is **not** equal to `b`.

```text
> c-v3 c 3 nis 1 + 2
0

> c-v3 c (3, 1, 4) nis (2, 1, 0)
1
```

### a ais b

Returns true \(1\) if `a` is **approximately** equal to `b`. The difference between them must be less than `1 * 10 ^ -6`. For vectors, this operator will compare the x and y components separately.

This operator is intended to be used when comparing the results of certain mathematical operations that produce slightly imprecise results \(like prime notation\).

```text
> c-v3 c 3.0000002 ais 3
1

> c-v3 c (3, 2, 0.9999999) ais (2.9999999, 2, 1)
1
```

### a anis b

Negates the behavior of the `ais` operator.

```text
> c-v2 c 3 anis 3
0

> c-v2 c (5, 2, 0) anis (1, 0, 2)
1
```

### a &gt; b

Returns true \(1\) if `a` is greater than `b`.

```text
> c-v3 c 3 > 2
1
```

### a &lt; b

Returns true \(1\) if `a` is less than `b`.

```text
> c-v3 c 3 < 2
0
```

### a &gt;= b

Returns true \(1\) if `a` is greater than or equal to `b`.

```text
> c-v3 c 3 >= 2
1

> c-v3 c 4 >= 4
1
```

### a &lt;= b

Returns true \(1\) if `a` is less than or equal to `b`.

```text
> c-v3 c 3 <= 2
0

> c-v3 c 4 <= 4
1
```

### a and b

Returns true if **both** `a` and `b` are **truthy** values.

```text
> c-v3 c 3 and 4
1

> c-v3 c 3 and 0
0
```

### a or b

Returns true if **either** `a` or `b` are **truthy** values.

```text
> c-v3 c 3 or 4
1

> c-v3 c 3 or 0
1

> c-v3 c 0 or 0
0
```

## Vector literals

### \(a, b, c\)

Syntax for a three-dimensional three-component vector.

```text
> c-v3 c (1, 2, 5)
(1, 2, 5)
```

### \(a, b, c, d, e, f\)

Syntax for a three-dimensional six-component vector. Vectors of this kind are implicitly converted to their component form when used with other operations during evaluation.

```text
> c-v3 c (1, 2, 5, 3, 2, 2)
(1, 2, 5, 3, 2, 2)
```

## Vector constants

These constants will always be available everywhere in all of `c-vector3`'s children commands.

* **`i`** = \(1, 0, 0\)
* **`j`** = \(0, 1, 0\)
* **`k`** = \(0, 0, 1\)
* **`zero`** = \(0, 0, 0\)

## Modified [Vector2](vector2.md) functions

All `c-vector2` functions as described [here](vector2.md#modified-calculate-functions) are available to use in `c-vector2 calculate`, and most of them have been adapted for use with `c-vector3 calculate`. There are some differences, however:

### Removed functions

These functions that are available in `c-vector2 calculate` are **not available** in `c-vector3 calculate`\(and have been replaced with similar functions\):

* [quad\(v\)](vector2.md#quad-v)
* [dir\(v\)](vector3.md#dir-v)

## Unique functions

These functions are unique to `c-vector3 calculate`:

### z\(v\)

Returns the `z` component of vector `v`.

```text
> c-v3 c z(2i + j + k)
1
```

### oct\(v\)

Returns the octant that vector `v`'s component's head lies in. If the head is on the x-axis, 9 is returned. If the head is on the y-axis, 10 is returned. If the head is on the z-axis, 11 is returned.

This function serves as the replacement for `c-vector2 calculate`'s [quad\(v\)](vector2.md#quad-v) function.

```text
> c-v3 c oct(2i + j + k)
1

> c-v3 c oct(k)
11
```

### dirx\(v\)

Returns the direction angle vector `v` makes with the x-axis.

This function, along with [diry\(v\)](vector3.md#diry-v) and [dirz\(v\)](vector3.md#dirz-v), serves as the replacement for `c-vector2 calculate`'s [dir\(v\)](vector2.md#dir-v) function.

```text
> c-v3 c dirx(k)
90
```

### diry\(v\)

Returns the direction angle vector `v` makes with the y-axis.

This function, along with [dirx\(v\)](vector3.md#dirx-v) and [dirz\(v\)](vector3.md#dirz-v), serves as the replacement for c-vector2 calculate's [dir\(v\)](vector2.md#dir-v) function.

```text
> c-v3 c diry(i + j + k)
54.73561031724535
```

### dirz\(v\)

Returns the direction angle vector `v` makes with the z-axis.

This function, along with [dirx\(v\)](vector3.md#dirx-v) and [diry\(v\)](vector3.md#diry-v), serves as the replacement for c-vector2 calculate's [dir\(v\)](vector2.md#dir-v) function.

```text
> c-v3 c dirz(i - j)
90
```

### cross\(v1, v2\)

Returns the cross product of vectors `v1` and `v2`.

```text
> c-v3 c cross((3, 1, 4), (-2, 0, 5))
(5, -23, 2)
```

