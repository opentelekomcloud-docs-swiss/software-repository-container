:original_name: swr_faq_0033.html

.. _swr_faq_0033:

Why Does the **docker pull** Command Fail to Be Executed?
=========================================================

x509: certificate sigined by unknown authority
----------------------------------------------

**Problem**: When you run the **docker pull** command to pull an image from SWR, error message "x509: certificate signed by unknown certificates" is displayed.

**Possible Causes**:

-  A container engine client and SWR communicate with each other using HTTPS. When the client verifies the server certificate and finds that the root certificate installed on the client is incomplete, the error message "x509: certificate signed by unknown certificates" is displayed.
-  A proxy is configured on the container engine client.

**Solution**:

-  If you trust the server and skip certificate authentication, manually configure the startup parameters for the container engine using either of the following methods (use the actual image repository address):

   -  Add the following configuration to the **/etc/docker/daemon.json** file. If the file does not exist, manually create it. Ensure that two-space indents are used in the configuration.

      .. code-block::

         {
           "insecure-registries":["Image repository address"]
         }

   -  /etc/sysconfig/docker:

      .. code-block::

         INSECURE_REGISTRY='--insecure-registry=Image repository address'

   After configuration, run the **systemctl restart docker** or **service docker start** command to restart the container engine.

-  Run the **docker info** command to check whether the proxy is correctly configured. If not, modify the configuration.

Error: remote trust data does not exist
---------------------------------------

**Problem**: When you run the **docker pull** command to pull an image from SWR, message "Error: remote trust data does not exist" is displayed.

**Possible cause**: The image signature verification is enabled on the client. However, the image to be pulled does not contain a signature layer.

**Solution**: Check whether the environment variable **DOCKER_CONTENT_TRUST** is set to **1**. If yes, delete **DOCKER_CONTENT_TRUST=1** from the **/etc/profile** file and run the **source /etc/profile** command to make the modification take effect.
