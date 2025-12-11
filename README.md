# TI-30XS MultiView™ data recovery

## Preamble

This document shows a step by step procedure to recover the entries of a TI-30XS MultiView™ or TI-30XB MultiView™ scientific calculator after it has been reset.

On those models, a reset can be performed by pressing `on` and `clear` at the same time, by accessing the reset menu (`2nd` `0`) and selecting the second option or by pressing the reset button on the back of the unit with a ballpoint pen or a paper clip.
The calculator is also automatically reset when the battery is replaced.

After it has been reset, the calculator shows `MEMORY CLEARED`, but the memory isn't truly cleared.

## Limitations

The method described in this document can recover the entries (inputs and answers) on the home screen. It cannot be used to restore settings, variables, data editor values, statistical data, etc.

This procedure is specific to the TI-30XS MultiView™ and TI-30XB MultiView™ models. But some others Texas Instruments calculators (TI-30X Pro MultiView™, TI-36X Pro, TI-34 MultiView™, …) have similar bugs, which this document is too narrow to contain.

## Disclaimer

This material is provided "as-is", without any express or implied warranty. In no event will the author be held liable for any damages arising in any way from the use of this material.

All company, product and service names used in this document are for identification purposes only. All brands, product names, trademarks and copyrights are property of their respective owners. Use of these names and brands does not imply endorsement.

This procedure has only been thoroughly tested on one unit. Different versions of these models might exist.

If the calculator becomes unresponsive or is behaving unexpectedly, it is highly recommended to reset it by pressing `on` and `clear` at the same time. The calculator will be working normally again.

## Note about keystrokes

In the following sections, `^` is the exponentiation key. Special care should be taken not to confuse it with `▲`, which represents the key to scroll up.

## Example

This section contains a simple proof of concept. It should be tested on a unit containing one or more entries in memory (**not** on one that has just been reset). The unit will be reset before showing the ability to recover those entries.

Back up any important data from the calculator before proceeding.

- Press `on` to turn on the calculator.
- Press `mode` to show the options.
- Make sure that the default options `NORM` (second line) and `FLOAT` (third line) are highlighted. If it's not the case, scroll down by pressing `▼` and select them by pressing `enter`.
- At the fourth line of the mode menu, **don't** switch from `MATHPRINT` to `CLASSIC` or from `CLASSIC` to `MATHPRINT` as doing so will remove all the entries in memory. That said, if `CLASSIC` (non default option) was highlighted, make sure to delete all inputs and results containing special symbols (exponents, fractions, …) before continuing as the calculator might crash after recovery when displaying those entries.
- Press `2nd` `on` `on` `2nd` `on` `on` to restart the calculator twice and place the cursor at the beginning of an empty line on the home screen.
- Press `.` `1` `enter` `enter`. The calculator should show the result `0.1` twice.
- Reset the unit by pressing `2nd` `0` `2` (or with any other method, including by replacing the battery or by pressing `on`&`clear` at the same time).
- Press the following keys : `.` `enter` `clear` `^` `enter` `clear` `data` `0` `enter` `▶` `sto▸` `data` `enter` `enter` `sto▸` `clear` `clear` `2nd` `mode` `▲` `enter` `◀` `▲` `enter` `delete` `delete` `clear` `▲` `delete` `delete`.
- Press `▲` to scroll through recovered entries.

[Here](assets/example.webm?raw=true) is a video illustrating this example.

[example.webm](https://github.com/ndeineko/TI-MultiView-data-recovery/assets/11009067/38b84176-1752-448e-9a26-5a588657b454)

## Full procedure

This section describes a more complete procedure. It will recover entries that were present before the reset, except the two most recent ones. That is, one expression and its associated result. This procedure should be done just after a reset. It might not work if new entries were added after `MEMORY CLEARED` was shown. It can also be used immediately after history disappears when switching mode from MathPrint™ to Classic. In that case, reset or switch back to MathPrint™ before continuing.

For special symbols (fractions, exponents, roots, …), MathPrint™ (textbook-style and default mode) and Classic don't use the same encoding. If the entries to recover were added in Classic mode, the calculator will crash or freeze when displaying the ones that contain those symbols.

For this to work, it's also imperative to remember the most recent result that was computed on the calculator (or, the most recent input, if that result was `Error`), in order to determine where the next entry is stored in memory.

The following steps should be done in chronological order. When a step contains "**If**" and the condition is not met, every sub-step must be skipped.

- The first step of this procedure is to find a value that we will call *size* :
	- Look at the [next section](#entry-size) for more information on how to calculate the size of an entry.
	- **If** the most recent calculation before reset resulted in an error :
		- *Size* is the size of the expression that resulted in this error.
	- Otherwise (**If** the most recent result before reset was **not** `Error`) :
		- *Size* is the size of that result **plus one**.


- Don't forget that value as it will be used and modified multiple times. Also, memorize if that most recent result was an error or not as it will be needed for a later step.


- **If** *size* is strictly smaller than *16* :
	- Press `data`.
	- (*40* times) Press `0` `enter`.
	- At this point, the bottom of the screen should show `L1(41)=    `. If it's not the case, insert or delete the right amount of cells to get *40* lines of zeros.
	- Press `▶`.
	- **If** *size* is strictly smaller than *3* :
		- (*41* or more times) Press `0` `enter`.
	- Otherwise (**If** *size* is greater than or equal to *3*) :
		- Press `sto▸` `data` `enter` `enter` `▲` `0` `enter`.
	- Press `◀` `0` `enter` `0` `enter` `enter` `0` `enter` `2nd` `delete`.
	- Increment *size* by *8* and memorize the new value.
	- **If** *size* is still strictly smaller than *16* :
		- Press `2nd` `delete`.
		- Increment *size* by *8* and memorize it.
	- Press `2nd` `0` `2`.


- **If** *size* is equal to *16*,*17*,*18*,*19*,*20* or *23* :
	- press `.` `enter` `clear` `clear`.


- **If** *size* is equal to *21* or *22* :
	- Press `data` `◀`.
	- (*40* times) Press `0` `enter`.
	- At this point, the bottom of the screen should show `L3(41)=    `. If it's not the case, insert or delete the right amount of cells to get *40* lines of zeros.
	- Press `◀` `sto▸` `data` `3` `enter` `▲` `0` `enter` `▶` `0` `enter` `0` `enter` `enter`.
	- (*18* times) Press `0` `enter`.
	- At this point, the bottom of the screen should show `L3(61)=    `.
	- Press `1` `0` `0` `0` `0` `0` `1`.


- **If** *size* is equal to *16* :
	- Press `)`.


- **If** *size* is equal to *17* :
	- Press `.`.


- **If** *size* is equal to *18* :
	- Press `−` `◀` `◀` `delete` `▶`.


- **If** *size* is equal to *19* :
	- Press `÷` `◀` `◀` `delete` `▶`.


- **If** *size* is equal to *20* :
	- Press `prb` `enter` `◀` `◀` `delete` `▶`.


- **If** *size* is equal to *21* :
	- Press `6` `π` `enter` `data` `4` `2nd` `÷` `delete` `delete` `enter` `enter` `clear` `2nd` `÷`.


- **If** *size* is equal to *22* :
	- Press `7` `π` `enter` `data` `4` `2nd` `÷` `delete` `delete` `enter` `enter` `clear` `2nd` `÷` `◀` `delete` `▶`.


- **If** *size* is equal to *23* :
	- Press `2nd` `(` `◀` `◀` `delete` `▶`.


- **If** *size* is strictly greater than *23* :
	- Press `(` `(`.
	- **If** *size* is an even number :
		- Press `×`.
	- Otherwise (**If** *size* is an odd number) :
		- Press `+`.
	- (*size minus 20* times) Press `(`.
	- Press `+` `enter` `clear` `clear` `clear` `ln`.


- Press `^` `enter` `clear` `data` `0` `enter` `▶` `sto▸` `data` `enter` `enter` `sto▸` `clear` `clear` `2nd` `mode` `▲` `enter` `◀` `▲` `enter` `delete` `delete` `clear` `▲` `delete`.


- **If** the most recent result before reset was `Error` :
	- Press `data` `sto▸` `data` `2` `enter` `sto▸` `clear` `clear` `2nd` `mode` `▲`.
- Otherwise (**If** the most recent result before reset was **not** an error) :
	- Press `delete`.


- **If** *size* is strictly greater than *23* :
	- Press `delete` until a recovered result is about to be deleted, that is, exactly *(size - 16) / 2* times if *size* is even or *(size - 15) / 2* times if *size* is odd.


- Scroll through recovered entries with `▲`.

## Entry size

This section explains how to calculate the size of an entry in memory. It works with inputs and results.

- Start with a size of zero.
- Add *1* for every classic (non textbook-style) symbol. A classic symbol can contain one (e.g., `5`, `)`, `÷` and `π`) or more (e.g., `cos(`, `ans`, ` nCr ` and `►％`) characters and still have a size of *1*.
- For MathPrint™ (textbook-style) symbols :
	- Add *1* for every rectangle with a dotted border (a placeholder, typically found inside a fraction, root or exponent).
	- Add *2* for every natural exponentiation symbol (and **don't** count `e` as a character).
	- Add *2* for every other exponentiation (with another base than `e`).
	- Add *2* for every square root symbol.
	- Add *3* for every n-th root symbol.
	- Add *3* for every fraction bar.

Some example entries, with their size, can be found in the table below.

| Entry | Symbols | Entry size</br>calculation |
| --- | --- | ---: |
| ![sin-1(0.5)►％](assets/size-example-1.png) | *6* classic symbols (<code>sin<sup>−1</sup>(</code>, `0`, `.`, `5`, `)` and `►％`) | *6* × 1 = **6** |
| ![(9√97)/97](assets/size-example-2.png) | *5* classic symbols (`9`, `9`, `7`, `9`, and `7`)<br/>*1* square root<br/>*1* fraction bar<br/><br/> | *5* × 1 = 5<br/>*1* × 2 = 2<br/>*1* × 3 = 3<br/>Sum = **10**<br/> |
| ![(e^√π)/cos(⬚/⬚)](assets/size-example-3.png) | *2* classic symbols (`cos(` and `π`)<br/>*2* rectangles with a dotted border<br/>*1* natural exponentiation symbol<br/>*1* square root<br/>*2* fraction bars<br/><br/> | *2* × 1 = 2<br/>*2* × 1 = 2<br/>*1* × 2 = 2<br/>*1* × 2 = 2<br/>*2* × 3 = 6<br/>Sum = **14**<br/> |
