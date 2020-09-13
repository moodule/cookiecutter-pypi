.. _console-script-setup:


Console Script Setup
=================

Optionally, your package can include a console script using Click or argparse (Python 3.2+).

How It Works
------------

Cookiecutter will add a file '__main__.py' in the project_slug subdirectory,
pointing to the main function.

Usage
------------
To use the console script in development:

.. code-block:: bash

    $ cd projectdir
    $ poetry install

'projectdir' should be the top level project directory with the setup.py file

The script will be generated with output for no arguments and --help.

--help
    show help menu and exit

More Details
------------

You can read more about Click at:
http://click.pocoo.org/
