To make contributions to the spec please follow these steps.

1.  [Report the
    issue](http://bugs.linux-foundation.org/enter_bug.cgi?product=spdx).
    Reporting an issue is a huge contribute. You can stop here and have
    our gratitude. If you want to try to fix the issue you can follow
    the steps below.
2.  Clone the repository and setup the build system (see below).
3.  Create a feature branch.
4.  Make your changes on that branch.
5.  [Create a proposal](Technical_Team/Proposals "wikilink") linking to
    the issue and describing your changes. Be sure to attach a patch
    (and include a link to your branch is if it published anywhere).

### Specification development setup

The master source for the specification resides in a git repository
hosted at linuxfoundation.org. Anyone can clone a working copy by doing:

`   git clone `<http://git.linuxfoundation.org/spdx-spec.git>

The spdx specification build system is based on ruby. The following
steps are required to generate the complete version of the
specification.

1.  Install Ruby 1.9.2 using the appropriate mechanism for your OS.
    (Earlier versions of Ruby will probably work but have not been
    tested.)
2.  Install sqlite3-ruby gem: gem install --source <http://rubygems.org>
    sqlite3-ruby --version 1.2.5
3.  Install rdf-context gem: ` gem install --source
     `<http://rubygems.org>`  rdf_context `
4.  Install mustache gem: ` gem install --source
     `<http://rubygems.org>`  mustache `

One you have performed those installations you can generate the full
specification by running `rake` in the spec-spec directory. This will
product a full html version of the spec, `build/spdx-1.0.html`, and an
rdf owl file containing the spdx ontology, `build/spdx-1.0-ont.html`.

If you have any issues getting up and running let us know and we'll get
your issue sorted out.

\<kes\> 20110516 - missing how to get contribution sent back - not ready
for general usage.

[Category:Technical](Category:Technical "wikilink")
