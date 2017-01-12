# Spinx
  * Sphinx adds to reStructuredText a way to connect multiple files to a single hierarchy of documents.

## Install Spinx

  1. Prerequisites
    1. Python 2.7
    1. Python 3.4
    1. [docutils] (http://docutils.sourceforge.net/)
      ´´´ sudo apt-get install docutils ´´´

    1. [Jinja2] (http://jinja.pocoo.org/)
      ´´´ pip install Jinja2 ´´´

    1. [Pygments] (http://pygments.org/)
      ´´´ pip install Pygments ´´´


  1. Sphinx Core
    ´´´ sudo apt-get install python-sphinx ´´´

    MAYBE
    ´´´ pip install Sphinx ´´´


## Set Up Sphinx

  1. General Documentation Structure
    * conf.py: Source DIR
    * index.srt: Master DOC
      * serves as startpage
      * contains the root of the Table of Contents Tree (toctree)
      * documents to include are given as document names (use slashes as directory separators)




  1. cd into Project DIR
    ´´´ cd /home/usr/.../docs ´´´

  1. sphinx-quickstart [[options] [projectdir]](http://www.sphinx-doc.org/en/1.5.1/invocation.html#invocation-apidoc)
    ´´´ sphinx-quickstart ´´´

    * builds docs/source/config.py file

    ´´´ > Root path for documentation [.]: -> ENTER
        > Separate source and build directories (y/n) [n]: y
        > Name prefix for templates and static dir [_]: -> ENTER
        > Project name: knowledge-base
        > Author name(s): tbu-rtd
        > Project version []: 0.0.1
        > Project release [0.0.1]: -> ENTER
        > Project language [en]: -> ENTER
        > Source file suffix [.rst]: -> ENTER
        > Name of your master document (without suffix) [index]: -> ENTER
        > Do you want to use the epub builder (y/n) [n]: -> ENTER
        ...
    ´´´

  docs
    build
      doctrees
      html
        source
        static
    source
  








  1. 

## Use Sphinx

  1. toctree
    * combines the seperate files into one documentation
    * ´´´
        .. toctree::
           :maxdepth: 2

           intro
           tutorial
           ...
      ´´´

  1. build

    ´´´ sphinx-build -b html sourcedir builddir ´´´

    ´´´ make html ´´´




