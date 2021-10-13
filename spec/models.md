# Models

Models section of the spec allows to define custom types. It supports [object types](#object-model), [enum types](#enum-model) and [tagged union types](#tagged-union-model). 

## Object Model

Here's an example of object model definition:

```yaml
Person:  # some information about person
  first_name: string
  middle_name: string?
  last_name: string
  year_of_birth: int  # in what year person was born
```

The object model above represents the JSON object. Here's an example of such JSON object:

```json
{
  "first_name": "John",
  "last_name": "Smith",
  "year_of_birth": 1935
}
```

Definition of `object` model is a dictionary where each item represents an object field. The key of the dictionary item as a field name and value a field type. 

The example above provides optional model descripton in the form of line comment `# some information about person`. This description is used for documentation purposes only.

Each field might have a description in the form of line comment, like `year_of_birth` has the comment `# in what year person was born` in the example above.

## Enum Model

Enum is represented in JSON as a string with limited set of possible values.

Here's an example of enum model:

```yaml
Model:   # count to three
  enum:
    first: ONE
    second: TWO
    third: THREE
```

The enum model above represents enumeration of following JSON values: `"ONE"`, `"TWO"`, `"THREE"`.

The `enum` field of the model definition defines enum items. Enum item name and value might be different as in example above: `first` value is `ONE`, etc. Enum item name is used in generated code and enum item value is the value that supposed to be in JSON when the enum model is serialized/deserializd. In this format `enum` field is a dictionary where each key is the name of enum item and value is JSON value of enum item.

The enum items could be declared in a short form if each enum item name and item value are the same. Here's an example of enum declared in such short format:

```yaml
Model:   # count to three
  enum:
    - first
    - second
    - third
```

The enum model above represents enumeration of following JSON values: `"first"`, `"second"`, `"third"`.

In this format `enum` field is an array of string values. Each string value is enum item name and item JSON value at the same time.

Both examples above provide optional model descripton (`# count to three`). This description is used for documentation purposes only.

## Tagged Union Model

The `oneOf` documentation will be provided here.