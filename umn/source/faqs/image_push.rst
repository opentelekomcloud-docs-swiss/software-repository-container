:original_name: swr_faq_0039.html

.. _swr_faq_0039:

Image Push
==========

How Do I Push an Image to SWR by Calling an API?
------------------------------------------------

Currently, SWR does not provide an API for pushing images. You can push images using a container engine client.

Can I Push Arm-based Container Images to SWR?
---------------------------------------------

SWR has no restriction on the kernel architecture of images. There is no difference between pushing an Arm-based image and an x86-based image to SWR.

What Protocol Is Used to Push Images to SWR When I Run the docker push Command?
-------------------------------------------------------------------------------

HTTPS is used.

Will an Existing Image Be Overwritten If I Push an Image That Has the Same Name and Tag with It?
------------------------------------------------------------------------------------------------

Yes. The existing image will be overwritten.

What Is the Maximum Size of an Image Layer?
-------------------------------------------

If you use the container engine client to push images to SWR, each image layer cannot exceed 50 GB.

What Is the Rate Limit for a Tenant to Push Images over the Internet?
---------------------------------------------------------------------

To avoid mutual interference between tenants when they push SWR images, the image push traffic for a single tenant is limited to 20 QPS. The traffic exceeding this value will be blocked. In this case, Docker will receive 503 and automatically retry the traffic control request.

Does SWR Support Resumable Image Push?
--------------------------------------

No.

What Can I Do If the Upload Is Slow or Suspended Due to Unstable Internet Connections When I Push Images to SWR over the Internet?
----------------------------------------------------------------------------------------------------------------------------------

You can adjust OS parameters to optimize the upload speed.

**Application scenario**: Linux kernel 4.9 or later (such as EulerOS 2.9, HCE 2.0, Ubuntu 18, and Rocky Linux 8+)

**Procedure**

#. Log in to the target host where the image is to be uploaded and switch to the **root** user.
#. Run the following commands to optimize network transmission performance:

.. code-block::

   # Set the default queueing discipline (qdisc) of the network core to fair queuing.
   sysctl -w net.core.default_qdisc=fq
   # Configure TCP congestion control algorithm parameters in the Linux kernel.
   sysctl -w net.ipv4.tcp_congestion_control=bbr
   # Set the size of the TCP send buffer in the Linux kernel.
   sysctl -w net.ipv4.tcp_wmem="4096 163840 41943040"

What Do I Do If the Error Message "ERR_BLOB_OUT_OF_MEMORY" Is Displayed When I Push Images in Batches?
------------------------------------------------------------------------------------------------------

**Symptom**:

A user clicked the **Upload** button on the SWR console to push multiple image packages in batches, the error message "(failed)net::ERR_BLOB_OUT_OF_MEMORY" was displayed, indicating that the upload failed.

|image1|

**Solution**:

-  Clear the browser cache.

   #. Close the current browser tab.
   #. Clear the browser cache, including cookies and site data.
   #. Open the browser again and log in to the SWR console.
   #. Push the images again.

-  For large images, push them through the client. For details, see .

.. |image1| image:: /_static/images/en-us_image_0000002587371450.png
