Step 11 - Rate Limiting
#######################

API Team wants to limit to 5 Requests / minute / user on Version 2 of the API.

Add a Rate Limit policy on API API-Proxy
========================================

#. In NMS, edit the API-Proxy ``sentence-api`` ``v2``
#. In ``Policies``, add new ``Rate Limit`` policy

   .. image:: ../pictures/lab1/add-rl.png
      :align: center

#. Add Rate Limit
#. Select ``Authenticated Client`` as key to apply, and ``5`` request per minute

   .. image:: ../pictures/lab1/rl-5req.png
      :align: center

#. Click ``Add``, ``Add``, ``Save & Publish``


Test it out
===========

#. In ``Postman``, Re-use the ``/colors`` on ``v2`` endpoint. As a reminder, it is ``http://api.sentence.com/v2/api/colors``
#. If the API Key is not there anymore, add it in Authorization
#. Send several requests and after few requests, they will be blocked

   .. code-block :: JSON

      {
        "message": "Too Many Requests",
        "status": "429"
      }

   .. image:: ../pictures/lab1/rl-blocked.png
      :align: center

.. note:: As you can notice, the blocking does not occure at the 5th request. Nginx calculates a mean per seconde based on your Rate Limiting configuration. 
   In our lab, we set 5 requests per minutes. It means 1 request every 12 secondes (60 sec / 5 req). If we wait 12 sec between each request, you will not be blocked.

