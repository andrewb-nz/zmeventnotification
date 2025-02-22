Breaking Changes
----------------

Version 3.9 onwards
~~~~~~~~~~~~~~~~~~~~
- Hooks now add ALPR, so you need to run `sudo -H pip install -r requirements.txt` again
- See modified objectconfig.ini if you want to add ALPR. Currently works with platerecognizer.com, so you will need an API key. See hooks docs for more info

Version 3.7 onwards
~~~~~~~~~~~~~~~~~~~
- There were some significant changes to ZM (will be part of 1.34), which includes migration to Bcrypt for passwords. Changes were made to support Bcrypt, which means you will have to add additional libraries. See the installation guide.

version 3.3 onwards
~~~~~~~~~~~~~~~~~~~

- Please use ``yes`` or ``no`` instead of ``1`` and ``0`` in ``zmeventnotification.ini`` to maintain consistency with ``objectconfig.ini``
- In ``zmeventnotification.ini``, ``store_frame_in_zm`` is now ``hook_pass_image_path``

version 3.2 onwards
~~~~~~~~~~~~~~~~~~~

- Changes in paths for everything. - event server config file now defaults to ``/etc/zm`` 
- hook config now defaults to ``/etc/zm`` 
- Push token file now defaults to ``/var/lib/zmeventnotification/push`` 
- all object detection data files default to ``/var/lib/zmeventnotification``
- If you are migrating from a previous version: 
        - Make a copy of your ``/etc/zmeventnotification.ini`` and ``/var/detect/objectconfig.ini`` (if you are using hooks) 
        - Run ``sudo -H ./install.sh`` again inside the repo, let it set up all the files 
        - Compare your old config files to the news ones at ``/etc/zm`` and make necessary changes 
        - Make sure everything works well 
        - You can now delete the old ``/var/detect`` folder as well as ``/etc/zmeventnotification.ini`` 
        - Run zmNinja again to make sure its token is registered in the new tokens file (in ``/var/lib/zmeeventnotification/push/tokens.txt``)
