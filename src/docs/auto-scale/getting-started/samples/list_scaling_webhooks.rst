.. code-block:: csharp

.. code-block:: java

  WebhookApi webhookApi = autoscaleApi.getWebhookApiForZoneAndGroupAndPolicy("{region}", "{groupId}", "{policyId}");
  FluentIterable<Webhook> webhooks = webhookApi.list();

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

  $webhooks = $policy->getWebhookList();

.. code-block:: python

  # After authenticating
  au = pyrax.autoscale
  webhooks = au.list_webhooks("{scalingGroupId}", "{policyId}")

.. code-block:: ruby

  my_policy.webhooks

.. code-block:: sh

  curl -X GET $ENDPOINT/groups/{groupId}/policies/{policyId}/webhooks \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
