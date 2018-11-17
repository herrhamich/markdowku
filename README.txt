====== markdowku Plugin ======

---- plugin ----
description: Integrates Markdown into DokuWiki syntax
author     : Julian Fagir 
email      : gnrp@komkon2.de
type       : Syntax
lastupdate : 2017-02-19
compatible : Adora Belle, Weatherwax, Binky, Ponder Stibbons, Elenor of Tsort
depends    : 
conflicts  : 
similar    : mediasyntax, creole, markdown, markdownextra
tags       : formatting, markup_language

downloadurl: https://komkon2.de/markdowku/markdowku.tgz
bugtracker : https://vcs.in-berlin.de/schrank21_dokuwiki/reportlist
sourcerepo : https://vcs.in-berlin.de/schrank21_dokuwiki
donationurl: # https://www.komkon2.de/dokuwiki/doku.php?id=donate FIXME
----

===== Installation =====

Search and install the plugin using the [[plugin:extension|Extension Manager]]. Refer to [[:Plugins]] on how to install plugins manually.

===== Examples/Usage =====

This plugin will go before the overlapping DokuWiki syntax definitions and overrule them with Markdown specifications.

For patterns that are not part of Markdown, you can still use DokuWiki, e.g. you're still able to use DokuWiki tables.

===== Syntax =====

This plugins tries to resemble Markdown as closely as possible and does not extend it.
It is a best-effort implementation - I didn't try to match the Markdown test suite, but rather provide a look-alike handler for Markdown syntax, as Markdown itself is somewhat underspecified.

You'll find the [[http://daringfireball.net/projects/markdown/basics|basic description]] on the [[http://daringfireball.net/|website]] of the Markdown author, as well as a [[http://daringfireball.net/projects/markdown/syntax|deeper description]] of the syntax.

If you encounter any incompatibilities in this version, feel free to add them here or report them.

==== Known incompatibilities ====

Due to the inner working of Markdown and DokuWiki, there are things which currently cannot be done with this plugin. I am working on getting this fixed. If you want to help, feel free to contact me (gnrp) in IRC.

All in all, this plugin is complete. Just when it comes to nesting things, i.e. putting things into each other, this plugin doesn't handle lists and blockquotes well.

This should be a complete list of current general incompatibilities. Everything else is a bug:
  * nested in blockquotes:
    * codeblocks
    * paragraph handling
    * lists
    * multiline reflinks/refimages
  * nested in lists:
    * codeblocks
    * quotes
    * multiline reflinks/refimages
    * ATX headers
    * Setext headers
    * horizontal rulers
  * codespans with more than five backticks (most probably never used)
  * using underscores to make text bold. Double underline is already used by DokuWiki for underlining text (Markdown can't do that), and I think it's better to have the option for underlining. In general notation, you also rather use underscores for underlining than making text bold.
  * conflict with [[https://www.dokuwiki.org/template:bootstrap3|bootstraps3 theme]] in bulleted lists

