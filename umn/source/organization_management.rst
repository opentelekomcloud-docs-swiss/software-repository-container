:original_name: swr_01_0014.html

.. _swr_01_0014:

Organization Management
=======================

Scenario
--------

Organizations enable efficient management of images. Organizations are used to isolate image repositories. With each organization being limited to one company or department, images can be managed in a centralized and efficient manner. An image name needs to be unique within an organization. The same user can access different organizations as long as the user has sufficient permissions, as shown in :ref:`Figure 1 <swr_01_0014__fig1924953913304>`.

You can grant different permissions, namely, read, write, and manage, to users created by the same account. For details, see :ref:`User Permissions <swr_01_0015>`.

.. _swr_01_0014__fig1924953913304:

.. figure:: /_static/images/en-us_image_0000001154801774.png
   :alt: **Figure 1** Organization

   **Figure 1** Organization

.. _swr_01_0014__section12921632181415:

Creating an Organization
------------------------

You can create organizations based on the organizational structure of your enterprise to facilitate image resource management. Create an organization before you push an image.

#. Log in to the SWR console.

#. In the navigation pane on the left, choose **Organization Management** and click **Create Organization**. On the page displayed, specify **Organization Name** and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001361826817.png
      :alt: **Figure 2** Creating an organization

      **Figure 2** Creating an organization

   .. note::

      -  The organization name must be globally unique. If a message is displayed indicating that the organization already exists, the organization name may have been used by another user. Use another organization name.
      -  After a tenant is deleted, residual organization resources may exist. In this case, the message indicating that the organization already exists could also be displayed when you create an organization. Use another organization name.

Viewing the Images of an Organization
-------------------------------------

After you create an organization and push images to it, you can view the image list of the organization.

#. Log in to the SWR console.

#. In the navigation pane, choose **Organization Management**. On the page displayed, click the desired organization name in the list.

#. To view the images of this organization, click the **Images** tab.


   .. figure:: /_static/images/en-us_image_0000001609224706.png
      :alt: **Figure 3** Viewing the images of an organization

      **Figure 3** Viewing the images of an organization

Deleting an Organization
------------------------

Before deleting an organization, delete all the images in the organization.

#. Log in to the SWR console.
#. In the navigation pane, choose **Organization Management**. On the page displayed, click the desired organization name in the list.
#. Click |image1|, and then click **Yes**.

.. important::

   Before you delete a tenant, delete its organizations first; otherwise, residual organization resources may exist. When you create an organization that has the same name with the residual organization, a message is displayed indicating that the organization already exists.

.. |image1| image:: /_static/images/en-us_image_0000001589705241.png
