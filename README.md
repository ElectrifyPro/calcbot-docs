---
description: >-
  An advanced math calculator with complex numbers, unit conversion, regression
  analysis, graphing, and more.
---

# CalcBot

## Welcome!

You have arrived at the CalcBot documentation repository, where you can learn about CalcBot's features, or try and troubleshoot issues you are having with CalcBot.

Get started by selecting one of the topics below, or scroll down a bit more to see the quick start guide. Feel free to contact me on Discord \(POOLED\#9848\) or join my **very** chill support server [here](https://discord.com/invite/3m7dK92).

* **CalcBot**
  * [Commands](reference/commands.md)
  * [Settings](settings.md)
  * [Glossary](reference/glossary.md)
* **Commands**
  * [Calculate](commands/calculate.md)
    * [Reference](reference/calculate.md)
  * [Formula](commands/formula.md)
  * [Graph](commands/graph.md)
  * Vector2
    * [Reference](reference/vector2.md)
  * Vector3
    * [Reference](reference/vector3.md)

## Quick start

### Default prefix

The bot's default prefix is **`c-`**. You can change it by running `c-admin setprefix <prefix>`.

### Basic calculator usage

The most commonly used CalcBot command is `c-calculate`, which you can also run with the shorter alias, `c-c`. Simply type `c-calculate` followed by an expression, like `1+1`, to get the result, for example:

```text
> c-calculate 1+1
2

> c-calculate 3*4
12

> c-calculate (11-4)*2
14
```

CalcBot's calculate command supports even more features like variable defining, complex numbers, and a large library of functions. You can find a full list of these features at [this](commands/calculate.md) page.

### Required permissions

Here is a list of permissions CalcBot needs to operate properly:

* **Read messages**
* **Send messages**
* **Attach files** - CalcBot generates and attaches images when using `c-graph` and `c-regression`. Disallowing this permission will break those commands.
* **Read message history**
* **View channel** - This permission is used to view voice channels. This is not needed by CalcBot at all, however it is automatically enabled when allowing the **Read messages** permission.

Enabling these permissions will enhance CalcBot's functionality, however they are **not** required:

* **Manage messages** - This allows CalcBot to delete user messages as they provide input while using the `c-formula` command to save space, and allows CalcBot to remove a user's reactions on CalcBot's messages described in the **Add reactions** permission.
* **Add reactions** - This allows CalcBot to add reactions to its help messages / messages. Users can react with the same reactions to delete a message, scroll through command pages, etc.

## Does something confuse you or not work the way you expect?

Please use the `c-featurerequest` / `c-anonfeaturerequest` command, or come let me know at my [support server](https://discord.com/invite/3m7dK92)! It's incredibly easy and takes less than 10 seconds to let me know of problems. However, very few users generally make reports, leading me to believe CalcBot is flawless, which definitely isn't true \(yet\).

Please also be as detailed as you can in your request / report, since I unfortunately don't possess mind-reading abilities \(yet\). One of my old requests came from a user not in my support server and it simply read "make the graphs interactive". As you can imagine, this request remains unfulfilled.

Here are some other questions some users have had:

### CalcBot doesn't respond to a given command.

That isn't a question, but a lot of things could've gone wrong if this happens. One of the most common issues is that the resulting message was too long \(over 2000 characters\); in this case, Discord will not allow the message to be sent, and CalcBot will not respond to your command. Another possible issue could simply be there was an error during the computation of the command, but there was no reply to let you know of the error. In either case, this should be reported using the feature request commands.

### CalcBot gives an incorrect answer for a command.

That also isn't a question, but what?? Report it with `c-featurerequest / c-anonfeaturerequest`, fast!

### Do you actually implement users' feature requests?

I've implemented and fixed many feature requests and reports by users! All feature requests are shown in the \#feature-request channel in my [support server](https://discord.com/invite/3m7dK92), and requests that I've completed are marked with a checkmark emoji.

### Add inequalities to graphing.

I see what you did there

