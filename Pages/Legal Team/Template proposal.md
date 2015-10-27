## Introduction

As discussed on the last legal call, here’s my proposal for enhancing
the markup.

There are two problems that need solving:

1.  Maintaining a version of the licenses with just enough markup to aid
    in the computer-hard decisions
2.  Make computer matching entirely logic-free by providing the required
    information to an implementation with markup

Since (2) may necessarily be difficult to maintain by hand, as well as
be error-prone (for example, finding \*every\* synonym instance in some
license text), I suggest that a build process is necessary to produce
the "enhanced" \[item (2)\] markup from the human-maintained "source"
markup.

## Categorization of matching guidelines

Items that belong in the source markup are items that are easy for a
human to identify but difficult for a program to identify (or easy for
multiple implementations to get "differently"). These items include:

  - Headers (copyright declaration, license name preface)
  - Bullets (specifically in the case of numbered bullets with roman
    numerals, it can be difficult to distinguish accurately from wrapped
    text ending a sentence)
  - Optional sections (such as instructions on license application)
  - References to the author / copyright holder

Items that belong in the enhanced markup are items that are easy for a
program to identify, where the build process can create a canonical
"correct" form of the text to-match, thus 1) obviating implementations
from the need to write boilerplate parsing code and 2) ensuring that
implementations produce the same results given the same sample text.
These include:

  - Varietal spellings
  - Copyright symbol
  - Punctuation (dashes and quotes)
  - Whitespace
  - Capitalization

The whitespace and capitalization items are somewhat questionable, but
since there is already a build process it doesn’t hurt us to add them,
and it means that implementations will not have a need to perform any
transformations on the matching-text beyond XML parsing. An important
note: whitespace between words being significant, this approach will not
necessarily lead to the desired results if we encounter a need or desire
to create \*optional\* sections of text. For example, ` James, while
John had had  `<alt match="(had )*"/>`  had had a better effect on the
teacher ` – in this example sentence, if zero matches occur, we will be
matching a sentence with two spaces in a row. I don’t believe this will
currently be a problem, because I don’t know of any reason for us to
mark up templates in this way; every matchable component should
encompass the left and right word boundaries, so spacing should not be
an issue and should be preserved exactly as produced in the enhanced
markup.

## Translation of current markup to proposal

Please correct me if I am mistaken – I appear to be unable to find
documentation on the current markup – but I observe two elements in the
current markup syntax: 1) entity replacement and 2) optional section
blocks. These are quite readily translated into an XML form. I am
uncertain if the variable function is used by any of the current
tooling, but it can be left off until desired or added as-is.

Suggested transformations:

1.  `<<var; name=foo; original=Original Text; match=.+>>`  
    becomes:  
    <alt match=".+" name="foo">`Original Text`</alt>
2.  `<<beginOptional; name=optionalIntro>>Some text
    here<`<endOptional>`>`  
    becomes:  
    <code>
    <section name="optionalIntro">
    Some text here
    </section>
    </code>

This is a fairly direct translation and could even be performed
programmatically on the existing data if we elect to use a generic
"optional" tag; above I’ve used "section" as a placeholder for multiple
candidate tags depending on the section being described.

While we can define all desired elements in terms of "alt" tags, I
believe some of them at least deserve their own tags. Bullets, for
example, I would suggest wrapping in "\<b\>"; this is primarily for
brevity:

`  `  
`<b>1.</b> Some clause …`  
`<b>2.</b> More items….`  
`  <b>a.</b> Sub-item…`

The need for brevity comes as a result of trying to keep the source
markup as human-manageable as possible. While it’s somewhat tempting to
designate hierarchical \<ol\> or \<ul\> items as in HTML, this doesn’t
actually provide any use for \*matching\* purposes, so has been
explicitly discarded.

Other items that might warrant their own tags actually become section
wrappers, such as for copyright declarations:

`<copyright>Copyright © <year> <owner>. All rights reserved.</copyright>`

(This also points out the need to escape \< and \> symbols as entities,
a task which can be performed programmatically in a conversion process
as well)

Other tags wrapping optional sections might include:

<title>

,

<footer>

,

<header>

, and <optional>.

## Synonyms

One extra tag can support the enhanced markup in a useful way: for
varietal/alternative spellings, an external file with some metadata can
define the allowed synonyms for some string of text, allowing this to be
updated without the need to modify the contents of the license templates
themselves. These can be substituted into the document at build time to
provide data-driven matching that supports these matching rules, e.g.:

` Neither the name of the  `<syn identifier="copyright-holder"/>`  nor
the names… `

(and, externally:)

`  `  
`<synonyms identifier="copyright-holder">`  
`  <synonym>Copyright holder</synonym>`  
`  <synonym>Copyright owner</synonym>`  
`</synonyms>`

While this approach can also be used to handle alternate values of
dashes, quotes, etc., plain normalization of the data in the enhanced
markup should suffice, a transformation which can be applied along with
the lowercasing and whitespace removal: all varieties of dashes become a
simple ascii hyphen, all varieties of quotes become a simple ascii
quote, etc.

It may be a good idea to also "externalize" matching of copyright
headers, bullets, dashes, quotes, etc. in this fashion, since their
structure and meaning is independent of an actual license file.
Providing an explicit list of valid characters or a regular expression
for these items in the SPDX database metadata will ensure that
implementations are kept consistent.

## Structure of overall document

This is pretty straightforward:

`  `  
`<license identifier="SuchAndSo">`  
`  <title>The Such and So License</title>`  
`  <copyright>Copyright © 2015 Foo Bars</copyright>`  
`  `  
`  <body>License text ...</body>`  
`  `  
`  <footer>How to apply this license: ...</footer>`  
`</license>`

Whitespace can be formatted such that the concatenated text content of
the XML file produces the original document, though that poses a minor
problem if we desire to include other data streams, which I recommend we
do. One way to handle that would be to wrap the above example in a
higher root element, which would allow us to include things such as
optional clauses and license headers:

`  `  
`<SPDX>`  
`  <header>This file is licensed under the Such and So License</header>`  
`  <license identifier="SuchAndSo">(as above)</license>`  
`  <optional identifier="SuchAndSo-foos-exception">…</optional>`  
`</SPDX>`

## Examples

Using the above ideas, here is a marked-up example of the BSD 3 clause
license in the "source" format:

`  `  
`<SPDX>`  
`<license identifier="BSD-3-Clause">`  
`<copyright>Copyright (c) <year> <owner>. All rights reserved.</copyright>`  
`  `  
`<body>Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:`  
`  `  
`<b>1.</b> Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer. `  
`  `  
`<b>2.</b> Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution. `  
`  `  
`<b>3.</b> Neither the name of <alt match=".+">the copyright holder</alt> nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.`  
`  `  
`THIS SOFTWARE IS PROVIDED BY <alt match=".+">THE COPYRIGHT HOLDERS AND CONTRIBUTORS</alt> "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL <alt match=".+">THE COPYRIGHT HOLDER OR CONTRIBUTORS</alt> BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.</body>`  
`</license>`  
`</SPDX>`

And again in the "enhanced" format:

`  `  
`<SPDX>`  
`<license identifier="BSD-3-Clause">`  
`<copyright><syn identifier="copyright"/> <syn identifier="copyright"/> <year> <owner>. all rights reserved.</copyright>`  
`<body>redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met: <bullet/> redistributions of source code must retain the above <syn identifier="copyright"/> notice, this list of conditions and the following disclaimer. <bullet/> redistributions in binary form must reproduce the above <syn identifier="copyright"/> notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution. <bullet/> neither the name of the <syn identifier="copyright-holder"/> nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission. this software is provided by the <syn identifier="copyright-holder"/>s and contributors "as is" and any express or implied warranties, including, but not limited to, the implied warranties of merchantability and fitness for a particular purpose are disclaimed. in no event shall the <syn identifier="copyright-holder"/> or contributors be liable for any direct, indirect, incidental, special, exemplary, or consequential damages (including, but not limited to, procurement of substitute goods or services; loss of use, data, or profits; or business interruption) however caused and on any theory of liability, whether in contract, strict liability, or tort (including negligence or otherwise) arising in any way out of the use of this software, even if advised of the possibility of such damage.</body>`  
`</license>`  
`</SPDX>`

Notice that I changed the bullets from <b>1.</b> to <bullet/> -- this is
because the "1." part doesn't matter for matching purposes, it's only
phrased that way in the source markup for the purpose of reproducing the
original text.

You’ll note that the product of the enhanced format could now be quite
readily translated into a regular expression, or parsed as an XML
document to apply matching directly by some other means. It actually
occurs to me that this transitory format may not be entirely necessary,
but once we have reduced it to something like a regular expression, we
remove the ability of a consumer to apply this data in other ways.

## Aside: normalization

As with the matching guidelines, we should define an explicit process
for normalizing candidate text to be matched against the SPDX data set,
and should use that same approach for normalizing the data used to
produce the enhanced markup. This includes \*exactly\* which Unicode
characters count as dashes, quotes, etc. and how (or whether) we
interpret hyphenated words vs dashes, especially with regards to
whitespace, and so on.

## Matching process

Following this proposal, the matching process for an implementer becomes
straightforward and accurate:

(optionally, if we don’t supply the data in regular expression form)
Build matcher from marked up template:

1.  Parse XML
2.  Render body (and/or header, exception, etc.) contents to a regular
    expression:
    1.  Replace “alt” tags with their “match” attribute
    2.  Replace “syn” tags with a synonym list \[e.g. (foo|bar|baz)\]
    3.  Replace “b” tags with a bullet matcher
    4.  Replace dashes and quotes with dash/quote matchers
3.  There’s no need to render copyright, title, or optional/footer
    sections since the matching guidelines say they can be safely
    ignored; only the body counts (and any addons)

Apply matcher:

1.  Identify candidate text
2.  Normalize candidate text (lowercase, remove whitespace
3.  Apply matcher(s) to candidate text

As you can see, no part of this involves making determinations about
what counts as a bullet, what counts as substantive text, etc., and
implementation is very straightforward, utilizing only basic string
manipulation and an XML parser (a tool which will be available in most
every language). Conclusion

This turned out to be quite long but, I hope, thorough. I will be
pasting it into the wiki too, for reference; please have a think on it
and reply with any comments/suggestions/etc.

\-Kris
