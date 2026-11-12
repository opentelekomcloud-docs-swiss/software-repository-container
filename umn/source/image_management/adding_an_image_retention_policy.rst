:original_name: swr_01_0102.html

.. _swr_01_0102:

Adding an Image Retention Policy
================================

Scenario
--------

You can add a retention policy to an image in SWR to automatically delete any unused image tags. The policy takes effect immediately after you set it. There are two types of policies:

-  Number of days: keeping only image tags that have been pushed to SWR within a certain number of days.
-  Number of tags: keeping only a certain number of the most recent image tags.

You can configure filters for your retention policy to prevent certain image tags from being affected by the retention policy.

Constraints
-----------

-  Only one retention rule can be added to an image. If you want to add a new retention policy, you must delete the existing policy.
-  You can view only the retention logs generated in the last three months.

Procedure
---------

#. Log in to the SWR console.

#. In the navigation pane, choose **My Images**. Then click the name of the target image.

#. On the **Retention** tab, click . Configure the policy based on :ref:`Table 1 <swr_01_0102__table156232449577>` and click **OK**.

   .. _swr_01_0102__table156232449577:

   .. table:: **Table 1** Adding an image retention policy

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                         |
      +===================================+=====================================================================================================================================================================================================================+
      | Policy Type                       | There are two types of retention policies:                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                     |
      |                                   | -  Number of days: keeping only image tags that have been pushed to SWR within a certain number of days.                                                                                                            |
      |                                   | -  Number of tags: keeping only a certain number of the most recent image tags.                                                                                                                                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Count Limit (Number of days)      | When you set **Policy Type** to **Number of days**, the value of **Count Limit** indicates how many days an image tag can be stored. The value should be an integer ranging from 1 to 365.                          |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Count Limit (Number of tags)      | When you set **Policy Type** to **Number of tags**, the value of **Count Limit** indicates the maximum number of the most recent image tags to be retained. The value should be an integer ranging from 1 to 1,000. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag Filter                        | Enter image tags that you do not want this retention policy to apply to.                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Regular Expression Filter         | Enter a regular expression. Image tags meeting this regular expression will not be affected by this retention policy.                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   After the retention policy is added, SWR immediately applies the policy and displays deleted image tags (if any) in the **Retention Logs** area.
