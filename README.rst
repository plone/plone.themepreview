plone.themepreview
==================

*plone.themepreview* is a special Selenium and Robot Framework -powered
Sphinx-documentation base to take screenshots tour of your Plone with various
browser window sizes.

Demo
----

To try *plone.themepreview* with Plone 4.3, try (with Firefox installed):

.. code:: bash

   $ git clone https://github.com/plone/plone.themepreview
   $ cd plone.themepreview
   $ python bootstrap.py
   $ bin/buildout
   $ bin/sphinx-build -b html source build

After Sphinx has finished its build, you should have a beautifully looking
Plone screenshots in your *build*-directory, similar to:

* http://collective.themetest.s3-website-us-east-1.amazonaws.com/artifacts/18/18.1/

Usage
-----

You can use *plone.themepreview* with your custom Plone-themes by either
parametrizing *plone.themepreview*'s buildout to include your theme package
or by merging the buildout into your own.

*plone.themepreview* creates a Plone sandbox with your theme by re-using a
special test layer provided in *plone.app.robotframework*. The layer can be
extended to include your theme add-on by providing two special environment
variables:

* *ROBOT_CONFIGURE_PACKAGES* can be give a comma separated list of packages,
  whose *configure.zcml* should read during test layer's *setUpZope*-phase.

* *ROBOT_APPLY_PROFILES* can be give a comma separated list of profiles,
  which should be imported during test layer's *setUpPloneSite*-phasee.

Examples
--------

- diazotheme.bootstrap (uses *plone.themepreview*'s buildout directly):

  * integration: https://github.com/datakurre/diazotheme.bootstrap/compare/kagesenshi:0150ee0582bd2c0527a3f78ad5559fdda5eef473...master
  * preview: http://diazotheme.bootstrap.s3-website-us-east-1.amazonaws.com/artifacts/1/1.1/

- plonetheme.onegov (merges *plone.themepreview*'s buildout into its own):

  * integration: https://github.com/datakurre/plonetheme.onegov/compare/OneGov:bc2e6e5066a25ed77b282df95493f4023d211ec9...master
  * preview: http://plonetheme.onegov.s3-website-us-east-1.amazonaws.com/artifacts/7/7.1/
