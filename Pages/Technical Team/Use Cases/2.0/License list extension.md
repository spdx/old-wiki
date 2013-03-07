An organization that does a lot of compliance work is likely to have a
license list already which is a superset of the SPDX license list. Such
an organization probably will have policies for how to deal with at
least some of these licenses. It is important that organizations be able
identify the equivalency of these non-SPDX listed license texts/notices.

(Use Case request is that there be possibility to convey non-SPDX (or
not-yet SPDX) licensing in an SPDX doc exchanged between knowing
partners referencing a short-form license identifier from that non-SPDX
list namespace)

## Stakeholders and interests

### Analyzer

A person or organization which produced the SDPX file and maintains
their own license list.

### Consumer

A person, organization or tool which wants to consume SPDX files
produced by one or more analyzer. This entity maintains its own license
list and policies for those licenses. This license list partially
overlaps with each of the Analyzers' license lists. The Consumer
maintains mappings between its list and those of the analyzers from
which it receives SPDX files.

## Main Scenario

1.  Analyzer analyzes a package and finds licenses it recognizes that
    are not listed on <http://spdx.org/licenses>
2.  Analyzer passes SPDX data to Consumer
3.  For each SPDX listed license Consumer performs appropriate action
    based on its policy for that license
4.  For each non-SPDX listed license Consumer maps from the globally
    unique id of the license in the Anaylzer's license list to the
    license in it's list and performs appropriate action based on its
    policy for that license

## Alternate scenario A

1.  Analyzer generates SPDX data referencing its license list for
    non-SPDX listed licenses
2.  Later one of the licenses in that SPDX file is added to SPDX license
    list
3.  Consumer detects non-SPDX listed license and maps it to the now SPDX
    listed license

## Alternate scenario B

1.  Analyzer analyzes a package and finds licenses it recognizes that
    are not listed on <http://spdx.org/licenses>
2.  Analyzer passes SPDX data to Consumer
3.  For each SPDX listed license Consumer performs appropriate action
    based on its policy for that license
4.  Consumer encounters license from Analyzers list that it does not
    have a mapping for
5.  Consumer fetches license data from Analyzer's license list and adds
    that license to its license list

## Failed scenario

1.  Failed scenario if there ends up being a collision between
    references to SPDX standard license list and reference to another
    license list.

[Category:Technical](Category:Technical "wikilink")
