## paragraph rearrangement

**resolved**

The consensus was that this is outside the scope of templatization.

## Whitespace normalization

**resolved**

How to deal with whitespace repeation and newlines vs space vs tab

1.  replace all whitespace characters with SPACE
2.  collapse repeated spaces to one space character

## Copyright notices

The text some of licenses in our list contain a copyright statement. Is
this actually part of the license text? In some cases (eg. gpl) it
definitely is. In others (eg. bsd) it does not feel like part of the
license. Would it be ok to remove the copyright statement from licenses
where that statement does not apply to the text of the license itself.

## Replaceable parts

Dealing with copyright owner, copyright year, etc.

Some sort of demarcation of replaceable elements in a license. These
would be limited to a discrete list of supported element types. For
example, year and copyright holder.

We could allow replaceable elements to be used in any license text at
the risk of colliding with non-template parts of the license text.
Alternatively, we could explicitly indicate that the license text of a
particular licenses has replaceable elements. An explicit indication of
templatization would allow us to simply not use replaceable elements for
licenses which would have collisions. However, it would prevent us from
templatizing licenses that would have collisions

Perhaps an esoteric template syntax would allow us to avoid the
collision issue. Maybe something like "{{{YEAR}}}"?

## Section/bullet numbering/lettering

If a sdpx registered license has a list labeled a,b,a does it match
license text that is identical except that the list is labeled i,ii,iii?

this issue has not been explored

## Different spellings of same word

color vs colour

Issue not dealt with. Perhaps a stemming algorithm of some sort?

## Separate field

Is a separate field for the normalized/templated version of the license
text necessary and desirable?

Normalization algorithm must be defined normatively in the spec.

Explicit field for normalized/templated version could be helpful as
examples. Perhaps example of every standard license is unnecessary.

[Category:Legal](Category:Legal "wikilink")
[Category:Archived](Category:Archived "wikilink")
