---
title: 'MMARK(1)'
author:
    - Mmark Authors
date: October 2019
---

# NAME

mmark \\- generate XML, HTML or manual pages from mmark markdown documents.

# SYNOPSIS

**mmark** [**OPTIONS**] [*FILE...*]

# DESCRIPTION

**Mmark** is a powerful markdown processor written in Go, geared towards writing IETF documents. It
is, however, *also* suited for writing complete books and other technical documentation.

Mmark provides an advanced markdown dialect that processes file(s) to produce internet-drafts in XML
[RFC 7991](https://tools.ietf.org/html/rfc7991) format. Mmark can produce xml2rfc (aforementioned
RFC 7991), HTML5 and manual pages.

The syntax is detailed at [https://mmark.miek.nl/syntax](https://mmark.miek.nl/syntax).

Compared to other markdown variants mmark adds:

*  (Extended) title block to specify authors and IETF specific bits.

*  (Special) sections for abstracts, prefaces or notes.

*  Including other files with the option to specify line ranges, regular expressions and/or
   prefixing each line with a custom string.

*  Document divisions: front matter, main matter and back matter.

*  Captions for code, tables, quotes and subfigures.

*  Asides for small notes.

*  Figures and subfigures that allow for grouping images into subfigures as well as giving a single
   image metadata (a link, attributes, etc.).

*  Block Level Attributes that allow to specify attributes, classes and IDs for elements.

*  Indices to mark an item (and/or a subitem) to be referenced in the document index.

*  Citations and adding XML References (those used by the IETF).

*  Cross references: short form of referencing a section in the document.

*  Super- and subscript.

*  Callouts in code and text.

*  BCP14 (RFC 2119) keyword detection.

## RFC 7991

This is the XML format used by the RFC editor for accepting Internet-Drafts.

## HTML5

The HTML5 renderer outputs HTML.

## Manual Pages

The man renderer outputs nroff that can be viewed via man(1).

# OPTIONS

`-ast`

:  print abstract syntax tree and exit

`-fragment`

:  don't create a full document


`-css` *URL*

:  *URL* to a CSS stylesheet (only used with -html)

`-head` *URL*

:  *URL* to HTML to be included in head (only used with -html)

`-html`

:  create HTML output

`-man`

:  output nroff (manual pages)

`-unsafe`

:  allow includes from anywhere in the filesystem, otherwise they are only allowed *below* the
   current document

`-unicode`

:  allow unicode characters in \<t\>, from xml2rfc 3.16.0 this is allowed. It's true by default, set
   to false if you have an older xml2rfc version. Note the \<u\> text/html output produced by
   xml2rfc is (extremely) verbose.

`-index`

:  generate an index at the end of the document (default true)

`-bibliography`

:  generate a bibliography section after the back matter (default true), this *needs* a
   `{{backmatter}}` in the document

`-version`

:  show mmark's version

# ALSO SEE

RFC 7991 and (maybe) RFC 7749. The main site for Mmark is
[https://mmark.miek.nl](https://mmark.miek.nl). The syntax used by mmark is explained in the [syntax
page](https://mmark.miek.nl/post/syntax/).
