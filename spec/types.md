# Types

JSON supports very limited number of types: string, number, boolean, object, array, null. Specifying JSON type is often not enough when it comes HTTP API definition and to what is allowed/prohibited as query/header/body value. For example, if the endpoint expects date and time in ISO 8601 format then in JSON it's just a string, though API user supposed to pass a string only in a specific format.

The null is a problem across all JSON types. All fields can be null in JSON. Though usually API is very sensitive to null values and does not allow nulls everywhere.

Spec has it's own list of supported types to close gaps mentioned above and to provide declarative way of defining types. This section describes these types.

## Primitive Types



| Spec type | JSON type | Notes |
| :--- | :--- | :--- |
| int int32 | number | -2147483648 to 2147483647 |
| long int64 | number | -9223372036854775808 to 9223372036854775807 |
| float | number | 32 bit IEEE 754 single-precision float |
| double | number | 64 bit IEEE 754 double-precision float |
| decimal | number | arbitrary-precision signed decimal |
| bool boolean | boolean |  |
| string str | string |  |
| uuid | string | lower case hex symbols with hyphens as 8-4-4-4-12 |
| date | string | ISO 8601 yyyy-mm-dd |
| datetime | string | ISO 8601 yyyy-mm-ddThh:mm:ss.ffffff |
| json | object | any unstructured JSON |
| empty | N/A | represents nothing, similar to unit is some langs |

## Nullable Types

By default all types can't have `null` value. The `?` modifier after type defines nullable type. For example `string` can not be `null` though `string?` can have null value.

## Array and Dictionary

Following modifiers allow to specify data structures:

| Modifier | JSON type | Notes |
| :--- | :--- | :--- |
| the\_type\[\] | array | array of items of the\_type |
| the\_type{} | object | dictionary with property values of the\_type |

For example `string[]` represents array of strings. The type `int{}` represents JSON object where all properties values are integers.

