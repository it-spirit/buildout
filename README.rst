================================================================
General testing and development buildouts for it-spirit projects
================================================================

This repository contains a number of configuration files for using `zc.buildout <https://pypi.python.org/pypi/zc.buildout/>`_ to quickly set up a testing/development environment for your package.
The intended usage is to create a ``buildout.cfg`` like::

   [buildout]
   extends =
       https://raw.github.com/it-spirit/buildout/master/common.cfg
       https://raw.github.com/it-spirit/buildout/master/qa.cfg
       https://raw.github.com/it-spirit/buildout/master/test.cfg
   package-name = spirit.example

Running buildout should give you a ``bin/test`` script, which can be used to run your package's tests.
If your tests have additional dependencies, you should declare them via the ``extras_require`` parameter of ``setuptools.setup`` and refer to the key used using the ` package-extras`` variable::

   [buildout]
   extends =
       https://raw.github.com/it-spirit/buildout/master/common.cfg
       https://raw.github.com/it-spirit/buildout/master/qa.cfg
       https://raw.github.com/it-spirit/buildout/master/test.cfg
   package-name = spirit.example
   package-extras = [test]
