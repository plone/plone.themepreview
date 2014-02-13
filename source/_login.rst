Login and logout
----------------

Login form
..........

.. figure:: _screenshots/login.png
.. code:: robotframework

   Capture Login Form Screenshot
       Disable autologin
       Go to  ${PLONE_URL}/login
       Capture page screenshot  _screenshots/login.png

Login failed
............

.. figure:: _screenshots/login-failed.png
.. code:: robotframework

   Capture Login Failed Screenshot
       Go to  ${PLONE_URL}/login
       Input text  __ac_name  invalid username
       Input text  __ac_password  invalid password
       Click Button  Log in
       Page should contain button  Log in
       Capture page screenshot  _screenshots/login-failed.png

Login successful
................

.. figure:: _screenshots/login-successful.png
.. code:: robotframework

   Capture Login Successful Screenshot
       Go to  ${PLONE_URL}/login
       Input text  __ac_name  ${SITE_OWNER_NAME}
       Input text  __ac_password  ${SITE_OWNER_PASSWORD}
       Click Button  Log in
       Page should not contain button  Log in
       Capture page screenshot  _screenshots/login-successful.png

Logout successful
.................

.. figure:: _screenshots/logout-successful.png
.. code:: robotframework

   Capture Logout Successful Screenshot
       Go to  ${PLONE_URL}/logout
       Capture page screenshot  _screenshots/logout-successful.png
