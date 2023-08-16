:original_name: swr_02_0070.html

.. _swr_02_0070:

Creating an Account Used for Image Sharing
==========================================

Function
--------

Create an account used for image sharing. You can share your private images with other users, granting them permissions to pull the images.

URI
---

POST /v2/manage/namespaces/{*namespace*}/repositories/{*repository*}/access-domains

For details about parameters, see :ref:`Table 1 <swr_02_0070__table11843162810214>`.

.. _swr_02_0070__table11843162810214:

.. table:: **Table 1** Parameter description

   ========== ========= ====== =====================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =====================
   namespace  Yes       String Organization name
   repository Yes       String Image repository name
   ========== ========= ====== =====================

Request
-------

-  Request parameters

   .. table:: **Table 2** Request body parameter description

      +---------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter     | Mandatory | Type   | Description                                                                                                                               |
      +===============+===========+========+===========================================================================================================================================+
      | access_domain | Yes       | String | Name of the account used for image sharing.                                                                                               |
      +---------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | permit        | Yes       | String | Currently, only the read permission is supported.                                                                                         |
      +---------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | deadline      | Yes       | String | Valid until (UTC). If the sharing is permanent, the value is **forever**. Otherwise, the sharing is valid until 00:00:00 of the next day. |
      +---------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | description   | No        | String | Description.                                                                                                                              |
      +---------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v2/manage/namespaces/group/repositories/busybox/access-domains

   Body:

   .. code-block::

      {
          "access_domain": "domain_name",
          "permit": "read",
          "deadline": "2021-10-01T16:00:00.000Z",
          "description": "description"
      }

Response
--------

-  Response parameters

   N/A

-  Example response

   .. code-block::

      {}

Status Code
-----------

=========== ===============================
Status Code Description
=========== ===============================
201         Creation successful.
400         Request error.
401         Authentication failed.
409         The repository has been shared.
500         Internal error.
=========== ===============================
