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

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --module-name   | yes      |         | module name                        |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for client-go                 |
|  -v    | --verbose       | no       | false   | verbose output                     |


## client-java

Generate Java client source code

```
specgen client-java [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --package-name  | yes      |         | package name                       |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for client-java               |
|  -v    | --verbose       | no       | false   | verbose output                     |


## client-kotlin

Generate Kotlin client source code

```
specgen client-kotlin [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --package-name  | yes      |         | package name                       |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for client-kotlin             |
|  -v    | --verbose       | no       | false   | verbose output                     |


## client-ruby

Generate Ruby client source code

```
specgen client-ruby [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for client-ruby               |
|  -v    | --verbose       | no       | false   | verbose output                     |


## client-scala

Generate Scala client source code

```
specgen client-scala [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for client-scala              |
|  -v    | --verbose       | no       | false   | verbose output                     |


## client-ts

Generate TypeScript client source code

```
specgen client-ts [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                                  |
|  :---- | :-------------- | :------: | :------ | :----------------------------------------------------------  |
|        | --client        | no       |         | client TypeScript library: axios, node-fetch, browser-fetch  |
|        | --generate-path | yes      |         | path to generate source code into                            |
|        | --spec-file     | yes      |         | path to specification file                                   |
|        | --validation    | no       |         | validation TypeScript library: superstruct, io-ts            |
|  -h    | --help          | no       | false   | help for client-ts                                           |
|  -v    | --verbose       | no       | false   | verbose output                                               |


## models-go

Generate Go models source code

```
specgen models-go [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --module-name   | yes      |         | module name                        |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for models-go                 |
|  -v    | --verbose       | no       | false   | verbose output                     |


## models-java

Generate Java models source code

```
specgen models-java [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --package-name  | no       |         | package name                       |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for models-java               |
|  -v    | --verbose       | no       | false   | verbose output                     |


## models-kotlin

Generate Kotlin models source code

```
specgen models-kotlin [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --jsonlib       | no       | jackson | Kotlin JSON library: jackson       |
|        | --package-name  | no       |         | package name                       |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for models-kotlin             |
|  -v    | --verbose       | no       | false   | verbose output                     |


## models-ruby

Generate Ruby models source code

```
specgen models-ruby [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for models-ruby               |
|  -v    | --verbose       | no       | false   | verbose output                     |


## models-scala

Generate Scala models source code

```
specgen models-scala [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                        |
|  :---- | :-------------- | :------: | :------ | :--------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into  |
|        | --spec-file     | yes      |         | path to specification file         |
|  -h    | --help          | no       | false   | help for models-scala              |
|  -v    | --verbose       | no       | false   | verbose output                     |


## models-ts

Generate TypeScript models source code

```
specgen models-ts [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                        |
|  :---- | :-------------- | :------: | :------ | :------------------------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into                  |
|        | --spec-file     | yes      |         | path to specification file                         |
|        | --validation    | no       |         | validation TypeScript library: superstruct, io-ts  |
|  -h    | --help          | no       | false   | help for models-ts                                 |
|  -v    | --verbose       | no       | false   | verbose output                                     |


## openapi

Generate OpenAPI specification

```
specgen openapi [flags]
```

**Flags**

|  Short | Long        | Required | Default | Description                 |
|  :---- | :---------- | :------: | :------ | :-------------------------  |
|        | --out-file  | yes      |         | path to output file         |
|        | --spec-file | yes      |         | path to specification file  |
|  -h    | --help      | no       | false   | help for openapi            |
|  -v    | --verbose   | no       | false   | verbose output              |


## service-go

Generate Go service source code

```
specgen service-go [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                             |
|  :---- | :-------------- | :------: | :------ | :-----------------------------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into                       |
|        | --module-name   | yes      |         | module name                                             |
|        | --services-path | no       |         | path to scaffold services code                          |
|        | --spec-file     | yes      |         | path to specification file                              |
|        | --swagger-path  | no       |         | path of generated OpenAPI (Swagger) specification file  |
|  -h    | --help          | no       | false   | help for service-go                                     |
|  -v    | --verbose       | no       | false   | verbose output                                          |


## service-java

Generate Java service source code

```
specgen service-java [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                             |
|  :---- | :-------------- | :------: | :------ | :-----------------------------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into                       |
|        | --package-name  | no       |         | package name                                            |
|        | --services-path | no       |         | path to scaffold services code                          |
|        | --spec-file     | yes      |         | path to specification file                              |
|        | --swagger-path  | no       |         | path of generated OpenAPI (Swagger) specification file  |
|  -h    | --help          | no       | false   | help for service-java                                   |
|  -v    | --verbose       | no       | false   | verbose output                                          |


## service-scala

Generate Scala service source code

```
specgen service-scala [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                             |
|  :---- | :-------------- | :------: | :------ | :-----------------------------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into                       |
|        | --services-path | no       |         | path to scaffold services code                          |
|        | --spec-file     | yes      |         | path to specification file                              |
|        | --swagger-path  | no       |         | path of generated OpenAPI (Swagger) specification file  |
|  -h    | --help          | no       | false   | help for service-scala                                  |
|  -v    | --verbose       | no       | false   | verbose output                                          |


## service-ts

Generate TypeScript client source code

```
specgen service-ts [flags]
```

**Flags**

|  Short | Long            | Required | Default | Description                                             |
|  :---- | :-------------- | :------: | :------ | :-----------------------------------------------------  |
|        | --generate-path | yes      |         | path to generate source code into                       |
|        | --server        | yes      |         | server TypeScript library: express, koa                 |
|        | --services-path | no       |         | path to scaffold services code                          |
|        | --spec-file     | yes      |         | path to specification file                              |
|        | --swagger-path  | no       |         | path of generated OpenAPI (Swagger) specification file  |
|        | --validation    | yes      |         | validation TypeScript library: superstruct, io-ts       |
|  -h    | --help          | no       | false   | help for service-ts                                     |
|  -v    | --verbose       | no       | false   | verbose output                                          |


## spec-convert

Convert spec from older versions to latest

```
specgen spec-convert [flags]
```

**Flags**

|  Short | Long       | Required | Default   | Description                                                            |
|  :---- | :--------- | :------: | :-------- | :--------------------------------------------------------------------  |
|        | --format   | yes      |           | specification format to convert specification from: spec-2.0, openapi  |
|        | --in-file  | yes      |           | path for input specification file                                      |
|        | --out-file | no       | spec.yaml | path to output file                                                    |
|  -h    | --help     | no       | false     | help for spec-convert                                                  |
|  -v    | --verbose  | no       | false     | verbose output                                                         |


## spec-format

Format spec

```
specgen spec-format [flags]
```

**Flags**

|  Short | Long        | Required | Default | Description                 |
|  :---- | :---------- | :------: | :------ | :-------------------------  |
|        | --spec-file | yes      |         | path to specification file  |
|  -h    | --help      | no       | false   | help for spec-format        |
|  -v    | --verbose   | no       | false   | verbose output              |