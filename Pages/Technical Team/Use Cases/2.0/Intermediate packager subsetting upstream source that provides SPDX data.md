1.  **Title:** Intermediate packager subsetting upstream source that
    provides SPDX data
2.  **Primary Actor:** Intermediate packager (someone building a rpm,
    deb, etc from upstream source)
3.  **Goal in Context:** To include in the package SPDX data describing
    the packages licensing information for the package base upon the
    SPDX data provided by the upstream source in a way that allows the
    packager to verifiably reference the upstream packagers SPDX data
    and to make clear that only a subset of the copyrightable artifacts
    provided by upstream maintainer are included in the copyright
    artifacts provided in the package. Examples would include -dev
    packages that only include headers, packages that do not package
    contrib/ subdirectories, or otherwise break up what upstream has
    provided into package shaped pieces.
4.  **Stakeholders and Interests:**
    1.  '''Upstream maintainers: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts.
        2.  To have their licenses respected
    2.  **Intermediate Packager:**
        1.  To communicate the licensing information for their package
        2.  To communicate the licensing information provided by the
            upstream maintainer.
        3.  To indicate that they are only passing on copyrightable
            artifacts based on a subset of the copyrightable artifacts
            provided by the upstream maintainers.
        4.  To respect the licenses of the upstream maintainer
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
    1.  Upstream maintainer has provided SPDX data
    2.  Packager understands how they are subsetting the upstream source
6.  **Main Success Senario:** Packager communicates accurate complete
    licensing information for their package in an SPDX data format via
    all of the applicable SPDX delivery mechanisms in such a way that
    indicates they are only using parts of what is provided in the
    upstream source.
    1.  NOTE: sub-setting the data from the upstream SPDX data may
        require modifications of the original data in the newly created
        sub-set. For example, eliminating the contrib files might mean
        that some licenses are no longer applicable.
7.  **Failed End Condition:** Package maintainer communicates inaccurate
    incomplete licensing information for their package.
8.  **Trigger:**
    1.  Release of a new package
9.  **Notes:** Upstream may be the root provider of the code, a source
    package, or some other intermediate party. At the end of the day
    it's who you got the code from.

[Category:Technical](Category:Technical "wikilink")
