# State Queries

**Retrieve Escrow Address**

{% code overflow="wrap" %}
```javascript
GET /ibc/apps/transfer/v1/channels/{channel_id}/ports/{port_id}/escrow_address
```
{% endcode %}

Fetches the escrow address tied to a specific channel and port. Parameters include the unique `channel_id` and `port_id`.



**Query Denomination Hash**

{% code overflow="wrap" %}
```javascript
GET /ibc/apps/transfer/v1/denom_hashes/{trace}
```
{% endcode %}

Retrieves denomination hash information for a given trace. Parameter: `trace` representing the denomination trace.



**Query All Denomination Traces**

{% code overflow="wrap" %}
```javascript
GET /ibc/apps/transfer/v1/denom_traces
```
{% endcode %}

Pulls data for all denomination traces. Pagination can be controlled using `pagination.key`, `pagination.offset`, `pagination.limit`, `pagination.count_total`, and `pagination.reverse`.



**Query Denomination Trace**

{% code overflow="wrap" %}
```javascript
GET /ibc/apps/transfer/v1/denom_traces/{hash}
```
{% endcode %}

Queries specific denomination trace information with the `hash` parameter.



**Query IBC-Transfer Module Parameters**

{% code overflow="wrap" %}
```javascript
GET /ibc/apps/transfer/v1/params
```
{% endcode %}

Fetches all parameters of the IBC-transfer module. No parameters are required.



**Query All IBC Light Clients**

{% code overflow="wrap" %}
```javascript
GET /ibc/core/client/v1/client_states
```
{% endcode %}

Retrieves data for all IBC light clients of a chain. Pagination parameters are the same as with the all denomination traces query.



**Query IBC Light Client**

{% code overflow="wrap" %}
```javascript
GET /ibc/core/client/v1/client_states/{client_id}
```
{% endcode %}

Fetches an IBC light client's data. Requires the `client_id` parameter representing the unique client identifier.

{% hint style="info" %}
Successful requests return a `200` response, while unexpected errors use the `default` response.
{% endhint %}
