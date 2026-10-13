:original_name: swr_faq_0006.html

.. _swr_faq_0006:

Why Does an Image Fail to Be Pushed Through a Container Engine Client?
======================================================================

denied: you do not have the permission
--------------------------------------

**Problem**: When you pushed an image to SWR through your container engine client, the operation failed with the following information returned:

**denied: you do not have the permission**

**Possible Causes**:

-  The organization name you specified has already been used by another user or the maximum number of organizations that you are allowed to create has been reached.
-  The **docker login** command you used to log in to SWR is generated using the AK and SK of an IAM user who does not have the permission of the target organization.

**Solutions**:

-  If the organization name has been registered by another user, create an organization and then upload the image.
-  If the number of SWR organizations has reached the quota (5 per user), push the image to an existing organization.
-  If the IAM user does not have the permission of the target organization, log in using the cloud account and grant the permission to the IAM user. Then, try again.

Message "tag does not exist: xxxxxx" or "An image does not exist locally with the tag: xxxxxx" Displayed
--------------------------------------------------------------------------------------------------------

**Problem**: When you pushed an image to SWR through your container engine client, the operation failed with the following information returned:

**tag does not exist: xxxxxx**

Or

**An image does not exist locally with the tag: xxxxxx**

**Possible cause**: The image or image tag to be pushed does not exist.

**Solution**: Run the **docker images** command to view all the local images. Check the target image name and tag, and push the image again.

name invalid: 'repository' is invalid
-------------------------------------

**Problem**: When you pushed an image to SWR through your container engine client, the operation failed with the following information returned:

**name invalid: 'repository' is invalid**

**Possible cause**: The organization name or image name does not comply with the naming rules.

**Solution**: The regular expressions of the organization (**namespace**) name and image (**repository**) name are as follows:

**namespace**: The value contains 1 to 64 characters and must meet regular expression **^([a-z]+(?:(?:(?:_|__|[-]*)[a-z0-9]+)+)?)$**.

**repository**: The value contains 1 to 128 characters and must meet regular expression **^([a-z0-9]+(?:(?:(?:_|__|[-]*)[a-z0-9]+)+)?)$**.

Specify a valid organization name or image name, and push the image again.

Failed to Upload an Image, and 400 Was Returned
-----------------------------------------------

**Problem**: When you pushed an image to SWR through your container engine client, the operation failed with the following information returned:

-  Error message 1:

   **ERROR: failed to solve: failed to push swr.xxx.com/xxx:xxx: failed commit on ref "index-sha256:xxx": unexpected status from PUT request to https://swr.xxx.com/xxx:xxx: 400 Bad Request**

-  Error message 2:

   **error from registry: Invalid image, fail to parse 'manifest.json'**

   |image1|

**Cause**: In SWR Basic Edition, images that comply with the Open Container Initiative (OCI) specifications (v1.0 and v1.1) cannot be uploaded.

**Solution**:

Run the **docker buildx build** command and add the **--provenance=false** parameter.

.. note::

   This method is suitable for images built by customers. Third-party images do not support this workaround.

Example:

.. code-block::

   docker buildx build --provenance=false --platform linux/amd64,linux/arm64 -t swr.*******.********.com/xxx/xxx:latest --push

.. |image1| image:: /_static/images/en-us_image_0000002534797983.png
