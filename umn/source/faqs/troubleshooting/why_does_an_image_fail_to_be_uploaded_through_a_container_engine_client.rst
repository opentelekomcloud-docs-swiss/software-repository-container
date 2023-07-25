:original_name: swr_faq_0006.html

.. _swr_faq_0006:

Why Does an Image Fail to Be Uploaded Through a Container Engine Client?
========================================================================

denied: you do not have the permission
--------------------------------------

**Problem**: When you push an image to SWR through your container engine client, the operation fails with the following information returned.

**denied: you do not have the permission**

**Possible Causes**:

-  The organization name you specified has already been used by another user or the maximum number of organizations that you are allowed to create has been reached.
-  The **docker login** command you used to log in to SWR is generated using the AK and SK of an IAM user who does not have the permission of the target organization.

**Solutions**:

-  If the organization name has been registered by another user, create an organization and then upload the image.
-  If the number of SWR organizations reaches the quota (5 per user), upload the image to an existing organization.
-  If the IAM user does not have the permission of the target organization, log in as the cloud account and grant corresponding permissions to the IAM user and try again.

Message "tag does not exist: xxxxxx" or "An image does not exist locally with the tag: xxxxxx" Displayed
--------------------------------------------------------------------------------------------------------

**Problem**: When you push an image to SWR through your container engine client, the operation fails with the following information returned.

**tag does not exist: xxxxxx**

Or

**An image does not exist locally with the tag: xxxxxx**

**Possible cause**: The image or image tag to be pushed does not exist.

**Solution**: Run the **docker images** command to view all the local images. Check the target image name and tag, and push the image again.

name invalid: 'repository' is invalid
-------------------------------------

**Problem**: When you push an image to SWR through your container engine client, the operation fails with the following information returned.

**name invalid: 'repository' is invalid**

**Possible cause**: The organization name or image name does not comply with the naming rules.

**Solution**: The regular expressions of the organization (namespace) name and image (repository) name are as follows:

namespace: The value contains a maximum of 64 characters and must meet regular expression **^([a-z]+(?:(?:(?:_|__|[-]*)[a-z0-9]+)+)?)$**.

repository: The value contains a maximum of 128 characters and must meet regular expression **^([a-z0-9]+(?:(?:(?:_|__|[-]*)[a-z0-9]+)+)?)$**.

Specify a valid organization name or image name, and push the image again.
