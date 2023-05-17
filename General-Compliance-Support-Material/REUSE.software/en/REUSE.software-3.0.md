# REUSE.software

This document is based on REUSE.software, a project launched by FSFE, and redistributed under CC-0 with their kind permission.

---
# SPDX-FileCopyrightText: 2019 Free Software Foundation Europe e.V.
# SPDX-License-Identifier: CC0-1.0

title: "REUSE Specification – Version 3.0"
---

This specification defines a standardized method for declaring copyright and
licensing for software projects. The goal of the specification is to have
unambiguous, human- and machine-readable copyright and licensing information for
each individual file in a project. Ideally this information is embedded into
every file, so that the information is preserved when the file is copied and
reused by third parties.

This specification implements [IETF RFC 2119: Key words for use in RFCs to
Indicate Requirement Levels](https://tools.ietf.org/html/rfc2119).

For the revision history of this specification, please see [the change
log](https://git.fsfe.org/reuse/docs/src/branch/stable/CHANGELOG.md).

## Definitions

These are the definitions for some of the terms used in this specification:

- REUSE Tool --- helper tool for compliance with this Specification; available
  at <https://github.com/fsfe/reuse-tool>.

- Project --- any unit of content that can be associated with a distribution of
  software. Typically, a Project is composed of one or more files. Also
  sometimes called a package.

- License File --- a file containing the text of a license.

- Copyright and Licensing Information --- the information that lists the
  copyright holders of a file or work, and describes under which licenses the
  file or work is made available.

- Covered File --- any file in a Project, except for
    - The License Files.
    - The files belonging to the Project's version control system (example:
      `.git/`).
    - The files ignored by the version control system (example: files listed in
      `.gitignore`).
    - The files in the `.reuse/` directory in the root of the Project. This
      directory MUST contain only files relevant for the operation of the REUSE
      Tool.
    - Symlinks and files with no data (zero-byte).
    - SPDX documents in their various formats as defined in the [SPDX
      Specification, Clause
      4.4](https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements)
      (example: `sbom.spdx.json`).

- Commentable File --- a plain text file that can contain comments.

- Uncommentable File --- either a plain text file that cannot contain comments
  or a file that is not a plain text file.

- SPDX Specification --- SPDX specification, version 2.3; as available on
  <https://spdx.org/specifications>.

- SPDX License Identifier --- SPDX short-form identifier, as defined in SPDX
  Specification. See also <https://spdx.org/ids> for a short introduction and
  examples.

- SPDX License Expression --- as defined in SPDX Specification, Annex D, at <https://spdx.github.io/spdx-spec/v2.3/SPDX-license-expressions/>.

- SPDX License List --- a list of commonly found licenses and exceptions; as
  available on <https://spdx.org/licenses/>.

- DEP5 --- [Machine-readable `debian/copyright` file, Version
  1.0](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/).
  Where the REUSE Specification and DEP5 state different things, the REUSE
  Specification takes precedence. Specifically in the case of the `Copyright`
  and `License` tags.

## License Files

A Project MUST include a License File for every license under which Covered
Files are licensed.

Each License File MUST be placed in the `LICENSES/` directory in the root of
the Project. The name of the License File MUST be the SPDX License Identifier of the
license followed by an appropriate file extension (example:
`LICENSES/GPL-3.0-or-later.txt`). The License File MUST be in plain text format.

If a license does not exist in the SPDX License List, its SPDX License Identifier
MUST be `LicenseRef-[idstring]` as defined by the SPDX Specification, Clause 10 available at <https://spdx.github.io/spdx-spec/v2.3/other-licensing-information-detected/>.

A Project MUST NOT include License Files for licenses under which none of the
files in the Project are licensed.

Everything that applies to licenses in this section also applies to license
exceptions, with the exception that it is NOT possible to have a license
exception that does not exist in the SPDX License List.

For avoidance of doubt, in practice this means that for every license and exception
that is part of any SPDX License Expression in any Copyright and Licensing Information
associated with any Covered File, there MUST exist a License File as defined in this section.

## Copyright and Licensing Information

Each Covered File MUST have Copyright and Licensing Information associated with
it. There are two ways to associate Copyright and Licensing Information with a
file. In addition, there is a way to associate Copyright and Licensing
Information with a snippet.

### Comment headers

To implement this method, each Commentable File SHOULD
contain comments at the top of the file (comment header) that declare that
file's Copyright and Licensing Information.

For Uncommentable Files, the comment header that declares the file's Copyright
and Licensing Information SHOULD be in an adjacent file of the same name with
the additional extension `.license` (example: `cat.jpg.license` if the original
file is `cat.jpg`).

`.license` files MAY be used with Commentable Files, but it is still RECOMMENDED
that comment headers be put inside Commentable Files.

The comment header MUST contain one or more `SPDX-FileCopyrightText` tags, and one or
more `SPDX-License-Identifier` tags. A tag is followed by a colon, followed by
a text value, and terminated by a newline.

The `SPDX-FileCopyrightText` tag MUST be followed by a copyright notice.

Instead of the `SPDX-FileCopyrightText` tag, the symbol `©`, or the word `Copyright` MAY
be used, in which case a colon is not needed.

The `SPDX-License-Identifier` tag MUST be followed by a valid SPDX License
Expression describing the licensing of the file (example:
`SPDX-License-Identifier: GPL-3.0-or-later OR Apache-2.0`). If separate sections
of the file are licensed differently, a different `SPDX-License-Identifier` tag
MUST be included for each section.

An example of a comment header:

```
# SPDX-FileCopyrightText: 2016, 2018-2019 Jane Doe <jane@example.com>
# SPDX-FileCopyrightText: 2019 Example Company
#
# SPDX-License-Identifier: GPL-3.0-or-later
```

If these tags are additionally used in the file without describing the file's
actual license or copyright but for example as part of an output command or
documentation, these occurrences MAY be put between two comments:
`REUSE-IgnoreStart` and `REUSE-IgnoreEnd`. The REUSE Tool then ignores all tags
within. This technique MUST NOT be used to ignore valid tags for licensing or
copyright.

An example for an ignored block:

```
# SPDX-FileCopyrightText: 2021 Jane Doe
#
# SPDX-License-Identifier: GPL-3.0-or-later

# REUSE-IgnoreStart
echo "SPDX-FileCopyrightText: $(date +'%Y') John Doe" > file.txt
echo "SPDX-License-Identifier: MIT" > file.txt
# REUSE-IgnoreEnd
```

### In-line snippet comments

If a copyright and/or licensing info is to apply only to a certain snippet
instead of the whole file, SPDX snippet tags SHOULD be used (as defined in [SPDX
Specification, Annex H](https://spdx.github.io/spdx-spec/v2.3/file-tags/#h3-snippet-tags-format)).

Such an annotated snippet block MUST start with `SPDX-SnippetBegin` to mark its
beginning and end with `SPDX-SnippetEnd` to mark the snippet's end.

Do note that SPDX snippet tags MUST start with `SPDX-Snippet`, meaning that the
correct copyright notice in a snippet is `SPDX-SnippetCopyrightText`.

Example:

```
# SPDX-SnippetBegin
# SPDX-License-Identifier: MIT
# SPDX-SnippetCopyrightText: 2022 Jane Doe <jane@example.com>

{$snippet_code_goes_here}

# SPDX-SnippetEnd
```

Snippets may nest, and this is denoted by having
`SPDX-SnippetBegin`/`SPDX-SnippetEnd` pairs within other pairs, in the same way
that parentheses nest in mathematical expressions. In the case of nested
snippets, the SPDX file tags are considered to apply to the inner-most snippet.

### DEP5

Alternatively, Copyright and Licensing Information MAY be associated with a
file through a DEP5 file. The intended use case of this method is large
directories where including a comment header in each file (or in `.license`
companion files) is impossible or undesirable.

The DEP5 file MUST be named `dep5` and stored in the `.reuse/` directory in the
root of the Project (i.e. `.reuse/dep5`).

The `License` tag MUST be followed by a valid SPDX License Expression describing
the licensing of the associated files.

The `Copyright` tag MUST be followed by a copyright notice.

An example of a DEP5 file:

```
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Upstream-Name: Project
Upstream-Contact: Jane Doe <jane@example.com>
Source: https://example.com/jane/project

Files: po/*
Copyright: 2019 Translation Company
License: GPL-3.0-or-later
```

## Format of copyright notices

A copyright notice MUST be prefixed by a tag, symbol or word denoting a
copyright notice as described in this specification.

The copyright notice MUST contain the name of the copyright holder. The
copyright notice SHOULD contain the year of publication and the contact address
of the copyright holder. The order of these items SHOULD be: year, name, contact
address.

The year of publication MAY be a single year, multiple years, or a span of
years.

The copyright holder MAY be an individual, list of individuals, group, legal
entity, or any other descriptor by which one can easily identify the
copyright holder(s).

Any contact address SHOULD be in between angle brackets.

Examples of valid copyright notices:

```
SPDX-FileCopyrightText: 2019 Jane Doe <jane@example.com>
SPDX-FileCopyrightText: © 2019 John Doe <joe@example.com>
© Example Corporation <https://corp.example.com>
Copyright 2016, 2018-2019 Joe Anybody
Copyright (c) Alice
```
