|CircleCI|_ |Coveralls|_ |Python35|_ |License|_ |Release|_ |PyPI|_ |DockerImage|_

.. |CircleCI| image:: https://img.shields.io/circleci/project/liontoolkit/liontoolkit.svg
.. _CircleCI: https://circleci.com/gh/liontoolkit/liontoolkit

.. |Coveralls| image:: https://coveralls.io/repos/github/liontoolkit/liontoolkit/badge.svg
.. _Coveralls: https://coveralls.io/github/liontoolkit/liontoolkit

.. |Python35| image:: https://img.shields.io/badge/python-3.5-blue.svg
.. _Python35: https://docs.python.org/3.5/

.. |License| image:: https://img.shields.io/github/license/liontoolkit/liontoolkit.svg
.. _License: https://mozilla.org/MPL/2.0/

.. |Release| image:: https://img.shields.io/github/release/liontoolkit/liontoolkit.svg
.. _Release: https://github.com/liontoolkit/liontoolkit/releases/latest

.. |PyPI| image:: https://img.shields.io/pypi/v/liontoolkit.svg
.. _PyPI: https://pypi.python.org/pypi/liontoolkit

.. |DockerImage| image:: https://img.shields.io/docker/automated/liontoolkit/liontoolkit.svg
.. _DockerImage: https://hub.docker.com/r/liontoolkit/liontoolkit

LIONtoolkit
===========

LIONtoolkit is a web application that allows data science enthusiasts
to create and run experiments involving machine learning and optimization
techniques via a simple browser-based drag-and-drop interface.

It is an idea and is currently maintained by the people at `LIONlab <http://lionlab.org/>`_, University of Trento - Italy, and it is distributed under the terms and conditions of the `Mozilla Public License, v. 2.0 <https://mozilla.org/MPL/2.0/>`_.

Dependencies
------------

LIONtoolkit is tested to work under Python 3.5 and Ubuntu...

The required dependencies to build and run the software are *Flask*...
You can install them with::

  $ pip install -r requirements.txt

For running the tests you need *nose* and its plugin *nose-cov*.
You can install them with::

  $ pip install -r requirements-test.txt

Install and run
---------------

Run inside a *Docker* container (recommended)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install Docker for your platform following the instructions `here <https://docs.docker.com/engine/getstarted/step_one/>`_.
No need to install other dependencies.

Once Docker is installed and running, pull our image and launch a new container with::

  $ docker run -d -p 8080:5000 liontoolkit/liontoolkit

and point your browser to::

  http://localhost:8080

Install from PyPI with *pip*
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install with::

  $ pip install liontoolkit

Run with::

  $ ...

and point your browser to::

  http://localhost:5000

Install from source with *setuptools*
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

From within the source directory, install with::

  $ python setup.py install

Run with::

  $ ...

and point your browser to::

  http://localhost:5000

For more detailed installation instructions,
see `docs/install.rst <https://github.com/liontoolkit/liontoolkit/blob/master/docs/install.rst>`_.

Testing
-------

You can launch the test suite from within the
source directory just with::

  $ nosetests

If you want also a code coverage report::

  $ nosetests --with-coverage --cover-inclusive

Finally, if you have already had the software installed, you can launch the test suite
from outside the source directory in this way::

  $ nosetests liontoolkit

Contributing
------------

We welcome all contributions. Do you like liontoolkit and want to make it better?
You can fix some bugs or add your own plugin/module!

And before opening a Pull Request, please have a look at `docs/extending.rst <https://github.com/liontoolkit/liontoolkit/blob/master/docs/extending.rst>`_ to make sure your code complies with our guidelines.

Thank you!
