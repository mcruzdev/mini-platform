# Hello minictl

## Before you begin

Before all, you need to install:

- GoLang version 1.20.4

## Creating the project

Let's start, create the folder to be the **minictl** home:

```sh
    mkdir minictl && cd minictl
```

Init the project with GoLang tooling:

```sh
    go mod init com.github.mcruzdev.miniplatform.minictl
```

## Creating the root command
Install cobra module:

```sh
    go get -u github.com/spf13/cobra@latest
```

Let's to create the *main.go* file:

The following file will be our entrypoint:

```go
// main.go
package main

import (
	"com.github.mcruzdev.miniplatform.minictl/cmd/minictl"
)

func main() {
	minictl.Execute()
}
```

Let's to create the main command (root):

```go
// cmd/minictl/minictl.go
package minictl

import (
	"fmt"
	"github.com/spf13/cobra"
)

var rootCmd = &cobra.Command{
	Use: "minictl",
	Run: func(cmd *cobra.Command, args []string) {
		fmt.Println("Running inside minictl")
	},
}

func Execute() {
	rootCmd.Execute()
}
```

To build and execute the CLI, do:

1. `go build main.go`
2. `./main.go`

The output should look like:

```sh
Running inside minictl
```

## Creating the **create application** command

To organize our CLI project, let's create a page for create command:

Inside the root directory, run the following command:

```sh
    mkdir create && touch create/create.go && touch create/application.go

```

First, we will create the command for command `create`, we can have some sub-commands.

```go
// create/create.go
package create

import (
	"fmt"
	"github.com/spf13/cobra"
)

// CommandCreate handles minictl create command.
func CommandCreate() *cobra.Command {
	var createCmd = &cobra.Command{
		Use: "create",
		Run: func(cmd *cobra.Command, args []string) {
			fmt.Println("Running create command")
		},
	}

	createCmd.AddCommand(CommandCreateApplication())
	return createCmd
}
```

On *create/application.go* we will handle the command `minictl create application --name=minictl-api` command.

```go
// create/application.go
package create

import (
	"fmt"
	"github.com/spf13/cobra"
	"log"
)

var applicationName string

func CommandCreateApplication() *cobra.Command {
	var createApplicationCmd = &cobra.Command{
		Use: "application",
		Run: func(cmd *cobra.Command, args []string) {
			log.Println(fmt.Sprintf("Creating application with name '%s'", applicationName))
		},
	}

	createApplicationCmd.PersistentFlags().StringVar(&applicationName, "name", "", "--name=application-name")
	_ = createApplicationCmd.MarkPersistentFlagRequired("name")

	return createApplicationCmd
}
```

Build the CLI and run again with `./main create application --name=my-application` to see the output.

The output should looks like it:

```sh
2023/05/11 21:34:17 Creating application with name 'my-application'
```


