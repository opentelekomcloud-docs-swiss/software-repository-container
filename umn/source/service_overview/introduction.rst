:original_name: swr_03_0001.html

.. _swr_03_0001:

Introduction
============

SoftWare Repository for Container (SWR) allows you to easily manage the full lifecycle of container images and facilitates secure deployment of images for your applications.

SWR can either work with CCE or be used as an independent container image repository.

|image1|

Features
--------

-  **Full lifecycle management of images**

   SWR manages the entire lifecycle of your container images, such as image push, pull, and deletion.

-  **Private image repository and access control**

   SWR provides private image repositories and fine-grained permission management, allowing you to grant different access permissions (read, edit, and manage) to different users.

-  **Large-scale image pull acceleration**

   SWR uses the image pull acceleration technology to ensure faster image pull for CCE clusters in high concurrency scenarios.

Accessing SWR
-------------

The cloud platform provides a web-based management console and HTTPS-based APIs through which you can access SWR.

-  Using APIs

   If you want to integrate SWR into a third-party system for secondary development, use APIs to access SWR. For details, see *SoftWare Repository for Container API Reference*.

-  Using the management console

   For other operations, access SWR through the management console.

.. |image1| image:: /_static/images/en-us_image_0000002533953233.png
