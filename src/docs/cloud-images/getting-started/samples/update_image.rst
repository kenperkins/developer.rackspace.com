.. code-block:: csharp

.. code-block:: java

  // jclouds doesn't support this API presently

.. code-block:: javascript

.. code-block:: php

    $image->update(array(
        'name'        => 'foo',
        'newProperty' => 'bar'
    ));

.. code-block:: python

  # After authenticating, get a reference to the client
  imgs = pyrax.images
  # `valueDict` is a dictionary of key/value pairs, where the key is the
  # attribute to be updated, and the value is its new value.
  imgs.update("{imageId}", {"someAttribute": "someValue",
        "anotherAttribute": "anotherValue"})

.. code-block:: ruby

  # Fog doesn't support this API presently

.. code-block:: sh

  curl -s $ENDPOINT/images/{imageId} -X PATCH \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/openstack-images-v2.1-json-patch" \
    -H "Accent: application/json" \
    -d '[
      {
        "op": "add",
        "path": "/someAttribute",
        "value": "someValue"
      },
      {
        "op": "add",
        "path": "/anotherAttribute",
        "value": "anotherValue"
      }
    ]' | python -m json.tool
