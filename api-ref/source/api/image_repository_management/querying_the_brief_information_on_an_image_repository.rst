:original_name: swr_02_0033.html

.. _swr_02_0033:

Querying the Brief Information on an Image Repository
=====================================================

Function
--------

Query the brief information on an image repository in an organization.

URI
---

GET /v2/manage/namespaces/{*namespace*}/repos/{*repository*}

For details about parameters, see :ref:`Table 1 <swr_02_0033__table184146147323>`.

.. _swr_02_0033__table184146147323:

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

      GET https://{Endpoint}/v2/manage/namespaces/group/repos/busybox

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter     | Type    | Description                                                                                                                                       |
      +===============+=========+===================================================================================================================================================+
      | id            | Integer | Image repository ID.                                                                                                                              |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | ns_id         | Integer | Organization ID.                                                                                                                                  |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | name          | String  | Image repository name.                                                                                                                            |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | category      | String  | Image repository type. The value can be **app_server**, **linux**, **framework_app**, **database**, **lang**, **other**, **windows**, or **arm**. |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | description   | String  | Brief description of the image repository.                                                                                                        |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | creator_id    | String  | Image repository creator ID.                                                                                                                      |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | creator_name  | String  | Image repository creator.                                                                                                                         |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | size          | Integer | Image repository size.                                                                                                                            |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | is_public     | Boolean | Whether the image repository is a public repository. The value can be **true** or **false**.                                                      |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | num_images    | Integer | Number of images in an image repository.                                                                                                          |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | num_download  | Integer | Download times of an image repository.                                                                                                            |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | url           | String  | URL of the image repository logo image. This field has been discarded and is left empty by default.                                               |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | path          | String  | External image pull address. The format is {*Repository address*}/{*Namespace name*}/{*Repository name*}.                                         |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | internal_path | String  | Internal image pull address. The format is {*Repository address*}/{*Namespace name*}/{*Repository name*}.                                         |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | created       | String  | Time when an image repository is created. It is the UTC standard time.                                                                            |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated       | String  | Time when an image repository is updated. It is the UTC standard time.                                                                            |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | domain_id     | String  | Account ID.                                                                                                                                       |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | priority      | Integer | Image sorting priority.                                                                                                                           |
      +---------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "id": 865151,
          "ns_id": 1334795,
          "name": "busybox",
          "category": "other",
          "description": "containerops",
          "creator_id": "050b12577f00269a1fcfc01f65239697",
          "creator_name": "admin",
          "size": 2099575,
          "is_public": false,
          "num_images": 1,
          "num_download": 0,
          "url": "",
          "path": "{Repository address}/group/busybox",
          "internal_path": "{Repository address}/group/busybox",
          "created": "2021-06-02T09:59:25.51307Z",
          "updated": "2021-06-02T17:59:25.538056Z",
          "domain_id": "da44776c316c4a99b3683bb174f8821b",
          "priority": 0
      }

Status Code
-----------

=========== ==============================================
Status Code Description
=========== ==============================================
200         Request successful.
400         Request error. Error information is returned.
401         Authentication failed.
404         The repository does not exist.
500         Internal error. Error information is returned.
=========== ==============================================
