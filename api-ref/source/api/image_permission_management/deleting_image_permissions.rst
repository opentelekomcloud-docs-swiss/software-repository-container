:original_name: swr_02_0047.html

.. _swr_02_0047:

Deleting Image Permissions
==========================

Function
--------

Delete the image operation permissions of certain users.

URI
---

DELETE /v2/manage/namespaces/{*namespace*}/repos/{*repository*}/access

For details about parameters, see :ref:`Table 1 <swr_02_0047__table73271639103420>`.

.. _swr_02_0047__table73271639103420:

.. table:: **Table 1** Parameter description

   ========== ========= ====== ==================
   Parameter  Mandatory Type   Description
   ========== ========= ====== ==================
   namespace  Yes       String Organization name.
   repository Yes       String Image name.
   ========== ========= ====== ==================

Request
-------

-  Request parameters

   .. table:: **Table 2** Request body parameter description

      +-------------------+-----------+------------------+---------------------------------------------------------+
      | Parameter         | Mandatory | Type             | Description                                             |
      +===================+===========+==================+=========================================================+
      | *[Array element]* | Yes       | Array of strings | ID array of users whose permissions need to be deleted. |
      +-------------------+-----------+------------------+---------------------------------------------------------+

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2/manage/namespaces/group/repos/busybox/access

   Body:

   .. code-block::

      ["fb3f175c1fd146ab8cdae3272be6107b"]

Response
--------

N/A

Status Code
-----------

=========== =========================
Status Code Description
=========== =========================
204         Deletion succeeded.
400         Request error.
401         Authentication failed.
404         The image does not exist.
500         Internal error.
=========== =========================
