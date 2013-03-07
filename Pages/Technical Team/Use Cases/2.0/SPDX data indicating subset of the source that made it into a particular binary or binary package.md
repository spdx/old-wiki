1.  **Title:** SPDX data indicating subset of the source that made it
    into a particular binary or binary package
2.  **Primary Actor:** Builder of binary copyrightable artifact
3.  **Goal in Context:** To be able to indicate the SPDX data for the
    source code copyrightable artifacts that made their way into a
    particular copyrightable binary artifacts.
4.  *' Stakeholders and Interests:*'
    1.  '''Binary Builder: '''
        1.  To communicate the licensing information for their binary
            copyrightable artifact, including what source files where
            built into it and a reference to their SPDX data.
        2.  To have their licenses respected
        3.  To help consumers understand what they are getting.
    2.  **Consumers of application copyrightable artifacts:**
        1.  To receive accurate and clear information of licensing of
            artifacts
        2.  To be able to comply easily with licenses for artifacts
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Binary builder has some way to understand what source is built
        into their binary
    2.  Binary builder has some understanding of the license informatino
        for the source built into their binary and an expression of it
        in SPDX form.
6.  **Main Success Scenario:** Binary builder builds a binary from a
    selection of source code files and can indicate exactly the SPDX
    data for that binary by referencing the source files SPDX data.
7.  '''Failed End Condition: '''Binary builder builds a binary from a
    selection of source code files and cannot indicate exactly the SPDX
    data for that binary by referencing the source files SPDX data.
8.  **Trigger:**
    1.  Binary build time
    2.  Commit time?
9.  **Notes:** analagous to the 'Postgres without contrib directory'
    scenario (i.e. my binary was built from all that source described by
    that SPDX file, EXCEPT I intentionally left out the contrib folder
    that was under GPL. Said another way, my build only included this
    subset of files. Similar to Yocto build scenario..)

[Category:Technical](Category:Technical "wikilink")
