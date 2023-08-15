:original_name: swr_faq_0004.html

.. _swr_faq_0004:

How Do I Create an Image Package?
=================================

Run the **docker save** command to compress the container image into a .tar or .tar.gz package. The command format is as follows:

**docker save [OPTIONS] IMAGE [IMAGE...]**

**[OPTIONS]** can be set to **--output** or **-o**, indicating that the image is exported to a file.

Example:

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
