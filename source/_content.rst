Document edit and view
----------------------

.. code:: robotframework

   Setup Document Edit And View Screenshots
       Enable autologin as  Site Administrator
       Set autologin username  ${USER_ID}

Edit document
.............

.. figure:: _screenshots/document-edit.png
.. code:: robotframework

   Capture Document Edit Screenshot
       ${uid} =  Create content  type=Document
       ...  id=new-document
       ...  title=${DUMMY_TEXT_LINE}
       ...  description=${DUMMY_TEXT_SHORT}  text=${DUMMY_TEXT}
       Fire transition  ${uid}  publish

       Go to  ${PLONE_URL}/new-document/edit
       Capture page screenshot  _screenshots/document-edit.png

View document
.............

.. figure:: _screenshots/document-view.png
.. code:: robotframework

   Capture Document View Screenshot
       Go to  ${PLONE_URL}/new-document
       Capture page screenshot  _screenshots/document-view.png

View document (anonymous)
.........................

.. figure:: _screenshots/document-anonymous-view.png
.. code:: robotframework

   Capture Document Anonymous View Screenshot
       Disable autologin
       Go to  ${PLONE_URL}/new-document
       Capture page screenshot  _screenshots/document-anonymous-view.png

.. code:: robotframework

   Teardown Document Edit And View Screenshots
       Enable autologin as  Site Administrator
       Delete content  /${PLONE_SITE_ID}/new-document
       Disable autologin

Folder edit and view
--------------------

.. code:: robotframework

   Setup Folder Screenshots
       Enable autologin as  Site Administrator
       Set autologin username  ${USER_ID}

       ${uid-folder} =  Create content  type=Folder
       ...  id=new-folder
       ...  title=${DUMMY_TEXT_LINE}
       ...  description=${DUMMY_TEXT_SHORT}
       Fire transition  ${uid-folder}  publish
       Go to  ${PLONE_URL}/new-folder
       Capture page screenshot  _screenshots/folder-edit.png

       ${uid} =  Create content  type=Document
       ...  container=${uid-folder}
       ...  id=document-1
       ...  title=${DUMMY_TEXT_LINE}
       ...  description=${DUMMY_TEXT_SHORT}  text=${DUMMY_TEXT}
       Fire transition  ${uid}  publish

       ${uid} =  Create content  type=Document
       ...  container=${uid-folder}
       ...  id=document-2
       ...  title=${DUMMY_TEXT_LINE}
       ...  description=${DUMMY_TEXT_SHORT}  text=${DUMMY_TEXT}
       Fire transition  ${uid}  publish

       ${uid} =  Create content  type=Document
       ...  container=${uid-folder}
       ...  id=document-3
       ...  title=${DUMMY_TEXT_LINE}
       ...  description=${DUMMY_TEXT_SHORT}  text=${DUMMY_TEXT}
       Fire transition  ${uid}  publish

Edit folder
...........

.. figure:: _screenshots/folder-edit.png
.. code:: robotframework

   Capture Edit Folder Screenshot

       Go To  ${PLONE_URL}/new-folder/edit
       Capture page screenshot  _screenshots/folder-edit.png

Folder contents
...............

.. figure:: _screenshots/folder-contents-view.png
.. code:: robotframework

   Capture Folder Contents Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_contents
       Capture page screenshot  _screenshots/folder-contents-view.png

Folder summary view
...................

.. figure:: _screenshots/folder-summary-view.png
.. code:: robotframework

   Capture Folder Summary Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_summary_view
       Capture page screenshot  _screenshots/folder-summary-view.png

Folder full view
................

.. figure:: _screenshots/folder-full-view.png
.. code:: robotframework

   Capture Folder Full View Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_full_view
       Capture page screenshot  _screenshots/folder-full-view.png

Folder tabular view
...................

.. figure:: _screenshots/folder-tabular-view.png
.. code:: robotframework

   Capture Folder Tabular View Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_tabular_view
       Capture page screenshot  _screenshots/folder-tabular-view.png

Folder album view
.................

.. figure:: _screenshots/folder-album-view.png
.. code:: robotframework

   Capture Folder Album View Screenshot

       Go To  ${PLONE_URL}/new-folder/atct_album_view
       Capture page screenshot  _screenshots/folder-album-view.png

Folder listing view
...................

.. figure:: _screenshots/folder-listing-view.png
.. code:: robotframework

   Capture Folder Listing Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_listing
       Capture page screenshot  _screenshots/folder-listing-view.png

Folder summary view (anonymous)
...............................

.. figure:: _screenshots/folder-anonymous-summary-view.png
.. code:: robotframework

   Capture Anonymous Folder Summary Screenshots
       Disable autologin

       Go To  ${PLONE_URL}/new-folder/folder_summary_view
       Capture page screenshot  _screenshots/folder-anonymous-summary-view.png

Folder full view (anonymous)
............................

.. figure:: _screenshots/folder-anonymous-full-view.png
.. code:: robotframework

   Capture Anonymous Folder Full View Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_full_view
       Capture page screenshot  _screenshots/folder-anonymous-full-view.png

Folder tabular view (anonymous)
...............................

.. figure:: _screenshots/folder-anonymous-tabular-view.png
.. code:: robotframework

   Capture Anonymous Folder Tabular View Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_tabular_view
       Capture page screenshot  _screenshots/folder-anonymous-tabular-view.png

Folder album view (anonymous)
.............................

.. figure:: _screenshots/folder-anonymous-album-view.png
.. code:: robotframework

   Capture Anonymous Folder Album View Screenshot

       Go To  ${PLONE_URL}/new-folder/atct_album_view
       Capture page screenshot  _screenshots/folder-anonymous-album-view.png

Folder listing view (anonymous)
...............................

.. figure:: _screenshots/folder-anonymous-listing-view.png
.. code:: robotframework

   Capture Anonymous Folder Listing Screenshot

       Go To  ${PLONE_URL}/new-folder/folder_listing
       Capture page screenshot  _screenshots/folder-anonymous-listing-view.png

Search and sitemap
------------------

Search result
.............

.. figure:: _screenshots/search.png
.. code:: robotframework

   Capture Search Screenshots
       Go To  ${PLONE_URL}/@@search?SearchableText=Plone
       Capture page screenshot  _screenshots/search.png

Sitemap
.......

.. figure:: _screenshots/sitemap.png
.. code:: robotframework

   Capture Sitemap Screenshots
       Go To  ${PLONE_URL}/sitemap
       Capture page screenshot  _screenshots/sitemap.png


.. code:: robotframework

   Teardown Content Screenshots
       Enable autologin as  Site Administrator
       Delete content  ${PLONE_SITE_ID}/new-folder
       Disable autologin
