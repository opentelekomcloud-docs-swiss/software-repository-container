:original_name: swr_02_0072.html

.. _swr_02_0072:

Updating an Account Used for Image Sharing
==========================================

Function
--------

Update an account used for image sharing.

URI
---

PATCH /v2/manage/namespaces/{*namespace*}/repositories/{*repository*}/access-domains/{*access_domain*}

For details about parameters, see :ref:`Table 1 <swr_02_0072__table11843162810214>`.

.. _swr_02_0072__table11843162810214:

.. table:: **Table 1** Parameter description

   +---------------+-----------+--------+--------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                |
   +===============+===========+========+============================================+
   | namespace     | Yes       | String | Organization name                          |
   +---------------+-----------+--------+--------------------------------------------+
   | repository    | Yes       | String | Image repository name                      |
   +---------------+-----------+--------+--------------------------------------------+
   | access_domain | Yes       | String | Name of the account used for image sharing |
   +---------------+-----------+--------+--------------------------------------------+

Request
-------

-  Request parameters

   .. table:: **Table 2** Request body parameter description

      +-------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Mandatory | Type   | Description                                                                                                                               |
      +=============+===========+========+===========================================================================================================================================+
      | permit      | Yes       | String | Currently, only the read permission is supported.                                                                                         |
      +-------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | deadline    | Yes       | String | Valid until (UTC). If the sharing is permanent, the value is **forever**. Otherwise, the sharing is valid until 00:00:00 of the next day. |
      +-------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | description | No        | String | Description. This parameter is left blank by default.                                                                                     |
      +-------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      PATCH https://{Endpoint}/v2/manage/namespaces/group/repositories/busybox/access-domains/domain_name

   Body:

   .. code-block::

      {
          "permit": "read",
          "deadline": "forever",
          "description": "description"
      }

Response
--------

N/A

Status Code
-----------

=========== ======================
Status Code Description
=========== ======================
201         Modified successfully.
400         Request error.
401         Authentication failed.
500         Internal error.
=========== ======================
