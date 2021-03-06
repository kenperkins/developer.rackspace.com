.. code-block:: csharp

.. code-block:: java

  RecordApi recordApi = cloudDNSApi.getRecordApiForDomain({domainId});
  Record createARecord = Record.builder()
          .type("A")
          .name("app.domain.com")
          .data("192.168.1.1")
          .ttl(3600)
          .build();

  List<Record> createRecords = ImmutableList.of(createARecord);

  Set<RecordDetail> records = awaitComplete(cloudDNSApi, recordApi.create(createRecords));

.. code-block:: javascript

  var recDetails = {
    name: 'app.example.com',
    data: '192.168.1.1',
    type: 'A'
  };

  rackspace.createRecord(myZone, recDetails, function (err, rec) {
    if (err) {
      console.dir(err);
      return;
    }
    console.log('Record ' + rec.name + ' was successfully created.');
  });

.. code-block:: php

  // Add an A record
  $record = $domain->record(array(
      'type' => 'A',
      'name' => 'app.example.com',
      'ttl'  => 3600,
      'data' => '192.168.1.1'
  ));

  $record->create();

.. code-block:: python

  domain.add_record({'type': 'A',
                     'name': 'app.example.com',
                     'ttl': 3600,
                     'data': '192.168.1.1'})

.. code-block:: ruby

  record = zone.records.create(
    :type => 'A',
    :name => 'app.example.com',
    :ttl => 3600,
    :value => '192.168.1.1'
  )

.. code-block:: sh

  curl -X POST -s -d \
    '{
        "records": [
            {
                "name" : "app.example.com",
                "type" : "A",
                "data" : "192.168.1.1",
                "ttl" : 3600
            }
        ]
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/domains/{domainId}/records | python -m json.tool
