# Glossary

## Argument

An argument is the value that is passed as input to a function. In computer science, arguments are also known as **actual arguments**.

For example, the numbers **8** and **2** in the example are considered **arguments** to the `log` function.

```text
> c-c log(8, 2)
3
```

See also: [parameter](glossary.md#parameter)

## Boolean

A boolean is a value that is either **true** or **false**. In CalcBot, **true** is represented with a one, and **false** is represented with a zero.

See also: [truthiness](glossary.md#truthiness)

## Parameter

A parameter is a variable in a function that holds the **arguments** passed to it. In computer science, parameters are also known as **formal arguments**.

For example, the variable `x` in the custom function below is considered a **parameter** of the function.

```text
> c-c squared(x) = x^2
squared(x) = x^2

> c-c squared(2)
4
```

See also: [argument](glossary.md#argument)

## Radix

The radix, also known as its **base**, indicates the amount of unique digits used to express a number. The most commonly used radix is 10, also known as the decimal system, since it uses 10 digits, from 0 to 9.

Other commonly used radixes include:

* \*\*\*\*[**Binary**](https://en.wikipedia.org/wiki/Binary_numeral_system): radix 2
* \*\*\*\*[**Octal**](https://en.wikipedia.org/wiki/Octal): radix 8
* \*\*\*\*[**Hexadecimal**](https://en.wikipedia.org/wiki/Hexadecimal): radix 16

CalcBot supports radix inputs from base 2 to 64. See the calculate [reference](calculate.md#an) to see how to use them.

## Symbol

A symbol is essentially a fancy name for **variable**. Symbol names in CalcBot can only consist of letters and underscores. The word is occasionally used in place of the other and vice versa.

## Truthiness

Truthiness refers to whether or not a value should be considered **true** or **false**. In CalcBot, all values are automatically considered **true**, except for zero \(and any vector whose components are zero\), which is considered **false**.

Examples of truthy expressions and values include `3i`, `0+1`, `sin(pi/2)`.

See also: [boolean](glossary.md#boolean)

