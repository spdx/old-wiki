There have been multiple discussions in different working groups about
the nomenclature, meaning and intent of the package license fields. To
ensure we are all on the right page, we want ot have some wiki-based
discussion about the fields with perhaps some examples and use cases tha
that we can capture for documentation, FAQs, etc. We may need to go thru
this same exercise at the file level, but let's start here.

Below is extracted (though for simplicity, not 100% complete) text from
the June 5 rev of the spec
(http://www.spdx.org/wiki/spdx/specification). Please make comments or
ask questions and identify yourself.

*4.9 Declared License*

*4.9.1 Purpose: This field lists the licenses that have been declared by
the authors of the package. Any license information that does not
originate from the package authors, e.g. license information from a
third party repository, should not be included in this field...*

*4.9.2 Intent: This is simply the license identified in text in the
actual package source code files. This field is not intended to capture
license information obtained from an external source, such as the
package website. Such information can be included in 4.7 Concluded
License. This field may have multiple declared licenses, if multiple
licenses are declared at the package level...*

*4.7 Concluded License*

*4.7.1 Purpose: TThis field contains the license the creator has
concluded as governing the package or alternative values, if the
governing license cannot be determined...*

*4.7.2 Intent: Here, the intent is to have the reviewer analyze the
license information in package, and other objective information, e.g.,
COPYING.txt file etc., together with the results from any scanning
tools, to arrive at a reasonably objective conclusion as to what license
governs the package.*

So, what do you think?

Is the distinction clear between the two fields?

Are both useful?

Can you provide examples of where they are useful?

Do you have an example that raises issues?

[Category:General](Category:General "wikilink")
[Category:Archived](Category:Archived "wikilink")
