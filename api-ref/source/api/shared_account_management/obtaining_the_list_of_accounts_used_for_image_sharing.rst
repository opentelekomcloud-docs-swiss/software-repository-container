:original_name: swr_02_0074.html

.. _swr_02_0074:

Obtaining the List of Accounts Used for Image Sharing
=====================================================

Function
--------

Obtain the list of accounts used for image sharing.

URI
---

GET /v2/manage/namespaces/{*namespace*}/repositories/{*repository*}/access-domains

For details about parameters, see :ref:`Table 1 <swr_02_0074__table11843162810214>`.

.. _swr_02_0074__table11843162810214:

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

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces/group/repositories/busybox/access-domains

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +-------------------+------------------------------------------------------------+------------------+
      | Parameter         | Type                                                       | Description      |
      +===================+============================================================+==================+
      | *[Array element]* | Array of :ref:`objects <swr_02_0074__table45446245174724>` | Shared accounts. |
      +-------------------+------------------------------------------------------------+------------------+

   .. _swr_02_0074__table45446245174724:

   .. table:: **Table 3** *[Array element]* parameter description

      +-----------------------+-----------------------+-------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                 |
      +=======================+=======================+=============================================================+
      | namespace             | String                | Organization name.                                          |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | repository            | String                | Image repository name.                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | access_domain         | String                | Name of the account used for image sharing.                 |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | permit                | String                | Permission.                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | deadline              | String                | Expiration time.                                            |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | description           | String                | Description.                                                |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | creator_id            | String                | Creator ID.                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | creator_name          | String                | Name of the creator.                                        |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | created               | String                | Time when an image is created. It is the UTC standard time. |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | updated               | String                | Time when an image is updated. It is the UTC standard time. |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | status                | Boolean               | Status.                                                     |
      |                       |                       |                                                             |
      |                       |                       | true: valid. false: expired.                                |
      +-----------------------+-----------------------+-------------------------------------------------------------+

-  Example response

   .. code-block::

      [
          {
              "namespace": "group",
              "repository": "busybox",
              "access_domain": "swr",
              "permit": "read",
              "deadline": "2021-10-01T16:00:00Z",
              "description": "description",
              "creator_id": "fb3f175c1fd146ab8cdae3272be6107b",
              "creator_name": "group",
              "created": "2021-06-10T08:14:42.56632Z",
              "updated": "2021-06-10T08:14:42.566325Z",
              "status": true
          }
      ]

Status Code
-----------

=========== ==========================================================
Status Code Description
=========== ==========================================================
200         The list of image sharing account is queried successfully.
400         Request error. Error information is returned.
401         Authentication failed.
500         Internal error. Error information is returned.
=========== ==========================================================
