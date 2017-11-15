## Babel 3.9t


This is Babel 3.9t.

** Babel 3.9o and 3.9p are deprecated.                         **
** For incompatibilities with polyglossia read the manual.     **
** You must recreate the formats if coming from version <3.9q. **

Version 3.9a fixed lots of bugs and added some new features, intended mainly to make it compatible somehow with Unicode engines. Some bugs have not been fixed to avoid backward incompatibilities, but they have been documented. Most of the new features (like package options) are intended to overcome issues in previous releases without changing significantly the behaviour of Babel.

Languages are not part of the Babel core any more; in particular, it shall be no longer necessary to synchronize Babel core releases with releases of Babel language files. See CONTRIB for further details about contributing a language.

To install it, just tex babel.ins and move the generated files to the corresponding place in your TeX distribution. Unlike former releases, formats must not be recreated, but it is recommended, at least the first time Babel is updated from 3.8 (or previous versions).

Changes are described in babel.pdf with the label "New 3.9". The manual has been expanded to include some tips and tricks, but it will be improved in next releases.


### Reporting Bugs

If you wish to report a problem or bug in any of these packages please use the [Issue Tracker for LaTeX2e on GitHub](https://github.com/latex3/latex2e/issues) and follow the guidelines that pop up if you press the `New issue` button.


In particular, to check that you are really seeing a bug, please write a short, self-contained document that shows the problem. This should include the `latexbug` package, which will warn if your test file is not suitable for one or the other reason. See the [CONTRIBUTING guide](https://github.com/latex3/latex2e/blob/master/CONTRIBUTING.md) for further details, or if you need to obtain the `latexbug` package.

If the bug turns out to be with third-party software then please contact the developer, and not us!


You may also report them to the author more informally on:

   http://www.texnia.com/contact.html

Bugs related to specific languages are best reported to their
respective authors.

Versions >=3.9i presumes the german style has been updated to 2.7.


### New

```
* babel.dtx
3.9b  - Fixed an idiot slip in hyphen.cfg: a \def instead of \let
3.9c  - Added the "modifiers" mechanism
      - Option shorthands accepts t for ~ and c for ,
      - \foreinglanguage inserted a par (because of an empty line
        in the doc part)
3.9d  - Fixed undefined \@expandtwoargs in Plain
      - Code reorganized (just an "internal" change)
3.9e  - Fixed a bug introduced in 3.9c which mangled key=value
        options.
3.9f  - Default hyphenmins were not set to 2 3. Now they are again.
3.9g  - bbplain.dtx and babel.dtx merged.
      - The number of languages was not printed in some formats.
      - A new mechanism to force \StartBabelCommands even without the
        'strings' key (\UseStrings didn't work at all).
      - With \AfterBabelCommands macros can be defined in the global scope.
      - A tool for readjusting lccodes for hyphenation (\SetHyphenMap and a
        package option).
      - Tentative macros for \fontspec.
3.9h  - Fixed bugs in \SetStringLoop (first token expanded prematurely)
        and \SetCase (sometimes ignored).
      - bplain didn't work (again). Fixed.
      - Other minor internal changes.
3.9i  - With LuaTeX, spaces are not ignored after shorthands and closing
        braces can follow them.
      - \textlatin and friends are deprecated. For the logos (see
	below) a new macro is used if necessary (\ensureascii), so
	\textlatin is not used in the core any more.
      - \babelensure can be used to wrap caption texts with \foreignlanguage,
        as well as to enforce an encoding.
      - \babeltags is just for syntactical sugar, and defines macros
	with short names to switch the language (eg, \textdeu and \deu).
      - Partial compatibility with languages named as \lang@ instead
	of \l@ (plain etex/xetex/luatex).
      - Bug fix. The logos \TeX and \LaTeX were typeset in a wrong font
	in some cases. Now if a non-ASCII font is not loaded they are not
	redefined at all.
      - Bug fix. \bbl@allowhyphens is now ignored in vertical mode.
      - Bug fix. Loops with \@for failed in Plain.
      - Bug fix. A few codes in xetex where wrong when loading patterns.
      - Bug fix. With strings=encoded captions were left unchanged in
	\MakeUppercase/\MakeLowercase.
3.9j  - Bug fix. Plain formats didn't work (Undefined \@filelist).
3.9k  - Code and doc reorganized with some `literate' concepts (with a
        slightly patched docstrip).
      - Removed the luatex stuff for shorthands. It was just a first step,
        but ended up in the final release of 3.9i (it shouldn't).
      - Improvements for Plain and other non-LaTeX formats.
3.9l  - Formerly, fontspec set \latinencoding to EUx if babel was loaded.
        Now, babel sets it if fontspec is loaded.
      - New package options 'nocase' (\SetCase is ignored) and 'silent'
      - Improved compatibility (hopefully) with babelbib.
3.9m  - Fixed melayu name (from meyalu).
      - A few lines for \babelpatterns (only luatex, see below).
3.9n  - Just fixes a couple of minor bugs (related to 2.09 and ifthen).
3.9o  - Adapted to the forthcoming Unicode encoding.
3.9p  - A little change for bbunicode 1.1b.
3.9q  - base now reads patterns in lua
      - Some minor changes for luatex
3.9r  - The three main dtx files now share version numbers.
      - bbunicode - Fixed a line break at \cs{foreignlanguage} with
        unloaded patterns. Also added \babelcatcodetablenum, just in
	case.
3.9s  - Bug fix - extra speces with \babelensure
3.9t  - Part of the code for 3.10 has been "back-ported" to this
        release, but they are only internal changes.
      - Fix - with \babelhyphen{soft} the hyphen could vanish.
      - English, Indonesian and Malay "dialects" now rely on the proxy
        files provided by these languages (eg, american.ldf, melayu.ldf).
	If you upgrade babel, you must upgrade those languages, too.

* bbunicode.dtx
1.0b  - Improvements by Elie Roux for LuaTeX.
1.0c  - Bug fix. A few codes in xetex where wrong when loading patterns.
1.0e  - \babelpatterns, which adds patterns to a language.
      - Use [[]] instead of \luaescapestring (the latter is not always
        available).
1.0f  - Code for luatex assigned mistakenly to xetex.
1.1a  - Revamped hyphenation loader for luatex.
1.1b  - Now patterns are loaded with lua(e)tex (and a bug fixed).
1.1c  - Patterns loader thorougly revised
3.9r and later - The three main dtx files now share version numbers. See
        changes above    
```



Javier Bezos
2017-04-28

