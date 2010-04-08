# Markdoc

Markdoc is a lightweight Markdown-based wiki system. It’s geared towards
managing technical documentation, but can be used for a range of purposes. It
has a few notable selling points:

*   Wikis are made up completely of plaintext files, so you can easily put them 
    under version control.

*   Wikis compile into standalone HTML directories, which can be distributed as 
    tarballs or served by a HTTP server.

*   Set up Google Analytics tracking in one line of configuration.

*   Create barebones wikis that just look like folders containing
    Markdown-formatted text files.

*   You can optionally include static media which will be compiled into the HTML 
    directory alongside all your rendered pages.

*   Markdoc comes with a fully-functional pure-Python WSGI application and HTTP 
    server for serving up compiled wikis.

*   You can render your wiki with a variety of Markdown extensions, such as 
    Pygments-based code highlighting, extended syntax for definition lists, TOC 
    generation, et cetera.

*   You can completely customize how your wiki is rendered by editing the Jinja2
    templates used to convert rendered Markdown into full HTML documents.


Quickstart
==========

Requirements
------------

The minimum requirements to run the Markdoc utility are:

  * Python 2.4 or later (2.5+ highly recommended)
  * A UNIX (or at least POSIX-compliant) operating system
  * [rsync](http://www.samba.org/rsync/) -- installed out of the box with most modern OSes, including Mac OS X and Ubuntu. In the future Markdoc may include a pure-Python implementation.

Installation
------------

    #!bash
    $ easy_install Markdoc  # OR
    $ pip install Markdoc

Making a Wiki
-------------

    #!bash
    $ markdoc init my-wiki
    $ cd my-wiki/
    $ vim wiki/somefile.md
    # ... write some documentation ...
    $ markdoc build
    $ markdoc serve
    # .. open http://localhost:8008/ in a browser ...

Layout
======

Markdoc wikis have the following default layout:

    WIKI_ROOT/
    |-- .html/
    |-- .templates/
    |-- .tmp/
    |-- static/
    |-- wiki/
    `-- markdoc.yaml

The `.html/` and `.tmp/` directories should be excluded from any VCS, since they
contain temporary files.

Consult the layout documentation in `doc/wiki/ref/layout.md` for more
information on the roles of various subdirectories.