:original_name: swr_02_0031.html

.. _swr_02_0031:

Deleting an Image Repository
============================

Function
--------

Delete an image repository in an organization.

URI
---

DELETE /v2/manage/namespaces/{*namespace*}/repos/{*repository*}

For details about parameters, see :ref:`Table 1 <swr_02_0031__table184146147323>`.

.. _swr_02_0031__table184146147323:

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

   N/A

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2/manage/namespaces/group/repos/busybox

Response
--------

N/A

Status Code
-----------

+-------------+---------------------------------------------------------------------------+
| Status Code | Description                                                               |
+=============+===========================================================================+
| 204         | The brief information about the image repository is successfully deleted. |
+-------------+---------------------------------------------------------------------------+
| 400         | Request error. Error information is returned.                             |
+-------------+---------------------------------------------------------------------------+
| 401         | Authentication failed.                                                    |
+-------------+---------------------------------------------------------------------------+
| 404         | The repository does not exist.                                            |
+-------------+---------------------------------------------------------------------------+
| 406         | The repository cannot be deleted because it contains images.              |
+-------------+---------------------------------------------------------------------------+
| 500         | Internal error. Error information is returned.                            |
+-------------+---------------------------------------------------------------------------+
