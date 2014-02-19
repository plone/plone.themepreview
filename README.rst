==================
plone.themepreview
==================

**plone.themepreview** is a special Selenium and Robot Framework -powered
Sphinx-documentation base to take screenshots tour of your Plone in various
browser window sizes to highlight each theme's responsive design.


Demo
====

To try **plone.themepreview** with Plone 4.3's *plonetheme.sunburst*, try (with
Firefox installed):

.. code:: bash

   $ git clone https://github.com/plone/plone.themepreview
   $ cd plone.themepreview
   $ python bootstrap.py
   $ bin/buildout
   $ bin/sphinx-build -b html source build

After Sphinx has finished its build, you should have a beautifully looking
Plone screenshots in your *build*-directory, similar to:

* http://collective.themetest.s3-website-us-east-1.amazonaws.com/latest/


Usage
=====

You can use **plone.themepreview** with your custom Plone-themes by either
parametrizing **plone.themepreview**'s buildout to include your theme package
or by merging its buildout into your packages' own buildout.

**plone.themepreview** creates a Plone sandbox with your theme by re-using a
special test layer provided in *plone.app.robotframework* called
``plone.app.robotframework.testing.PLONE_ROBOT_TESTING``. This ayer can be
extended to include your theme add-on by providing two special environment
variables:

* ``ROBOT_CONFIGURE_PACKAGES``, which should equals a comma separated list of
  packages, whose ``configure.zcml`` should read during test layer's
  **setUpZope**-phase.

* ``ROBOT_APPLY_PROFILES``, which accepts a comma separated list of profiles,
  which should be imported during test layer's **setUpPloneSite**-phase.


Examples
========

diazotheme.bootstrap
--------------------

Uses **plone.themepreview**'s buildout:

- **Integration:** https://github.com/datakurre/diazotheme.bootstrap/compare/kagesenshi:0150ee0582bd2c0527a3f78ad5559fdda5eef473...master

- **Preview:** http://diazotheme.bootstrap.s3-website-us-east-1.amazonaws.com/latest/


plonetheme.onegov
-----------------

Merges **plone.themepreview**'s buildout into its own:

* Integration: https://github.com/datakurre/plonetheme.onegov/compare/OneGov:bc2e6e5066a25ed77b282df95493f4023d211ec9...master

* Preview: http://plonetheme.onegov.s3-website-us-east-1.amazonaws.com/latest/


Misc
====

You can speed up themepreview development cycle with robot-server, by

.. code:: bash

   $ bin/robot-server plone.app.robotframework.testing.PLONE_ROBOT_FIXTURE -v

and then running an individual Sphinx-page as a Robot Framework test
suite with

.. code:: bash

   $ bin/robot source/mobile

.. note::

   When **plone.themepreview**'s Sphinx documents are run through Robot
   Framework for capturing screenshots, the sandbox is being reset only once
   for each Sphinx document (this is different from normal acceptance tests
   where each tests is run in isolation; it would be possible to reset the
   sandbox for each test, but in Sphinx's context is make sense to reset the
   sandbox only when document changes).

