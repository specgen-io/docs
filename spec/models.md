# Models

Models section of the spec allows to define custom types. It supports [object types](#object), [enum types](#enum) and [tagged union](#tagged-union). 

## Object

Here's an example of object model definition:

```yaml
Person:  # some information about person
  object:
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

The `object` field is a dictionary where each item represents single field. The key of the dictionary item as a field name and value is a field type.

The example above provides optional model descripton in the form of line comment `# some information about person`. This description is used for documentation purposes only.

Each field might have a description in the form of line comment, like `year_of_birth` has the comment `# in what year person was born` in the example above.

## Enum

Enum is represented in JSON as a string with limited set of possible values.

Here's an example of enum model:

```yaml
Count:   # count to three
  enum:
    first: ONE
    second: TWO
    third: THREE
```

The enum model above represents enumeration of following JSON values: `"ONE"`, `"TWO"`, `"THREE"`.

The `enum` field of the model definition defines enum items. Enum item name and value might be different as in example above: `first` value is `ONE`, etc. Enum item name is used in generated code and enum item value is the value that supposed to be in JSON when the enum model is serialized/deserializd. In this format `enum` field is a dictionary where each key is the name of enum item and value is JSON value of enum item.

The enum items could be declared in a short form if each enum item name and item value are the same. Here's an example of enum declared in such short format:

```yaml
Count:   # count to three
  enum:
    - first
    - second
    - third
```

The enum model above represents enumeration of following JSON values: `"first"`, `"second"`, `"third"`.

In this format `enum` field is an array of string values. Each string value is enum item name and item JSON value at the same time.

Both examples above provide optional model descripton (`# count to three`). This description is used for documentation purposes only.

## Tagged Union

[Tagged union](https://en.wikipedia.org/wiki/Tagged_union) is a data structure used to hold a value that could take on several different, but fixed, types. Only one of the types can be in use at any one time, and a tag field explicitly indicates which one is in use. There are other names for tagged union. This documentation intentionally uses "tagged union" to emphasize role of the tag.

There's no built-in support for tagged unions in JSON format. However there are two conventions for tagged unions representation: [tagged-union-wrapping-object](#) and [tagged-union-discriminator-field](#). These both conventions are supported by spec. 

### Tagged Union - Wrapping Object

Let's imagine there's tagged union of two types: `kitten` of type `Cat` and `puppy` of type `Dog`.
Here's how it could be defined in the spec:

```yaml
Pet:  # pet allowed to live in apartment
  oneOf:
    kitten: Cat
    puppy: Dog   # dogs are better
```

In the example above `kitten` and `puppy` are tags and `Cat` and `Dog` are tags types. Object models definitions for `Cat` and `Dog` are omitted here. The `oneOf` field is a dictionary where each item represents single tag. The key of the dictionary item as a tag name and value is a tag type.

Here's how such tagged union would look like in JSON in wrapping object format:

```json
{ "kitten": ...Cat... }

{ "puppy": ...Dog... }
```

In the example above tagged union wrapping object is an object with the single field, the name of the field is the name of the tag and value of the field corresponds to tag type.

The example above provides optional model descripton in the form of line comment `# pet allowed to live in apartment`. This description is used for documentation purposes only.

Each tag might have a description in the form of line comment, like `puppy` has the comment `# dogs are better` in the example above.

### Tagged Union - Discriminator Field

The other possible representation of the tagged union in JSON is adding discriminator field to the object denoting the tag. Here's how it would look like for the `Pet` model:

```json
{ "case": "kitten", ...Cat fields... }

{ "case": "puppy", ...Dog fields... }
```

Here's `case` is the discriminator field. It's value points to the union tag. Such discriminator field is added to the object representing tag value. This way of representation is limitted since discriminator field can be added only to some object hence tag type has to be object model type.

Here's how to make tagged union to be represented by object with discriminator field:

```yaml
Pet:  # pet allowed to live in apartment
  discriminator: case
  oneOf:
    kitten: Cat
    puppy: Dog   # dogs are better
```

The definition above differs from [wrapping object](#tagged-union-wrapping-object) by additional field `discriminator`. The value of `discriminator` field is the name of the `discriminator` field as it should appear in JSON. In the example above `case` is defined as `discriminator` field.