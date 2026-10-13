:original_name: swr_01_0026.html

.. _swr_01_0026:

Sharing Private Images
======================

Scenario
--------

You can share your **private images** with other accounts and grant the accounts permissions to pull the images.

A user under the account with which you shared the image can then log in to the SWR console to view the image by clicking **My Images** > **Images From Others**. On the tab, the user can click the target image to check its details, such as the image tag and image pull command.

.. caution::

   -  Images shared by other accounts can only be downloaded.
   -  Images are shared with all users in the target account.

Constraints
-----------

-  Only private images can be shared. Public images cannot be shared.
-  Only users authorized to manage the private images can share images. The users with whom you share your images only have the read-only permission, which only allows them to pull the images.
-  You can share images only with accounts in the same region. Cross-region image sharing is not supported.
-  A private image can be shared with a maximum of 500 tenants.

Procedure
---------

#. Log in to the SWR console.

#. In the navigation pane, choose **My Images**. Then click the name of the target image.

#. On the details page, click the **Sharing** tab.

#. Click **Share Image**. Set parameters based on :ref:`Table 1 <swr_01_0026__table15531841319>`, and click **OK**.

   .. _swr_01_0026__table15531841319:

   .. table:: **Table 1** Sharing an image

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Share With  | Enter an account name with which you want to share the image.                                                           |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Valid Until | Set a validity period. If you want the image to be permanently accessible to the account, select **Permanently valid**. |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Permission  | Only the **Pull** permission is supported currently.                                                                    |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Enter a maximum of 1,000 characters.                                                                                    |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. To view all the images that you have shared, choose **My Images** in the navigation pane, click the **Private Images** tab, and select **My shared images**.
