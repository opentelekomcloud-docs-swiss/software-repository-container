:original_name: swr_01_0072.html

.. _swr_01_0072:

Configuring IAM Permissions
===========================

This section describes how to use for fine-grained permission management on your SWR resources. With IAM, you can:

-  Create IAM users for employees based on your enterprise's organizational structure. Each IAM user will have their own security credentials for accessing SWR resources.
-  Grant only the permissions required for users to perform a specific task.
-  Entrust a cloud account or cloud service to perform efficient O&M on your SWR resources.

If your account does not need individual IAM users, you may skip this section.

This section describes the procedure for granting permissions (see :ref:`Figure 1 <swr_01_0072__fig5293113815405>`).

Prerequisites
-------------

Learn about the permissions supported by SWR and choose policies or roles based on your requirements.

Process Flow
------------

.. _swr_01_0072__fig5293113815405:

.. figure:: /_static/images/en-us_image_0000001127297210.png
   :alt: **Figure 1** Process for granting SWR permissions

   **Figure 1** Process for granting SWR permissions

#. .. _swr_01_0072__li8135822590:

   Create a user group and assign permissions.

   Create a user group on the IAM console and assign the **SWR Admin** policy to the group.

#. Create an IAM user and add the user to a user group.

   Create a user on the IAM console and add the user to the group created in :ref:`1 <swr_01_0072__li8135822590>`.

#. Log in as the IAM user and verify permissions.

   Log in to the management console as the created user. Switch to the authorized region. Perform the following operations. If they can be successfully performed, the permissions are successfully granted.

   a. Choose **Service List** > **Software Repository for Container**. The SWR console is displayed.
   b. In the navigation pane on the left, choose **Organization Management**, click **Create Organization** in the upper right corner, and enter an organization name to create an organization.
   c. In the navigation pane on the left, choose **My Images**, click **Upload Through Client** in the upper right corner. Select the organization created in the previous step and a local image file. The image is successfully uploaded.
