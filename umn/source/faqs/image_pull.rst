:original_name: swr_faq_2005.html

.. _swr_faq_2005:

Image Pull
==========

How Do I Pull an Image from SWR by Calling an API?
--------------------------------------------------

Currently, SWR does not provide an API for pulling images. You can use a container engine client to pull images. For Docker, run **docker pull**. For containerd, run **crictl pull**.

Where Are the Images Pulled by docker pull Stored?
--------------------------------------------------

Images pulled by running the **docker pull** command are stored on your local host. You can run the **docker save** command to save images into TAR archive files.

Can I Pull Images on the SWR Console to a Local PC?
---------------------------------------------------

Images stored in SWR cannot be directly downloaded through the console. You can perform the following operations to pull the images:

#. Obtain the image pull command on the image details page.

#. Run the obtained command on the device where the Docker client is installed.

#. Save the image as a TAR or TAR.GZ file.

   Example:

   **docker save** **nginx:v1** **>** **nginx.tar**

#. Download the file to the local host.

What Are the Possible Causes of Slow Image Pull?
------------------------------------------------

#. The network is abnormal.
#. There are multiple image layers.
#. Image pull tasks are serially executed. A task cannot be executed until the previous task is complete. The timeout interval for a pull task is 30 minutes.

Will a Pulled Image Overwrite an Existing Image with the Same Name and Tag?
---------------------------------------------------------------------------

If they have the same manifest, the existing image will not be overwritten. Otherwise, it will be overwritten.
