JSLint′
=======

One of the very few completely essential tools in any developers' belt, JSLint
is an amazing piece of applied engineering.  It's steered, however, by a man
with an ideal vision of Good JavaScript that doesn't always coincide with the
code that works in practice.  I belive JSLint needs to be a little more
forgiving of these practical necessities in a few areas (mostly in its CSS
checks), but I've had little luck in submitting patches to JSLint via official
channels.  As that's simply become a painful process, I'm taking advantage of
Crockford's foresight in making the project open source.  This fork is
completely unofficial, and certainly unapproved.

See [the changelog][changelog] for details.

[changelog]:  http://projects.mikewest.org/jslint

Layout
------

The `master` branch will contain the patches I consider important, with tests.

The `rebased` branch will contain the same content as `master`, rebased on top
of the most current `mirror` for ease of application to trunk, should Crockford
happen by.  :)  I'll be rebasing this branch more or less all the time, so be
careful if you decide to track it.  You'll be doing forced pulls all the time,
which would be annoying.

[jslint]:   http://jslint.com/
