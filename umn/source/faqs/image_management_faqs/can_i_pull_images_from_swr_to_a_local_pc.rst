:original_name: swr_faq_0035.html

.. _swr_faq_0035:

Can I Pull Images from SWR to a Local PC?
=========================================

Container images cannot be downloaded from the SWR console, but you can run commands to pull them.

#. Obtain the image pull command on the image details page.

#. Run the pull command on the Docker client.

   Example:

   **docker pull** *{Image-repository-address}*\ **/group/nginx:v1**

3. Save the image as a tar or tar.gz package.

   Example:

   **docker save nginx:v1 > nginx.tar**

4. Download the package to your local PC.
