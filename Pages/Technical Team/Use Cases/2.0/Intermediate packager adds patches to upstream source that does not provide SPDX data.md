1.  **Title:** Intermediate packager adds patches to upstream source
    that does not provide SPDX data
2.  **Primary Actor:** Intermediate packager (someone building a rpm,
    deb, etc from upstream source)
3.  **Goal in Context:** To include in the package SPDX data describing
    the packages licensing information for the package when the upstream
    source does not include SPDX data and also to include SPDX data
    describing the packagers additions (patches) to the project.
4.  **Stakeholders and Interests:**
    1.  '''Upstream maintainers: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts.
        2.  To have their licenses respected
    2.  **Intermediate Packager:**
        1.  To communicate the licensing information for their package
        2.  To communicate the licensing information for the packagers
            additions (patches) to the upstream source.
        3.  To communicate the licensing information provided by the
            upstream maintainer.
        4.  To respect the licenses of the upstream maintainer
    3.  **Consumers of packages:**
        1.  To receive accurate and clear information of licensing of
            packages
        2.  To receive accurate and clear information of the licensing
            of the packagers additions (patches) to the upstream source.
        3.  To be able to comply easily with licenses for packages
        4.  To be able to trust that the package SPDX data is in
            alignment with the upstream maintainers license assertions.
        5.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Intermediate Packager understands the licensing information of
        the upstream project.
    2.  Package maintainer has selected a license for their additions
        (patches) to the upstream source
6.  **Main Success Senario:** Packager communicates accurate complete
    licensing information for their package in an SPDX data format via
    all of the applicable SPDX delivery mechanisms.
7.  **Failed End Condition:** Package maintainer communicates inaccurate
    incomplete licensing information for their package.
8.  **Trigger:**
    1.  Release of a new package
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
