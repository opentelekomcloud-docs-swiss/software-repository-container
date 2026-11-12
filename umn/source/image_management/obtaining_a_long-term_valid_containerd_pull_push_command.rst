:original_name: swr_01_1001.html

.. _swr_01_1001:

Obtaining a Long-Term Valid containerd Pull/Push Command
========================================================

Scenario
--------

This section describes how to obtain a containerd pull/push command that is permanently valid.

.. note::

   -  For security purposes, you are advised to obtain the commands in a development environment.

   -  Ensure that you have permission to access the IAM service.

Procedure
---------

#. Obtain the programmatic access permission by referring to :ref:`Step 1 <swr_01_1000__li122491614174210>`.

#. Obtain the resource space name, image repository address, AK, and login key by referring to :ref:`Step 5 <swr_01_1000__li5768123671815>` to :ref:`Step 6 <swr_01_1000__li132430753010>`.

#. Concatenate the obtained information to form a long-term valid containerd command.

   1. Image pull command

   **ctr image pull --user** *[Resource space name]* **@**\ *[AK]*\ **:** *[Login key]* *[Image repository address]*

   In the command, the resource space name and image repository address are obtained in :ref:`Step 5 <swr_01_1000__li5768123671815>`, the AK in :ref:`Step 2 <swr_01_1000__li1863783911295>`, and the login key in :ref:`Step 6 <swr_01_1000__li132430753010>`.

   2. Image push command

   **ctr image push --user** *[Resource space name]* **@**\ *[AK]*\ **:** *[Login key]* *[Image repository address]*

   In the command, the resource space name and image repository address are obtained in :ref:`Step 5 <swr_01_1000__li5768123671815>`, the AK in :ref:`Step 2 <swr_01_1000__li1863783911295>`, and the login key in :ref:`Step 6 <swr_01_1000__li132430753010>`.

   .. note::

      -  The login key is encrypted and cannot be decrypted into an SK.
      -  The commands can be executed on other containerd clients to pull and push images.
