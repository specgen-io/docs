# specgen

Code generation based of service specification

### Commands
* [client-go](#client-go)
* [client-ruby](#client-ruby)
* [client-scala-sttp](#client-scala-sttp)
* [client-ts-axios](#client-ts-axios)
* [completion](#completion)
* [markdown](#markdown)
* [models-go](#models-go)
* [models-java](#models-java)
* [models-ruby](#models-ruby)
* [models-scala-circe](#models-scala-circe)
* [models-ts](#models-ts)
* [openapi](#openapi)
* [service-go](#service-go)
* [service-java-spring](#service-java-spring)
* [service-scala-play](#service-scala-play)
* [service-ts](#service-ts)
* [spec-format](#spec-format)

## client-go

Generate Go client source code

```
specgen client-go [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for client-go
      --module-name string     Module name
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## client-ruby

Generate Ruby client source code

```
specgen client-ruby [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for client-ruby
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## client-scala-sttp

Generate Scala Sttp client source code

```
specgen client-scala-sttp [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for client-scala-sttp
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## client-ts-axios

Generate TypeScript Axios client source code

```
specgen client-ts-axios [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for client-ts-axios
      --spec-file string       Path to service specification file
      --validation string      TypeScript validation library: superstruct, io-ts (default "superstruct")
  -v, --verbose   verbose output
```

## completion

generate the autocompletion script for the specified shell

### Synopsis


Generate the autocompletion script for specgen for the specified shell.
See each sub-command's help for details on how to use the generated script.


### Options

```
  -h, --help   help for completion
  -v, --verbose   verbose output
```

## completion bash

generate the autocompletion script for bash

### Synopsis


Generate the autocompletion script for the bash shell.

This script depends on the 'bash-completion' package.
If it is not installed already, you can install it via your OS's package manager.

To load completions in your current shell session:
$ source <(specgen completion bash)

To load completions for every new session, execute once:
Linux:
  $ specgen completion bash > /etc/bash_completion.d/specgen
MacOS:
  $ specgen completion bash > /usr/local/etc/bash_completion.d/specgen

You will need to start a new shell for this setup to take effect.
  

```
specgen completion bash
```

### Options

```
  -h, --help              help for bash
      --no-descriptions   disable completion descriptions
  -v, --verbose   verbose output
```

## completion fish

generate the autocompletion script for fish

### Synopsis


Generate the autocompletion script for the fish shell.

To load completions in your current shell session:
$ specgen completion fish | source

To load completions for every new session, execute once:
$ specgen completion fish > ~/.config/fish/completions/specgen.fish

You will need to start a new shell for this setup to take effect.


```
specgen completion fish [flags]
```

### Options

```
  -h, --help              help for fish
      --no-descriptions   disable completion descriptions
  -v, --verbose   verbose output
```

## completion powershell

generate the autocompletion script for powershell

### Synopsis


Generate the autocompletion script for powershell.

To load completions in your current shell session:
PS C:\> specgen completion powershell | Out-String | Invoke-Expression

To load completions for every new session, add the output of the above command
to your powershell profile.


```
specgen completion powershell [flags]
```

### Options

```
  -h, --help              help for powershell
      --no-descriptions   disable completion descriptions
  -v, --verbose   verbose output
```

## completion zsh

generate the autocompletion script for zsh

### Synopsis


Generate the autocompletion script for the zsh shell.

If shell completion is not already enabled in your environment you will need
to enable it.  You can execute the following once:

$ echo "autoload -U compinit; compinit" >> ~/.zshrc

To load completions for every new session, execute once:
# Linux:
$ specgen completion zsh > "${fpath[1]}/_specgen"
# macOS:
$ specgen completion zsh > /usr/local/share/zsh/site-functions/_specgen

You will need to start a new shell for this setup to take effect.


```
specgen completion zsh [flags]
```

### Options

```
  -h, --help              help for zsh
      --no-descriptions   disable completion descriptions
  -v, --verbose   verbose output
```

## markdown

Generate doc documentation

```
specgen markdown [flags]
```

### Options

```
  -h, --help   help for markdown
  -v, --verbose   verbose output
```

## models-go

Generate Go models source code

```
specgen models-go [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for models-go
      --module-name string     Module name
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## models-java

Generate Java models source code

```
specgen models-java [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for models-java
      --package-name string    Package name
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## models-ruby

Generate Ruby models source code

```
specgen models-ruby [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for models-ruby
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## models-scala-circe

Generate Scala models source code

```
specgen models-scala-circe [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for models-scala-circe
      --spec-file string       Path to service specification file
  -v, --verbose   verbose output
```

## models-ts

Generate TypeScript models

```
specgen models-ts [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for models-ts
      --spec-file string       Path to service specification file
      --validation string      TypeScript validation library: superstruct, io-ts
  -v, --verbose   verbose output
```

## openapi

Generate OpenAPI specification

```
specgen openapi [flags]
```

### Options

```
  -h, --help               help for openapi
      --out-file string    Path to output file
      --spec-file string   Path to service specification file
  -v, --verbose   verbose output
```

## service-go

Generate Go service source code

```
specgen service-go [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for service-go
      --module-name string     Module name
      --services-path string   Path to scaffold services code
      --spec-file string       Path to service specification file
      --swagger-path string    Path to folder where swagger specification should be generated
  -v, --verbose   verbose output
```

## service-java-spring

Generate Spring Java service source code

```
specgen service-java-spring [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for service-java-spring
      --package-name string    Package name
      --services-path string   Path to scaffold services code
      --spec-file string       Path to service specification file
      --swagger-path string    Path to folder where swagger specification should be generated
  -v, --verbose   verbose output
```

## service-scala-play

Generate Scala Play service source code

```
specgen service-scala-play [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for service-scala-play
      --services-path string   Path to scaffold services code
      --spec-file string       Path to service specification file
      --swagger-path string    Path to folder where swagger specification should be generated
  -v, --verbose   verbose output
```

## service-ts

Generate TypeScript Axios client source code

```
specgen service-ts [flags]
```

### Options

```
      --generate-path string   Path to generate source code into
  -h, --help                   help for service-ts
      --server string          TypeScript server library: express, koa
      --services-path string   Path to scaffold services code
      --spec-file string       Path to service specification file
      --swagger-path string    Path to folder where swagger specification should be generated
      --validation string      TypeScript validation library: superstruct, io-ts
  -v, --verbose   verbose output
```

## spec-format

Format spec

```
specgen spec-format [flags]
```

### Options

```
  -h, --help               help for spec-format
      --spec-file string   Path to service specification file
  -v, --verbose   verbose output
```