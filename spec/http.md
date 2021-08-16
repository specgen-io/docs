# Operation

Here's an example of operation:

```yaml
create_sample:
  description: creates sample
  endpoint: POST /sample
  header:
    Authorization: string
  query:
    sample_id: uuid
    user_id: int?
  body:
    description: sample that will be created
    type: Sample
  response:
    ok: Sample
    forbidden: empty
```

Here's information about operation definition fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| endpoint | yes | HTTP endpoint of operation |
| body | yes for POST and PUT | HTTP body of the request |
| response | yes | dictionary of supported HTTP responses and response body |
| header | no | dictionary of HTTP header parameters and types |
| query | no | dictionary of HTTP query parameters and types |
| description | no | description of the field, used for documentation |

## Endpoint

Endpoint determines what url operation is processing. Endpoint has following format: `METHOD url`. Method might be one of follwing: `GET`, `POST`, `PUT`, `DELETE`. Url is just a string always starting from `/`. Url can contain parameters in following format: `{param:type}`. Here's an example for enpoint with url parameter:

```yaml
GET /sample/{id:uuid}
```

## Header Parameters

The `header` field of [operation](https://github.com/specgen-io/spec/blob/main/README.md#operation) allows to describe HTTP header parameters. The `header` is a dictionary where key is the name of the header parameter and value is the definition of the parameter. Here are fields of parameter definition:

| Field | Required | Details |
| :--- | :--- | :--- |
| type | yes | type of the parameter |
| default | no | default value for the parameter |
| description | no | description of the parameter, used for documentation |

Here's an example of two header parameters definition: `Authorization` \(`string`\) and `X-Request-Id` \(`uuid`\):

```yaml
header:
  Authorization:
    type: string
    description: authorization token
  X-Request-Id:
    type: uuid
    description: original request id passed
```

Header parameters names should be in Pascal-Kebab case because this is how they should appear in real HTTP request.

Header parameters could be declared in a short form:

```yaml
header:
  Authorization: string  # authorization token
  X-Request-Id: string   # original request id passed
```

When short form is used the default value for parameter could be specified through `=` separator:

```yaml
header:
  X-Request-Id: string = some default id
```

## Query Parameters

The `query` field of [operation](https://github.com/specgen-io/spec/blob/main/README.md#operation) allows to describe HTTP query parameters. The `query` is a dictionary where key is the name of the query parameter and value is the definition of the parameter. Here are fields of parameter definition:

| Field | Required | Details |
| :--- | :--- | :--- |
| type | yes | type of the parameter |
| default | no | default value for the parameter |
| description | no | description of the parameter, used for documentation |

Here's an example of two query parameters definition: `page_size` and `page_number`, both of them are `int`:

```yaml
query:
  page_size:
    type: int
    description: size of the page
  page_number:
    type: int
    description: number of requested page
```

Query parameters names should be in snake\_case case.

Query parameters could be declared in a short form:

```yaml
query:
  page_size: int     # size of the page
  page_number: int   # number of requested page
```

When short form is used the default value for parameter could be specified through `=` separator:

```yaml
query:
  page_size: int = 100   # size of the page
  page_number: int = 0   # number of requested page
```

## Request Body

The `body` field of [operation](https://github.com/specgen-io/spec/blob/main/README.md#operation) defines body of HTTP request. Here are fields of body definition:

| Field | Required | Details |
| :--- | :--- | :--- |
| type | yes | type that represents body |
| description | no | description of body |

Here's an example of body definition represented by custom type `Sample`:

```yaml
body:
  type: Sample
  description: sample that will be created
```

Body could be declared in a short form:

```yaml
body: Sample  # sample that will be created
```

## Response

Here's an example of response definition with 2 responses: `ok` and `forbidden`, the `ok` response has a body of type `Sample`:

```yaml
response:
  ok:
    description: sample is created
    type: Sample
  forbidden:
    description: user is forbidden to create sample
    type: empty
```

The `response` field of [operation](https://github.com/specgen-io/spec/blob/main/README.md#operation) defines all possible responses of HTTP request. The `response` is a dictionary where key is the name of the response and value is the definition of the response. The name of responses should be in a text form according to [RFC 7231](https://tools.ietf.org/html/rfc7231) but in snake\_case. So, `OK` will be `ok`, `Unauthorized` - `unauthorized`, `Method Not Allowed` - `method_not_allowed`.

Here are fields of response definition:

| Field | Required | Details |
| :--- | :--- | :--- |
| type | yes | type that represents response body |
| description | no | description of response |

Response could be declared in a short form, here's short form equivalent of responses above:

```yaml
response:
  ok: Sample        # sample is created
  forbidden: empty  # user is forbidden to create sample
```

