arCHMage
========

arCHMage is a reader and decompiler for files in the CHM format.  This is the
format used by Microsoft HTML Help, and is also known as Compiled HTML.

[![Latest Version](https://pypip.in/version/archmage/badge.svg)](https://pypi.python.org/pypi/archmage/)
[![Downloads](https://pypip.in/download/archmage/badge.svg)](https://pypi.python.org/pypi/archmage/)
[![License](https://pypip.in/license/archmage/badge.svg)](https://pypi.python.org/pypi/archmage/)

Usage
=====

Extract CHM content into directory
----------------------------------

    archmage -x <chmfile> [output directory]

Extraction does not overwrite existing directories.

Dump HTML data from CHM
-----------------------

    archmage -d <chmfile>

Convert CHM file into another format
------------------------------------

    archmage -c (html|text|pdf) <chmfile> [output file]

This feature requires `htmldoc(1)`, and `lynx(1)` or `elinks(1)` installed.

Serve CHM contents over HTTP
----------------------------

    archmage -p <port> <chmfile|dir with chm files>

Serve CHM contents from Apache
------------------------------

TODO: document how to proxy Apache to running `archmage -p`.

Then `http://youserver/sample.chm` will serve raw CHM file, and
`http://yourserver/sample.chm/` will serve unpacked CHM file view.

Installation
============

arCHMage requires the following libraries:

  * Python >= 2.3
  * PyCHM
  * Beautiful Soup

Optional dependencies:

  * htmldoc - converting to plain text, single HTML, PDF formats
    (Debian/Ubuntu: `htmldoc`)
  * Lynx or ELinks - converting to plain text
    (Debian/Ubuntu: `lynx`)

Use the regular `setup.py` stanza:

    python setup.py install
