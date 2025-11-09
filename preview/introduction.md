---
description: c-preview and changes to CalcBot in development preview
---

# CalcBot development preview

CalcBot is currently undergoing a major development overhaul, with a focus on
significantly better performance. Not all commands and features are currently
available, but you can test the implemented features by enabling the preview
mode.

You can try the new CalcBot by running the command `c-preview on`. You can
easily return to the old CalcBot by running `c-preview off`. **Your data is
separated between the two versions, while your settings will remain the same**.
Any changes to your data made in the preview version will not impact your data
in the current version, and vice versa.

Your feedback is incredibly valuable, especially during this development phase!
You can let me know what you think, report bugs, and / or suggest improvements
using the `/report` slash command, the `c-report` command, or the `c-anonreport`
command.

## Currently available commands

These commands are the ones currently available in the preview version of
CalcBot. More will be added in future updates.

- **c-about**
- **c-calculate**
	- The new `c-calculate` command is much, much faster and more precise. All
	features of the current `c-calculate` command are still supported!
	- For power users, the new `c-calculate` is fully programmable and has
	features that make it more like a programming language, like multiline
	functions, `if` / `else` expressions, `for` and `while` loops (and
	specialized summation and product loops), lists, higher-order functions,
	beautiful error messages and more.
	- You can learn more about the new `c-calculate` features (besides speed)
	here: [`cas-rs`](cas.md)
- **c-calculate tolatex**
- **c-dictionary**
- **c-help**
- **c-help commands**
- **c-link**
- **c-remind**
	- Support for "together mode" reminders, where users can choose to receive a
	reminder with you, has been temporarily removed, but will be re-added in a
	future update.
	- Otherwise, the new `c-remind` suite of commands have a few small niceties
	that make life a bit nicer.
	- Timer IDs are always lowercase letters, so they're easier to type.
	- Timers display times and links to channels using Discord's timestamp
	formatting, so they always show up in your timezone.
- **c-unitconvert**
	- Not all units from the current `c-unitconvert` are supported yet, but many
	common units are available.
	- The command now supports compound units, like `kg*m/s^2`. However, these
	cannot yet be simplified (e.g., converting `N` to `kg*m/s^2`).

## Next planned features / changes

- **c-graph**
- **c-unitconvert customratio**
	- This command may be removed, since it is not widely used, and makes the
	calculator more complex.
