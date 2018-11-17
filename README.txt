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

===== Development =====

=== Change Log ===

**Please note that this plugin is not actively developed anymore!**

You can find the whole release history on [[https://www.tolledomain.ch/dokuwiki/doku.php?id=projects:markdowku|the plugin website]].

**Last update: 2017-02-19**: Relese a new version. Compatibility with PHP 7.0 is now inside. I am sorry for the long delay with that. I had the code around, but testing was a bit difficult with PHP 7.0. However, it is released now.

=== Bugs/Issues ===

There is a [[https://vcs.in-berlin.de/schrank21_dokuwiki/reportlist|bug tracker]] online. Please note you have to log in anonymous (go to Login page, click "Fill out captcha") before you can commit bugs. Also, you can write me an e-mail and I will enter the bug to the bug tracker.

=== ToDo/Wish List ===

This plugin is not complete yet. Incompatibilities are listed above at [[#Known incompatibilities]].

In the end, I want to extend this plugin to be able to handle different markdown flavours (esp. Github), with a switch in the configuration to choose between those all.

A switch like <no_markdown> will allow to avoid problems with existing native markup pages. (jseto) -- I'll see what is possible, but I think it will be difficult to implement that. (gnrp 13-09-23)

The plugin editor does not work together with markdown. Either have the possibility to disable it, or even better, make it work with Markdown (Celano 13-08-08, reformatted by gnrp 13-09-23)

The plugin seem useful as we write in markdown but eventually need to use some DokuWiki syntax. I have to say that the wiki display markdown files created elsewhere by peoples using markdown editor and they doesn’t want to change to a new syntax. The idea is they work as they used to in markdown tools, and eventually had some DokuWiki synthax for some site related features and needs. I have three problems that prevent us to use the plugin which I hope could be improved. 

  * Html doesn’t work but html is correct markdown and really useful for things markdown can’t do. Even the %%<html></html>%% tags of DokuWiki doesn’t work either. I have allowed html in config options but the plugin just seems to ruin the page when it enconter any %%<tag>%%. FIXME
  * Second problem is that we use a lot the footnote syntax of markdown extra (a footnote syntax %%[^1]%% which become near a standard in markdown tools) [[https://michelf.ca/projects/php-markdown/extra/#footnotes|https://michelf.ca/projects/php-markdown/extra/#footnotes]]. This addition would be very nice. 
  * Reference-style links from classic markdown doesn’t works. [[http://daringfireball.net/projects/markdown/syntax#link|http://daringfireball.net/projects/markdown/syntax#link]]
(dinobib 15-05-25)


If it used .md, I might be able to keep it synced with my .md files in dropbox. 

===== FAQ =====

=== There are already two Markdown plugins, why do you write a third one? ===

The prior two plugins ([[markdown]], [[markdownextra]]) work completely different. The other two just create a large container (either defined by ''<markdown>'' tags or a .md file ending) and parse everything inside them as Markdown.

This plugin adds Markdown to the DokuWiki syntax, i.e. it still uses DokuWiki definitions for lists, headers, etc.  Thus, markdowku enables you to use internal links, mix Markdown with other plugins and other syntaxes and have clean section headers and media embedding.

===== Discussion =====

It would be nice if Commonmark would be supported!
==== Date of the latest version ====
Latest version is 2016-01-16, however the plugin repository is incorrectly showing 2017-02-19 as the current version, making the Extension Manager show an available update (that won't work since plugin.info.txt doesn't match the supposedly new version date).

==== Donation doesn't work ====

I want to donate some bucks for the developer of the plugin. But donation didn't work.

