:original_name: swr_02_0032.html

.. _swr_02_0032:

Updating the Brief Information on an Image Repository
=====================================================

Function
--------

Update the brief information on an image repository in an organization, including the **category**, **is_public**, and **description**.

URI
---

PATCH /v2/manage/namespaces/{*namespace*}/repos/{*repository*}

For details about parameters, see :ref:`Table 1 <swr_02_0032__table16521054337>`.

.. _swr_02_0032__table16521054337:

.. table:: **Table 1** Parameter description

   ========== ========= ====== ======================
   Parameter  Mandatory Type   Description
   ========== ========= ====== ======================
   namespace  Yes       String Organization name.
   repository Yes       String Image repository name.
   ========== ========= ====== ======================

Request
-------

-  Request parameters

   .. table:: **Table 2** Request body parameter description

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                               |
      +=================+=================+=================+===========================================================================================================================+
      | category        | No              | String          | Repository type.                                                                                                          |
      |                 |                 |                 |                                                                                                                           |
      |                 |                 |                 | The value can be **app_server**, **linux**, **framework_app**, **database**, **lang**, **other**, **windows** or **arm**. |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------+
      | description     | No              | String          | Repository description.                                                                                                   |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------+
      | is_public       | Yes             | Boolean         | Whether the repository is a public repository. The value can be either **true** or **false**.                             |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      PATCH https://{Endpoint}/v2/manage/namespaces/group/repos/busybox

   Body:

   .. code-block::

      -F "category=linux" \
      -F "description=this is a busybox repository" \
      -F "is_public=false"

   Or

   .. code-block::

      {
          "category": "linux",
          "description": "this is a busybox repository",
          "is_public": false
      }

   .. note::

      The form format will no longer be supported soon. You are advised to use the body in the JSON format to call the API.

Response
--------

-  Response parameters

   N/A

-  Example response

   .. code-block::

      {}

Status Code
-----------

+-------------+---------------------------------------------------------------------------+
| Status Code | Description                                                               |
+=============+===========================================================================+
| 201         | The brief information about the image repository is successfully updated. |
+-------------+---------------------------------------------------------------------------+
| 400         | Request error. Error information is returned.                             |
+-------------+---------------------------------------------------------------------------+
| 401         | Authentication failed.                                                    |
+-------------+---------------------------------------------------------------------------+
| 404         | The repository does not exist.                                            |
+-------------+---------------------------------------------------------------------------+
| 500         | Internal error. Error information is returned.                            |
+-------------+---------------------------------------------------------------------------+
