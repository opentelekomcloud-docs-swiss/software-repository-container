:original_name: swr_03_0003.html

.. _swr_03_0003:

Basic Concepts
==============

Image
-----

Images are like templates that include everything needed to run applications. When deploying containerized applications, you can use images from the Docker image center and your private image registries. For example, an image can contain a complete Ubuntu operating system, in which only the required programs and dependencies are installed. Docker images are used to create Docker containers. Docker provides an easy way to create and update your own images. You can also pull images created by other users.

Container
---------

A container is a running instance of a Docker image. Multiple containers can run on one node. Containers are actually software processes. Unlike traditional software processes, containers have separate namespaces and do not run directly on a host.

Images become containers at runtime, that is, containers are created from images. Containers can be created, started, stopped, deleted, and suspended.

Repository
----------

Image repositories are used for storing Docker images. An image repository hosts different versions of a specific containerized application.

Organization
------------

Organizations are used to isolate image repositories. With each organization being limited to one company or department, images can be managed in a centralized and efficient manner. A user can access different organizations as long as the user has corresponding permissions. Different permissions, namely read, write, and manage, can be assigned to different users in the same account.


.. figure:: /_static/images/en-us_image_0195122694.png
   :alt: **Figure 1** Organization

   **Figure 1** Organization
