1.  **Title:** Consuming Code Snippets
2.  **Primary Actor:** Committer / submitter of code to either an open
    source project or a commercial product
3.  **Goal in Context:** To include small amounts of code with implement
    specific functionality or algorithms developed by the open source
    community
4.  '''Stakeholders and Interests: '''
    1.  '''Committers to the open source project: '''
        1.  Leverage pre-existing algorithms or functionality (e.g. MD5
            Hash Algorithm) within a license compatible with the open
            source license
    2.  **Submitter to a commercial product:**
        1.  Leverage pre-existing algorithms or functionality (e.g. MD5
            Hash Algorithm) within a license compatible with the
            commercial license
    3.  **Downstream consumers of the resultant software:**
        1.  Adhere to the license obligations of the code snippet
    4.  **Legal/compliance for the consuming organization:**
        1.  Adhere to the license obligations of the code snippet
5.  **Preconditions:**
    1.  Open source project containing code snippet is
        available/accessible
    2.  Licensing for the project containing the code snippet is
        available or the author can be contacted for permission to use
6.  **Main Success Scenario:** Given that a snippet within a file
    (subset of file) is determined to have originated from somewhere
    else under some license, licensing information is included in the
    SPDX file provided with the source code product along with
    information on the location of the code snippet. Downstream consumer
    aggregate the license information from the Snippet with the license
    information from the rest of the package(s) to determine the full
    obligations. (Regardless of whether the snippet includes comments
    indicating the origin of the code snippets.)
7.  **Failed End Condition:**
    1.  Committer / submitter does not indicate the inclusion of the
        code snippet
    2.  Originator of the code snippet does not provide adequate
        licensing information
    3.  If insufficient info to determine if a conflict exists between
        the license used for the code snippet and the license for the
        large component
8.  **Trigger:**
    1.  Development of code
9.  **Example:** A file implementing a verification algorithm specific
    to a package needs to implement an hash algorithm in a compatible
    manner to another open source project. The code implementing the
    hash is copied into the source file which implements the
    verification algorithm.

[Category:Technical](Category:Technical "wikilink")
