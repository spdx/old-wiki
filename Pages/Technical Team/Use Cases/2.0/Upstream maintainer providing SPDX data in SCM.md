1.  **Title:** Upstream maintainer providing SPDX data in SCM
2.  **Primary Actor:** Member of upstream maintainer team
3.  **Goal in Context:** To include with the copyrightable artifacts
    distributed by the project SPDX data describing it's licensing
    information in the SCM (source control management system, for
    example git,cvs,svn). The goal is to have the SPDX data at any given
    point in the SCM match the source code at that point in the SCM, so
    that whenever code is checked out from the SCM, it has SPDX data
    appropriate to it.
4.  **Stakeholders and Interests:**
    1.  '''Upstream maintainers: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts.
        2.  To have their licenses respected
    2.  **Consumers of upstreams copyrightable artifacts:**
        1.  To receive accurate and clear information of licensing of
            artifacts
        2.  To be able to comply easily with licenses for artifacts
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Upstream has selected licenses for the copyrightable artifacts
        originating with the project (package, files, etc)
    2.  Upstream has identified license data for other copyrightable
        artifacts they consume
6.  **Main Success Scenario:** Upstream communicates accurate complete
    licensing information for their copyrightable artifacts in an SPDX
    data format in the SCM matching the code present in the SCM at that
    point. (such that someone who subsequently checks-out/pulls from
    that point in the SCM can obtain corresponding SPDX data)
7.  **Failed End Condition:** Upstream communicates inaccurate
    incomplete licensing information for their copyrightable artifacts.
8.  **Trigger:**
    1.  SCM Commit
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
