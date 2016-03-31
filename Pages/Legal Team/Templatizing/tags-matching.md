## SPDX License List Matching Guidelines and tag name

### XML templatizing tag values and nesting rules

The general structure of the MASTER xml files (located in /src) is as
follows:

`  `  
`<SPDX name="full name" identifier="SPDX short identifier" osi-approved="true/false">`  
`  <urls>`  
`    <url>URL for license</url>`  
`    <url>additional URL for license</url>`  
`  </urls>`  
`  <notes>notes on license, if any</notes>`  
`  <header>standard license header, if any</header>`  
`  <license>`  
`    <title>license name or title (Guideline 10) </title>`  
`    <copyright>Copyright notice (Guideline 9) </copyright>`  
`    <body> Substantive text of license - most matching guidelines apply here`  
`      <list>`  
`        <li><b>a bullet (Guideline 7) </b>text of the list item</li>`  
`      </list>`  
`      <p>some more text</p> `  
`    </body>   `  
`    <optional>some text that is omitable (Guideline 2) </optional>`  
`  </license>`  
`</SPDX>`

The tags are defined as follows:

  - SPDX tag: root element tag; has attributed to specify full license
    name, short identifier, and OSI-approved (if the license is OSI
    approved, this field/tag will indicate "yes", otherwise, left blank)
    \[Equivalent property names in the published format: licenseId,
    isOsiApproved, name\]
  - URLs/URL tag: each url for the official text of the license or
    exception \[Note: This is the seeAlso tag in the published format\]
  - Notes tag: factual info about the license, e.g. date of release,
    license has been deprecated, links to official translations \[Note:
    this is the comment tag in the published format\]
  - Header tag: the short form of a license that references the full
    license text. This is a separate entity, not a part of the license
    proper \[Note: this is the standardLicenseHeader tag in the
    published fromat\]
  - License tag: the root element that contains the license data \[Same
    tag name as the published format\]
  - Title tag: denotes an optional (as per Matching Guideline 10)
    section of the license content, with the implication that it
    contains the title/heading content that prefaces the substantive
    text \[There is no equivalent tag in the published format - suggest
    title, lower case to be consistent with Dublin Core spec\]
  - Copyright tag: denotes an optional (as per Matching Guideline 9)
    section of the license content, with the implication that it
    contains copyright notices \*that apply to the code under license\*;
    this is explicitly \*not\* intended to include copyright notices
    that apply to the license itself
  - Body tag: substantive text of the license itself \[There is no
    equivalent tag in the published format, there is copyrightText
    property name used in other parts of the spec\]
  - B tag: denotes a bullet or section marker whose style and formatting
    is unimportant to the substantive content of the license text as per
    Matching Guideline 7 \[There is no equivalent tag in the published
    fomart - B is fine\]
  - Optional tag: denotes otherwise optional (as per Matching Guildeline
    2) text content, such as appendices explaining how to use a license
    and/or defining the license's header form \[This is OK - could
    translate to beginOptional/endOptional\]
  - alt tag: denotes a small portion of the text that is specific to the
    content being licensed, such as the name of the copyright holder.
    The "name" attribute can be ignored for matching purposes, but if
    present should specify a unique identifier that the actual matched
    content (when a template is applied to some target text for
    matching) should be stored in. The "match" attribute specifies a
    regular expression that governs what text is suitable/allowed to
    match in lieu of the original text content \[Currently, this is
    "var", but alt should be OK\]

The general structure of the MATCHING FORMAT (output/build product) xml
files (not yet produced) is as follows:

`  `  
`<license name="Full license name" identifier="Identifier">`  
`  <header>Header version of license</header>`  
`  <body>`  
`    <title>Optional title text</title>`  
`    <copyright>Copyright notice</copyright>`  
`    Substantive license text`  
`    <b>bullet</b> more text...`  
`    Sometimes the text will include <alt name="foo" match="bar">original text</alt>`  
`    The only difference between the master xml file and the matching format xml files is the <syn identifier="synonym">synonym</syn> tag.`  
`    <optional>Other optional text such as appendices</optional>`  
`  </body>`  
`</license>`

This format is almost identical to the master files, with the exception
that synonyms are automatically identified and marked as part of a build
process. This allows a separate list of valid synonyms to be maintained
and referenced without needing to find and mark all synonyms by hand or
change every xml file if the synonym list in altered.

  - syn tag: denotes meaningful substantive text that may have
    variations in spelling (regional or otherwise), for which alternate
    spellings are valid and have identical meaning. A separate file
    should be curated that lists all applicable synonyms. The
    "identifier" attribute specifies which set of synonymous words may
    match, and the tag wraps the original text as given in the license
    proper.

### Specific use cases

Display the original text content of the license: extract the inner text
content of the \<body\> tag, stripping all XML.

Display the substantive license text of the license: extract the inner
text content of the \<body\> tag, removing all optional tag sections.

Generate a regular expression to be used for identifying a license:
within the body tag, replace all instances of the \<b\< tag with a
suitable regular expression to match bullets. Replace all instances of
the \<alt\> tag with the regular expression specified by the "match"
attribute. Replace all instances of the \<syn\> tag with a regular
expression that matches only the allowed set of synonyms. Flatten
whitespace and match case-insensitively. Target text will also need to
be normalized by flattening whitespace. Alternately, make the regular
expression all lowercase, and normalize all target text to lowercase.

License header text should be matched separately/independently of the
license body.

### SPDX License List Matching Guidelines (draft revisions)

<strong>SPDX License List Matching Guidelines, v2.0</strong>

This document provides guidelines to be used for the purposes of
matching licenses and license exceptions against those included on the
SPDX License List. There is no intent here to make a judgment or
interpretation, but merely to ensure that when one SPDX user identifies
a license as "BSD 3-clause," for example, it is indeed the same license
as what someone else identifies as "BSD 3-clause" and the same license
as what is listed on the SPDX License List. Examples of how to apply
some of the matching guidelines to a license or exception are provided
via templates.  Templates are comprised of technical markup within the
master license text file to provide further or specific guidance to SPDX
document creators or tool makers.  Not all licenses or exceptions will
have templates.

<strong>1. How These Guidelines Are Applied</strong>

<span style="text-decoration: underline;">1.1 Purpose:</span>  To ensure
consistent results by different SPDX document creators when matching
license information that will be included in the License Information in
File field. SPDX document creators or tools may match on the license or
exception text itself, the official license header, or the SPDX License
List short identifier.

<span style="text-decoration: underline;">1.1.1 Guideline: Official
License Headers</span>  The same matching guidelines used for license
and exception text apply to the official license headers. Where
applicable, an official license header template file with markup is
included with the SPDX License List. Official license headers are
defined by the SPDX License List as specific text specified within the
license itself to be put in the header of files. (see
<a href="http://spdx.org/spdx-license-list/license-list-overview"><http://spdx.org/spdx-license-list/license-list-overview></a>
for more info).

<strong>2. Substantive Text</strong>

<span style="text-decoration: underline;">2.1 Purpose:</span>  To ensure
that when matching licenses and exceptions to the SPDX License List,
there is an appropriate balance between matching against the substantive
text and disregarding parts of the text that do not alter the
substantive text. Further guidelines of what can be disregarded or
considered replaceable for purposes of matching are listed below here
and in the subsequent specific guidelines. A conservative approach is
taken in regards to rules about disregarded or replaceable text.

<span style="text-decoration: underline;">2.1.1 Guideline:  Verbatim
Text</span>  License and exception text should be the same verbatim text
(except for the guidelines stated here). The text should be in the same
order, e.g., differently ordered paragraphs would not be considered a
match.

<span style="text-decoration: underline;">2.1.2 Guideline:   No
Additional Text </span>Matched text should only include that found in
the vetted license or exception text. Where a license or exception found
includes additional text or clauses, this should not be considered a
match.

<span style="text-decoration: underline;">2.1.3 Guideline:  Replaceable
Text</span>  Some licenses include text that refers to the specific
copyright holder or author, yet the rest of the license is exactly the
same as a generic version. The intent here is to avoid the inclusion of
a specific name in one part of the license resulting in a non-match
where the license is otherwise an exact match (e.g., the third clause
and disclaimer in the BSD licenses, or the third, fourth, and fifth
clauses of Apache 1.1). In these cases, there should be a positive
license match.

Text that can be considered replaceable for matching purposes is
indicated in the SPDX License List template with mark-up and in the
corresponding HTML pages with colored text. The text indicated as such
can be replaced with similar values (e.g., a different name or generic
term; different date) and still be considered a positive match. This
rule also applies to text-matching in official license headers (see
Guideline \#1).

<span style="text-decoration: underline;">2.1.4 Guideline:  Omitable
Text</span>  Some licenses have text that can simply be ignored. The
intent here is to avoid the inclusion of certain text that is
superfluous or irrelevant in regards to the substantive license text
resulting in a non-match where the license is otherwise an exact match
(e.g., directions on how to apply the license or other similar
non-substantive exhibits). In these cases, there should be a positive
license match.

Text that can be considered omitable for matching purposes is indicated
in the SPDX License List template with mark-up and in the corresponding
HTML pages with colored text. The license should be considered a match
if the text indicated is present and matches OR the text indicated is
missing altogether.

<strong>3. Whitespace</strong>

<span style="text-decoration: underline;">3.1 Purpose:</span>   To avoid
the possibility of a non-match due to different spacing of words, line
breaks, or paragraphs.

<span style="text-decoration: underline;">3.1.1 Guideline:</span>  All
whitespace should be treated as a single blank space. Templates do not
include markup for this guideline.

<strong>4. Capitalization</strong>

<span style="text-decoration: underline;">4.1 Purpose:</span>  To avoid
the possibility of a non-match due to lower case or upper case letters
in otherwise the same words.

<span style="text-decoration: underline;">4.1.1 Guideline:</span>  All
upper case and lower case letters should be treated as lower case
letters<em>. </em>Templates do not include markup for this guideline.

<strong>5. Punctuation</strong>

<span style="text-decoration: underline;">5.1 Purpose:</span>  Because
punctuation can change the meaning of a sentence, punctuation needs to
be included in the matching process. License template files do not
include markup for this guideline.

<span style="text-decoration: underline;">5.1.1 Guideline: 
Punctuation</span>  Punctuation should be matched, unless otherwise
stated in these guidelines.

<span style="text-decoration: underline;">5.1.2 Guideline:  Hyphens,
Dashes</span>  Any hyphen, dash, en dash, em dash, or other variation
should be considered equivalent.

<span style="text-decoration: underline;">5.1.3 Guideline: 
Quotes</span>  Any variation of quotations (single, double, curly, etc.)
should be considered equivalent.

<strong>6. Code Comment Indicators</strong>

<span style="text-decoration: underline;">6.1 Purpose:</span>  To avoid
the possibility of a non-match due to the existence or absence of code
comment indicators placed within the license text, e.g. at the start of
each line of text.

<span style="text-decoration: underline;">6.1.1 Guideline:</span>  Any
kind of code comment indicator or prefix which occurs at the beginning
of each line in a matchable section should be ignored for matching
purposes. Templates do not include markup for this guideline.

<strong>7. Bullets and Numbering </strong>

<span style="text-decoration: underline;">7.1 Purpose:</span>  To avoid
the possibility of a non-match due to the otherwise same license using
bullets instead of numbers, number instead of letter, or no bullets
instead of bullet, etc., for a list of clauses.

<span style="text-decoration: underline;">7.1.1 Guideline:</span>  Where
the template specifies a bullet (with the \<b\> tag), the target text
may include bullets or bullet-like text \[TODO: specify precisely what
counts, possibly provide a regular expression\]. Templates include
markup for this guideline.

<strong>8. Varietal Word Spelling</strong>

<span style="text-decoration: underline;">8.1 Purpose:</span>  English
uses different spelling for some words. By identifying the spelling
variations for words found or likely to be found in licenses, we avoid
the possibility of a non-match due to the same word being spelled
differently. This list is not meant to be an exhaustive list of all
spelling variations, but meant to capture the words most likely to be
found in open source software licenses.

<span style="text-decoration: underline;">8.1.1 Guideline:</span>  The
SPDX templates are published alongside an XML file containing a list of
valid synonyms. Where a template specifies the \<syn\> tag, any word in
this list with the same identifier may be matched. Templates include
markup for this guideline.

<strong>9. Copyright Symbol</strong>

<span style="text-decoration: underline;">9.1 Purpose:</span>  By having
a rule regarding the use of "©", "(c)", or "copyright", we avoid the
possibility of a mismatch based on these variations.

<span style="text-decoration: underline;">9.1.1 Guideline:</span> 
Different forms of the copyright identifier (e.g. "©", "(c)", or
"Copyright") should be considered equivalent and interchangeable. They
are included in the synonym list and marked up in the template files
accordingly. Templates include markup for this guideline.

<strong>10. Copyright Notice</strong>

10.1 <span style="text-decoration: underline;">Purpose:</span>  To avoid
a license mismatch merely because the copyright notice (usually found
above the actual license or exception text) is different. The copyright
notice is important information to be recorded elsewhere in the SPDX
file, but for the purposes of matching a license to the SPDX License
List, it should be ignored because it is not part of the substantive
license text.

10.1.1 <span style="text-decoration: underline;">Guideline:</span>  You
may ignore the contents of the \<copyright\> tag for the purposes of
matching. Templates include markup for this guideline.

<strong>11. License Name or Title</strong>

11.1 <span style="text-decoration: underline;">Purpose:</span>  To avoid
a license mismatch merely because the name or title of the license is
different than how the license is usually referred to or different than
the SPDX full name. This also avoids a mismatch if the title or name of
the license is simply not included.

11.1.1 <span style="text-decoration: underline;">Guideline:</span>  You
may ignore the contents of the \<title\> tag for the purposes of
matching. Templates include markup for this guideline.

<strong>12. Extraneous Text At the End of a License</strong>

<span style="text-decoration: underline;">12.1 Purpose:</span>  To avoid
a license mismatch merely because extraneous text that appears at the
end of the terms of a license is different or missing. This also avoids
a mismatch if the extraneous text merely serves as a license notice
example and includes a specific copyright holder's name.

<span style="text-decoration: underline;">12.1.1 Guideline:</span>  You
may ignore the contents of the \<optional\> tag for the purposes of
matching. Templates include markup for this guideline.

### Notes

There remains one slightly computer-hard problem to solve with regards
to matching a template to a license: code comment indicators. This
cannot be solved by the SPDX templates themselves, since the text that
needs to be modified is the target text being matched against, not the
markup that specifies the matching process.

I've changed my mind on the subject of formatting the templates in
lowercase and stripping out whitespace: these can be done readily and
easily by a program, and preemptively applying them in the build process
destroys information unnecessarily. I've also decided to keep the master
and matching formats equivalent in all other ways.
