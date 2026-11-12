:original_name: swr_faq_2008.html

.. _swr_faq_2008:

Logins
======

What Are the Differences Between Long-Term and Temporary Login Commands?
------------------------------------------------------------------------

-  You can specify the validity period, from 15 minutes to 24 hours, for a temporary login command. After the validity period reaches, the login command cannot be used anymore. A temporary login command can be used in scenarios such as temporary use and one-time external authorization. For production clusters that have high security requirements, it can also be used with periodic refresh.
-  Long-term login commands are permanently valid. A long-term valid login command can be used in scenarios such as preliminary tests, CI/CD pipelines, and image pull from container clusters.
-  After you obtain a long-term valid login command, your temporary login commands will still be valid as long as they are in their validity periods.

-  Both long-term and temporary login commands can be used by multiple users at the same time.
