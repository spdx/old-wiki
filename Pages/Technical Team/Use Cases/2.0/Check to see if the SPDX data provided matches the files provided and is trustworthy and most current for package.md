1.  **Title:** Check to see if the SPDX data provided matches the files
    provided
2.  **Primary Actor:** Downstream consumer of a package
3.  **Goal in Context:** Verify that the license obligations for code
    provided by the upstream supplier matches the licensing information
    provided by the supplier
4.  **Stakeholders and Interests:**
    1.  '''Upstream Supplier: '''
        1.  Express the contents of the delivered software and the
            license obligations in a manner which can be easily verified
            by the consumer
    2.  **Downstream Consumer:**
        1.  Verify the files match the description provided
        2.  Verify the origin of the files match
        3.  Verify the license obligations match
        4.  Provide the verified information to further downstream
            consumers
5.  **Preconditions:**
    1.  Upstream provider provides an SPDX file along with the package
6.  **Main Success Scenario:**
    1.  Supplier provides package and SPDX file.
    2.  Consumer runs runs file checksums against received files and
        compares to the SPDX file to validate file origin.
    3.  Consumer compares SPDX author and reviewer information and
        compares to a "trusted" list of authors. Reviewer and supplier
        information is confirmed by verifying their signatures.
        (signing)
    4.  Consumer searches for any later revisions of the SPDX file which
        may contain corrections.
    5.  Consumer runs independent tools verifying information. If any
        corrections are required, an updated SPDX file is produced and
        sent back to the supplier for comment.
7.  **Failed End Condition:** No SPDX file provided. No signatures for
    author and/or reviewers. Internally inconsistent SPDX file.
8.  **Trigger:**
    1.  Delivery of a software package
9.  **Notes:**
    1.  The scenerio could work without an initial SPDX file if all of
        the information is provided in a different format. In this
        scenario, an SPDX file would be created as an output and the
        input pre-conditions would be essentially all of the required
        fields of the SPDX document.
    2.  Possibly related/required functionality: the ability to easily
        compute the differences between different SPDX documents about
        the same or slightly different packages. e.g. two different SPDX
        producers provide SPDX documents for package 'time'. If they are
        indeed for the same exact package / set of files, do they agree
        on the overall licensing and per-file licensing? If they are for
        slightly different packages (e.g. 'time' package version X vs.
        time package Y, which files are different from in each SPDX doc
        and which licensing has changed?

[Category:Technical](Category:Technical "wikilink")
