1.  **Title:** Intermediate packager builds source package from upstream
    source that does not provide SPDX data
2.  **Primary Actor:** Intermediate packager (someone building a rpm,
    deb, etc from upstream source)
3.  **Goal in Context:** To include in the package SPDX data describing
    the packages licensing information for the package base even though
    the upstream project is not providing SPDX data.
4.  **Stakeholders and Interests:**
    1.  '''Upstream maintainers: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts.
        2.  To have their licenses respected
    2.  **Intermediate Packager:**
        1.  To communicate the licensing information for their package
        2.  To communicate the licensing information provided by the
            upstream maintainer.
        3.  To respect the licenses of the upstream maintainer
    3.  **Consumers of packages:**
        1.  To receive accurate and clear information of licensing of
            packages
        2.  To be able to comply easily with licenses for packages
        3.  To be able to trust that the package SPDX data is in
            alignment with the upstream maintainers license assertions.
        4.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Packager has some means to understand the licensing information
        from the upstream source.
6.  **Main Success Senario:** Packager communicates accurate complete
    licensing information for their package in an SPDX data format via
    all of the applicable SPDX delivery mechanisms.
7.  **Failed End Condition:** Package maintainer communicates inaccurate
    incomplete licensing information for their package.
8.  **Trigger:**
    1.  Release of a new package
9.  **Notes:** This is a base case, it is well understood that packagers
    both add to the upstream source, but also subset it.

[Category:Technical](Category:Technical "wikilink")
