:original_name: swr_faq_1012.html

.. _swr_faq_1012:

Image Push and Pull
===================

How Do I Push an Image to SWR by Calling APIs?
----------------------------------------------

Currently, SWR does not provide APIs for image push. You can push images using the **docker push** command on a client or using the SWR console.

How Do I Pull an Image from SWR by Calling APIs?
------------------------------------------------

Currently, SWR does not provide APIs for image pull. You can pull images using the **docker pull** command on a client.

Can I Push Arm-based Container Images to SWR?
---------------------------------------------

SWR has no restriction on the kernel architecture of images. There is no difference between pushing an Arm-based image and an x86-based image to SWR.

What Protocol Is Used to Push Images to SWR When I Run the **docker push** Command?
-----------------------------------------------------------------------------------

HTTPS is used.

Will an Image Be Overwritten If I Push an Image That Have the Same Name and Tag with it?
----------------------------------------------------------------------------------------

Yes, the original image will be overwritten.

Where Are the Images Pulled by Running the **docker pull** Command Stored?
--------------------------------------------------------------------------

Images pulled by running the **docker pull** command are stored on your local hosts. You can run the **docker save** command to save images into TAR archive files.

What Is the Maximum Size of an SWR Layer?
-----------------------------------------

If you use the container engine client to push images to SWR, each image layer cannot exceed 10 GB.

Can SWR Be Accessed over Private Networks? Will I Be Charged for Pushing and Pulling Images over Private Networks?
------------------------------------------------------------------------------------------------------------------

If your machine and the image repository are in the same region, you can access the image repository through private networks. No additional fees are charged for private network access because you have paid for your servers and EIPs.

If your machine and the image repository are in different regions, the node must have access to public networks to pull images from the image repository.
