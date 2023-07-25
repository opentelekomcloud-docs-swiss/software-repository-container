:original_name: swr_02_0081.html

.. _swr_02_0081:

Querying a Specific API Version
===============================

Function
--------

Query a specific API version of SWR.

URI
---

GET /{*api_version*}

For details about parameters, see :ref:`Table 1 <swr_02_0081__tae82a09e27434bef9a38b734d798ae6c>`.

.. _swr_02_0081__tae82a09e27434bef9a38b734d798ae6c:

.. table:: **Table 1** Parameter description

   =========== ========= ====== ===========
   Parameter   Mandatory Type   Description
   =========== ========= ====== ===========
   api_version Yes       String API version
   =========== ========= ====== ===========

Request
-------

-  Request parameters

   N/A

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2

Response
--------

-  Response parameters

   .. table:: **Table 2** Response body parameter description

      +-----------+--------------------------------------------------+-------------------------------------------+
      | Parameter | Type                                             | Description                               |
      +===========+==================================================+===========================================+
      | version   | :ref:`Object <swr_02_0081__table45446245174724>` | A list of objects related to the version. |
      +-----------+--------------------------------------------------+-------------------------------------------+

   .. _swr_02_0081__table45446245174724:

   .. table:: **Table 3** version parameter description

      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                                           | Description                                                                                                                                                                    |
      +=======================+================================================+================================================================================================================================================================================+
      | id                    | String                                         | Version ID (version number), for example, v2.                                                                                                                                  |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | links                 | :ref:`Object <swr_02_0081__table453717423323>` | API URL.                                                                                                                                                                       |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | version               | String                                         | If the APIs of this version support microversions, set this parameter to the supported maximum microversion. If the microversion is not supported, leave this parameter blank. |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                                         | Version status. The options are as follows:                                                                                                                                    |
      |                       |                                                |                                                                                                                                                                                |
      |                       |                                                | -  **CURRENT**: The version is the primary version.                                                                                                                            |
      |                       |                                                | -  **SUPPORTED**: The version is an old version, but it is still supported.                                                                                                    |
      |                       |                                                | -  **DEPRECATED**: The version is a deprecated version, which may be deleted later.                                                                                            |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated               | String                                         | Version release time, which must be the UTC time. For example, the release time of v2 is **2018-06-28T12:20:21Z**.                                                             |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | min_version           | String                                         | If APIs of this version support microversions, set this parameter to the supported minimum microversion. If the microversion is not supported, leave this parameter blank.     |
      +-----------------------+------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _swr_02_0081__table453717423323:

   .. table:: **Table 4** links parameter description

      ========= ====== ===========
      Parameter Type   Description
      ========= ====== ===========
      href      String Link
      rel       String Description
      ========= ====== ===========

-  Example response

   .. code-block::

      {
          "version": {
              "id": "v2",
              "links":
                  {
                      "href": "https://xxx",
                      "rel": "self"
                  }
              "min_version": "2.0",
              "status": "CURRENT",
              "updated": "2017-12-09T00:00:00Z",
              "version": "2.26"
          }
      }

Status Code
-----------

+-------------+----------------------------------------------------------------------+
| Status Code | Description                                                          |
+=============+======================================================================+
| 200         | Request successful.                                                  |
+-------------+----------------------------------------------------------------------+
| 500         | Failed to complete the request because of an internal service error. |
+-------------+----------------------------------------------------------------------+
