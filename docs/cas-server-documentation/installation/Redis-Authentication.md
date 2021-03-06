---
layout: default
title: CAS - Redis Authentication
category: Authentication
---

{% include variables.html %}

# Redis Authentication

Verify and authenticate credentials using [Redis](https://redis.io/).

Support is enabled by including the following dependency in the WAR overlay:

{% include casmodule.html group="org.apereo.cas" module="cas-server-support-redis-authentication" %}

User accounts are mapped to a `username` field as the key. The user account record would contain the following fields:

| Field                     | Description    
|---------------------------|----------------------------------------------------------------------------
| `password`           | User password with applicable encoding, if any.
| `status`             | One of `OK`, `LOCKED`, `DISABLED`, `EXPIRED`, `MUST_CHANGE_PASSWORD`.
| `attributes`         | User attributes modeled as `Map<String, List<Object>>`.

{% include {{ version }}/principal-transformation.md configKey="cas.authn.redis" %}

{% include {{ version }}/password-encoding.md configKey="cas.authn.redis" %}

{% include {{ version }}/redis-configuration.md configKey="cas.authn" %}

{% include {{ version }}/redis-authentication-configuration.md %}

## Redis Principal Attributes

The above dependency may also be used, in the event that principal attributes need to be fetched from a 
Redis database without necessarily authenticating credentials against Redis. 

To see the relevant list of CAS properties, please [review this guide](../configuration/Configuration-Properties.html#redis).
