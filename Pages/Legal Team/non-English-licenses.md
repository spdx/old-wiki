## Working Page for Policy on Non-English Licenses

The issue of how or how to best handle licenses in languages other than
English or with multiple language translations has come up repeatedly
over the years of the SPDX License List's existence. This is especially
critical in relation to how short identifiers are assigned and when a
license is considered a match (or a different license). There are a
number of non-English licenses or licenses with multiple language
translations on the SPDX License List and the treatment thereof has
formed a sort of "default policy". However, such treatment is not
complete and does not fully address the question of license matching.

Jilayne Lovejoy and Kate Stewart presented the background of the issue
and current "default policy" along with a list of questions to an
international audience at the FSFE Legal and Licensing Workshop in April
2017. This page is for capturing various discussions that have come out
of that to try to form concrete proposals to be considered by the larger
SPDX community and then a sensible and complete policy formed.

As a starting point, please review the slides from the presentation
available here:
<https://docs.google.com/presentation/d/1miQz9F7q_oVbYCibTuhSrJ_qog6eHWs0DxcXxQ-ZLuk/edit?usp=sharing>

### Summary of current "default policy" and questions/issues to be resolved

By way of summary (also in the above slides), the SPDX License List
default policy for non-English license can be described as:

1.  Add the license to the SPDX License List in the "canonical" or
    original language; or the language version as requested (or what
    came first)
2.  Assign a short identifier based on 1
3.  If the license has "official" translations, then provide links to
    such translations in the notes field (but do not add translations as
    different languages) where "official" translations are those by the
    license author or otherwise blessed by the license author

the above implies the following:

  - one short identifiers can be used for all official translations
  - one can consider a match across any official translation

### Key Questions / Issues

  - How do we determine if it's "official"?
      - Is it enough to trust the license author?
      - What other criteria can be used (if translation is not done by
        license author or license author is not available)?
  - How do we deal with "unofficial" translations?
      - If use different identifier, will that be confusing?
      - GPL has designated unofficial translations (and a defined
        policy) available here:
        <https://www.gnu.org/licenses/translations.html> The FSF makes
        it clear that the English language license prevails and that
        translations in other languages help with understanding the GPL.
        In this case, it would see that the same short identifier should
        not be used and an unofficial translation in another language
        would not constitute a match to the original English text. As
        such, then what should the short identifier be in this case? As
        the main goal of the SPDX License List is license
        identification, it is helpful to indicate this is a translation,
        even if unofficial.
  - How do we use matching? Does a translation in one language
    constitute a match to a translation in another language? If so, then
    how do we implement that for tools and in the context of the XML
    file change?

#### Various discussion/points already raised on legal team calls

  - Current practice of putting a link to translations in the Notes
    field is helpful, but does not indicate it is an "official" or
    "unofficial" translation
  - re: tools and matching: Dennis shared approach from Scancode with
    treats any translation as same license and uses same identifier
    (roughly implements above "default policy")
  - seems ok to take word of author if they have multiple translations
    and to then use the same identifier, but what if someone else does
    translation?
  - see meeting minutes:
    <https://wiki.spdx.org/view/Legal_Team/Minutes/2013-04-11> (license
    list v1.18 discussion section)
  - see meeting minutes:
    <https://wiki.spdx.org/view/Legal_Team/Minutes/2016-03-03> (related
    to request to add Free Art License)
  - see meeting minutes:
    <https://wiki.spdx.org/view/Legal_Team/Minutes/2016-10-27>

## Proposals

### SPDX License Cluster Distance Value

*Proposed by Karsten Reincke (on general mailing list, so thread is
reproduced/summarized here for convenience)*

The problem was that we have to deal with translations of original FOSS
licenses. An example for such a set of related licenses is the EUPL. In
this specific case the translations have an 'official' state. Other
licenses are sometimes translated by 'not so official translators'.
About the EUPL it is said that the official translations preserve the
legal power with respect to the different European countries.
Unfortunately - as one member of that LLW session mentioned - it turned
out that this statement is not true.

So, the problem is how to reliably group licenses which are linked to
other licenses in any sense. During our LLW session there exist the
clear wish to create a specific SPDX file for each translation of each
FOSS license. That means NOT to group the licenses - due to the fact
that they are not 'identical'.

In consequence we will have a large set SPDX files. And that might
reduce the usability of SPDX.

So, my proposal is, to classify each element of such a license cluster
like EUPL by a number which indicates the distances to the original. The
idea is to encode the reliability of a license in number. Using that
technique would allow us to specify a license cluster by one SPDX file
(and a distance number \[which could be incorporated into the SPDX
file\]).

For being able to use SPDX License Cluster Distance Value, we would have
to define some dimensions whose values determine the distance to an
original. Then we would have to prioritize these dimensions and values
so that we get an ordered row of distance factors - ordered by priority.
To create a distance number on that base is simple. The main idea would
be:

The less that number the less the distance to the original.

**How could look that concretely?**

Let us link an English original to a zero. Here are some dimensions
(which have been mentioned in the LLW session):

  - (0) Is the license an English written original? (YES=0 | NO=1)
  - (1) Is the license a translation / derivation (YES=2 | NO=0)
  - (3) Is the license an official translation (YES=0 | NO=4)
  - (4) Does the translated license preserve the legal power (YES=0 |
    UNKNOWN=8 | NO=16)

Finally build the sum.

With respect to the EUPL, this algorithm delivers the following distance
values

  - English version = 0 + 0 + 0 + 0 = 0
  - Greek version =
      - 1 (because it's not the English original) +
      - 2 (because it is a translation) +
      - 0 (because it is an official translation)
      - 0 (because it preserves the legal power)
      - \= 03
  - Spain version =
      - 1 (because it's not the English original) +
      - 2 (because it is a translation) +
      - 0 (because it is an official translation)
      - 8 (because it is unknown whether it preserves the legal power)
      - \= 11
  - Freman \[of the hypothetical prospective country French+German\]
    version =
      - 1 (because it's not the English original) +
      - 2 (because it is a translation) +
      - 4 (because it is an unofficial translation)
      - 16 (because it does not preserve the legal power)
      - \= 23

**What does such a technique mean for one the problems Jilayne
mentioned?**

  - In the case, that we do not have an English spoken original, the
    SPDX License Cluster Distance Value would be 1 instead of zero, but
    nevertheless this number indicates a very small distance from the
    ideal. And it indicates, that the English spoken community might
    have (minor) problems to use such a licensed software.
  - On the other hand, if we have an English translation of a non
    English original, that license get the value (0 + 2 + x + y) which
    clearly indicates that the distance to the original / ideal is
    greater than the distance between a foreign original and the ideal.

A predictable question:

  - This idea might evoke the idea also to cluster variants like
    BSD-4-Clause, BSD-3-Clause, BSD-2-Clause' and the newest version
    'BSD-3-Clause with patent'. This would mean to encode also such
    contentual differences into the SPDX License Cluster Distance Value.
  - I don't like that idea. I think, that textual literal different
    license in the same language should ever have a different SPDX file
    - because they intentionally are different licenses.

A last remark:

  - In the LLW session someone voted for having only English originals.
    He argued that in case of foreign-language licenses, SPDX does not
    reliably know whether it really is a FOSS license. I can't follow
    that position:

Even as a English native speaker you do not know in case of an English
written License, whether it is really a Free or Open Source License.
This can only be evaluated by an established official process - as for
example the OSI offered. (The OSI requires English only and to be
officially translated). Hence: If SPDX wants to cover other licenses
which are not blessed by any processes the problem of the reliable FOSS
status is the same, in English and in foreign-language license.
Foreign-language license have the advantage the they more clearly
indicate the existence of the problem.

#### Feedback

Alan:

  - One issue I see is the issue we run into about trying to avoid
    making a legal judgment when classifying the licenses. That would
    imply we wouldn't use dimension 4 about "preserving legal power."
  - Also for dimension 3 regarding "official" licenses, perhaps we need
    some more gradation for something where it's not "official" but it's
    at least acknowledged or referenced. For example, the GPL
    translations aren't official:
    <https://www.gnu.org/licenses/translations.en.html> I think if we're
    factually relying on statements made by the license steward, it's
    less a concern about making a legal judgment.

Karsten: Such a differentiation would be helpful. Together with the
simplification not to use the dimension 'legal power' you can use a
better and simpler representation: licenses

  - original
  - English 00
  - foreign 01
  - translation
  - approved 10
  - audited 20
  - ...
  - unclear f0

Brad: Let me say that I emphatically believe SPDX should cover
non-English licenses. The world of FOSS software contribution is
multilingual, and I think SPDX should be as well. This may require some
extra work when adding a new license (finding a native-speaking
attorney, English review of an auto-translation, or something in
between), but I think it will prove worthwhile in the end as we expand
coverage to all widely-used FOSS contribution languages. In addition, we
have the license list source-controlled so that we can make changes and
fix issues over time, so I wouldn't be too worried about our ability to
make corrections if we felt an addition was ultimately a mistake.

### Each License/Translation Treated Individually

*Proposed by Bradlee Edmondson* Each license/language text should be
tracked, treated, and marked up individually by SPDX, i.e. one license
for GPL-en, another for GPL-de, another for GPL-fr, etc. (presumably 24
for the EUPL?). To my mind, these are collections of related license
texts, not multiple ways to get to the "same" license, since even if the
"same" license is in fact what the author intended (e.g. in the case of
an "official" translation), it would still be up to a court to decide
whether the legal terms as represented in one language are identical to
a similar, purportedly "identical" representation in another language
(even in the same jurisdiction). So I would say, let's track them all,
and get at the problem of relating one to another with more metadata.

Assuming all license translations are individually tracked, I think the
best way to go about relating them to each other is to use something as
close to native XML as possible. We already have the unique identifiers,
XML tags, and attributes for each license, so why not add an XML tag
that can reference another license by unique identifier? For EU Public
License in German, that might look something like this: ...
<relatedLicenses>

`  `<relatedLicense relationshipType="official-translation" targetLicenseIdentifier="EUPL-1.1">`EUPL-1.1`</relatedLicense>

</relatedLicenses> ... Other relationshipTypes might be
"unofficial-translation," "official-translation-ported,"
"official-translation-unported," and "derived-from" (there may be
others, or maybe we don't need all of those). That just represents the
facts as we've perceived them, without getting into too much judgment as
to how close the relationship might be. This would allow us to say,
essentially, "this is what we think the relationships are; have your
open-source counsel review what that means for you."

Another way of throwing data at the problem might be to individually
track all of the licenses, without built-in cross-references to other
license IDs, but at the same time also publish a separate document
specifying which of those licenses are related to each other and what
kind of bundles those are. This is the same data as proposed in the
previous paragraph, but laid out explicitly (again with reference to the
unique license ID) rather than emergent from the XML. I think I prefer
the emergent solution, but that's just me, and what I think today.

#### Feedback

JL: If we did this, then how would we differentiate between "official"
translations and "unofficial" translations? That is, if we added all
20-something EUPL translations as, EUPL-1.1-en, EUPL-1.1-fr, and so on -
how would we treat the GPL unofficial translations? If we treated them
the same, it would seem to imply those translations carry the same
"weight" as the EUPL translations, but given the stance by the FSF, I
don't think they do.

## Codify Default Policy and Incorporate into Matching Guidelines

  - Licenses are added to the SPDX License List in the "canonical" or
    original language; or the language version as requested (or what
    came first)
  - Short identifier is assigned as per the official language
  - License text for official translations is captured in SPDX License
    List source file via additional XML tag
  - Matching guidelines clarified such that official translation can use
    the same short identifier

<!-- end list -->

  - Unofficial translations can be added to the license list as separate
    licenses and use the same identifier (to show association), but with
    a language identifier at end (en, fr, etc.). This would also require
    explaining this differentiation (and possibly review or notification
    by license authors to make sure they are okay with this)
