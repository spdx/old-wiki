1.  **Title:** Committer annotates source files with SPDX data
2.  **Primary Actor:** Committer
3.  **Goal in Context:** To indicate SPDX data for the file in the
    source code file.
4.  **Preconditions:**
    1.  Committer has decided the license for the file they are
        committing
5.  **Stakeholders and Interests:**
    1.  **Committer:**
        1.  To communicate the license information for the file in line
            with the file.
    2.  '''Upstream maintainers: '''
        1.  To be able to have the source code be self documenting in a
            machine and human readable manner with respect to license
            information.
        2.  To communicate the licensing information for their
            copyrightable artifacts.
        3.  To have their licenses respected
    3.  **Consumers of upstream source:**
        1.  To receive accurate and clear information of licensing of
            upstream source
        2.  To be able to comply easily with licenses for upstream
            source
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
6.  **Main Success Senario:** Source code files contain complete
    accurate SPDX data sufficient to communicate their licensing
    information in a way that is both human and machine readable.
7.  **Failed End Condition:**
    1.  Source code files lack accurate SPDX data.
    2.  Source code files lack complete accurate SPDX data.
    3.  The annotation turns out not to be machine-readable
        (inappropriate syntax?)
8.  **Trigger:**
    1.  Commit of code to an upstream project.
9.  '''Notes: '''There may be sub-use cases here around the distinction
    between original authorship of a file and capturing in SPDX existing
    information about the file, either from existing file headers or
    from commit logs.

[Category:Technical](Category:Technical "wikilink")
