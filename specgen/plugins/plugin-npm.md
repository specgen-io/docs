# npm

Spec TypeScript code generation is packaged in form of npm package. Add following dependency to your project:

```shell
% npm install --dev specgen.io
```

The has specgen command line tool is built inside of the npm package.

Add the following [script](https://docs.npmjs.com/cli/v7/using-npm/scripts) to `package.json`:

```json
"specgen": "specgen <command>  <args>"
```

In this `specgen` script `<command>` stands for specific [specgen tool](../specgen.md) command. Here are commands that generate TypeScript code: [`service-ts`](../specgen.md#service-ts), [`client-ts`](../specgen.md#client-ts), [`models-ts`](../specgen.md#models-ts).

To run code generation execute `specgen` script:

```shell
% npm run specgen
```

This page provides some examples of specgen scripts configuration.

## Express Service

The example below generates [Express](https://expressjs.com/) server with [Superstruct](https://docs.superstructjs.org/) models to `./src/spec` and OpenAPI specification to `./docs/swagger.yaml`. The command also scaffolds services (only if they don't exist yet) that should be implemented by developers and puts the code into `./src/services` path.

```json
"specgen": "specgen service-ts --server express --validation superstruct --spec-file ./spec.yaml --generate-path ./src/spec --swagger-path ./docs/swagger.yaml --services-path ./src/services"
```

Read [`service-ts`](../specgen.md#service-ts) documentation for command details.

## Koa Service

The example below generates [koa](https://koajs.com/) server with [io-ts](https://github.com/gcanti/io-ts) models to `./src/spec` and OpenAPI specification to `./docs/swagger.yaml`. The command also scaffolds services (only if they don't exist yet) that should be implemented by developers and puts the code into `./src/services` path.

```json
"specgen": "specgen service-ts --server koa --validation io-ts --spec-file ./spec.yaml --generate-path ./src/spec --swagger-path ./docs/swagger.yaml --services-path ./src/services"
```

Read [`service-ts`](../specgen.md#service-ts) documentation for command details.

## Axios Client

The example below generates [Axios](https://axios-http.com/docs/intro) HTTP client with [Superstruct](https://docs.superstructjs.org/) models from `./spec.yaml` speicification and puts generated code to `./src/spec`.


```json
"specgen": "specgen client-ts --client axios --validation superstruct --spec-file ./spec.yaml --generate-path ./src/spec"
```

Read [`client-ts`](../specgen.md#client-ts) documentation for command details.

## Superstruct Models

The example below generates [Superstruct](https://docs.superstructjs.org/) models from `./spec.yaml` speicification and puts generated code to `./src/spec`.

```json
"specgen": "specgen models-ts --validation superstruct --spec-file ./spec.yaml --generate-path ./src/spec"
```

Read [`models-ts`](../specgen.md#models-ts) documentation for command details.

## io-ts Models

The example below generates [io-ts](https://github.com/gcanti/io-ts) models from `./spec.yaml` speicification and puts generated code to `./src/spec`.

```json
"specgen": "specgen models-ts --validation io-ts --spec-file ./spec.yaml --generate-path ./src/spec"
```

Read [`models-ts`](../specgen.md#models-ts) documentation for command details.