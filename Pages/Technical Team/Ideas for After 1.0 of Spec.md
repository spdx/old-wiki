This is a placeholder for tabling items that are not going to make it
into first version but we want to discuss further for subsequent
versions of the spec.

  - Create a version of the specification that can be included inside a
    package. Note the problem is that the uniquie ID of the package
    (SHA1) field has to be taken over the entire package, and if the
    analysis is part of it, we can't include the SHA1 of the package.
    (requested by package creators, to carry forward with package, keep
    accurate).
  - Incorporate an optional MD5 checksum field at package level to
    permit correllation to other existing analysis of a package
    (requested for consideration by Bill S.)
  - Further simplification of RDF - make more human writable friendly.
    (requested for consideration by Kate S.)
  - In detected licenses, consider adding counts per license (requested
    by Bill S.)

## Brought up during 7/22 meeting

  - How to detect licenses where synonyms are used in licenses;
    "package" instead of "software", for example. Can this be handled by
    templating? British vs. English spelling, too\!
  - How do we want to deal with JAR files? They can contain dependency
    info, licenses, etc - and how do they relate to their source files?
  - How to deal with the case where the license is NOT part of the
    distribution, but is (for example) on the project web site.
  - Variations of licenses - BSD and MIT
  - 8/5 Kim W - we should consider adding disjunctive licenses to the
    Detected License field on the package. This would be helpful when
    you are looking at the Detected Licenses to give you a summary of
    licenses because you would be able to tell that there is a choice to
    make without having to examine every single file license.
  - 8/5 Kim W - we should consider adding an optional field to the file
    section to identify the Component that the file (and license) came
    from. This would be helpful because the reviewer could better
    understand where the license info came from, validate things with
    developers, and do research on the project.

[Category:Technical](Category:Technical "wikilink")
