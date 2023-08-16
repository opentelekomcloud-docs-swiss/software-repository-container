:original_name: swr_faq_0013.html

.. _swr_faq_0013:

About SWR
=========

How Many Images Can Be Stored in SWR?
-------------------------------------

SWR has no limit on the number of images. You can upload any number of images.

What Is the Bandwidth of SWR?
-----------------------------

The bandwidth of SWR dynamically changes based on actual usage.

Is SWR Charged?
---------------

The billing items of SWR include storage space and traffic. Currently, it is free of charge.

Does SWR Support Querying the CPU Architecture (x86 or Arm) of an Image?
------------------------------------------------------------------------

-  For a public image, you can log in to the SWR console, go to the image center, search for the target image, and view its details, including the architectures supported by the image.

-  For a private image, you can Run **docker inspect** **[Image name:Version name]** to query the image architecture.

*Example:* **docker inspect openjdk:7**\ *.*


.. figure:: /_static/images/en-us_image_0000001539405909.png
   :alt: **Figure 1** Example

   **Figure 1** Example
