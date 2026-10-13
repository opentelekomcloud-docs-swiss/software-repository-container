:original_name: swr_01_0015.html

.. _swr_01_0015:

Image Authorization Management
==============================

Scenario
--------

To manage SWR permissions, you can use Identity and Access Management (IAM). If you have the SWR Admin or Tenant Administrator permission, you become an admin user of SWR accounts. You can grant permissions to other IAM users in SWR.

To push an image, you must have edit or manage permissions. To pull a private image, you must have read, edit, or manage permissions. To pull a public image, no permissions are required.

.. note::

   -  An SWR account admin user is granted image management permission of all organizations by default, even if the user is not in the authorized user list of the organizations.
   -  SWR is deployed and accessed in specific physical regions. To assign permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect.

If you lack SWR administrator permissions, ask an SWR administrator to grant you access to a specific image or to all images in an organization.

Authorization Method
--------------------

You can grant permissions to users in SWR by using either of the following methods:

-  :ref:`Grant permissions on the image details page <swr_01_0015__section851514354541>` to allow users to read, edit, and manage a specific image.

-  :ref:`Grant permissions on the organization details page <swr_01_0015__section950354645517>` to allow users to read, edit, and manage all images in the organization.


   .. figure:: /_static/images/en-us_image_0000002658308592.png
      :alt: **Figure 1** User permissions

      **Figure 1** User permissions

You can grant the following three types of permissions to users:

-  Read: Users can only pull images.
-  Edit: Users can pull and push images and edit image attributes.
-  Manage: Users can pull and push images, delete images or tags, edit image attributes, grant permissions, and share images with other users.

.. _swr_01_0015__section851514354541:

Granting Permissions for a Specific Image
-----------------------------------------

To allow users to read, edit, and manage a specific image, grant corresponding permissions to them on the image details page.

#. Log in to the SWR console.
#. In the navigation pane, choose **My Images**. Then click the name of the target image.
#. On the image details page, click the **Permissions** tab.
#. Click **Grant Permission**. Select **Read/Edit/Manage** next to the user name to grant corresponding permissions.

Modifying or Deleting Permissions for a Specific Image
------------------------------------------------------

You can also modify or delete user permissions on the image details page.

-  Modifying permissions: On the **Permissions** tab, click **Edit** in the row of the desired username. Select permissions from the **Permission** drop-down list and click **Save** in the **Operation** column.
-  Deleting permissions: On the **Permissions** tab, click **Delete** in the row of the desired username, enter **DELETE** in the dialog box displayed, and then click **OK**.

.. _swr_01_0015__section950354645517:

Granting Permissions for an Organization
----------------------------------------

To allow users to read, edit, and manage all the images in an organization, grant corresponding permissions to them on the details page of this organization.

Only users with the **Manage** permission can grant permissions for other users.

#. Log in to the SWR console.
#. In the navigation pane, choose **Organizations**. On the **Organizations** page, click **Users** under the organization to be authorized.
#. On the **Users** tab, click **Grant Permission**. In the dialog box displayed, select permissions for users and click **OK**.

Modifying or Deleting Permissions for an Organization
-----------------------------------------------------

You can also modify or delete user permissions of an organization.

-  Modifying permissions: On the **Users** tab, click **Edit** in the row of the desired username. Select permissions from the **Permission** drop-down list and click **Save** in the **Operation** column.
-  Deleting permissions: On the **Users** tab, click **Delete** in the row of the desired username, enter **DELETE** in the dialog box displayed, and then click **OK**.
