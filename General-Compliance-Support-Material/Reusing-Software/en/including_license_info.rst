.. title: Including license information
.. subtitle: Help users and developers by making it easy

:Contact: info@commonsconservancy.org
:Copyright: 2017, The Commons Conservancy
:SPDX-License-Identifier: CC0-1.0
:Date: 2017-09-27

Including license information into your source code is important, in a number
of way. There have been great advances in this area in the last couple of
years. It used to lack uniformity, but things are becoming more and more
structured, reliable and convenient. 

While certainly there is some work involved, it does make a lot of sense if you
want your software to be picked up and used by many.  You may need to get used
to it once, but then the modern way of working makes things *a lot* less
ambiguous and thus simpler.

Actually, if you think about how companies have to deal with thousands upon
thousands of applications, all with their own licenses - and that some
companies have to employ lawyers to make sure that they comply with all the
license conditions - you may appreciate the fact that doing this work one time
upstream is better for everyone.  

Actually it is just a few simple steps. In most cases you should be done in ten
minutes, with the knowledge that you've just saved all of your future
users time. In this how-to we take you throough these steps. If
something is unclear, let us know!

.. contents:: Basic steps

We will go through each of these steps one by one.

.. sectnum::

Add the license to individual source files
------------------------------------------

Step one is adding the license to the individual source files (all of
them).

The preferred (and shortest) option is to include a SPDX license identifier
near the top of every file (after a short description of the title of the
project and its function):

.. code::

  # Copyright: 2017, The Commons Conservancy eduVPN Programme
  # SPDX-License-Identifier: GPL-3.0+

SPDX is a simple unified format for licenses that is short and
machine-readable. The latter is *very* important for compliance management, the
first is of course great for keeping the amount of cruft low.

Note that you use // , {- , <-- --> or whatever instead of hashes for comments,
depending on your programming language. 

Feel free to use whatever conventions you know for making comments more
readable, although we advise to keep the copyright statement on one line and
the license identifier on one line as well if you can.

.. code:: 

  /**
   * eduVPN - End-user friendly VPN
   *
   * Copyright: 2017, The Commons Conservancy eduVPN Programme
   * SPDX-License-Identifier: GPL-3.0+
   *
   */

Do note that "2017" is actually a range: **[year file created]-[last year file
modified]**. If both are the same, they SHOULD be collapsed. Next year however,
it would be "2017-2018", etc.

Include the full human readable version(s) in your repository
-------------------------------------------------------------

Step two is to include the **human readable version** (for instance the full
text of the GPLv3) in the top level of the project repository. Put it in a file
named LICENSE. 

We suggest you download the file from its canonical source, or a known source
like https://opensource.org/licenses .  

Obviously, otherwise, a source from which you copy the file may have
reformatted, wrongly copied  or even edited (parts of) the text. By taking the
original license text, you avoid all of those issues. Note that in some cases,
editing the license itself is actually not allowed.  However, even knowing
that, spare yourself and your users the energy and cost they would incur if
some abberation triggers manual inspection.

In the case of the GPLv3, the location of the original license would
be:

  http://www.gnu.org/licenses/gpl-3.0.txt

If you have multiple licenses on the same code base, you can either (in order
of preference) create a folder called LICENSE and include the canonical texts
there, use a the SPDX identifier as the name suffix for the individual files
(e.g.  LICENSE.GPLv3Plus, LICENSE.BSD3) and put these alongside each other in
the top level of your project repository, or concatenate multiple license into
a single file name LICENSE.

Don't forget to add the same copyright holder information from step 1 here to
the license texts too.

Create a SPDX file
------------------

Step three is to create an SPDX (text) file called LICENSE.spdx with at least
something like the following content:

.. code:: 

  SPDXVersion: SPDX-2.1
  DataLicense: CC0-1.0
  PackageName: eduVPN
  DataFormat: SPDXRef-1
  PackageSupplier: Organization: The Commons Conservancy eduVPN Programme
  PackageHomePage: https://eduvpn.org
  PackageLicenseDeclared: GPL-3.0+
  PackageCopyrightText: 2017, The Commons Conservancy eduVPN Programme
  PackageSummary: <text>EduVPN is designed to allow users to connect
  securely and encrypted to the Internet from any standard device.
                  </text>
  PackageComment: <text>The package includes the following libraries; see
  Relationship information.
                  </text>
  Created: 2017-06-06T09:00:00Z
  PackageDownloadLocation: git://github.com/eduVPN/reponame
  PackageDownloadLocation: git+https://github.com/eduVPN/reponame.git
  PackageDownloadLocation: git+ssh://github.com/eduVPN/reponame.git
  Creator: Person: Jane Doe 
  

Note that you'd change "github.com/eduVPN/reponame" into whatever the name of
your repo is, and that PackageComment should list any stuff you get from
elsewhere. If there is externally licenced code going in there, this needs to
be declared.

(For most, this will be the simplest notation. You could also use RDF/XML
format if you'd prefer. The syntax for both can be found here:
https://spdx.org/spdx-specification-21-web-version)

For future reference, the overview of SPDX licenses is here:

  https://spdx.org/licenses/

A nice tutorial is here:

  https://github.com/david-a-wheeler/spdx-tutorial

(Optional) Include license info in the package description
----------------------------------------------------------

Many programming languages have their own package management systems.
Obviously, it is helpful to have the license information in the package
description, if you were to create one.

This allows users to automatically find your project when they are looking for
solutions with specific licenses. Each languague may have different packaging
solutions, and the syntaxes may vary. Check the documentation.

See for instance:

- [PYTHON] https://packaging.python.org/tutorials/distributing-packages/
- [HASKELL] https://www.haskell.org/cabal/users-guide/developing-packages.html
- [RUST] http://doc.crates.io/manifest.html

Put it in your contributor description
--------------------------------------

New files that get added over time don't automatically get the right copyright
info added. Putting your preferred method into the document in which you
describe how new developers can board the project, will help them to pick up
your best practises.




