This is the working area for the technical and legal teams. The focus of
this effort is for recording ideas and considerations about improving
machine detection and recognition of licenses and headers in code.

## Key Links

  - Bugzilla bug 1302, which started this particular conversation:
    <https://bugs.linuxfoundation.org/show_bug.cgi?id=1302>
  - Meeting minutes from Aug 6, 2015 Legal call:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-08-06>
  - Matching Guidelines:
    <http://spdx.org/spdx-license-list/matching-guidelines>
  - Pull Request Proposal for SPDX License List (Gary):
    <https://docs.google.com/document/d/115Lis1SJV7Rp-XuNjIysU61urzFGjUOBPqEdVyGLsfI/edit>
  - Meeting minutes from Oct 29, 2015 Legal call:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-10-29>
  - Initial proposal, full write-up (Kris):
    <http://wiki.spdx.org/view/Legal_Team/Template_proposal>
  - Meeting minute from Feb 9 joint tech/legal call:
    <http://wiki.spdx.org/view/Technical_Team/Minutes/2016-02-09>
  - Meeting minutes from Feb 18 legal call:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2016-02-18>
  - Proposal for exact tag names and edits to matching guidelines:
    <http://wiki.spdx.org/view/Legal_Team/Templatizing/tags-matching>
  - **Plan for review of XML license files:**
    <http://wiki.spdx.org/view/Legal_Team/Templatizing/ReviewXML>
  - Action plan for whole project:
    <http://wiki.spdx.org/view/Legal_Team/Templatizing/ActionPlan>
  - XML tags naming discussion:
      - link to Oct 26 joint tech/legal team meeting minutes:
        <http://wiki.spdx.org/view/Technical_Team/Minutes/2016-10-25>
      - The working document is available at
        <https://docs.google.com/document/d/1z9n44xLH2MxT576KS_AbTOBtecyl5cw6RsrrQHibQtg>
  - Link to XML conversion tool Kris wrote for initial conversion:
    <https://github.com/myndzi/license-tool>
  - Kris' tool for seeing XML conversion:
    <http://krisreeves.com/xmledit/>
  - XML validator: <https://www.w3schools.com/xml/xml_validator.asp>

## Background

(from JL) The current Matching Guidelines and license markup was
developed over the past several years. While the guidelines were
relatively easier to come up with, how much markup to use and how to
implement it was an on-going discussion of much debate. As relevant to
the proposals here, the discussion around how much markup to use
recognized that more markup would increase consistent results by
reducing the need for tool makers to interpret the guidelines. However,
due to the amount of work of potentially having markup on every license
file, a more conservative approach was taken with the recognition that
we could always add more markup over time (but taking it away would be
harder).

The template language was a result of a collaboration between members of
the legal and technical teams. The goal of the template was developed
with the following goals in mind:

  - Enable both humans and, to a lesser extent, tools to be able to
    determine if two license texts were equivalent.
  - Preserve the original language of the license text.
  - Leverage existing annotations and tools (e.g. the use of regular
    expressions to denote matches to variable text).

The current templating language is documented in Appendix II of the
specification (http://spdx.org/sites/spdx/files/SPDX-2.0.pdf)

  - Please review the current Matching Guidelines here:
    <http://spdx.org/spdx-license-list/matching-guidelines>
  - Also see Bugzilla bug 1302, which started this particular
    conversation:
    <https://bugs.linuxfoundation.org/show_bug.cgi?id=1302>
  - Meeting minutes from Aug 6, 2015 Legal call:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-08-06>

## Proposal

(from Gary) As a result of the initial bug 1302 discussion, Gary
suggested to enable pull requests to be made against the SPDX License
List, which would encourage contributions to markup by others. Such pull
requests/contributions would be moderated by the Legal team (especially
regarding determinations of markup and potential impact on legal
interpretation of the license) with help from the Tech team as needed.
Everyone on the Aug 6 legal call agreed this would be a great approach.
Gary, Jilayne, Kate have begun to discuss how to implement this. A
process also needs to be outlined for how pull requests will be handled,
etc. A rough draft process proposal can be found in the google document
<https://docs.google.com/document/d/115Lis1SJV7Rp-XuNjIysU61urzFGjUOBPqEdVyGLsfI/edit?usp=sharing>

(from Kris) Things that would improve working with the data
programmatically:

  - Get away from spreadsheets as the index for the licenses. Use JSON
    or XML (leaning towards XML to keep the toolset the same as markup
    parsing). A tool to compile the spreadsheet (for humans to work
    with) down to an XML file would probably work.
  - Put all information about a license in the same place for each
    license (headers, addons/exceptions/whatever). Likely within markup
    within the license files themselves.
  - Use XML or some other widespread format for the markup. This ensures
    there are tools available to work with the data in any language
    without having to write custom parsing tools or use tools tied to a
    specific platform because they're the only ones that exist.
  - As, and if, the data moves towards a more markup-heavy format, it
    might be wise to simply include the full text verbatim in its own
    section rather than "recreate" it from marked up data.

An example of what a more normalized (to xml) data set might look like:

index.xml:

` `<licenses>  
`   `<license identifier="Apache-2.0" file="Apache-2.0.xml">`Apache License 2.0`</license>  
`   ...`  
` `</licenses>

LGPL-2.0.xml:

` `<license>  
`   `<original>`...full original text content...`</original>  
`   `<template>  
`     `

<header>

...Licensed under the Apache License, version 2.0, etc....

</header>

<body>

Some text blah blah <match regex="foo|bar"/> more text

</body>

`   `</template>  
` `</license>

An alternative:

` `<template>  
`   `

<header>

....etc

</header>

<body>

...THE SOFTWARE IS PROVIDED "AS IS" AND
<alt regex="THE AUTHOR">ISC</match> DISCLAIMS ALL WARRANTIES...

</body>

` `</template>

The above carries the useful property that the text content of the body
tag is the original source without any modification; processing can
instead replace "alt" tag contents with their regex attribute to
"convert" to a matchable format.

I don't actually like XML, but it seems to be a good fit for this
purpose. It helps keep the intrusiveness of the markup into the license
text focused and to a minimum, lets us wrap entire sections as optional,
keep the canonical original text if desired, and specify alternate
license formats such as the short-form license header and any desired
metadata all in one place. And there are tools to read XML in every
language.

I recommend that the template content be \*without\* the parts that the
matching guidelines say to ignore, and preferably it should have
normalized or marked up bullets, etc. Best of all would be, simply,
normalized text content in a full regular expression that can be used to
match directly, rather than a bunch of markup that must be turned into a
regular expression -- but I think this would make maintenance much
harder. Again, a compilation step could help. There's a lot of work to
be done here that can be qualified as preprocessing, and there's no
reason we can't make sure the preprocessing is "done right" and publish
the results, instead of requiring programmers to reimplement their own
version of the preprocessing with uncertain results.

A particular note about normalizing text: Bullet items are one of the
problematic points for parsing because it can be troublesome to
distinguish a bullet point like "ii." from the end of a sentence that
got wrapped to the start of the next line. (I actually encountered this
in my testing; a saving grace is that the bullets tend to be things that
are hard to confuse for words, but it's really easy to write a regular
expression that isn't that smart.)

For what it's worth, I'm quite happy to contribute when it comes to
tooling; I already have code to do the most of this anyway. -Kris

## Detailed proposal

See:
[Legal\_Team/Template\_proposal](Legal_Team/Template_proposal "wikilink")

## Use and Feedback re: Current Markup

Feedback was solicited on the legal and tech mailing lists to this end:

We have a task to add markup to some of the standard headers and have
also had input to add/edit markup on existing licenses. As a result of
the latter, it has been raised that perhaps the markup could be
improved. Before adding more markup (to standard headers, license text
or both), it seemed prudent to start a discussion as to whether the
existing markup is effective. Please ponder the following questions:

`   a) have you used the existing markup for matching purposes?`  
`       i) if no, why not?`  
`       ii) if yes, has it been helpful/effective?  Could it be improved, and if so, how? (this will likely involve putting forward a proposal for review)`

Please record your input in a section here, by name or tool or both:

### Gary O'Neall

For the SourceAuditor commercial tools, the markup is used to validate
that 2 licenses are equivalent per the matching guidelines. The open
source SPDX tools uses the markup is used in a number of ways. The
"compareSpdx" and "compareMultipleSpdx" commands use the markup to
determine if the licenses are equivalent. There are library methods
implemented to compare license text and report if the license text
matches any of the SPDX LicenseList.

In all cases above, the markup is used to compare 2 existing known
license text. It is NOT used to match license text against a library of
possible license matches. In the commercial tool, a separate algorithm
implements this functionality and the markup language turned out to be
too inefficient for this purpose - at least for the performance
requirements of our application.

Note: When we originally discussed the markup language, we debated
whether to cover the use case of searching a library of possible license
matches and the decision was taken not to support this.

In my opinion, the markup works fine for matching two license texts. If
we wanted to support a searching use case, we would need to
modify/extend the markup language to enable this to be efficient.

Performance would be greatly improved if we bounded the RE's. Something
which is within the spec, but is not implemented in the templates. I
would support implementing bounding all RE's in an upcoming release and
changing the spec to encourage bounding. I think we could pick a pretty
practical upper bound that would improve the performance.

Also note - this is more of an issue with the "matching against a
library of licenses" issue than simply comparing two license texts since
the former is more performance sensitive.

### Sam Ellis

I will share a few points from my experience in templatization. I
currently use a different templatization syntax that predates SPDX, but
the principle of using regular expressions embedded within the license
text is similar.

The major barrier to me adopting the SPDX templates is insufficient
templatization within the existing licenses. The SPDX templates
currently encode what I perceive to be the ‘official’ variations, i.e.
organization name, person name, product name etc. However, real-world
licenses contain may minor variations that may be inconsequential from a
legal perspective, but nonetheless do not warrant separating out as
separate licenses. Here is an example from the GPL-3.0 notice where it
is common to see two variations in one of the sentences:

distributed in the hope that it will be useful distributed in the hope
that they will be useful

The example above is fairly uncontroversial, I would hope. However,
there are plenty of other examples that border on having a legal impact.
For example, in these two BSD-2-Clause variations it is necessary to
consider whether the additional word constitutes an acceptable minor
variation or warrants a different classification altogether:

Redistributions of source code must retain the above copyright notice,
this list of… Redistributions of source code must retain the above
copyright notice unmodified, this list of…

It is the grey cases like these that make expanding the use of
templating difficult. Inevitably it leads to having to make some
judgements about the impact of a particular word or phrase on the legal
interpretation, something that I am aware SPDX tries to avoid.

Whether it is worth templating all the cases like these primarily
depends on the goals of the SPDX templates. If they are for human use to
see what official variations are permitted, then they are not necessary.
On the other hand, if they are to be used by automated license scanning
tools, then covering these cases is essential in order to have a tool
that works effectively on real-world code. So I think an important point
is to gain clarity on the purpose of the templates.

In terms of the current application of the templates, I have a technical
concern over the use of unbounded regular expressions, for example:

\<\<var;name=copyrightHolderAsIs;original=THE COPYRIGHT HOLDERS AND
CONTRIBUTORS;match=.+\>\>

This is unbounded because it will match any number of characters for the
copyrightHolderAsIs field. The practical consequence of this is that
regular expression matching can explode in terms of time. I don’t have a
concrete example to hand, but my own experience with using the same
unbounded regular expressions on real-world licenses is that I have seen
it take minutes just to process one regular expression on a single file,
and this does not scale well when there are millions of files to
process. Clearly, in terms of English language there is no maximum size
on the length of a copyright statement. Using an unbounded regular
expression is therefore correct in theory but difficult to use in
practice. I have had to use size bounded regular expressions in order to
have a scanning tool that will complete in a reasonable time. The
problem in switching to bounded regular expressions is in deciding on
what is an acceptable upper bound on the size, and this can really only
be judged by experimentation against real-world licenses, and does then
require on-going tweaking as new license variations are discovered.

Neither of these are problems with templatization per-se, and they are
more to do with the extent and way in which they are currently applied.

### Philippe Ombredanne

a) have you used the existing markup for matching purposes?

Yes and No: ScanCode uses an SPDX-inspired/derived markup, but instead
of reusing the markup directly from the main license texts, markup is
transformed in a simpler  syntax added to copies of these texts used
only for detection purpose.

Because: - adding more markup to a reference license text makes this
eventually no longer usable as a reference text and harder to read by
humans - the many variations found in the wild make it hard to put all
in a single template. - the markup syntax implies eventually an
implementation using regular expressions. ScanCode does not use regex,
but inverted indexes and string alignments.

ii) if yes, has it been helpful/effective? Could it be improved, and if
so, how? (this will likely involve putting forward a proposal for
review)

I think a simple markup is a very effective way to detect licenses with
minor text variations and still call this an exact match. It is also a
very effective way to indicate variations for humans. I find it hard
personally to mix the human readability and technical detection concerns
in the same file without compromises.

As food for thought, here are some examples of markup as used in
ScanCode:

<https://github.com/nexB/scancode-toolkit/blob/b37be4de78152fbd3ed54761627c960010ce26a3/src/licensedcode/data/rules/apache-1.1_38.RULE#L17>
<https://github.com/nexB/scancode-toolkit/blob/b37be4de78152fbd3ed54761627c960010ce26a3/src/licensedcode/data/rules/bzip2-libbzip-1.0.5_1.RULE#L1>

The syntax is using double curly braces to enclose variable parts. There
is no regex involved. Optionally a number can be used after the opening
braces to indicate the number of variable words, defaulting to 5 words.
For instance {{ Copyright (c) 2015 Myco }} would match up to 5 words and
{{ 10 Copyright (c) 2015 Myco inc.}} would match up to 10 words.

I hope this helps even though this is a slightly different take.

### Bill Schnineller

`          a) have you used the existing markup for matching purposes?`

No.

`                       i) if no, why not?`

In a nutshell, partly due to timing of our dev efforts ahead of SPDX
templatization rollout, partly due to performance in context of our
internal Use Case of scanning every single open source file (not just a
handful of applications).

Details: Black Duck has a corpus of license variants extracted from our
Knowledge Base of around half a billion unique open source source/text
and binary files. Several years ago, prior to SPDX license
templatization, we went through multiple iterations of grouping license
text variants, as well as license name/nickname variants. Our groupings
were based on applying similarity algorithms, followed by human review.
Our methodology has been in place for some time prior to the templates /
regular expressions subsequently rolled out by SPDX.

Variations we've encountered, such as the street address of an
organization, or typos / word substitutions that SPDX license templates
might not have covered are some of the reasons we haven't yet gone
through the exercise to see which license variants the SPDX templates
might not 'match' to the license id's we've grouped them under.

We use our license scanner to scan (and rescan) every single open source
file to populate our Knowledgebase of file-level license data. Our
scanner uses multiple techniques to discover license references, but
does not use regular expressions because of performance concerns.

Because Black Duck does not provide legal advice, consumers of our tools
are able review the license text which our tools highlight in order to
make a final determination. This fits well with the SPDX concept of
separating discovered and concluded information.

Outlook: SPDX license templates / regexes aren't as useful or efficient
as other matching techniques we have, when automatically bulk scanning
large codebases to determine ‘LicenseFoundInFile'.

But when a human is in the loop producing a final SPDX Document with
Concluded License, SPDX license templates / regexes could be useful to
focus legal review on deviations which may or may not be significant.

### Nuno Brito

`a) have you used the existing markup for matching purposes?`  
`  i) if no, why not?`

Didn't use the markup. At the time haven't found documented the pattern
keywords to find inside each license term. For example, one can find
\[xxxx\]-\[xxxx\], \[Owner Organization\], <AUTHOR>. However, didn't
seemed to be used consistently throughout the list of licenses. That was
my opinion at that time, might certainly be proven erroneous.

If help is welcome, I can volunteer for normalizing the data for the
complete list (top to bottom) and document the used keywords. However,
for our own tooling usage as template I'd replace the text on some
specific license terms so that we could later generate new licence docs
where only the copyright holder changes.

Such example would be
<http://spdx.org/licenses/BSD-3-Clause-Attribution.html> where:
"Universidad de Palermo, Argentina" (http://www.palermo.edu/).'" becomes
"<AUTHOR>".

### Kris Reeves

I have been thinking about the proposed format in detail, and it has
become clear to me that it will be undesirable to attempt to maintain a
canonical single source of truth in the format we would want to expose
to consumers. This is made clearest by the synonym matching rule: it is
unfeasible to ask or expect a person editing a license file to find,
identify, and mark up all candidates for synonym replacement. It is,
however, easily possible to expose data that has been thus marked-up to
consumers of the SPDX data. This implies that there must be a build step
of some sort in the mix.

Given that there would be a build step, the case for altering the source
markup is weakened somewhat; it's not strictly \*necessary\* to support
(my) goal of providing data that can be consumed directly without any
programmatic logic required to match a license, but still retains a
number of benefits including: utility in editing/managing the license
content itself, ease of integration into tooling required to produce the
"built" product, ready extension, familiarity to newcomers/potential
contributors, and even brevity.

Given the above, there are really two classes of markup to consider:

1\) Markup used to clarify / identify information that is obvious to a
human but difficult for a computer to interpret (for example:
identifying bullet points)

2\) Markup used to provide more robust matching that is easy for a
computer to generate but difficult for a human to maintain (for example:
identifying synonymous word spellings)

The most useful focus for markup in the first category is ease of use by
a human editor: it should be unobtrusive and succinct, lending to ready
interpretation by a reader/editor of the license text in a
legal-meaningful way and imposing a minimum of technical knowledge for
correct and confident interpretation.

The most useful focus for markup in the second category is ease of
consumption by a program: it should be thorough and explicit, lending to
immediately useful applications with little to no business logic
required in the consuming code.

I'm working on the proposal discussed in the last legal call, but
splitting it into two parts by these guidelines. This approach feels a
bit messy to me, but I see no way around it other than to write custom
tooling that can abstract the category-2 markup away from a human and
let them work in terms of category-1 markup.

### Compatibility with Current Markup

If we do change the format in a way which is incompatible with the
existing markup, we may break existing applications. I originally did
not think this would be much of an issue based on the responses above,
but then I ran across the comment
<https://github.com/sindresorhus/spdx-license-list/issues/6#issuecomment-150606727>
where the existing syntax is used to extract the license text. There may
be other such applications that we are not aware of. -- Gary O'Neall

This is actually a point in favor of going ahead: if people are writing
regular expressions to parse the current data, that is happening because
the tools to do it properly aren't available to them. Markup change
would obviously be a major version bump, so tools such as the above
would still work and continue to function on the v2.0 data. New/updated
tools, however, would become less fragile by virtue of using parsing
tools that know how to deal with XML, and the markup itself can thus be
extended to incorporate new needs without breaking existing fragile
regular expressions. -- Kris

## Markup to add/consider

\[JL\] This is simply a list of various specific licenses that may need
additional markup or things to consider related to the matching
guidelines, to ensure we don't forget to add/edit later\!

  - Apache-2.0 - instructions as to how to apply license, markup as
    optional? (from Kris)
  - MIT - "THE AUTHORS OR COPYRIGHT HOLDERS" - markup to be variable
    (from DMG's student paper)
  - add "noninfringment" and "non-infringement" and "non infringement"
    as equivalent words in Matching Guideline \#8 list of words (from
    DMG's student paper)
  - add "contributors" and "co-contributors" and "co contributors" as
    equivalent words in Matching Guideline \#8 list of words, needs some
    discussion (from DMG's student paper)
  - ISC license needs markup (and link fixed)

[Category:Technical](Category:Technical "wikilink")
[Category:Legal](Category:Legal "wikilink")
