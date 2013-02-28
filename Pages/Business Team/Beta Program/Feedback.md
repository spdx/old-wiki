Beta Feedback Meeting 7/7/2011

## Attendees

  - Kim Weins, OpenLogic
  - Nicholas, Protecode
  - Mark Gisi, Wind River
  - Kirsten Newcomer, Black Duck
  - Bill Schineller, Balck Duck
  - Phil Koltun, Kinux Foundation
  - Scott Lamons, HP
  - Peter Williams, OpenLogic
  - Gary O'Neall, Source Auditor
  - Phil Odence, Black Duck
  - Guillaume Rousseau, Antelilnk
  - Freddy Munoz, Antelink
  - Pierre Lapointe, nexB
  - Jilyane Lovejoy, OpenLogic
  - Steve Cropper, Cisco
  - Philippe, Antelink

## HP - Scott Lamons

**How well did the SPDX format cover information you need to exchange?**

The most useful part for our review process is the higher level package
information because we require product/project teams to enter
information into our tracking system about the open source package they
are using/distributing -- often these teams make mistakes or enter
incomplete information. SPDX potentially provides a better and more
trustworthy way for teams to enter this information into our system.

**What was effort involved in converting to/from SPDX format?**

Very straight forward using the tools that Gary provided although it
might be helpful to have a GUI based tool for non-expert users. We did
encounter a few bugs but I believe these have since been corrected.

**Did the SPDX format help you understand what was in the software?**

Yes, the spreadsheet format is well organized and easy to follow.'''

**How did the standard license information work for you?**

**Can you see how using SPDX could save your organization time/money?**

**Are any changes needed to make SPDX meet your needs?**

Separate package name and version fields would be helpful. Combining
name and version into the PackageName field will require additional
processing and interpretation which we would rather not do since our
system has seperate fields for FOSS name and version.

Some corrections and comments in the specification are attached in MS
Word format.

Issue: Spearate package name and version fields

  - Several people want this
  - Should be a Must-Do for 1.0
  - Version should be optional or allow for an "Unknown"

Issue: Confusion/Disagreement over package level licenses - what they
mean, how they should be used, what's important

  - Still confusion over which license fields are valuable and how
  - Scott L - He sees value of Declared and Licenses in File. Not sure
    about Concluded
  - Mark G - He uses the concept of an "aasociated" license -- what the
    community thinks
  - We need to make this a Must-Do for 1.0.

Issue: Time it takes to do the analysis

  - Mark G - Had to be more careful with analysis because he knew that
    there would be more eyeballs on the results
  - Scott L -- uses package level data more. file by file is useful, but
    package is more important.
  - Mark G. - to really get it right, you have to go down to the file
    level

## Antelink -- Freddy Munoz

1.  **How well did the SPDX format cover information you need to
    exchange?** The format provides reliable information about licenses
    (based on human analysis) and the distinction between the licences
    who are declared by the package creator and those which are found in
    files.
2.  **What was effort involved in converting to/from SPDX format?** The
    conversion from the SPDX file format to an object model was easily
    made.
3.  **Did the SPDX format help you understand what was in the
    software?** The SPDX file format gives declarative fine scale
    information about the licenses and the origin of each file in the
    package.
4.  **How did the standard license information work for you?** For us
    the standard license information is very important because is much
    more precise and reliable than a simple declaration of the licence's
    name with no standard formatting.
5.  **Can you see how using SPDX could save your organization
    time/money?** When we collect information about open source
    projects, it would be easier to parse information if the licence
    information were completely machine readable. SPDX format provides
    this feature.
6.  **Are any changes needed to make SPDX meet your needs?** If any
    file's licence cannot be defined ("none") it would be better if the
    format allowed to use "none" as one of concluded licenses. It's
    necessary to impose every concluded license to be the concluded
    license of at least one file, otherwise some licenses could be
    considered as concluded licenses of the package but we cannot know
    from which file (component) they come from.

<!-- end list -->

  - Was pretty happy with the format
  - Some concern with different types of licenses - Global license might
    be overridden by file level license
  - If conclusion at file leve is that you are not able to determine a
    license, how can you create a package level info.
  - If you have a match against source code, should that go into
    concluded license.
  - Discussion about "no assertion" vs "none" and what they mean.
  - Must-do for 1.0 -- provide guidelines about when to use none vs
    no-assertion at file level licenses
  - Must-do for 1.0 -- provide guidelines on concluded license at file
    level vis a vis source code matches
  - Few artifacts of were tagged.

Additional issues:

  - Issue of standardization on package names

[Category:Business](Category:Business "wikilink")
[Category:Archived](Category:Archived "wikilink")
