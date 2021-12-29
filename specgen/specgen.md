# specgen

Code generation based on specification

## Commands List
* [client-go](#client-go)
* [client-java](#client-java)
* [client-kotlin](#client-kotlin)
* [client-ruby](#client-ruby)
* [client-scala](#client-scala)
* [client-ts](#client-ts)
* [models-go](#models-go)
* [models-java](#models-java)
* [models-kotlin](#models-kotlin)
* [models-ruby](#models-ruby)
* [models-scala](#models-scala)
* [models-ts](#models-ts)
* [openapi](#openapi)
* [service-go](#service-go)
* [service-java](#service-java)
* [service-scala](#service-scala)
* [service-ts](#service-ts)
* [spec-convert](#spec-convert)
* [spec-format](#spec-format)


## client-go

Generate Go client source code

```
specgen client-go [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--module-name` - Module name.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for client-go.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## client-java

Generate Java client source code

```
specgen client-java [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--package-name` - Package name.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for client-java.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## client-kotlin

Generate Kotlin client source code

```
specgen client-kotlin [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--package-name` - Package name.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for client-kotlin.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## client-ruby

Generate Ruby client source code

```
specgen client-ruby [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for client-ruby.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## client-scala

Generate Scala client source code

```
specgen client-scala [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for client-scala.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## client-ts

Generate TypeScript client source code

```
specgen client-ts [flags]
```

**Flags**
* `--client` - Client TypeScript library: axios, node-fetch, browser-fetch.
     Not required.
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--validation` - Validation TypeScript library: superstruct, io-ts.
     Not required.
* `--help`, `-h` - Help for client-ts.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-go

Generate Go models source code

```
specgen models-go [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--module-name` - Module name.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for models-go.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-java

Generate Java models source code

```
specgen models-java [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--package-name` - Package name.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for models-java.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-kotlin

Generate Kotlin models source code

```
specgen models-kotlin [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--jsonlib` - Kotlin JSON library: jackson.
     Not required. Default value: `jackson`.
* `--package-name` - Package name.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for models-kotlin.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-ruby

Generate Ruby models source code

```
specgen models-ruby [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for models-ruby.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-scala

Generate Scala models source code

```
specgen models-scala [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for models-scala.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## models-ts

Generate TypeScript models source code

```
specgen models-ts [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--validation` - Validation TypeScript library: superstruct, io-ts.
     Not required.
* `--help`, `-h` - Help for models-ts.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## openapi

Generate OpenAPI specification

```
specgen openapi [flags]
```

**Flags**
* `--out-file` - Path to output file.
     Required.
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for openapi.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## service-go

Generate Go service source code

```
specgen service-go [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--module-name` - Module name.
     Required.
* `--services-path` - Path to scaffold services code.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--swagger-path` - Path of generated OpenAPI (Swagger) specification file.
     Not required.
* `--help`, `-h` - Help for service-go.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## service-java

Generate Java service source code

```
specgen service-java [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--package-name` - Package name.
     Not required.
* `--services-path` - Path to scaffold services code.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--swagger-path` - Path of generated OpenAPI (Swagger) specification file.
     Not required.
* `--help`, `-h` - Help for service-java.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## service-scala

Generate Scala service source code

```
specgen service-scala [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--services-path` - Path to scaffold services code.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--swagger-path` - Path of generated OpenAPI (Swagger) specification file.
     Not required.
* `--help`, `-h` - Help for service-scala.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## service-ts

Generate TypeScript client source code

```
specgen service-ts [flags]
```

**Flags**
* `--generate-path` - Path to generate source code into.
     Required.
* `--server` - Server TypeScript library: express, koa.
     Required.
* `--services-path` - Path to scaffold services code.
     Not required.
* `--spec-file` - Path to specification file.
     Required.
* `--swagger-path` - Path of generated OpenAPI (Swagger) specification file.
     Not required.
* `--validation` - Validation TypeScript library: superstruct, io-ts.
     Required.
* `--help`, `-h` - Help for service-ts.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## spec-convert

Convert spec from older versions to latest

```
specgen spec-convert [flags]
```

**Flags**
* `--format` - Specification format to convert specification from: spec-2.0, openapi.
     Required.
* `--in-file` - Path for input specification file.
     Required.
* `--out-file` - Path to output file.
     Not required. Default value: `spec.yaml`.
* `--help`, `-h` - Help for spec-convert.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.


## spec-format

Format spec

```
specgen spec-format [flags]
```

**Flags**
* `--spec-file` - Path to specification file.
     Required.
* `--help`, `-h` - Help for spec-format.
     Not required. Default value: `false`.
* `--verbose`, `-v` - Verbose output.
     Not required. Default value: `false`.

