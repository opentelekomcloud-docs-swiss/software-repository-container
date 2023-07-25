:original_name: swr_02_0073.html

.. _swr_02_0073:

Checking the Existence of an Account Used for Image Sharing
===========================================================

Function
--------

Check whether an account used for image sharing exists.

URI
---

GET /v2/manage/namespaces/{*namespace*}/repositories/{*repository*}/access-domains/{*access_domain*}

For details about parameters, see :ref:`Table 1 <swr_02_0073__table11843162810214>`.

.. _swr_02_0073__table11843162810214:

.. table:: **Table 1** Parameter description

   +---------------+-----------+--------+---------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                 |
   +===============+===========+========+=============================================+
   | namespace     | Yes       | String | Organization name                           |
   +---------------+-----------+--------+---------------------------------------------+
   | repository    | Yes       | String | Image repository name                       |
   +---------------+-----------+--------+---------------------------------------------+
   | access_domain | Yes       | String | Name of the account used for image sharing. |
   +---------------+-----------+--------+---------------------------------------------+

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2/manage/namespaces/group/repositories/busybox/access-domains/domain_name

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +-----------------------+-----------------------+-------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                 |
      +=======================+=======================+=============================================================+
      | exist                 | Boolean               | **true**: Exist. **false**: Not exist.                      |
      +-----------------------+-----------------------+-------------------------------------------------------------+
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

      {
          "exist": true,
          "namespace": "group",
          "repository": "busybox",
          "access_domain": "xxx",
          "permit": "read",
          "deadline": "2021-10-01T16:00:00Z",
          "description": "description",
          "creator_id": "0504186e6a8010e01f3ec009a7279baa",
          "creator_name": "xxx",
          "created": "2021-06-10T08:14:42.56632Z",
          "updated": "2021-06-10T08:14:42.566325Z",
          "status": true
      }

Status Code
-----------

=========== ======================
Status Code Description
=========== ======================
200         Query succeeded.
400         Request error.
401         Authentication failed.
500         Internal error.
=========== ======================
