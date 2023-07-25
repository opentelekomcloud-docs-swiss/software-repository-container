:original_name: swr_01_0006.html

.. _swr_01_0006:

Basics of the Container Engine
==============================

The container engine, namely, Docker, is an open-source engine which allows you to create a lightweight, portable, and self-sufficient container for any application. SWR is compatible with Docker, allowing you to use Docker CLI and APIs to manage your images.

Installing Docker
-----------------

Before installing Docker, get a basic understanding of what Docker is and how it works. For more information, see `Docker Documentation <https://docs.docker.com>`__.

Docker is compatible with almost all operating systems. Select a Docker version that best suits your needs. If you are not sure which Docker community edition to use, see https://docs.docker.com/engine/install/.

.. note::

   -  Before using SWR to store container images, ensure that the Docker client used to push images to SWR is updated to 1.11.2 or later.
   -  Bind an elastic IP address first if your server runs in a private network as the installation requires Internet connection.

On a device running Linux, run the following commands to quickly install Docker:

.. code-block::

   curl -fsSL get.docker.com -o get-docker.sh
   sh get-docker.sh
   sudo systemctl daemon-reload
   sudo systemctl restart docker

Building a Container Image
--------------------------

This section walks you through the steps of using a Dockerfile to build a container image for a simple web application. Dockerfile is a text file that contains all the instructions a user can call on the command line to build an image. A container image is a stack consisting of multiple layers. Each instruction creates a layer.

When using a browser to access a containerized application built from a Nginx image, you will see the default Nginx welcome page. In this section, you will build a new image based on the Nginx image to change the welcome message to **Hello, SWR!**

#. Log in to the device running Docker as a root user.

#. Run the following commands to create an empty file named **Dockerfile**:

   **mkdir mynginx**

   **cd mynginx**

   **touch Dockerfile**

#. Edit Dockerfile.

   **vim Dockerfile**

   Add the following instructions to the Dockerfile:

   .. code-block::

      FROM nginx
      RUN echo '<h1>Hello,SWR!</h1>' > /usr/share/nginx/html/index.html

   In the preceding instructions:

   -  **FROM**: creates a layer from the base image. A valid Dockerfile must start with a **FROM** instruction. In this example, the **Nginx** image is used as the base image.
   -  **RUN**: executes a command to create a new layer. One of its syntax forms is RUN <command>. In this example, the **echo** command is executed to display **Hello, SWR!**

   Save the changes and exit.

#. Run **docker build** [*option*] <*context path*> to build an image.

   **docker build -t nginx:v1 .**

   -  **-t nginx:v1**: specifies the image name and tag.
   -  **.**: indicates the path where the Dockerfile is located. All contents in this path are packed and sent to the Docker to build an image.

#. Run the following command to check the created image. The command output shows that the nginx image has been created with a tag of v1.

   **docker images**

Creating an Image Package
-------------------------

This section describes how to compress a container image into a .tar or .tar.gz package.

#. Log in to the device running Docker as a root user.

#. Run the following command to list images.

   **docker images**

   Check the name and tag of the image to be compressed.

#. Run the following command to compress the image into a package.

   **docker save [OPTIONS] IMAGE [IMAGE...]**

   .. note::

      **OPTIONS**: You can set this to **--output** or **-o**, indicating that the image is exported to a file.

      The file should be in either .tar or .tar.gz.

   Sample:

   .. code-block::

      $ docker save nginx:latest > nginx.tar
      $ ls -sh nginx.tar
      108M nginx.tar

      $ docker save php:5-apache > php.tar.gz
      $ ls -sh php.tar.gz
      372M php.tar.gz

      $ docker save --output nginx.tar nginx
      $ ls -sh nginx.tar
      108M nginx.tar

      $ docker save -o nginx-all.tar nginx
      $ docker save -o nginx-latest.tar nginx:latest

Importing an Image File
-----------------------

This section describes how to import an image package as an image using the **docker load** command.

There are two modes:

**docker load <** **Path/File name.tar**

**docker load --input** **Path/File name.tar** or **docker load -i** **Path/File name.tar**

Sample:

.. code-block::

   $ docker load --input fedora.tar
