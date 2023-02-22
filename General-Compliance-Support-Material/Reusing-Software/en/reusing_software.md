# Reusing Software

This document is based on reuse.software, a project launched by FSFE, and redistributed under CC-0 with their kind permission.

<!--START_HTML-->

<h2>Summary</h2>

<table>
  <tr>
    <td>
     <img alt="1. " src="/img/one_sm.png" />
    </td>
    <td>Provide the exact text of each license used, in verbatim form, without removing any existing license texts. <a href="#one">[read more]</a>
    </td>
  </tr>
  <tr>
    <td>
     <img alt="2. " src="/img/two_sm.png" />
    </td>
    <td>
      Include a copyright notice and license in each file, with a consistent style, with a reference to the license text and an appropriate SPDX License Identifier. <a href="#two">[read more]</a>
    </td>
  </tr>
  <tr>
    <td>
     <img alt="3. " src="/img/three_sm.png" />
    </td>
    <td>
     Provide an inventory for included software, but only if you can generate it automatically! <a href="#three">[read more]</a>
    </td>
  </tr>
</table>

<div style="margin: 6em;"></div>
<!--END_HTML-->

# Best practices

<a name="one"></a>
## 1. Provide the exact text of each license used
Free and open source software licenses are standardised and have standard
texts. Regardless of which license you use, you should include the
license text in your project. You should also include the license text of
any code which may be under a different license, and it's important you
do not change the license text on other software you include.

If the license you use is included in the SPDX License List[^1], you
should download and copy the text representation of the license
directly from the SPDX repository[^2]. Doing so ensures that unless you modify
the license text, the checksum of the license file will be identical across
all projects using the same license.

If your project only includes code licensed under a single license, you
may provide the text of this license in a file in the top level directory
of your repository with the name "LICENSE" (you may attach some suffix
to the filename as well, such as LICENSE.md, if relevant).

Since many projects include code under different licenses, it's often not
feasible to include all licenses in the top level, in which case you should
create a directory at the top level called "LICENSES" within which you
include the license text of each license used.

You must include all licenses which are used in your project, and you must
never change any license texts even if they are very similar to existing ones.
Some licenses, like the BSD 2 Clause license, must be
adapted to include the name of the copyright holder in the license
text. Your project may end up including multiple versions of the same
BSD 2 Clause license because some parts may be written by Alice and others
by Bob, resulting in two different license files, even if the only
difference is the copyright holder.

This is how your source code tree can end up looking regarding the license
files included:

~~~~~~~
  LICENSES/
           GPL-2.0.txt
           BSD-2-Clause_Alice.txt
           BSD-2-Clause_Bob.txt
~~~~~~~

Keep in mind:

 * Don't change any license texts, use the verbatim form of the license text
 * Don't remove any license texts, include the license texts of all software
 * Keep the filename of the licenses consistent, so you can refer to it
   from the source code files (see the following practice)

[^1]: https://spdx.org/licenses/
[^2]: https://github.com/spdx/license-list

<a name="two"></a>
## 2. Include a copyright notice and license in each file
You should ensure all files in your project have a license header, and
that all license headers files have the same format. Even if your project has a
license header which looks different from other projects, it helps to have
a consistent style to the header. It's important you do not remove
information in existing headers, though.

Source code files are often reused across multiple projects, taken from their
origin and repurposed, or otherwise end up in repositories where they are
separate from its origin. Each file should, therefore,
have enough information in itself to convey copyright 
information.

You may record information about copyright by relying on the underlying
version control system you're using, but special care must be taken if you
do. Keep in mind that version control systems typically record authorship,
not copyright. When using metadata in a version control system, you may end up having
more accurate information, but you increase the risk of the information being
separated from the source code.

For a project using the version control system to convey information about
copyright, you must:

 * make sure the version control system is publicly accessible and take
   steps[^3] to ensure it will remain so,
 * provide a link back to the original file in version control from each header,
 * ensure that if someone copies the source repository without version
   control system metadata (such as if they make a tar-file of it),
   then the version control system metadata relevant for determining
   copyright must still be included,
   for example in the form of a bill of material (see later), an
   automatically generated log file or similar,
 * make sure the commit metadata reflect the actual copyright
   (this is particularly important if a project accepts code contributed
   through mailing lists, bug trackers, or similar, where the original
   copyright holder is not the one pushing code to version control, or
   where the copyright is held by an organisation rather than the author.)

An appropriate header could be:

~~~~~~~
 /*
  * This file is part of project X. It's copyrighted by the contributors
  * recorded in the version control history of the file, available from
  * its original location http://git.example.com/X/filename.c
  * 
  * SPDX-License-Identifier: BSD-2-Clause
  * License-Filename: LICENSE/BSD-2-Clause_Charlie.txt
  */
~~~~~~~

If the project is not using a version control system to convey copyright
information, the same information should be included in the source
code file. Notices should have a consistent format and be sorted
by year. They should list the actual copyright holder, which may be
an organisation rather than the author.

~~~~~~~
 /*
  * Copyright (c) 2017 Alice Commit <alice@example.com>
  * Copyright (c) 2009-2016 Bob Denver <bob@example.com>
  * Copyright (c) 2007 Company Example <charlie@example.com>
  * 
  * SPDX-License-Identifier: BSD-2-Clause
  * License-Filename: LICENSE/BSD-2-Clause_Charlie.txt
  */
~~~~~~~

The "License-Filename" tag shall be a persistent URL or a filename in
the repository where the actual license text is available. This is more
accurate than the SPDX license identifier and ensures the full license
text is always referenced from the individual source file. The tag can
be repeated if multiple license files are relevant.

You should include information about your project's practices in the
README or similar file.

If your project includes binaries or source code files in which
comments can not be placed, you should provide them separately. We
recommend one of two ways:

 * If you have files with different copyright notices and licenses, you should, for each file named FILENAME, include the text file "FILENAME.license" which includes a copyright header according to the format you customarily use for headers.
 * If you have many such files, but each have the same copyright notice and license, you may instead use the [DEP-5/copyright](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/) file format, and place a single copyright file documenting those files.

If you wish to be explicit about the license of an output file, which does
not exist in the repository but which will be created at build time, you
may include a .license file without the corresponding binary file.

Keep in mind:

 * Use a consistent style of your headers throughout the project
 * Don't remove existing headers, but only add to them
 * Do consider using version control systems to keep a record of copyright holders
 * Do keep your version control system public if you use it
 * Make references to the license text and the SPDX identifier from each source code file
 * Include license and copyright information also for files which can not include a proper header, either in a separate .license file, or using the DEP-5/copyright specification.

[^3]: Establish project governance committed to public access, vet material added to project to protect against vulnerability to takedown, only include material under a free and open source license so it can be copied and archived freely and ensure project is archived by institutions dedicated to long-term preservation of software code, eg. Software Heritage.


<a name="three"></a>
## 3. Provide an inventory for included software
Aside from the license files included in the project, and the file level
copyright information, you may include a bill of material for your project,
but you should only do so if this is generated automatically.

A bill of material can be very complicated and lengthy, making it difficult to
maintain. If you do not generate it automatically, it's very likely someone
will forget to update it when making changes. In these cases, it's best not
to have a bill of material, but to rely only on the information coupled
with the source code files.

If you do have a way of automatically creating a bill of material, and if
you choose to do so, you should generate it automatically from
the most reliable information you have about each file in your project.
This includes copyright information kept in version control systems and
licenses on files which include a standard header, or which includes
the header in a separate license file.

You may also choose to include in the bill of material your output files
generated when compiling the project, such that you can signal through the
bill of material, which license is relevant for the output files depending
on the included source code.

The bill of material should be conformant to the SPDX specification and
included in a file in the top level directory of your repository called
"LICENSE.spdx".

Keep in mind:

 * Don't create a bill of material if you can't generate it automatically
 * If you generate one automatically, it's helpful to include one
 * Make your bill of material conformant to the SPDX specification
 * It doesn't hurt to run your project through ScanCode or FOSSology, to make sure these tools can parse and understand your project's licensing.

<br style="margin: 10em;" />