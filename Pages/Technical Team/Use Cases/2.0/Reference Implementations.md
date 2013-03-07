1.  **Title:** Reference Implementations
2.  **Primary Actor:** Provideor of a reference implementation
3.  **Goal in Context:** To include with the copyrightable artifacts
    distributed by the reference implementation SPDX data describing
    it's licensing information and the type of copyrightable artifacts.
    The reference implementation is typically a hardware device (board)
    that comes in a box with software pre-flashed to demonstrate some
    functionality, documentation, cables and so forth. There may also be
    DVDs, CDs, an SD card, etc that could contain host development
    tools, the software for the pieces running on the flash, additional
    SDKs, applications (test and/or demonstration), a distribution of
    some sort and so forth. This can be a very large amount of material
    and software and this use case could be seen as a superset of the
    application, SDK, etc use cases. Note: Some artifacts like
    Makefiles, sample data files and/or other project files (e.g. IDE
    project files), scripts and so forth may be machine generated and
    thus not have a copyright or license and other “incidental” project
    files may not have copyrights as well.
4.  *' Stakeholders and Interests:*'
    1.  '''Reference Implementation Provider: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts and the type of artifacts.
        2.  To have their licenses respected
        3.  To help consumers understand what they are getting.
    2.  **Consumers of Reference Implementation artifacts:**
        1.  To receive accurate and clear information of licensing of
            artifacts
        2.  To be able to comply with licenses for artifacts
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Upstream has selected licenses for the copyrightable artifacts
        originating with the project (package, files, etc)
    2.  Upstream has indentified license data for other copyrightable
        artifacts they consume
6.  **Main Success Scenario:** Reference Implementation Provider
    communicates accurate and complete licensing information for the
    copyrightable artifacts in an SPDX data format.
7.  **Failed End Condition:** Reference Implementation Provider
    communicates inaccurateand/or incomplete licensing information for
    the copyrightable artifacts.
8.  **Trigger:**
    1.  Reference implementation release (ship)
    2.  Commit time?
    3.  Checkout from a repository?
    4.  Inclusion of external artifacts into the reference platform
    5.  Posting of updated software for a reference implementation

**Notes:** This use case can be viewed as a superset of the application,
SDK, distribution, Yocto, etc uses cases where many things are
aggregated together. There may be a lot of SPDX documents. Software on
Reference Implementations are typically updated and could be posted for
download from a website or made accessible though a source code control
system. (as examples).

[Category:Technical](Category:Technical "wikilink")
