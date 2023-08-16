:original_name: en-us_topic_0000001539235197.html

.. _en-us_topic_0000001539235197:

Why Does a CCE Workload Cannot Pull an Image from SWR and the Message Indicating "Not Logged In" Is Displayed?
==============================================================================================================

If a CCE workload cannot pull an SWR image and the message indicating "Not logged in" is displayed, check whether the YAML file of the workload contains the **imagePullSecrets** field and whether the value of **name** is fixed to **default-secret**.

Example:

.. code-block::

   apiVersion: extensions/v1beta1
   kind: Deployment
   metadata:
     name: nginx
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: nginx
     strategy:
       type: RollingUpdate
     template:
       metadata:
         labels:
           app: nginx
       spec:
         containers:
         - image: nginx
           imagePullPolicy: Always
           name: nginx
         imagePullSecrets:
         - name: default-secret
