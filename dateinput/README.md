# DateInput

Visual date picker script. Very compact at 1760 bytes minified and gzipped.

Developed and customized/optimized for inclusion with Wedge plugins by John "live627" Rayes.

## WeCss styles
Recognise the SASS structure?
```css
.cal
	border: 1px solid #bbb
	box-shadow: 2px 2px 6px 0 rgba(0,0,0, .15)
	border-radius: 10px
	background: #f7fcf7
	display: none
	padding: 0.5em
	position: absolute
	z-index: 999
	.center
		margin-bottom: 0.5em
	.ui-datepicker-header a
		margin-top: 5px
	table
		cell-padding, cell-spacing: 0
		td
			padding: 6px 8px
		td.disabled
			color: #aaa
		td:not(.disabled)
			border-radius: 3px
			cursor: pointer
			color: #300
		td.hove
			color: #000
			background-color: rgba(0,0,0, .075)
		td.today
			color: #900
		td.chosen
			font-weight: bold
```
## Usage
In your Wedge plugin, add the script file (obviously) and add some seperate JS like so:
```php
<?php

add_js('
	var
		days = ' . json_encode(array_values($txt['days'])) . ',
		daysShort = ' . json_encode(array_values($txt['days_short'])) . ',
		months = ' . json_encode(array_values($txt['months'])) . ',
		monthsShort = ' . json_encode(array_values($txt['months_short'])) . ';');

	?>
```
## Changelog
Filesizes were computed using Packer (in Wedge) and gzipping the file.

    0.2 (30 April 2012)
    ---
    * Optimise the code for an even smaller size: 1760 bytes
    ! Combine two `unbind` statements into one
    - Remove references to `self`, as they were unnecessary

    0.1 (01 April 2012)
    ---
    * Down to 1.82 KB from the original ~3.5 KB.
    - Remove almost all public methods, and made the rest private (maybe three or four were necessary for successful operation).
    + Add some keyboard shortcuts, to resemble the UI widget somewhat.
    - Remove all callbacks.
    * Reformat functions to be variable declarations.
    ! Max and min did not limit the date selectors properly.
    * Use as few queries as possible, since querying the document isn't cheap. We're all for speed here, right?

## Sources

This work is based on [jQuery Tools Dateinput](http://flowplayer.org/tools/form/dateinput/).

## Legal

This work is released under the [Creative Commons Attribution-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0/).

## TODO

* Use the scroll wheel to change months.