# Introduction

I've worked in several companies where it was necessary to do all the deployment manually, I work in a company where I don't need to worry about anything about CI, just having a Dockerfile at the root of my Java application, GoLang or NodeJS. 

The idea here is give to our developers a way to create a version for their applications and finally publish this versions as a docker image artefact for deploying.

## Adding a new command for our CLI

We have a command called `minictl`, you can see the how I created it [here](../creating-minictl/index.md).

The following code aims to add a new CLI command to create a version:

```go
package create

import (
	"fmt"
	"log"

	"github.com/spf13/cobra"
)

var version string

func NewCreateVersionCommand() *cobra.Command {
	createVersionCommand := &cobra.Command{
		Use: "version",
		Run: func(cmd *cobra.Command, args []string) {
			log.Println(fmt.Sprintf("Creating a new version with semver number '%s'", version))
		},
	}

	createVersionCommand.PersistentFlags().StringVar(&version, "number", "", "--version=0.1.0")
	_ = createVersionCommand.MarkPersistentFlagRequired("number")

	return createVersionCommand
}
```

Was necessary to add this command to parent command `create`:

```go
// create/create.go

	createCmd.AddCommand(NewCreateApplicationCommand())
	createCmd.AddCommand(NewCreateVersionCommand())
```

I've decided not to worry about validations here, I'll worry about calling our continue integration tool now.