---
description: This page overviews spec format
---

# Format Overview

## Basics

Spec format is based on YAML. Each spec file is YAML file. In many aspects spec format resembles to [OpenAPI](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md). Main purpose of spec is to provide more compact \(then OpenAPI\) way of defining API and also limit some capabilities of OpenAPI.

## Spec Structure

Here's an example of simplest spec:

```yaml
idl_version: 1               # meta information
service_name: example
version: '1'

operations:                  # HTTP operations
  sample:                    # group of operations
    get_sample:
      endpoint: GET /sample
      response:
        ok: Sample

models:                      # models specification
  Sample:                    # name of the model
    field1: string
    field2: int
```

Spec YAML file consists of following sections:

* Meta information
* Operations
* Models

## Meta Information

Meta information is presented in form for keys at the top level of the YAML file. In the example above `idl_version` and `name` are meta information fields.

Here's the list of supported meta information fields:

| Name | Description |
| :--- | :--- |
| idl\_version | Version of spec format |
| name | Name of the specification, should be in [kebab-case](http://wiki.c2.com/?KebabCase) |
| version | Version of the specification |

## Operations

Operations are defining HTTP requests in `operations` section of spec file. Operations are grouped, groups are used in code generation and normally should bundle together related operations. The operation group name should be in [snake\_case](https://en.wikipedia.org/wiki/Snake_case).

## Models

Models section allows to define custom user types, including dictionaries, enums, etc. Described models can be used in operations where needed just by name of the model.

## Short Form

Most entities are defined in YAML as dictionary. Some entities also support short form definition. Short form allows to define APIs in very compact way. While long form allows to specify all details of the API entities. Short form is better readable by humans.

Compare long and short forms of defining field as an example:

```yaml
# short form
field: string = the value     # some field

# long form
field:
  type: string
  default: the value
  description: some field 
```

Entities supporting short form are documented accordingly. Descriptions of most entities could be provided in a comment on the same line where key for entity is defined. In the example above `some field` is a description for the `field` specified via comment on the same line as the field key `field`.

