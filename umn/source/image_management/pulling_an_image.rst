:original_name: swr_01_0017.html

.. _swr_01_0017:

Pulling an Image
================

Scenario
--------

To use an image stored in a repository, you need to pull it from the repository first. Then, you can use this image to deploy containerized applications in CCE or CCI. Pulling an image is actually downloading an image. Images are classified as public or private.

You can use Docker or containerd to pull images from SWR.

Docker
------

#. Log in to the VM running Docker as the **root** user.

#. Obtain a login command by referring to :ref:`Step 1 <swr_01_0011__en-us_topic_0112596104_en-us_topic_0075378957_li58001655123>` and access SWR.

#. Log in to the SWR console.

#. In the navigation pane, choose **My Images**. Then click the name of the target image.

#. .. _swr_01_0017__en-us_topic_0084266454_li197783469319:

   On the image details page, click |image1| next to the docker pull command on the **Pull/Push** tab.

#. Replace *{Tag}* in the image download command copied in :ref:`Step 5 <swr_01_0017__en-us_topic_0084266454_li197783469319>` with the tag of the image to be downloaded and run the command on the VM.

   Run the **docker images** command to check whether the images are successfully pulled.

   .. code-block::

      # docker images
      REPOSITORY                                  TAG       IMAGE ID       CREATED         SIZE
      xxx/group/nginx                             v2.0.0    22f2bf2e2b4f   5 hours ago     22.8MB

#. (Optional) Run the following command to save the image as an archive file:

   **docker save** [*Image name:tag name*] **>** [*Archive file name*]

containerd
----------

#. Log in to the SWR console.

#. In the navigation pane, choose **My Images**. Then click the name of the target image.

#. .. _swr_01_0017__en-us_topic_0000001952079513_li16192124154316:

   On the **Tags** tab, click **containerd command** in the **Operation** column to copy the image pull command. Alternatively, go to the **Pull/Push** tab to copy the image pull command.

   .. note::

      You can set the temporary login command to expire between 15 minutes and 24 hours after creation. For details about how to obtain a long-term download command, see :ref:`Obtaining a Long-Term Login or Image Pull/Push Command <swr_01_1000>`.

#. Log in to the VM running containerd as the **root** user.

#. Run the command copied in :ref:`Step 3 <swr_01_0017__en-us_topic_0000001952079513_li16192124154316>`.

   -  If the command was copied from the **Operation** column, run it as follows.

      |image2|

   -  If the command was copied from the **Pull/Push** tab, run it as follows. Change the organization name, image name, and tag to those of the image to be uploaded.

      |image3|

#. Check whether the image is pulled successfully.

   -  If the command was copied from the **Operation** column, run **crictl images** to check whether the pull is successful.

      |image4|

   -  If the command was copied from the **Pull/Push** tab, run **ctr images list** to check whether the pull is successful.

      |image5|

.. |image1| image:: /_static/images/en-us_image_0000002502216028.png
.. |image2| image:: /_static/images/en-us_image_0000002000854844.png
.. |image3| image:: /_static/images/en-us_image_0000002037053129.png
.. |image4| image:: /_static/images/en-us_image_0000002001013122.png
.. |image5| image:: /_static/images/en-us_image_0000002037094013.png
