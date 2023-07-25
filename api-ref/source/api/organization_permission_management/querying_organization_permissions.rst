:original_name: swr_02_0045.html

.. _swr_02_0045:

Querying Organization Permissions
=================================

Function
--------

Query organization permissions.

URI
---

GET /v2/manage/namespaces/{namespace}/access

For details about parameters, see :ref:`Table 1 <swr_02_0045__table73271639103420>`.

.. _swr_02_0045__table73271639103420:

.. table:: **Table 1** Parameter description

   ========= ========= ====== ==================
   Parameter Mandatory Type   Description
   ========= ========= ====== ==================
   namespace Yes       String Organization name.
   ========= ========= ====== ==================

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces/group/access

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameters

      +--------------+-----------------------------------------------------------+----------------------------------+
      | Parameter    | Type                                                      | Description                      |
      +==============+===========================================================+==================================+
      | id           | Integer                                                   | Permission ID.                   |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | name         | String                                                    | Organization name.               |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | creator_name | String                                                    | Organization creator.            |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | self_auth    | :ref:`Object <swr_02_0045__table16690123312516>`          | Permissions of the current user. |
      +--------------+-----------------------------------------------------------+----------------------------------+
      | others_auths | Array of :ref:`objects <swr_02_0045__table2060620585538>` | Permissions of other users.      |
      +--------------+-----------------------------------------------------------+----------------------------------+

   .. _swr_02_0045__table16690123312516:

   .. table:: **Table 3** self_auth parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | user_id               | String                | User ID.              |
      +-----------------------+-----------------------+-----------------------+
      | user_name             | String                | Username.             |
      +-----------------------+-----------------------+-----------------------+
      | auth                  | Integer               | User permission       |
      |                       |                       |                       |
      |                       |                       | -  7: Manage          |
      |                       |                       | -  3: Write           |
      |                       |                       | -  1: Read            |
      +-----------------------+-----------------------+-----------------------+

   .. _swr_02_0045__table2060620585538:

   .. table:: **Table 4** others_auths parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | user_id               | String                | User ID.              |
      +-----------------------+-----------------------+-----------------------+
      | user_name             | String                | Username.             |
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
          "id": 1334795,
          "name": "group",
          "creator_name": "user",
          "self_auth": {
              "user_id": "050b12577f00269a1fcfc01f65239697",
              "user_name": "user",
              "auth": 7
          },
          "others_auths": [
              {
                  "user_id": "06d89c3b6d800f2d1f28c01f0d882285",
                  "user_name": "user_01",
                  "auth": 1
              },
              {
                  "user_id": "050b12577f00269a1fcfc01f65239697",
                  "user_name": "user",
                  "auth": 7
              }
          ]
      }

Status Code
-----------

=========== ================================
Status Code Description
=========== ================================
200         Request successful.
400         Request error.
401         Authentication failed.
404         The organization does not exist.
500         Internal error.
=========== ================================
