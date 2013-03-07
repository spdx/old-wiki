Some times the data needed to populate all the fields in SPDX is not
available. This can be because the data was collected before the full
requirements of SPDX were known, or because the tools being used to
produce the SPDX files are not completely implemented. In these cases
the SPDX producer would like to generate an SPDX file with the
information that is available and omit any information that is not known
and have this file be considered a valid SPDX file. In this situation
consumers would be able to parse the partial SPDX file and decide
whether to accept the data based on whatever trust heuristics are
appropriate for its goal.

## Stakeholders and interests

  - **SPDX producer**The agent that is generating the SPDX file. In this
    use case this agent does not have all the information required to
    populate all the mandatory part of an SPDX file.
  - **Lax SPDX consumer**An agent which is attempting to use the
    information encoded in the partial SPDX file and can still
    accomplish its goal in the face of missing information.
  - **Strict SPDX consumer**An agent which is attempting to use the
    information encoded in the partial SPDX file but requires a full
    SPDX file to accomplish its goal.

## Main scenario

1.  Long ago (before SPDX 1.0 was complete) SPDX producer analyzed a
    package using tooling that checksumed files using the SHA-256
    algorithm.
2.  SPDX producer does not want to redo the analysis because it is too
    costly.
3.  SPDX producer generates an SPDX file which is complete and valid
    except that all checksum properties are omitted.
4.  SPDX producer delivers the SPDX file to Lax SPDX consumer.
5.  Lax SPDX consumer reads SPDX file, noting the lack of checksums, and
    uses the licensing information to ensure compliance with the
    packages licensing.

## Alternate scenario A

1.  Long ago (before SPDX 1.0 was complete) SPDX producer analyzed a
    package using tooling that checksumed files using the SHA-256
    algorithm.
2.  SPDX producer does not want to redo the analysis because it is too
    costly.
3.  SPDX producer generates an SPDX file which is complete and valid
    except that all checksum properties are omitted.
4.  SPDX producer delivers the SPDX file to Strict SPDX consumer.
5.  Strict SPDX consumer reads SPDX file and refuses to accept it
    because its trust heuristics require checksums be present.
6.  Strict SPDX consumer either procedes without SPDX info for this
    package or requests that SPDX producer produce an SPDX file with
    checksums.

## Alcatel-Lucent scenario statement (from Michel Ruffin on mailing list)

ALU has a DB with 5000 entries for open source maintained since 2002
describing IPR issues. Since 2007 we are requesting from all our
suppliers the list of FOSS coming with their products with license, URL
of origin, etc. Then one of our 200 FOSS evaluators look at this list
compares it to what we have in our database to see if we can accept it
or not. He/She enters in the DB the missing entries, … (and I can tell
you that this is useful because on nearly 2 contracts on 3 with our
suppliers, we find issues that need mitigation). The SPDX standard
should allow us to automate partly this process. And our customers are
now starting to ask us similar information.

These 2 fields (see below 4.3 Package File Name and 4.7 Package
Verification Code) are not relevant in this context to my knowledge. So
if these fields are mandatory and we implement an export function, we
will generate files that would not be compliant to the standard and then
it might be worthless. For the import function we can ignore them I
guess.

If there is a good reason for keeping these fields mandatory ALU will
try to align its DB on it, but it would be a huge work. But if there is
no good reason we ask to make them optional.

*4.3 Package File Name*

*4.3.1 Purpose: Provide the actual file name of the package. This may
include the*

*packaging and compression methods used as part of the file name.*

*4.3.2 Intent: Here, the actual file name of the compressed file
containing the*

*package is a significant technical element that needs to be included
with each*

*package identification information.*

*4.3.3 Cardinality: Mandatory, one.*

*4.7 Package Verification Code*

*4.7.1 Purpose: This field provides an independently reproducible
mechanism*

*identifying specific contents of a package based on the actual files
(except the*

*SPDX file itself, if it is included in the package) that make up each
package*

*and that correlates to the data in this SPDX file. This identifier
enables a*

*recipient to determine if any file in the original package (that the
analysis*

*was done on) has been changed and permits inclusion of an SPDX file as
part of a*

*package.*

*4.7.2 Intent: Providing a unique identifier based on the files inside
each*

*package, eliminates confusion over which version or modification of a
specific*

*package the SPDX file refers to. The SPDX file can be embedded within
the*

*package without altering the identifier.*

*4.7.3 Cardinality: Mandatory, one.*

[Category:Technical](Category:Technical "wikilink")
