.. code-block:: csharp

.. code-block:: java

  WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
  boolean result = webhookApi.delete("{webhookId}");

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $webhook->delete();

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  au.delete_webhook("{scalingGroupId}", "{policyId}", "{webhookId}")

.. code-block:: ruby

  my_webhook.destroy

.. code-block:: sh

  curl -X DELETE $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks/{webhookId} \
    -H "X-Auth-Token: $TOKEN"
