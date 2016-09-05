.. The LIONtoolkit project - http://liontoolkit.org/
  
  Authors:
  Andrea Mariello <andrea.mariello@unitn.it>
  Marco Zugliani <marco.zugliani@studenti.unitn.it>
  Mauro Brunato <mauro.brunato@unitn.it>
  Roberto Battiti <roberto.battiti@unitn.it>
  
  License:
  This Source Code Form is subject to the terms of the Mozilla Public
  License, v. 2.0. If a copy of the MPL was not distributed with this
  file, You can obtain one at http://mozilla.org/MPL/2.0/.

LIONtoolkit - How to Install
============================

Dependencies
------------

LIONtoolkit is tested to work under *Python 3.5*, *Debian 8 (Jessie)* and *Ubuntu 14.04 (Trusty)*. Anyway, it should work on any Debian-based distribution as well as other Linux/Unix distributions where it is possible to install Python 3.5 and NumPy.
It has not been directly tested on macOS/Mac OS X and Windows.
Should you have any issues with dependencies, we recommend you to run LIONtoolkit through a *Docker* container, which is tested to work exactly the same on Linux, Mac and Windows, with all the necessary requirements already satisfied.

The required Python packages to build and run the software are listed in `requirements.txt <https://github.com/liontoolkit/liontoolkit/blob/master/requirements.txt>`_.
If you wish/need to install them before the actual LIONtoolkit installation (e.g. when you install from source) and you have *pip* installed, you can use the following command in order to resolve any secondary dependencies::

  $ pip install -r requirements.txt

..

*Optional*
  For running the tests you also need *nose* and its plugin *nose-cov*.
  You can install them with::
  
    $ pip install -r requirements-test.txt

Install and run
---------------

Run inside a *Docker* container (recommended)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install Docker for your platform following the instructions `here <https://docs.docker.com/engine/getstarted/step_one/>`_.
*No need to install other dependencies.*

*Optional for Windows/Mac users*
  For a more solid installation and use, we invite you to configure Docker in order to reserve at least 2 GBs of RAM for the Linux VM. Increase this number in case you are going to use LIONtoolkit intensively. See how to do that for `Windows <https://docs.docker.com/docker-for-windows/#advanced>`_ or for `Mac <https://docs.docker.com/docker-for-mac/#preferences>`_.

Once Docker is installed and running, by using any kind of terminal (the Linux Console, the Mac Terminal, the Windows PowerShell etc.), you can pull our image *before* launching a new container with::

  $ docker pull liontoolkit/liontoolkit

That command will search and download to your machine the *latest* image hosted at the `Docker Hub <https://hub.docker.com/r/liontoolkit/liontoolkit/>`_. That repository contains also information about the `Build Details <https://hub.docker.com/r/liontoolkit/liontoolkit/builds/>`_, the `Dockerfile <https://hub.docker.com/r/liontoolkit/liontoolkit/~/dockerfile/>`_ and all the available `Tags <https://hub.docker.com/r/liontoolkit/liontoolkit/tags/>`_.

*Optional*
  In case you need a different tag (e.g. a different version or the development version), use this command (the default tag is *latest*)::
  
    $ docker pull liontoolkit/liontoolkit:<your tag here>

To effectively start using LIONtoolkit, you have to launch a new container with the latest version of our image, so type the following::

  $ docker run -d -p 8080:5000 liontoolkit/liontoolkit

That command will search for the latest version of our image and will download it in case you have not already pulled its most recent version by using the commands described above. After that, a new container is created in *detached* mode (-d) and with its *exposed* port 5000 *mapped* to the port 8080 of your machine (but you can choose a different port).

Now, as long as the container is up and running, you can use LIONtoolkit by pointing your browser to::

  http://localhost:8080 or http://127.0.0.1:8080

To stop the execution and then restart from that point, you can use::

  $ docker stop <LIONtoolkit container ID or name here>
  $ docker start <LIONtoolkit container ID or name here>

But if you want to stop and remove the container to start all over again with *docker run*, you should use::

  $ docker stop <LIONtoolkit container ID or name here>
  $ docker rm <LIONtoolkit container ID or name here>

..

*Optional*
  You can give a memorable name to your container using the *--name* option for *docker run*::
  
    $ docker run -d -p 8080:5000 --name <your name here> liontoolkit/liontoolkit

..

*Optional*
  To easily share files between the LIONtoolkit container and your file system (e.g. to make your data accessible by LIONtoolkit and viceversa), we provide a *volume* that can be mounted with this command::
  
    $ docker run -d -p 8080:5000 -v </your/directory/here>:/home/liontoolkit/workspace liontoolkit/liontoolkit
  
  This command mounts your directory (*/your/directory/here*) into the container at the predefined location (*/home/liontoolkit/workspace*). After that, you can copy and paste files from/to your directory to make LIONtoolkit see them.
  
..

*Optional*
  You can start the container in *interactive* mode with the options *-it* instead of *-d*::
  
    $ docker run -it -p 8080:5000 liontoolkit/liontoolkit
  
  That will attach you to the LIONtoolkit log until you type *Ctrl+c* to stop the application. Then, to leave and stop the container, you should enter the *exit* command.
  
  You can also start the container without launching LIONtoolkit. The following command, for example, launch the *bash* program (e.g. to inspect the internals)::
  
    $ docker run -it -p 8080:5000 liontoolkit/liontoolkit bash
  
  Then, if you want to start LIONtoolkit from within the container, you can just enter *liontoolkit*.
  Finally, if you want to exit the interactive mode leaving the container in detached mode (without stopping it), you should type *Ctrl+p+q*.

For more information on Docker and its commands and options, look at the `Docker Documentation <https://docs.docker.com/>`_

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

