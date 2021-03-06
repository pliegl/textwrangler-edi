# BBEdit EDI tools
This repository contains some [EDIFACT](http://en.wikipedia.org/wiki/EDIFACT) enhancements for [BBEdit editor](https://www.barebones.com/products/bbedit/) on Mac OS. The goal is to make working with plain EDIFACT text files less tedious, by adding a better EDIFACT user experience.

The tools include syntax highlighting for EDIFACT files as well as two text filters for expanding/flattening EDIFACT files.


# EDIFACT syntax highlighting

The [codeless language module (CLM)](http://www.barebones.com/support/develop/clm.html) provided in this repository adds syntax highlighting for [EDIFACT](http://en.wikipedia.org/wiki/EDIFACT) to [BBEdit](https://www.barebones.com/products/bbedit/).

## How to use

Take the file `edifact.plist` and copy it to `~/Library/Application Support/BBEdit/Language Modules`.

Restart BBEdit for changes to take effect.

Open any arbitrary EDIFACT file, such as the following one.

![EDIFACT file](https://raw.githubusercontent.com/pliegl/textwrangler-edi/master/site/regular.png?raw=true "EDIFACT file")

On the lower left hand side select *EDIFACT* as file type. Voilà - all segments, segment separators, and composite data element separators are highlighted.

Note, that any file ending on `.edi` will automatically be recognized as EDIFACT file.

![Enabled EDIFACT CLM](https://raw.githubusercontent.com/pliegl/textwrangler-edi/master/site/enabled.png?raw=true "Enabled CLM")

An even better experience may be achieved if you use [Andrew Hazelden's Charcoal Color Scheme](http://www.andrewhazelden.com/blog/2012/09/charcoal-color-scheme-for-textwrangler-and-bbedit/).

![Enabled EDIFACT CLM with dark theme](https://raw.githubusercontent.com/pliegl/textwrangler-edi/master/site/enabled_dark.png?raw=true "Enabled CLM with dark theme")

If you want to change the used colors go to *BBEdit* > *Preferences* > *Text Colors*

The following colors may be set:

 * `Predefined Names` for the coloring of the following segments: UNA, UNB, UNG, UNH, UNS, UNT, UNE, UNZ

 * `Keywords` for all other segments.

 * `String constants` for segment separators `+` and `'`

 * `Comments` for component data element separators `:`

## Supported EDIFACT document types

Currently, the following document types of EDIFACT EANCOM D01B and EDIFACT EANCOM D96A are supported:

 * ORDERS
 * DESADV
 * INVOIC
 * DELFOR


# EDIFACT Text Filters

The EDIFACT text filters facilitate the processing of EDIFACT files by automatically adding line breaks to EDIFACT files (for better legibility) and removing line breaks (to make them EDIFACT compliant - EDIFACT files must not contain line breaks).

## How to use

Take the files `expandEDIFACT.py` and `flattenEDIFACT.sh` and copy them to `~/Library/Application Support/BBEdit/Text Filters`.

Access the filters under *Text* > *Apply Text Filter*

Applying `expandEDIFACT.py` will add line breaks after every `'`.

Applying `flattenEDIFACT.sh` will remove any line breaks from the EDIFACT file, thus, making it EDIFACT-compliant.
