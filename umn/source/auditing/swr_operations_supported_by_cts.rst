:original_name: swr_01_0084.html

.. _swr_01_0084:

SWR Operations Supported by CTS
===============================

Scenario
--------

CTS records operations on cloud resources in your account. You can use the logs to perform security analysis, track resource changes, audit, and locate faults.

With CTS, you can record operations associated with SWR for future query, audit, and backtrack operations.

Key Operations Recorded by CTS
------------------------------

.. table:: **Table 1** SWR Basic Edition operations recorded by CTS

   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Operation                                                      | Resource Type               | Trace Name                        |
   +================================================================+=============================+===================================+
   | Pushing an image                                               | images                      | postMultipartImagePackage         |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Obtaining a login command                                      | dockerlogincmd              | createDockerConfig                |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying the overview                                          | overview                    | getDomainOverview                 |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Query monitoring metrics                                       | overview                    | getDomainResourceReports          |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an organization                                       | usernamespace               | createUserNamespace               |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an organization                                       | usernamespace               | deleteUserNamespace               |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing organizations                                          | usernamespace               | listUserNamespaces                |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about an organization                         | usernamespace               | showUserNamespace                 |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an organization authorization                         | usernamespaceauth           | createUserNamespaceAuth           |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an organization authorization                         | usernamespaceauth           | deleteUserNamespaceAuth           |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about an organization authorization           | usernamespaceauth           | showUserNamespaceAuth             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an organization authorization                         | usernamespaceauth           | updateUserNamespaceAuth           |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating a repository                                          | imagerepository             | createImageRepository             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting a repository                                          | imagerepository             | deleteImageRepository             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Query details about a repository                               | imagerepository             | showImageRepository               |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating a repository                                          | imagerepository             | updateImageRepository             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing repositories                                           | imagerepository             | listImageRepositories             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an image tag                                          | imagetag                    | createImageTag                    |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an image tag                                          | imagetag                    | deleteImageTag                    |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing image tags                                             | imagetag                    | listImageTags                     |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an image authorization                                | userrepositoryauth          | createUserRepositoryAuth          |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an image authorization                                | userrepositoryauth          | deleteUserRepositoryAuth          |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about an image authorization                  | userrepositoryauth          | showUserRepositoryAuth            |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an image authorization                                | userrepositoryauth          | updateUserRepositoryAuth          |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing image authorizations                                   | userrepositoryauth          | listSharedReposDetails            |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Sharing an image with other accounts                           | imagerepositoryaccessdomain | createImageRepositoryAccessDomain |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an account from the sharing list                      | imagerepositoryaccessdomain | deleteImageRepositoryAccessDomain |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about an account that an image is shared with | imagerepositoryaccessdomain | showImageRepositoryAccessDomain   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an account that an image is shared with               | imagerepositoryaccessdomain | updateImageRepositoryAccessDomain |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing the accounts an image is shared with                   | imagerepositoryaccessdomain | listImageRepositoryAccessDomain   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Sharing an image                                               | reposhare                   | createRepoShare                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Stopping sharing an image                                      | reposhare                   | deleteRepoShare                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about sharing an image                        | reposhare                   | getRepoShare                      |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating details about sharing an image                        | reposhare                   | updateRepoShare                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Viewing image sharing list                                     | reposhare                   | listRepoShares                    |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an image retention policy                             | retention                   | createRetention                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Deleting an image retention policy                             | retention                   | deleteRetention                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Querying details about an image retention policy               | retention                   | showRetention                     |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an image retention policy                             | retention                   | updateRetention                   |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing image retention policies                               | retention                   | listRetentions                    |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Listing image retention records                                | retention                   | listRetentionHistories            |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Creating an image layer                                        | blob                        | createBlob                        |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an image layer by data chunk                          | blob                        | updateImageLayerChunk             |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Updating an image layer                                        | blob                        | updateImageLayer                  |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Pulling an image layer                                         | blob                        | downloadImageLayer                |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
   | Pushing image manifest                                         | manifest                    | uploadManifest                    |
   +----------------------------------------------------------------+-----------------------------+-----------------------------------+
