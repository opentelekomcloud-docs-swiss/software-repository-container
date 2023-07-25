:original_name: swr_02_0043.html

.. _swr_02_0043:

Deleting Organization Permissions
=================================

Function
--------

Delete the organization operation permissions of certain users.

URI
---

DELETE /v2/manage/namespaces/{*namespace*}/access

:ref:`Table 1 <swr_02_0043__table15218458175016>` describes the parameters.

.. _swr_02_0043__table15218458175016:

.. table:: **Table 1** Parameter description

   ========= ========= ====== ==================
   Parameter Mandatory Type   Description
   ========= ========= ====== ==================
   namespace Yes       String Organization name.
   ========= ========= ====== ==================

Request
-------

-  Request parameters

   .. table:: **Table 2** Request body parameter description

      +-------------------+-----------+------------------+---------------------------------------------------------+
      | Parameter         | Mandatory | Type             | Description                                             |
      +===================+===========+==================+=========================================================+
      | *[Array element]* | Yes       | Array of strings | ID array of users whose permissions need to be deleted. |
      +-------------------+-----------+------------------+---------------------------------------------------------+

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2/manage/namespaces/group/access

   Body:

   .. code-block::

      ["fb3f175c1fd146ab8cdae3272be6107b"]

Response
--------

N/A

Status Code
-----------

=========== ================================
Status Code Description
=========== ================================
204         Deleted successfully.
400         Request error.
401         Authentication failed.
404         The organization does not exist.
500         Internal error.
=========== ================================
