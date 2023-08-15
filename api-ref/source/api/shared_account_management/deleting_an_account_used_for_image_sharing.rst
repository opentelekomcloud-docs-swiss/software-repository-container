:original_name: swr_02_0071.html

.. _swr_02_0071:

Deleting an Account Used for Image Sharing
==========================================

Function
--------

Delete an account used for image sharing.

URI
---

DELETE /v2/manage/namespaces/{*namespace*}/repositories/{*repository*}/access-domains/{*access_domain*}

For details about parameters, see :ref:`Table 1 <swr_02_0071__table11843162810214>`.

.. _swr_02_0071__table11843162810214:

.. table:: **Table 1** Parameter description

   +---------------+-----------+--------+---------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                 |
   +===============+===========+========+=============================================+
   | namespace     | Yes       | String | Organization name.                          |
   +---------------+-----------+--------+---------------------------------------------+
   | repository    | Yes       | String | Image repository name.                      |
   +---------------+-----------+--------+---------------------------------------------+
   | access_domain | Yes       | String | Name of the account used for image sharing. |
   +---------------+-----------+--------+---------------------------------------------+

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2/manage/namespaces/group/repositories/busybox/access-domains/domain_name

Response
--------

N/A

Status Code
-----------

+-------------+----------------------------------------------------------------------+
| Status Code | Description                                                          |
+=============+======================================================================+
| 204         | Deleted successfully.                                                |
+-------------+----------------------------------------------------------------------+
| 400         | Request error.                                                       |
+-------------+----------------------------------------------------------------------+
| 401         | Authentication failed.                                               |
+-------------+----------------------------------------------------------------------+
| 500         | Failed to complete the request because of an internal service error. |
+-------------+----------------------------------------------------------------------+
