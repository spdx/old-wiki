As a software publisher in order to reduce my legal risk I want to
understand the obligations associated with my intended use of a software
package. I do not have the internal capabilities/capacity to determine
this information so i request a third party to analyze my entire
codebase to determine all rights holders and licenses for every file in
the codebase.

## Stackholders and Interests

  - **Developer**The organization developing (or in possession of) the
    code that wants to understand the licensing and rights holders of
    that code.
  - **Compliance office**The organization that is responsible for
    ensuring that the licensing of the code is complied with.
  - **Analyzer**Third party that need to analyze the codebase and inform
    the auditee of what the licensing is and who the rights holders are.

## Main Success Scenario

1.  Developers delivers code to analyzer
2.  Analyzer determines membership in sub-packages/components for each
    file.
3.  Analyzer imports/embeds existing SPDX data for
    sub-packages/components.
4.  Analyzer extracts licensing and copyright information from remaining
    files.
5.  Analyzer determines the following for every remaining file in code
    base:
      - Rights holders
      - Licensing terms
6.  Analyzer provides above data to Compliance office.
7.  Compliance office looks at concluded licensing and right holder and
    take any necessary actions to comply with the licenses

## Alternate Scenario A

1.  Developers delivers code to analyzer
2.  Analyzer determines membership in sub-packages/components for each
    file.
3.  Analyzer imports/embeds existing SPDX data for
    sub-packages/components.
4.  Analyzer extracts licensing and copyright information from remaining
    files.
5.  Analyzer determines the following for every remaining file in code
    base:
      - Rights holders
      - Licensing terms
6.  Analyzer provides above data to Compliance office.
7.  Compliance office looks at concluded licensing and right holder and
    determines that certain sub-packages/components are unacceptable.
8.  Developer removes the offending sub-components.
9.  Developer delivers modified code to analyzer.
10. Analyzer redoes analysis (consider: not redo from scratch but
    re-using results of the earlier SPDX data) and provide new SPDX data
    to Compliance office.
11. Compliance office looks at concluded licensing and right holder and
    take any necessary actions to comply with the licenses

## A failure scenario

Failed scenario if the third party auditor cannot take advantage of
existing SPDX data about external packages/components in producing the
SPDX data for the analyzed code which re-uses those external
packages/components.

[Category:Technical](Category:Technical "wikilink")
