# Enum Model

Enum is represented in JSON as a string with limited set of possible values.

Here's an example of enum model:

```yaml
Model:
  description: the model
  enum:
    first:
      value: FIRST
      description: First option
    second:
      value: SECOND
      description: Second option
    third:
      value: THIRD
      description: Third option
```

Here's information about enum definition fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| enum | yes | either list of strings or dictionary with keys and values with enum item information |
| description | no | description of the model, used for documentation |

## Short Form

Here's an equivalent example for short form of enum definition:

```yaml
Model:  # the model
  enum:
  - first   # First option
  - second  # Second option
  - third   # Third option
```

## Enum Item

Enum item definition supports following fields:

| Field | Required | Details |
| :--- | :--- | :--- |
| value | no | value of the enum item that should be used in json, if not specified item name is used |
| description | no | description of the item, used for documentation |

### Shortest Format

```yaml
Model:  # the model
  enum:
  - first   # First option
  - second  # Second option
  - third   # Third option
```

### Custom Value

```yaml
Model:  # the model
  enum:
    first:  FIRST   # First option
    second: SECOND  # Second option
    third:  THIRD   # Third option
```

### Longest Format

```yaml
Model:
  enum:
    first:
      value: FIRST
      description: First option
    second:
      value: SECOND
      description: Second option
    third:
      value: THIRD
      description: Third option
```

