---
description: c-settings
---

# Settings

CalcBot has a few settings you can change to customize its behavior. This page will describe those settings and how to change them.

### `c-calculate` input

CalcBot, by default, uses a period / dot \(`.`\) as the decimal separator. There are, of course, [many other countries](https://en.wikipedia.org/wiki/Decimal_separator#Countries_using_decimal_comma) who use a comma \(`,`\) as the decimal separator.

You can change the symbol used to separate decimals with the command, `c-settings calcin <mode>`, where `<mode>` can be one of two options:

* `dec` \(default\) - Decimal numbers are represented with a period / dot \(`.`\); function parameters are separated by commas \(`,`\)
* `com` - Decimal numbers are represented with a comma \(`,`\); function parameters are separated by periods / dots \(`.`\)

Note, that by changing the way decimal numbers are represented, you also will change the way function parameters, e.g. `log(8, 2)`, are distinguished.

### `c-calculate` output

CalcBot will automatically format results from `c-calculate` in decimal, scientific, and imaginary notation.

You can change how results should be formatted with the command, `c-settings calcout <mode>`, with these possible modes:

* `auto` \(default\) - Displays all numbers as decimals, switching to scientific / imaginary notation as needed
* `scin` - Displays all numbers in scientific notation
* `frac` - Displays all numbers as fractions
* `word` - Displays all numbers in word form

### `c-recollect` date localization

The `c-recollect` commands allow you to collect previously deleted / edited messages. Running these commands \(`c-recollect deleted` / `c-recollect edited`\) will display the date of when the message was deleted / edited, by default, in English as used in the USA.

You can change the format of these dates by setting your locale with `c-settings locale <locale>`. The simplest of the many possible locales would be `<language code>-<region code>`. For example, `en-US` is a valid locale, and this represents the English language as used in the USA. Here are examples of valid locales and links to find your specific locale:

* `en-GB` - English language as used in Great Britain
* `vi-VN` - Vietnamese language as used in Vietnam
* `ko-KR` - Korean language as used in South Korea
* [JavaScript locale syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl#Locale_identification_and_negotiation)
* [ISO 639-1 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
* [ISO 3166-1 alpha-2 country codes](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements)

### `c-clock` and `c-remind at` functionality

The `c-clock` and `c-remind at` commands depend on your time zone. It is impossible to detect your time zone directly through Discord, so you'll need to set your time zone manually with `c-settings timezone <offset>`. The value of `<offset>` should be the time in hours your time zone is displaced from UTC time. You can find the UTC offset of your current time zone with a quick [Google search](https://google.com/search?q=what%20is%20my%20time%20zone).

