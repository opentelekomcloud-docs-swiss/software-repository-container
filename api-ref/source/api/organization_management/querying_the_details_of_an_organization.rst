:original_name: swr_02_0029.html

.. _swr_02_0029:

Querying the Details of an Organization
=======================================

Function
--------

Query the details of an organization by its name.

URI
---

GET /v2/manage/namespaces/{*namespace*}

For details about parameters, see :ref:`Table 1 <swr_02_0029__table05962819187>`.

.. _swr_02_0029__table05962819187:

.. table:: **Table 1** Parameter description

   ========= ========= ====== =================
   Parameter Mandatory Type   Description
   ========= ========= ====== =================
   namespace Yes       String Organization name
   ========= ========= ====== =================

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces/group

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | id                    | Integer               | Organization ID       |
      +-----------------------+-----------------------+-----------------------+
      | name                  | String                | Organization name     |
      +-----------------------+-----------------------+-----------------------+
      | creator_name          | String                | IAM username          |
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
          "name": "group",
          "creator_name": "username",
          "auth": 7
      }

Status Code
-----------

=========== ================================
Status Code Description
=========== ================================
200         Query succeeded.
400         Request error.
401         Authentication failed.
404         The organization does not exist.
500         Internal error.
=========== ================================
