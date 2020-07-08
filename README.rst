buildtest-stampede2
=====================

This repository contains the the test suite to be run with buildtest for `Stampede2 <https://www.tacc.utexas.edu/systems/stampede2>`_ at TACC. To get started first
`install buildtest <https://buildtest.readthedocs.io/en/devel/installing_buildtest.html>`_ in your user account, then proceed with cloning this repository.

To get started you can clone the repository via `git` or `buildtest repo` command.

::

  git clone https://github.com/buildtesters/buildtest-stampede2


::

  buildtest repo add git@github.com:buildtesters/buildtest-stampede2.git


Next copy the ``.buildtest/settings.yml`` file provided in this repo into ``$HOME/.buildtest/settings.yml``. Once you are done, you can do a few preliminary 
steps to check your setup is valid.

1. Validating buildtest configuration 

::

  (buildtest) login2.stampede2(1034)$ buildtest config validate
  /home1/06908/sms1990/.buildtest/settings.yml is valid


2. Confirm ``buildtesters/buildtest-stampede2`` is an active repository

::

  (buildtest) login2.stampede2(1035)$ buildtest repo list
  buildtesters/buildtest-stampede2


3. Find and validate all buildspecs for buildtesters/buildtest-stampede2

::

  buildtest buildspec find


Building Test
---------------

To build test you will need to use ``buildtest build -b <buildspec>`` you may want to review `Getting Started Guide <https://buildtest.readthedocs.io/en/devel/getting_started.html>`_ to
get familiar with the client tool.

To build & run all buildspecs in ``system`` directory, you can do the following::

  $ buildtest build -b system

You may build individual buildspec by specifying a file path for example::

  $ buildtest build -b system/dns.yml
  
References
------------

- buildtest documentation: https://buildtest.readthedocs.io/en/devel/

- buildtest schema docs: https://buildtesters.github.io/schemas/
