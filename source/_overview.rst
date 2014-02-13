Overview
--------

Front page
..........

.. figure:: _screenshots/front-page.png
.. code:: robotframework

   Capture Front Page Screenshot
       Go to  ${PLONE_URL}
       Capture page screenshot  _screenshots/front-page.png

Accessibility information
.........................

.. figure:: _screenshots/accessibility.png
.. code:: robotframework

   Capture Accessibility Screenshots
       Go To  ${PLONE_URL}/accessibility-info
       Capture page screenshot  _screenshots/accessibility.png

Contact information form
........................

.. figure:: _screenshots/contact-info.png
.. code:: robotframework

   Capture Contact Form Screenshots
       Go To  ${PLONE_URL}/contact-info
       Capture page screenshot  _screenshots/contact-info.png
