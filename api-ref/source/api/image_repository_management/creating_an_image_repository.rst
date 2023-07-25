:original_name: swr_02_0030.html

.. _swr_02_0030:

Creating an Image Repository
============================

Function
--------

Create an image repository in an organization.

URI
---

POST /v2/manage/namespaces/{*namespace*}/repos

For details about parameters, see :ref:`Table 1 <swr_02_0030__table155961192716>`.

.. _swr_02_0030__table155961192716:

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                     |
   +=================+=================+=================+=================================================================================================================================================================================================================================================================================================================================+
   | namespace       | Yes             | String          | Organization name.                                                                                                                                                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                 |
   |                 |                 |                 | Enter 1 to 64 characters, starting with a lowercase letter and ending with a lowercase letter or digit. Only lowercase letters, digits, periods (.), underscores (_), and hyphens (-) are allowed. Periods, underscores, and hyphens cannot be placed next to each other. A maximum of two consecutive underscores are allowed. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   .. table:: **Table 2** FormData parameter description

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                    |
      +=================+=================+=================+================================================================================================================================================================================================================================================================================================================================+
      | repository      | Yes             | String          | Image repository name.                                                                                                                                                                                                                                                                                                         |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                |
      |                 |                 |                 | Enter 1 to 128 characters, starting and ending with a lowercase letter or digit. Only lowercase letters, digits, periods (.), slashes (/), underscores (_), and hyphens (-) are allowed. Periods, slashes, underscores, and hyphens cannot be placed next to each other. A maximum of two consecutive underscores are allowed. |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | category        | No              | String          | Repository type.                                                                                                                                                                                                                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                |
      |                 |                 |                 | The value can be **app_server**, **linux**, **framework_app**, **database**, **lang**, **other**, **windows** or **arm**.                                                                                                                                                                                                      |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description     | No              | String          | Brief description of the image repository.                                                                                                                                                                                                                                                                                     |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | is_public       | Yes             | Boolean         | Whether the repository is a public repository. When the value is **true**, it indicates the repository is public. When the value is **false**, it indicates the repository is private.                                                                                                                                         |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v2/manage/namespaces/group/repos

   Body:

   .. code-block::

      -F "repository=busybox" \
      -F "category=linux" \
      -F "description=this is a busybox repository" \
      -F "is_public=true"

   Or

   .. code-block::

      {
          "repository": "busybox",
          "category": "linux",
          "description": "this is a busybox repository",
          "is_public": true
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

=========== ==============================================
Status Code Description
=========== ==============================================
201         Creation successful.
400         Request error. Error information is returned.
401         Authentication failed.
409         The repository already exists.
500         Internal error. Error information is returned.
=========== ==============================================
