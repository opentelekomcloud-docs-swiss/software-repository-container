:original_name: swr_01_0014.html

.. _swr_01_0014:

Organization Management
=======================

Scenario
--------

Organizations enable efficient management of images. Organizations are used to isolate image repositories. With each organization being limited to one company or department, images can be managed in a centralized and efficient manner. An image name needs to be unique within an organization. The same user can belong to different organizations, as shown in :ref:`Figure 1 <swr_01_0014__fig1924953913304>`.

You can grant different permissions (read, edit, or manage) to users created under the same account. For details, see :ref:`Image Authorization Management <swr_01_0015>`.

.. _swr_01_0014__fig1924953913304:

.. figure:: /_static/images/en-us_image_0000001154801774.png
   :alt: **Figure 1** Organization

   **Figure 1** Organization

.. _swr_01_0014__section12921632181415:

Creating an Organization
------------------------

You can create organizations based on the organizational structure of your enterprise to facilitate image resource management. Create an organization before you push an image.

#. Log in to the SWR console.

#. In the navigation pane, choose **Organizations**. Click **Create Organization** in the upper right corner. On the page displayed, specify **Name** and click **OK**.

   |image1|

   .. note::

      -  The organization name must be globally unique. If a message is displayed indicating that the organization already exists, the organization name may have been used by another user. Use another organization name.
      -  After a tenant is deleted, residual organization resources may exist. In this case, the message indicating that the organization already exists could also be displayed when you create an organization. Use another organization name.
      -  The organization name cannot be **library**, which is reserved for the system.

Viewing the Images of an Organization
-------------------------------------

After you create an organization and push images to it, you can view the images in the organization.

#. Log in to the SWR console.

#. In the navigation pane, choose **Organizations**. On the page displayed, click the desired organization name in the list.

#. To view the images of the current organization, click the **Images** tab.

   |image2|

Deleting an Organization
------------------------

Before deleting an organization, delete all the images in the organization.

#. Log in to the SWR console.
#. In the navigation pane, choose **Organizations**. On the page displayed, click the desired organization name in the list.
#. Click |image3| and then click **Yes**.

.. important::

   Before deleting a tenant, delete all associated organizations first; otherwise, residual organization resources may remain. If you subsequently create an organization with the same name as a residual organization, an error message indicates that the organization already exists.

.. |image1| image:: /_static/images/en-us_image_0000002502354718.png
.. |image2| image:: /_static/images/en-us_image_0000002534035407.png
.. |image3| image:: /_static/images/en-us_image_0000001667904456.png
