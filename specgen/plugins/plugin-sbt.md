# Sbt

Spec scala code generation is packaged in form of SBT plugins. Add `sbt-specgen` plugin library into the sbt project using following line in the `plugins.sbt`:

```text
addSbtPlugin("io.specgen" % "sbt-specgen" % "<version>")
```

Instead of `<version>` use latest available from [Maven Central Repository](https://search.maven.org/artifact/io.specgen/sbt-specgen).

## Play Service

Spec code generation has full support for Scala Play applications. Models, controllers, services traits and services scaffolded implementations are generated by `SpecPlay` plugin.

To enable server side code generation from spec enable `SpecPlay` plugin in your `build.sbt`:

```text
enablePlugins(SpecPlay)
```

Following dependencies are defined in `SpecPlay` and should be added into `libraryDependencies`:

```text
libraryDependencies ++= specPlayDependencies
```

Specgen plugin generates router that should be pluged into `conf/routes`:

```text
#  spec routes
-> / app.SpecRouter
```

Here are `SpecPlay` settings that allow customization of code generation:

| Setting          | Default                              | Description |
| :--------------- | :----------------------------------- | :---------- |
| specFile         | `spec.yaml`                          | Path to service specification file; relative to project folder |
| specSwagger      | `public/swagger.yaml`                | Path to generated OpenAPI/Swagger specification file |
| specGeneratePath | `target/scala/src_managed/main/spec` | Path to generate source code into |
| specServicesPath | `app/services`                       | Path to scaffolded services files; these services are scaffolded only if they do not exist |

Default settings are aligned with the standard [Play application layout](https://www.playframework.com/documentation/2.7.x/Anatomy).

Generated swagger (OpenAPI) documentation could be hosted. Following routes should be added to `conf/routes`:

```text
#  documentation
GET  /docs              controllers.Default.redirect(to="/docs/index.html?url=swagger.yaml")
GET  /docs/swagger.yaml controllers.Assets.at(path="/public", file="swagger.yaml")
GET  /docs/*file        controllers.Assets.at(path="/public/lib/swagger-ui", file)
```

This setup above hosts swagger documentation at `/docs` route of the Play application.

## Sttp Client

Spec code generation can generate HTTP client in Scala based on spec. The generated client is using [sttp](https://github.com/softwaremill/sttp) client under the hood with provided ability to plugin backend of your taste.

To enable client code generation from spec enable `SpecSttp` plugin in your `build.sbt`:

```text
enablePlugins(SpecSttp)
```

Following dependencies are defined in `SpecSttp` and should be added into `libraryDependencies`:

```text
libraryDependencies ++= specSttpDependencies
```

Here are `SpecSttp` settings that allow customization of code generation:

| Setting          | Default                              | Description |
| :--------------- | :----------------------------------- | :---------- |
| specFile         | `spec.yaml`                          | Path to spec file relative to project folder |
| specGeneratePath | `target/scala/src_managed/main/spec` | Path to generated code is placed |

## Models Circe

Spec code generation can generate only (de)serializable to JSON [circe](#https://github.com/circe/circe) models without any application specifics.

To enable models generation from spec enable `SpecCirce` plugin in your `build.sbt`:

```text
enablePlugins(SpecModels)
```

Following dependencies are defined in `SpecCirce` and should be added into `libraryDependencies`:

```text
libraryDependencies ++= specCirceDependencies
```

Here are `SpecCirce` settings that allow customization of code generation:

| Setting          | Default                              | Description |
| :--------------- | :----------------------------------- | :---------- |
| specFile         | `spec.yaml`                          | Path to spec file relative to project folder |
| specGeneratePath | `target/scala/src_managed/main/spec` | Path to generated code is placed |

## Under the Hood

All specgen SBT plugins are running [specgen](https://github.com/specgen-io/specgen) command line tool. The specgen command line tool binaries are packaged as a resource into `sbt-specgen` plugin jar. On any `sbt-specgen` plugin execution it unpacks `specgen` binaries from itself and executing commands using those binaries.