PHPDocumentor MarkDown export
=============================

This script will generate markdown (.md) API documentation files from a
PHPDocumentor XML output file.

It only documents classes and interfaces.

This project was originally developed by [Evert Pot](https://twitter.com/evertp).
See his [repo](https://github.com/evert/phpdoc-md) for more details.

Installation
------------

This project assumes you have composer installed.

```bash
$ composer require dcramble/phpdoc-md "~0.1"
```


Usage
-----

First ensure that phpdocumentor 2 is installed somewhere, after, you must
generate a file called `structure.xml`.

The easiest is to create a temporary directory, for example named `docs/` as
phpDocumentor2 creates a lot of 'cache' directories.

    # phpdoc command
    mkdir docs
    cd docs
    phpdoc  -d [project path] -t . --template="xml"
    rm -r phpdoc-cache-*

    # Next, run phpdocmd:
    phpdocmd structure.xml [outputdir]

Options
-------

    --lt [template]
        This specifies the 'template' for links we're generating. By default
        this is "%c.md".
    
    --namespaced-names
        This specifies the fully qualified classes, with namespaces, should
        be printed.

This should generate all the .md files.


