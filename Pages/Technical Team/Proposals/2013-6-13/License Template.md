1 License Template Certain sections of a license vary as they are used.
Some of this variability is by design (think of the BSD family of
licenses). In other cases it is due to small changes in licenses as they
are copied and propagated. The License Template describes which sections
of the license can be varied and which sections have standard text.

1.1 Standard License List Template Download The SPDX Standard License
List will maintain a template for each of the licenses in the SPDX
Standard License List. The download location for the current version can
be found in the link at the bottom of the page spdx.org/licenses.

1.2 Standard License List Template RDFa Access The template text for the
standard license can be accessed using the RDF tag licenseTemplate on
the web page containing the standard license.

1.3 Template Format A template is composed of text with zero or more
rules embedded in it. A rule is a variable section of a license wrapped
between double angle brackets “\<\<\>\>” and is composed of 5 fields.
Each field is separated with a semi-colon “;”. Rules cannot be embedded
within other rules.

Rules begin with a case sensitive tag followed by a colon “:”.

Rule fields:

  - original: the original text of the rule. It should be the first
    field. It is required.
  - match: a POSIX ERE regular expression (see below). This field is
    required.
  - name: name of the field in the template. This field is required.
  - type: one of “required” or “optional” (case sensitive). This field
    is required.
      - “required” indicates that text matching the regular express must
        be supplied to be a valid license
      - “optional” indicates that no text is required, but can be
        optionally supplied
  - example: another example of the use of the text. This field is
    optional.

The POSIX ERE regular expression has the following restrictions and
extensions:

  - Semicolons are escaped with \\;
  - POSIX Bracket Extensions are not allowed

Example:

\<\<original=THE AUTHOR OR
CONTRIBUTORS;match=.+;name=copyrightHolderLiability;type=required;example=dmg
inc.\>\>
