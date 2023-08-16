:original_name: swr_01_1000.html

.. _swr_01_1000:

Obtaining a Long-Term Valid Login Command
=========================================

Scenario
--------

This section describes how to obtain a login command that is valid for a year.

.. note::

   For security purposes, it is advised to obtain the login command in the development environment.

Process
-------

You can obtain a long-term valid login command as the following process:


.. figure:: /_static/images/en-us_image_0000001539605245.png
   :alt: **Figure 1** Process

   **Figure 1** Process

Procedure
---------

#. **Obtain the programmatic access permission. (If the current user has the permission, skip this step.)**

   a. Log in to the management console as an administrator.
   b. Click |image1| in the upper left corner and select a region and a project.
   c. Click |image2| in the navigation pane on the left and choose **Management & Governance** > **Identity and Access Management**.
   d. Enter the name of the user to whom you want to grant the programmatic access permission in the search box on the **Users** page.
   e. Click the user to go to its details page.
   f. Click |image3| next to **Access Type**.
   g. Select **Programmatic access**. (You can select only programmatic access or both access types.)

#. .. _swr_01_1000__li5768123671815:

   Obtain the region, project name, and image repository address.

   a. Log in to the management console, click your username in the upper right corner, and click **My Credentials**.
   b. On the **Projects** tab page, search for the project corresponding to the current region.
   c. Obtain the image repository address by referring to :ref:`1.b <swr_01_0011__en-us_topic_0112596104_li182568055016>`. The domain name at the end of the login command is the image repository address.

#. .. _swr_01_1000__li1863783911295:

   Obtain an AK/SK.

   .. note::

      The access key ID (AK) and secret access key (SK) are a pair of access keys used together to authenticate users who wish to make API requests. The AK/AS pair provides functions similar to a password. If you already have an AK/SK, skip this step.

   a. Log in to the management console, click your username in the upper right corner, and click **My Credentials**.
   b. On the **Access Keys** tab page, click **Add Access Key**.
   c. Enter the login password and verification code sent to your mailbox or mobile phone.
   d. Download the access key, which includes the AK and SK.

      .. note::

         Keep the access key secure and do not disclose it to any unauthorized personnel.

#. .. _swr_01_1000__li132430753010:

   Log in to a Linux PC and run the following command to obtain the login key:

   **printf "$AK" \| openssl dgst -binary -sha256 -hmac "$SK" \| od -An -vtx1 \| sed 's/[ \\n]//g' \| sed 'N;s/\\n//'**

   In the command, **$AK** and **$SK** indicate the AK and SK obtained in :ref:`Step 3 <swr_01_1000__li1863783911295>` respectively.


   .. figure:: /_static/images/en-us_image_0165729699.png
      :alt: **Figure 2** Sample command output

      **Figure 2** Sample command output

#. Put the information you obtained in the following format to generate a long-term valid login command:

   **docker login -u** [*Regional project name*]\ **@**\ [*AK*] **-p** [*Login key*] [*Image repository address*]

   In the command, the regional project name and image repository address are obtained in :ref:`Step 2 <swr_01_1000__li5768123671815>`, the AK in :ref:`Step 3 <swr_01_1000__li1863783911295>`, and the login key in :ref:`Step 4 <swr_01_1000__li132430753010>`.

   .. note::

      The login key is encrypted and cannot be decrypted. Therefore, other users cannot obtain the SK from -p.

      The login command can be used on other devices.

#. Run the **history -c** command to clear the operation records.

.. |image1| image:: /_static/images/en-us_image_0000001507688112.png
.. |image2| image:: /_static/images/en-us_image_0000001558527697.png
.. |image3| image:: /_static/images/en-us_image_0000001507528236.png
