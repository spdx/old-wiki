1.  **Title:** Collecting enough information to allow auditor to make
    recommendations to remove or not a component
2.  **Primary Actor:** Auditor of open source code
3.  **Goal in Context:** To provide the consumer of the code audit
    sufficient information to make changes to the copyrighted materials
    in order to comply with the consumers policies regarding open source
    compliance.
4.  '''Stakeholders and Interests: '''
    1.  '''Consumer of the audit: '''
        1.  Organization which has an interest in the license
            obligations of the copyrighted materials
        2.  Will typically have policies (either formal or informal) on
            the use of open source
5.  **Preconditions:**
    1.  Access to souce code tree by auditor
6.  **Main Success Scenario:**
    1.  Source code is analyzed by the auditor and the origin for code
        and associated license is created
    2.  Policy violations are identified to the file (at least) level
    3.  Information on the audit is provided in an SPDX file +
        additional information (e.g. report) \[the additional, external
        report would for example be able to reference items in the SPDX
        file, and externally capture which company policy is being
        violated and how\]
    4.  Remediations are made to the source to comply with the policy
    5.  Source code is re-analyzed and an SPDX file describing the
        compliant code is produced
7.  **Failed End Condition:**
8.  **Trigger:**Audit
9.  **Notes:** A data element missing from SPDX 1.x which may be
    generally needed to establish policy violations is "Code Usage
    information (e.g. statically vs. dynamically linked)"
10. **Example:** Company has a policy not to deploy any GPL code
    compiled into their proprietary commercial software. Audit is
    performed to identify any GPL code and comply with the policy prior
    to a product release.

[Category:Technical](Category:Technical "wikilink")
