mikewest/JSLint Changelog
=========================

2010-11-21
----------

*	JSLint has an official GitHub presence!  Excellent!  I've reworked this
	repository entirely so that it's based on the official repository, which
	means that the `mirror` branch has been dropped entirely, and that all
	the SHA1 IDs have changed.  If you've forked this repository, or stored
	it locally for any reason at all, you'll run into problems.  Please
	reclone and start over.

	It's inconvenient, I know, but this will make it much simpler to keep in
	step with changes in the official repo.

2010-10-06
----------

*	Updating to the 2010-10-06 release, and backing out my fix
	for the `url(...)` bug in favour of the official fix.

2010-10-04
----------

*	Fixing a bug in yesterday's fix for font shorthand syntax.  The
	line-height doesn't _have_ to be specified.  It can be inherited.

*	Fixing support for `url(/path/to/image.jpg)` in `background` shorthand
	syntax.  The following should pass linting now, when the `css` option
	is set:

		div {
			background:	url(/path/to/image.jpg);
		}
	
	In the current JSLint trunk, it throws a JavaScript error.  That's bad.

2010-10-03
----------

*	Simple font shorthand syntax like `font: 12px/1 Helvetica;` throws
	errors.  It shouldn't.

*	`last-child` is an acceptable pseudoclass.

2010-09-11
----------

*	Adding an `args` option to support the `arguments.callee` and
	`arguments.caller` properties that I use quite often.

2010-05-16
----------

*	Added support for `#RRGGBBAA` style hex colours for alpha support via
	IE's `filter` attribute.  The following should pass linting now, when
	the `css` option is set:
	
		.myclass {
			filter:progid:DXImageTransform.Microsoft.Gradient(StartColorStr=#FFFFFF50,EndColorStr=#FFFFFF50);
		}
	
	In the current JSLint trunk, it throws a "Bad hex value" warning.

*	Added support for CSS3's `::` selector to designate pseudo-elements.
	The following should pass linting now, when the `css` option is set:

		.myclass::first-line {
			color:	red;
		}

	In the current JSLint trunk, it throws a "Expected pseudo, found
	':first-line' warning.

*	Added support for vendor-specific prefixes in pseudo-selectors.  The
	following should pass linting now, when the `css` option is set:

		input::-moz-focus-inner {
			padding:	0;
		}
	
	This is especially important, given Gecko's tendency to add 3px of
	padding to input elements that can only be removed via manipulation
	of `input::-moz-focus-inner`, but was [rejected][vendorprefix] when
	submitted to the list.

[vendorprefix]: http://tech.groups.yahoo.com/group/jslint_com/message/1280
