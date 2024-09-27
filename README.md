# Git Secrets Replacer
[![Go Report Card](https://goreportcard.com/badge/github.com/TylerStrel/git-secrets-replacer)](https://goreportcard.com/report/github.com/TylerStrel/git-secrets-replacer)

## Overview

Git Secrets Replacer is a tool to help you remove sensitive information (secrets) from the entire history of a Git repository. It allows you to replace secrets in all commits with a sanitized version and optionally force push the changes to the remote repository.

## Features

- Replace secrets across all commits in a Git repository.
- Supports multiple secrets from a secrets file.
- Optionally force push changes to the remote repository.
- Utilizes goroutines for faster processing.

## Installation

### Precompiled Binaries

Download the precompiled binaries for your operating system from the [Releases](https://github.com/TylerStrel/git-secrets-replacer/releases) page.

### From Source

To build from source, you need to have Go installed. Clone the repository and build the binary:

```bash
git clone https://github.com/TylerStrel/git-secrets-replacer.git
cd git-secrets-replacer
go build -o git-secrets-replacer main.go
```

## Usage

### Running the Binary

Run the precompiled binary and follow the prompts:

```bash
./git-secrets-replacer
```

### Running from Source

To run the tool directly from the source code, use the `go run` command:

```bash
go run main.go
```

### Command-Line Flags

The following command-line flags can be used to configure the tool:

- `repoPath`: Path to the repository that the code will run on.
- `secretsFilePath`: Path to the file containing all the secrets that need to be removed.
- `forcePushToOrigin`: True or False flag if the code should force push the changes to the remote/origin.

Example usage:

```bash
go run main.go --repoPath /path/to/repo --secretsFilePath /path/to/secrets.txt --forcePushToOrigin true
```
### Secrets

The `secretsFilePath` should point to a text file that contains all the secrets that need to be removed from the repository history. Each secret should be on a new line.

For example, your `secrets.txt` file might look like this:

```
myPassword
anotherSecret
123456
```
The tool will search for each of these secrets in the repository and replace them with `**REMOVED**`.

### Examples

#### Running from the Source

To run the project from the source, you need to have Go installed on your machine. Follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/TylerStrel/git-secrets-replacer.git
   cd git-secrets-replacer
   ```
 2. Run the project:
    ```sh
    go run main.go
    ```
#### Command Line Flags

You can also run the project using command line flags:

```sh
go run main.go --repoPath=/path/to/repo --secretsFilePath=/path/to/secrets.txt --forcePushToOrigin=true
```

In this example:

    --repoPath specifies the path to the repository.
    --secretsFilePath specifies the path to the secrets file.
    --forcePushToOrigin is a boolean flag that determines whether to force push the changes to the remote repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

If you have any questions or suggestions, please feel free to reach out.

You can also open an issue on this repository: [GitHub Issues](https://github.com/TylerStrel/git-secrets-replacer/issues)


