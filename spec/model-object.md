# Object Model

Here's an example of object model definition:

```yaml
Model:
  description: the model
  fields:
    field1: string
    field2: int
```

Here's information about object model fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| fields | yes | dictionary of fields, keys are names of fields |
| description | no | description of the model, used for documentation |

As table above shows object model could be defined in short form with fields only:

```yaml
Model:  # the model
  field1: string
  field2: int
```

## Object Field

Here's an example of field definition:

```yaml
field1:
  type: string
  description: some field
```

Here's information about field definition fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| type | yes | type of the field |
| description | no | description of the field, used for documentation |

Here's an example of short form equivalent to long field definition from above:

```yaml
field1: string # some field
```



