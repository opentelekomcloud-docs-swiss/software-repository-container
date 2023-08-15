:original_name: swr_02_0049.html

.. _swr_02_0049:

Querying Image Permissions
==========================

Function
--------

Query image permissions.

URI
---

GET /v2/manage/namespaces/{*namespace*}/repos/{*repository*}/access

For details about parameters, see :ref:`Table 1 <swr_02_0049__table73271639103420>`.

.. _swr_02_0049__table73271639103420:

.. table:: **Table 1** Parameter description

   ========== ========= ====== =================
   Parameter  Mandatory Type   Description
   ========== ========= ====== =================
   namespace  Yes       String Organization name
   repository Yes       String Image name
   ========== ========= ====== =================

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces/group/repos/busybox/access

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +--------------+-----------------------------------------------------------+----------------------------------+
      | Parameter    | Type                                                      | Description                      |
      +==============+===========================================================+==================================+
      | id           | Integer                                                   | Permission ID.                   |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | name         | String                                                    | Image name.                      |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | self_auth    | :ref:`Object <swr_02_0049__table16690123312516>`          | Permissions of the current user. |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | others_auths | Array of :ref:`objects <swr_02_0049__table2060620585538>` | Permissions of other users.      |
      +--------------+-----------------------------------------------------------+----------------------------------+

   .. _swr_02_0049__table16690123312516:

   .. table:: **Table 3** self_auth parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | user_id               | String                | User ID               |
      +-----------------------+-----------------------+-----------------------+
      | user_name             | String                | Username              |
      +-----------------------+-----------------------+-----------------------+
      | auth                  | Integer               | User permission       |
      |                       |                       |                       |
      |                       |                       | -  7: Manage          |
      |                       |                       | -  3: Write           |
      |                       |                       | -  1: Read            |
      +-----------------------+-----------------------+-----------------------+

   .. _swr_02_0049__table2060620585538:

   .. table:: **Table 4** others_auths parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | user_id               | String                | User ID               |
      +-----------------------+-----------------------+-----------------------+
      | user_name             | String                | Username              |
      +-----------------------+-----------------------+-----------------------+
      | auth                  | Integer               | User permission       |
      |                       |                       |                       |
      |                       |                       | -  7: Manage          |
      |                       |                       | -  3: Write           |
      |                       |                       | -  1: Read            |
      +-----------------------+-----------------------+-----------------------+

-  Example response

   .. code-block::

      {
          "id": 1422,
          "name": "busybox",
          "self_auth": {
              "user_id": "3059e6b5562241fda3fa441cca6f228b",
              "user_name": "admin",
              "auth": 7
          },
          "others_auths": [
              {
                  "user_id": "fb3f175c1fd146ab8cdae3272be6107b",
                  "user_name": "user",
                  "auth": 1
              }
          ]
      }

Status Code
-----------

=========== =================================================
Status Code Description
=========== =================================================
200         Query succeeded.
400         Request error.
401         Authentication failed.
404         The image or the image permission does not exist.
500         Internal error.
=========== =================================================
