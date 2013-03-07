As an [auditor](http://spdx.org/stakeholders#auditor) in order to be
certain that the licensing and provenance information regarding a
binary, or compiled, file is correct i want a manifest of the files used
to create it.

## Stakeholders and interests

  - **Auditor:** The person or organization performing an audit on the
    licensing and provenance information of a package.
  - **Project maintainer:** The person pr organization which maintains
    the open source software in question.
  - **Developer:** The person or organization using the software package
    provided by Project maintainer.

## Main Scenario

1.  Project maintainer builds binary files keeping track of which source
    files are included in the binary.
2.  Project maintainer publishes package with SPDX that provides
    references to every source used to create each compiled file in the
    package.
3.  Developer downloads binary/compiled package from Package maintainer.
4.  Developer requests audit of code base before shipping.
5.  Auditor wants to verify that provided licensing and provenance info
    for compiled files are actually what the provided SPDX file claims.
6.  Auditor uses the built from file list for the compiled file to
    narrow the analysis to particular files and specific versions of
    those files.
7.  Auditor performs deep analysis to ensure the that the licensing and
    provenance of the files are indeed as claimed
8.  Auditor provides clean bill of health

## Alternate Scenario A

1.  Project maintainer builds binary files keeping track of which source
    files are included in the binary.
2.  Project maintainer publishes package with SPDX that provides
    references to every source used to create each compiled file in the
    package.
3.  Developer downloads binary/compiled package from Package maintainer.
4.  Developer requests audit of code base before shipping.
5.  Auditor wants to verify that provided licensing and provenance info
    for compiled files are actually what the provided SPDX file claims.
6.  Auditor uses the built from package list for the compiled file to
    narrow the analysis to particular packages and specific versions of
    those packages.
7.  Auditor performs deep analysis to ensure the that the licensing and
    provenance of the files are indeed as claimed
8.  Auditor provides clean bill of health

**NOTES: on 2012-10-02 having difficulty understanding the distinction
between Main Scenario and Alternate A. versions of files vs. versions of
Packages? (step 6)**

[Category:Technical](Category:Technical "wikilink")
