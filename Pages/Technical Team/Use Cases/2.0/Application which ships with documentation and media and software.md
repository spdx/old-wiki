1.  **Title:** Application which ships with documentation + media +
    software
2.  **Primary Actor:** Member of the application team
3.  **Goal in Context:** To include with the copyrightable artifacts
    distributed by the application SPDX data describing it's licensing
    information and the type of copyrightable artifacts and that this
    grouping belongs to this application. Typically applications will
    include not only source code and/or pre-built images but there will
    also be other copyrightable artifacts associated with it. These can
    include such things as media files, documentation (user guides,
    programming guides, API guides, help files, etc), Makefiles or other
    project files (e.g. IDE project files), scripts and so forth. Some
    may be machine generated and thus not have a copyright or license
    and other “incidental” project files may not have copyrights as
    well.
4.  *' Stakeholders and Interests:*'
    1.  '''Application Provider: '''
        1.  To communicate the licensing information for their
            copyrightable artifacts, the type of artifacts and that they
            are a logical grouping (they go with this application).
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
    1.  Application provider has selected licenses for the copyrightable
        artifacts originating with the project (package, files, etc)
    2.  Software being brought in for the application (if any) has SPDX
        documents decsribing the copyrigthable artifacts.
6.  **Main Success Scenario:** Application Provider communicates
    accurate and complete licensing information for all copyrightable
    artifacts in an SPDX data format.
7.  **Failed End Condition:** Application Provider communicates
    inaccurate and/or incomplete licensing information for their
    copyrightable artifacts, or does not describe the type of artifact
    or does not express that this is a logical grouping (is this really
    a failure if the type of artifact at a minimum is expressed?).
8.  **Trigger:**
    1.  Application release
    2.  Commit time?
    3.  Checkout from a repository?
    4.  Software being brought in from an external source
9.  **Notes:** It’s possible that some of the artifacts used by the
    application are in turn shared with other applications. For a single
    application this may not matter, but in the case of where many
    applications are aggregated together to form as an example an SDK
    then this is possible. Creating logical groupings and possibly even
    types of artifacts may involve manual intervention.

We should break down an application like this in the context of the 1.0
spec and really look at how it can be described and maybe how it
could/should be described. Here is an example to put the artifacts in
context:

![appusecase.jpg](appusecase.jpg "appusecase.jpg")

[Category:Technical](Category:Technical "wikilink")
