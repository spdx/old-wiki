## Action Items - Stage 1a: XML Conversion of Existing Licenses

### Existing License PRs

  - <span style="color: red;">Finish main review of all licenses so that
    all can merged (Who: ALL)</span>
  - Kris to put original "conversion" tool (to convert text files into
    XML format, to then be reviewed) in public repository so anyone else
    can use it or improve it (KRIS) -- DONE
      - can be found here: <https://github.com/myndzi/license-tool> see
        further notes on this below

### Exceptions

  - Convert and add exceptions to repository (KRIS) - DONE
  - note from Gary: tools don't care whether in same or different
    directory --\> they are in their own directory
  - Review exceptions and merge exception PRs (ALL) - DONE

### Deprecated licenses

  - outcome: Proposed solution to add a boolean attribute named
    deprecated to the SPDX element with a default value of false. For
    the "+" deprecated licenses, we would copy the XML file, rename it
    to include the "+" and add deprecated=true to the SPDX attributed.
  - <span style="color: red;">Convert and add deprecated licenses to
    repository (GARY) </span> - almost done
  - <span style="color: red;">Review and merge deprecated license PRs
    (ALL) </span>

### PRs tagged "requires acknowledgement" or "has self-referring numbering"

  - Originally, we planned to add XML tags to reflect these
    characteristics (and not merge these licenses until we do so). For
    now, though, we will leave this as a potential feature for the
    future, and proceed to merge these licenses as long as their basic
    formatting looks correct. (We will be able to go back and review
    which PRs had these labels even after merging.)
  - Merge those labeled "approved" and "requires acknowledgement"
    (JILAYNE) - DONE
  - In future, may also need a more thorough review of existing licenses
    to see if any others meet these criteria (i.e. can't rely solely on
    the labeled PRs)

### True-up license list to current release

  - <span style="color: red;">Need to true-up changes to existing
    licenses from 2.3 (when XML repo was created) to current 2.6 release
    using spreadsheet (JILAYNE)</span>
  - Convert and add new licenses to repo from 2.4, 2.5. 2.6 (KRIS or
    someone from tech team using Kris' tool) - DONE
  - Review and merge PRs for new licenses/exceptions since 2.3 (ALL) -
    DONE

### General Cleanup / Future Tag Changes

  - <span style="color: red;">After review is complete and all licenses
    and exceptions have been merged, general clean-up to include:
    (GARY)</span> --\>
  - Initial round of clean-up to include:
      - remove body tag
      - fix lower case spdx tags
      - get rid of HTML-escaped characters where not needed / keep those
        that are needed (e.g., greater than / less than symbols)
      - update XML tag names as per tech team recommendations (see
        below)
      - pretty-print XML
  - Clean-up or formatting issues to be considered later:
      - <s>does all text need to be wrapped in \<p\> tags? or could
        titles just be \<title\>license title\</title\> instead of
        \<title\>\<p\>license title\</p\>\</title\>?</s> Yes,
        [everything
        needs](https://github.com/spdx/license-list-XML/issues/414#issuecomment-320094253)
        \<p\> and \<br\> tags
      - add back the \<br\> tags Brad removed / generally prettify
        licenses so that they display as close to original as possible
      - check license families (CC-BY, GPL, etc.) for consistent markup
        (e.g., what is optional in CC-BY licenses?)
      - add a tag for "deprecated licenses", possibly add more
        definitive advice on alternative license expression

### Tracking license list version for new licenses

  - when a new license is added to the list is currently recorded in the
    new license request list and in the SPDX License List master
    spreadsheet. Where will this info be in the new XML world? should we
    put this meta data in license itself, as a new tag or can we use
    Github release magic to track that way? --\> discuss at OSLS, see
    minutes here:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2017-02-15-OSLS>
      - added new attribute for this, but will only implement for 2.6
        and onward, need to check on attribute name - In Google doc
  - Add attribute to new licenses as of v2.6 - DONE

### Finalize XML tag names

  - Gary to bring to tech team for Sept 20 call, tech team to decide,
    with final review/sanity check by legal team - DONE
      - process: build a table for existing field name (machine-readable
        name for these from current spec) and new XML tag - DONE
      - Gary took to tech team, and had joint call with legal and tech
        team to finalize. Notes here:
        <http://wiki.spdx.org/view/Technical_Team/Minutes/2016-10-25>
        and
        <https://docs.google.com/document/d/1z9n44xLH2MxT576KS_AbTOBtecyl5cw6RsrrQHibQtg/edit>
  - update tags as per tech team recommendations (action item noted
    above) as part of "General Clean-up" in above section

## Action Items - Stage 1b: Switch to Github, using old license list format - Jan 30

  - Update info for README on Github for initial switch to Github from
    Git repo, prior to XML conversion (Dennis to draft, ALL review) -
    DONE
      - completed - see here:
        <https://docs.google.com/document/d/1kGSs3CXbtjF_uZmVsjhXMGChyP-pzlszktTr8t4PmmI/edit#>
  - <span style="color: red;">update README on Jan 30 or after with this
    text </span>
  - update webpages where needed: (JILAYNE w/help from rest of legal
    team) - DONE
      - links to master files
      - page on requesting a new license - how to update, just point to
        README?
      - what else?
  - what to do with existing license request tracking spreadsheet: will
    need to move any "live" items into issue tracking in Github; leave
    where it is otherwise as dormant? download and post somewhere on
    wiki to be safe?
      - where does data as to what version a license gets added to list
        go going forward? (see above)

## Action Items - Stage 2: Go live with XML conversion

### Check website generation and tools

  - As of Sept 16 call, Gary had done a first pass on tools to generate
    website and caught a bunch of validation errors, many of which were
    from lower case <spdx> tag. Gary to see what other validations were
    and fix and merge if simply or create pull request/submit to legal
    team if needs review
  - <span style="color: red;">other updates to spdx-tools for new XML
    format to generate the website along with the 5 different license
    formats in available in the license-list-data git repository (Gary)
    </span>
  - preview of website before release
  - make sure everything is in there (i.e., diff on text files that they
    are identical)

### Documentation

  - Review various webpages for updating
      - Alan did first pass, which raised various questions and other
        things to address, need to revisit now that naming issue has
        been resolved with tech team
      - license matching guidelines web page
      - license list overview web page
      - README in repo and info in repo itself
      - request a new license web page
      - Appendix in spec:
          - Appendix 1 is list of licenses - check
          - Appendix 2 must be updated
          - Appendix IV and V - check for links, references, etc.
      - other pages?
      - info about XML tags
        (http://wiki.spdx.org/view/Legal\_Team/Templatizing/tags-matching)
        - this may become part of spec as an appendix, but where to put
        in meantime?

### Coordination with tech team and SPDX Spec v2.2

  - revisions to current appendix in spec as to markup (e.g., var v. alt
    markup tag)
  - explanation of XML tags - to go in markup appendix or new appendix?
  - v2.2 of spec is not going out this year, so may want to think about
    stuff that we might want to go into a new appendix eventually, where
    should it go in the meantime and plan for a migration?
  - \---\> discuss at OSLS

### Incorporating Synonyms into XML license documents

  - Kris had a plan to do this, but not sure he can contribute that now.
  - will postpone this until someone has a plan and can do the work, but
    will include in the .xsd schema
  - 2 options: all within license text itself or via a file that's
    stored in repository and lists them all in a structured way tools
    can use
  - will need someone to work on this

### Create new tool to take text of new license and convert to XML file

  - to do so by hand is a bit tedious. Will still need human review
    before finalizing. Initial tool Kris used probably won't be
    applicable. Would be nice if this could be web-based
  - discuss with tech team, find someone to take this on? ---\> discuss
    at OSLS

### Tool for verifying XML against known matching/known non-matching text files

  - Testing regime for XML (either manually or by continuous
    integration) to validate that XML source generates other formats
    correctly
