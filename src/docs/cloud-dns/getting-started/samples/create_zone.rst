.. code-block:: csharp

.. code-block:: java

  DomainApi domainApi = cloudDNSApi.getDomainApi();
  List<CreateDomain> createDomains = Lists.newArrayList();
  CreateDomain createDomain = CreateDomain.builder()
          .name(DOMAIN)
          .email("admin@domain.com")
          .ttl(300)
          .build();

  createDomains.add(createDomain);

  Set<Domain> domains = awaitComplete(cloudDNSApi, domainApi.create(createDomains));

.. code-block:: javascript

  var details = {
    name: 'example.com',
    email: 'admin@example.com',
    ttl: 300,
    comment: 'Root level for example.com'
  };

  rackspace.createZone(details, function (err, zone) {
    if (err) {
      // TODO handle appropriately
      return;
    }

    // TODO use the created zone
  });

.. code-block:: php

  $dnsService = $client->dnsService();

  $domain = $dnsService->domain();
  $domain->create(array(
      'name'         => 'example.com',
      'emailAddress' => 'admin@example.com',
      'ttl'          => 300,
      'comment'      => 'Root level for example.com'
  ));

.. code-block:: python

  domain = pyrax.cloud_dns.create(name="example.com",
                                  emailAddress="admin@example.com",
                                  ttl=300)

.. code-block:: ruby

  zone = @client.zones.create(
    :domain => 'example.com',
    :email => 'admin@example.com',
    :ttl => 300,
    :comment => 'Root level for example.com'
  )

.. code-block:: sh

  curl -X POST -d \
    '{
        "domains" : [ {
            "name" : "example.com",
            "comment" : "Root level for example.com",
            "subdomains" : {
                "domains" : []
            },
            "ttl" : 300,
            "emailAddress" : "admin@example.com"
        } ]
    }' \
    -H "X-Auth-Token: $TOKEN" \
    -H "Content-Type: application/json" \
    $ENDPOINT/domains | python -m json.tool
