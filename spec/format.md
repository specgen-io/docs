---
description: This page overviews spec format
---

# Format Overview

## Basics

Spec format is based on YAML. Each spec file is a YAML file. In many aspects spec format resembles to [OpenAPI](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md). Main purpose of spec is to provide more compact (then OpenAPI) way of defining API and also limit some capabilities of OpenAPI.

## Spec Structure

Here's an example of simplest spec:

```yaml
spec: 2                      #  Meta information
name: example
version: 1

http:                        #  HTTP Endpoints
  sample:                    #  API
    get_sample:              #  Endpoint
      endpoint: GET /sample
      response:
        ok: Sample

models:                      #  Models
  Sample:                    #  Model name
    field1: string
    field2: int
```

Spec YAML file consists of following sections:

* Meta information
* HTTP
* Models

## Meta Information

Meta information is presented in form for keys at the top level of the YAML file. In the example above `spec`, `name` and `version` are meta information fields.

Here's the list of supported meta information fields:

| Name | Description |
| :--- | :--- |
| spec | Version of spec format |
| name | Name of the specification, should be in [kebab-case](http://wiki.c2.com/?KebabCase) |
| version | Version of the specification |

## HTTP Endpoints

HTTP endpoints are defined in `http` section of the spec. Endpoints are grouped in APIs. APIs are used in code generation and should bundle together related endpoints. Read more about endpoints in the [HTTP Endpoints](http.md) section.

## Models

Models are defined in `models` section of the spec. This section allows to define custom user types, including object models, enums, and tagged unions. These user-defined models can be used in endpoints where needed by their names.

Read more about endpoints in the [Models](models.md) section.