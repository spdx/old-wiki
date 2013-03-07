A vendor wants to embed information about a package in its SPDX file
that is not representable using standard SPDX fields (and/or classes).

## Stakeholders and interests

  - **SPDX producer**The person or organization that is producing the
    SPDX and wish to extend it with non-standard information.
  - **standard SPDX consumer**A person, organization or tool that can
    read and process standard SPDX data but is not aware of the
    non-standard extensions being used by "SPDX producer".
  - **extended SPDX consumer**A person, organization or tool that can
    read and process the non-standard extensions used by "SPDX producer"
    as well as standard SPDX data.

## Main scenario

1.  SPDX producer analyzes the package for all the standard SPDX data
2.  SPDX producer analyzes the package for the list actions they believe
    are required to comply with the licensing of the package
3.  SPDX producer generates an SPDX file which included both the
    standard SPDX data and the compliance checklist
4.  SPDX producer publishes this file on their website as a "SPDX file
    for package X"
5.  An extended SPDX consumer downloads the SPDX file and uses the
    checklist to ensure they are meeting their licensing obligations

## Alternate scenario A

1.  SPDX producer analyzes the package for all the standard SPDX data
2.  SPDX producer analyzes the package for the list actions they believe
    are required to comply with the licensing of the package
3.  SPDX producer generates an SPDX file which included both the
    standard SPDX data and the compliance checklist
4.  SPDX producer publishes this file on their website as a "SPDX file
    for package X"
5.  A standard SPDX consumer downloads the SPDX file and uses the
    standard data as input into their compliance processes

## Failed scenario

1.  **Fails if the extensions "break" 'standard consumer/tools' such
    that they can't even process the standard stuff.**

[Category:Technical](Category:Technical "wikilink")
