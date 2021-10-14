# HTTP Endpoints

Here's an example of endpoint definition:

```yaml
create_sample:
  description: creates sample
  endpoint: POST /sample
  header:
    Authorization: string
  query:
    sample_id: uuid
    user_id: int?
  body: Sample
  response:
    ok: Sample
    forbidden: empty
```

Here's information about endpoint definition fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| description | no | description, used for documentation |
| [endpoint](#endpoint) | yes | HTTP method and endpoint URL |
| [header](#header-parameters) | no | dictionary of HTTP header parameters and their types |
| [query](#query-parameters) | no | dictionary of HTTP query parameters and their types |
| [body](#request-body) | no for POST and PUT | HTTP body of the request |
| [response](#response) | yes | dictionary of supported HTTP responses and response body |

## Endpoint

Endpoint defines HTTP method and URL to which service should respond.

Endpoint has the following format: `METHOD url`. Method might be one of follwing: `GET`, `POST`, `PUT`, `DELETE`.

Url is just a string always starting from `/`. Url can contain parameters in following format: `{param:type}`. Here's an example for enpoint with url parameter:

```yaml
GET /sample/{id:uuid}
```

## Parameters

This section describes parameters format that is used for both [header parameters](#header-parameters) and [query parameters](#query-parameters).

```yaml
parameter: type [= default_value] [# description]
```

|  | Required | Details |
| :--- | :--- | :--- |
| parameter | yes | parameter name |
| type | yes | type of parameter according to [types](https://docs.specgen.io/spec/types) |
| default_value | no | default value for the parameter |
| description | no | description in a form of line comment, used for documentation |

Here's an example of parameter `page_size` of type `int` default value `20` and description `number of items per page`:

```yaml
page_size: int = 20  # number of items per page
```

Here's an example of parameter `page` of type `int` without default value or description:

```yaml
page: int
```

## Header Parameters

The `header` field of [endpoint](#endpoint) allows to define HTTP header parameters. The `header` field value is a dictionary where each item is using [parameters](#parameters) format.

Here's an example of two header parameters definition: `Authorization` (`string`) and `X-Request-Id` (`uuid`):

```yaml
header:
  Authorization: string  # authorization token
  X-Request-Id: uuid     # original request id passed
```

Omit `header` field in endpoint defintion if there no header parameters needed. 

## Query Parameters

The `query` field of [endpoint](#endpoint) allows to define HTTP header parameters. The `query` field value is a dictionary where each item is using [parameters](#parameters) format.

Here's an example of two query parameters definition: `page_size` (`int`) and `page_number` (`int`):

```yaml
query:
  page_size: int = 100  # size of the page
  page_number: int      # number of requested page
```

Omit `query` field in endpoint defintion if there no query parameters needed. 

## Request Body

The `body` field of [endpoint](#endpoint) defines body type of HTTP endpoint request.

Here's an example of body definition represented by custom type `Sample`:

```yaml
body: Sample  # sample that will be created
```

The `body` field can not have default value.
Omit `body` field in endpoint definition if request body is not required.

## Response

Here's an example of response definition with 2 responses: `ok` and `forbidden`, the `ok` response has a body of type `Sample` along with descriptions:

```yaml
response:
  ok: Sample        # sample is created
  forbidden: empty  # user is forbidden to create sample
```

The `response` field of [endpoint](#endpoint) defines all possible responses of the HTTP endpointed. The `response` is a dictionary where key is the name of the response and value is the type of the response. Responses names should be in a text form according to [RFC 7231](https://tools.ietf.org/html/rfc7231) but in `snake_case`. So, `OK` will be `ok`, `Unauthorized` - `unauthorized`, `Method Not Allowed` - `method_not_allowed`, etc.

At least one response should be always defined for any HTTP endpoint.