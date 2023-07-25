:original_name: swr_02_0028.html

.. _swr_02_0028:

Querying the List of Organizations
==================================

Function
--------

Query the list of organizations.

URI
---

GET /v2/manage/namespaces

.. table:: **Table 1** Query parameters

   +-----------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                                                                                                                                                                                                                             |
   +===========+===========+========+=========================================================================================================================================================================================================================================================================================================================================================+
   | namespace | No        | String | Organization name. Enter 1 to 64 characters, starting with a lowercase letter and ending with a lowercase letter or digit. Only lowercase letters, digits, periods (.), underscores (_), and hyphens (-) are allowed. Periods, underscores, and hyphens cannot be placed next to each other. A maximum of two consecutive underscores are allowed.      |
   +-----------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | filter    | No        | String | Enter **namespace::{namespace}|mode::{mode}**. **{namespace}** indicates the organization name. If **{mode}** is not set, the list of authorized organizations is displayed. If **{mode}** is set to **visible**, the list of visible organizations is displayed. (Some organizations can be viewed by the repository, but cannot by the organization.) |
   +-----------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces?filter=namespace::group

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +------------+-----------------------------------------------------------+-------------------+
      | Parameter  | Type                                                      | Description       |
      +============+===========================================================+===================+
      | namespaces | Array of :ref:`objects <swr_02_0028__table1787854911167>` | Organization list |
      +------------+-----------------------------------------------------------+-------------------+

   .. _swr_02_0028__table1787854911167:

   .. table:: **Table 3** namespaces parameter description

      +-----------------------+-----------------------+-----------------------+
      | Parameter             | Type                  | Description           |
      +=======================+=======================+=======================+
      | ID                    | Integer               | Organization ID       |
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
          "namespaces": [
              {
                  "id": 1343008,
                  "name": "group",
                  "creator_name": "username",
                  "auth": 7
              }
          ]
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
