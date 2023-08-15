:original_name: swr_01_0017.html

.. _swr_01_0017:

Pulling an Image
================

Scenario
--------

You can run the **docker pull** command to pull images from SWR.

Procedure
---------

#. Log in to the VM running the container engine as the **root** user.

#. Obtain a login command by referring to :ref:`Step 1 <swr_01_0011__en-us_topic_0112596104_en-us_topic_0075378957_li58001655123>` and access SWR.

#. Log in to the SWR console.

#. In the navigation pane, choose **My Images** and click the target image.

#. .. _swr_01_0017__en-us_topic_0084266454_li197783469319:

   On the **Image Tags** tab page, in the same row as the target image tag, click |image1| in the **Image Pull Command** column to copy the command.

#. Run the **image pull** command obtained in :ref:`Step 5 <swr_01_0017__en-us_topic_0084266454_li197783469319>` on the VM.

   Run the **docker images** command to check whether the images are successfully pulled.

   .. code-block::

      # docker images
      REPOSITORY                                  TAG       IMAGE ID       CREATED         SIZE
      xxx/group/nginx                             v2.0.0    22f2bf2e2b4f   5 hours ago     22.8MB

#. (Optional) Run the following command to save the image as an archive file:

   **docker save** [*Image name:tag name*] **>** [*Archive file name*]

.. |image1| image:: /_static/images/en-us_image_0282767856.png
