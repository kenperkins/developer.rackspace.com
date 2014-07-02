.. code-block:: csharp

.. code-block:: java

  GroupApi groupApi = autoscaleApi.getGroupApiForZone("{region}");
  FluentIterable<Group> groups = groupApi.list();

.. code-block:: javascript

  // Not currently supported by this SDK

.. code-block:: php

    $groups = $service->groupList();

.. code-block:: python

    # After authenticating
    au = pyrax.autoscale
    scaling_groups = au.list()

.. code-block:: ruby

  scaling_groups = service.groups

.. code-block:: sh

  curl -X GET $ENDPOINT/groups \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
