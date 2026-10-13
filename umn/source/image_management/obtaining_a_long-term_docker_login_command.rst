:original_name: swr_01_1000.html

.. _swr_01_1000:

Obtaining a Long-Term Docker Login Command
==========================================

Scenario
--------

This section describes how to obtain a Docker login command that is valid for a year.

Process
-------

You can obtain a long-term valid login command as the following process:


.. figure:: /_static/images/en-us_image_0000001539605245.png
   :alt: **Figure 1** Process

   **Figure 1** Process


Obtaining a Long-Term Docker Login Command
------------------------------------------

#. .. _swr_01_1000__li122491614174210:

   Obtain the programming access permission. (If you already have the programming access permission, skip this step.)

   a. Log in to the management console as an administrator.
   b. Click |image1| in the upper left corner and select a region and a project.
   c. Click |image2| in the navigation pane on the left and choose **Management & Deployment** > **Identity and Access Management**.
   d. On the **Users** page, enter the target username in the search box.
   e. Click the username to go to its details page.
   f. Click next to **Access Type**.
   g. Select **Programmatic access**. (You can select only programmatic access or both access types.)

#. .. _swr_01_1000__li1863783911295:

   Obtain an AK/SK. (If you already have an AK/SK, skip this step.)

   .. note::

      The access key ID (AK) and secret access key (SK) are a pair of access keys used together to authenticate API requests. The AK/SK pair functions similarly to a password. If you already have an AK/SK pair, skip this step.

   a. Log in to the management console, click your username in the upper right corner, and click **My Credentials**.
   b. On the **Access Keys** tab, click **Add Access Key**.
   c. Enter the login password and verification code sent to your mailbox or mobile phone.
   d. Download the access key, which includes the AK and SK.

      .. note::

         Keep the access key secure and do not disclose it to any unauthorized personnel.

#. Log in to the SWR console.

#. Click **Generate Login Command**. On the **Long-Term Login Command** tab, click **Import Access Keys** to upload **credentials.csv** or enter the **Access Key ID** and **Secret Access Key** contained in **credentials.csv** obtained in :ref:`Step 2 <swr_01_1000__li1863783911295>`. Click **Generate Command**. No further action is required. If the **Long-Term Login Command** tab is not displayed on the console, skip this step and manually combine the long-term login command.

#. .. _swr_01_1000__li5768123671815:

   Obtain the region, project name, and image repository address.

   a. Log in to the management console, click your username in the upper right corner, and click **My Credentials**.
   b. On the **Projects** tab, search for the project corresponding to the current region.
   c. Obtain the image repository address by referring to :ref:`1.b <swr_01_0011__li753764116129>`. The domain name at the end of the login command is the image repository address.

#. .. _swr_01_1000__li132430753010:

   Log in to a Linux PC and run the following command to obtain a login secret:

   **printf "$AK" \| openssl dgst -binary -sha256 -hmac "$SK" \| od -An -vtx1 \| sed 's/[ \\n]//g' \| sed 'N;s/\\n//'**

   In the command, *$AK* and *$SK* indicate the AK and SK obtained in :ref:`Step 2 <swr_01_1000__li1863783911295>`.


   .. figure:: /_static/images/en-us_image_0165729699.png
      :alt: **Figure 2** Sample command output

      **Figure 2** Sample command output

#. Put the information you obtained in the following format to generate a long-term valid login command:

   **docker login -u** [*Regional project name*]\ **@**\ [*AK*] **-p** [*Login key*] [*Image repository address*]

   In the command, the regional project name and image repository address are obtained in :ref:`Step 5 <swr_01_1000__li5768123671815>`, the AK in :ref:`Step 2 <swr_01_1000__li1863783911295>`, and the login key in :ref:`Step 6 <swr_01_1000__li132430753010>`.

   .. note::

      -  The login key is encrypted and cannot be decrypted. Therefore, other users cannot obtain the SK from -p.
      -  The login command can be used on other devices.

#. Run the **history -c** command to clear the operation records.

Obtaining a Long-Term Push/Pull Command for containerd
------------------------------------------------------

#. Obtain programmatic access permission. To do so, perform the following steps:

   a. Log in to the IAM console as an administrator.
   b. Click |image3| in the upper left corner and select a region and a project.
   c. On the **Users** page, enter the target username in the search box.
   d. Click the username to go to its details page. Click |image4| next to **Access Type**. Select **Programmatic access**. (You can also select both access types.)

#. .. _swr_01_1000__en-us_topic_0000001188003789_li27781149939:

   Obtain an AK/SK pair. If you already have one, skip this step.

   .. note::

      Ensure you have permission to access the IAM service.

   a. Log in to the IAM console, hover over the username, and click **My Credentials**.
   b. In the navigation pane, choose **Access Keys** and click **Create Access Key**.
   c. Enter a description and click **OK**.
   d. In the displayed dialog box, click **Download**.
   e. After the credential file is downloaded, obtain the AK/SK from **credentials.csv**.

      .. table:: **Table 1** Example of credentials.csv

         =========== ================ ===================
         *User Name* *Access Key Id*  *Secret Access Key*
         =========== ================ ===================
         ``a*****``  ``RVHVMX******`` ``H3nPwzgZ******``
         =========== ================ ===================

      .. note::

         Each credential file can be downloaded only once. Keep it secure.

#. .. _swr_01_1000__en-us_topic_0000001188003789_li1217103521711:

   Obtain the project name and image repository address.

   a. Log in to the IAM console.
   b. Hover over the username in the upper right corner.
   c. Choose **My Credentials** from the drop-down list.
   d. In the project list, find the region and project your VM belongs to.
   e. Obtain the image repository address by referring to :ref:`1.b <swr_01_0011__li753764116129>`. The domain name at the end of the login command is the image repository address.

#. .. _swr_01_1000__en-us_topic_0000001188003789_li921335121719:

   Log in to a Linux PC and run the following command to obtain a login secret:

   .. code-block::

      printf "$AK" | openssl dgst -binary -sha256 -hmac "$SK" | od -An -vtx1 | sed 's/[ \n]//g' | sed 'N;s/\n//'

   Replace **AK** with the access key ID and **SK** with the secret access key from **credentials.csv** obtained in :ref:`Step 2 <swr_01_1000__en-us_topic_0000001188003789_li27781149939>`.

   Example:

   .. code-block::

      printf "RVHVMX******" | openssl dgst -binary -sha256 -hmac "H3nPwzgZ******" | od -An -vtx1 | sed 's/[ \n]//g' | sed 'N;s/\n//'

   After execution, the following login secret is returned:

   .. code-block::

      cab4ceab4a1545***************

   .. note::

      The login secret shown above is an example only.

#. Concatenate the obtained information to form long-term valid pull and push commands.

   1. Image pull command

   .. code-block::

      ctr image pull --user [project-name]@[AK]:[login-secret] [image-repository-address]/{organization-name}/{image-name}:{tag}

   In this command, the project name and image repository address are obtained in :ref:`Step 3 <swr_01_1000__en-us_topic_0000001188003789_li1217103521711>`, the AK is the *Access Key Id* field in the **credentials.csv** file obtained in :ref:`Step 2 <swr_01_1000__en-us_topic_0000001188003789_li27781149939>`, and the login secret is the execution result in :ref:`Step 4 <swr_01_1000__en-us_topic_0000001188003789_li921335121719>`.

   2. Image push command

   .. code-block::

      ctr image push --user [project-name]@[AK]:[login-secret] [image-repository-address]/{organization-name}/{image-name}:{tag}

   In this command, the project name and image repository address are obtained in :ref:`Step 3 <swr_01_1000__en-us_topic_0000001188003789_li1217103521711>`, the AK is the *Access Key Id* field in the **credentials.csv** file obtained in :ref:`Step 2 <swr_01_1000__en-us_topic_0000001188003789_li27781149939>`, and the login secret is the execution result in :ref:`Step 4 <swr_01_1000__en-us_topic_0000001188003789_li921335121719>`.

   .. note::

      -  The login key is encrypted and cannot be decrypted back into an SK.
      -  These commands can be executed on other containerd clients to pull and push images.

.. |image1| image:: /_static/images/en-us_image_0000001507688112.png
.. |image2| image:: /_static/images/en-us_image_0000001558527697.png
.. |image3| image:: /_static/images/en-us_image_0000002684107496.png
.. |image4| image:: /_static/images/en-us_image_0000002713827197.png
