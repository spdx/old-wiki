## Plan for review of XML license file

The files can be found here: <https://github.com/spdx/license-list-XML>

You will need to have a Github account to participate in the review. Let
Jilayne know your Github account ID to be added to the repository team.

### Key things to review before reviewing the XML files:

  - SPDX License List Matching Guidelines:
    <http://spdx.org/spdx-license-list/license-list-overview>
  - Explanation of the SPDX License List fields:
    <http://spdx.org/spdx-license-list/license-list-overview> (at bottom
    of page)
  - Description of current proposal and XML tags:
    <http://wiki.spdx.org/view/Legal_Team/Templatizing/tags-matching>
  - Video of review process demonstrated:
    <https://www.youtube.com/watch?v=E_VoRQbDyEc>

You may also want to watch:

  - Using Git (on Windows):
    <https://www.youtube.com/watch?v=nsSjT4cmVEc>

### Key things to look at during review:

1.  identify which parts of the license template are important or
    unimportant for purposes of matching (as per the Matching
    Guidelines), e.g., is optional tag in the right place, etc.
2.  structural components - ensuring we have groups of clauses correctly
    identified (automated process takes care of most of this, but sanity
    check). Note that if a license does not have info for certain tags
    (e.g., Notes or a Standard Header) these tags won't appear in the
    XML
3.  look at the labels created for other things to note whilst reviewing
    the licenses
4.  consider any changes that need to be made to the Matching Guidelines
    or License List Overview/description of fields as you go along

Note:

  - nested lists should begin with the nested <list> tag within the last
    list item (before the
    </li>
    ) for which the nested list is a sub-item (like HTML)
  - if you find licenses that did not render this correctly, you can
    either edit them or tag them with the *bug* label
  - Kris made a viewing tool to be able to see what the license will
    look like: <http://krisreeves.com/xmledit/>
      - You can paste whatever XML you want in the left and use the
        excellent Ace editor to manipulate it. It's transformed into an
        HTML fragment via an XSLT stylesheet, though browser support may
        not be robust and the resulting html isn't fantastic yet. It
        highlights replaceable text and makes optional text gray,
        formats lists, and exposes some basic information. There's lots
        that could be improved but I figure it might at least be enough
        to help in the short term.
      - One thing that jumps out at me is that styling the lists with
        CSS isn't quite as useful as I had hoped it would be. Initially
        I had wanted to essentially put a "negative indent" on the
        bullets and treat the rest of the content like normal. I've done
        this to an extent here, but wide bullets will still break things
        and other quirks still exist, such as multiple paragraph tags
        not lining up with each other.
      - The Ace editor should issue warnings about malformatted XML. As
        an example I load up the Apache 2.0 license, which suffered from
        a case mismatch in the open and close SPDX tags (I've committed
        a fix to the repo).

### Process for Review

1.  go to <https://github.com/spdx/license-list-XML> (you need a Github
    account)
2.  go to pull requests (this represents all the licenses that need to
    be reviewed)
3.  to ensure you are working on licenses that have not been reviewed or
    are not being reviewed by others:
    1.  filter the list using the facets on the right side by: Labels =
        unlabeled; and then Assignee = Assigned to nobody
    2.  check off a handful of licenses you are going to work on and
        then Assign to yourself
4.  pick a license to review ; go to "Files changed" to view the actual
    file (in diff format)
    1.  use <http://krisreeves.com/xmledit/> for split view of what you
        are editing
5.  if everything looks good, then go back to "conversation" tab and you
    can either:
    1.  merge the pull request if you feel confidant to do so; or
    2.  leave a comment that you reviewed it and label this as
        "approved" - labels are found in the right side (see below for
        more on labels)
6.  if you see something you have a question about or think needs
    editing, then you can:
    1.  if you want to actually edit the content, click on the pencil
        icon in the top right corner (you will need access to Kris' fork
        of this account); or
    2.  comment in-line

### Labels created in Github

See: <https://github.com/spdx/license-list-XML/labels>

  - *approved* = someone looked at it, thinks it's good to go, there is
    nothing to review, but didn't merge it
  - *requires acknowledgement* = if you find a license that requires the
    reproduction of specific acknowledgment text, then label it with
    "has acknowledgement" - for example see:
    <https://github.com/spdx/license-list-XML/pull/279/files> (if it's
    otherwise approved, then label with both, but do not merge it)
  - *need legal discussion* = there is a question that is
    legal/interpretation related that you want to discuss on the next
    call. leave a comment, so members of legal team review and comment
    in b/w calls - if 3 people agree with assessment, then no need to
    discuss
  - *bug* = if the text and substance looks good, but there is an issue
    with the tags only, e.g., list tags are not properly nested or some
    other such issue that Kris specifically needs to look at. If
    otherwise good to go, also add "approved" label
  - *question* = use if you have a question that does not fit into one
    of the other categories or cuts across other categories
  - *help wanted* = try not to use and put under one of other categories
  - *has self-referring numbering* = no longer in use
