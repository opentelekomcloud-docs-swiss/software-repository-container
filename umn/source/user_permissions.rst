:original_name: swr_01_0015.html

.. _swr_01_0015:

User Permissions
================

Scenario
--------

To manage SWR permissions, you can use Identity and Access Management (IAM). If you have the SWR Admin or Tenant Administrator permission, you become an admin user of SWR accounts. You can grant permissions to other IAM users in SWR.

If you are not an SWR account admin user, you can request an SWR account admin user to grant you permissions to read, write, or manage a specific image or images in a specific organization.

.. note::

   -  An SWR account admin user is granted image management permission of all organizations by default, even if the user is not in the authorized user list of the organizations.
   -  SWR is deployed and accessed in specific physical regions. To assign permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect.

Authorization Method
--------------------

You can grant permissions to users in SWR by using either of the following methods:

-  :ref:`Grant permissions on an image details page <swr_01_0015__section851514354541>` to allow users to read, write, and manage a specific image.

-  :ref:`Grant permissions on an organization details page <swr_01_0015__section950354645517>` to allow users to read, write, and manage all the images in an organization.


   .. figure:: /_static/images/en-us_image_0000001200802327.png
      :alt: **Figure 1** User permissions

      **Figure 1** User permissions

You can grant the following three types of permissions to users:

-  Read: Users can only pull images.
-  Write: Users can pull and push images and edit image attributes.
-  Manage: Users can pull and push images, delete images or tags, edit image attributes, grant permissions, and share images with other users.

.. _swr_01_0015__section851514354541:

Granting Permissions for a Specific Image
-----------------------------------------

To allow users to read, write, and manage a specific image, grant corresponding permissions to them on the details page of this image.

#. Log in to the SWR console.
#. In the navigation pane, choose **My Images** and click the desired image.
#. On the image details page, click the **Permissions** tab.
#. Click **Add Permission**. On the page displayed, click **Read**, **Write**, or **Manage** in the row of the desired username. Click **OK** to confirm.

Modifying or Deleting Permissions for a Specific Image
------------------------------------------------------

You can also modify or delete user permissions on the image details page.

-  To modify permissions, click **Modify** in the row of the desired username on the **Permissions** tab page. Select a permission in the **Permission** drop-down list, and click **Save** in the **Operation** column.
-  To delete permissions, click **Delete** in the row of the desired username on the **Permissions** tab page, enter **DELETE** in the dialog box displayed, and then click **Yes**.

.. _swr_01_0015__section950354645517:

Granting Permissions for an Organization
----------------------------------------

To allow users to read, write, and manage all the images in an organization, grant corresponding permissions to them on the details page of this organization.

Only users with the **Manage** permission can grant permissions for other users.

#. Log in to the SWR console.
#. In the navigation pane, choose **Organization Management**. Then click **Details** in the row of the desired organization.
#. On the **Users** tab page, click **Add Permission**. In the dialog box displayed, select permissions for users and click **OK**.

Modifying or Deleting Permissions for an Organization
-----------------------------------------------------

You can also modify and delete user permissions of an organization.

-  To modify permissions, click **Modify** in the row of the desired username on the **Users** tab page. Select a permission in the **Permission** drop-down list, and click **Save** in the **Operation** column.
-  To delete permissions, click **Delete** in the row of the desired username on the **Users** tab page. In the dialog box displayed, enter **DELETE** and click **Yes**.
