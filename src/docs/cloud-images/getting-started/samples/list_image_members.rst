.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

    $members = $image->listMembers();

    foreach ($members as $member) {
        /** @param $member OpenCloud\Image\Resource\Member */
    }

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  members = imgs.list_image_members("{imageId}")

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh

  curl -s $ENDPOINT/images/{imageId}/members \
    -H "X-Auth-Token: $TOKEN" \
    -H "Accept: application/json" | python -m json.tool
