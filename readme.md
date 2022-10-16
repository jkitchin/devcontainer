devcontainer - Python script for launching devcontainers
--------------------------------------------------------

# Installation

`devcontainer` is not on pypi yet. You can install it like this.

> pip install git+git://github.com/jkitchin/devcontainer

Installation provides one shell command `devcontainer` in your path.

# Usage

In a directory that has a .devcontainer directory you simply run `devcontainer` in a shell. This will parse the devcontainer.json file to find the Docker image or Dockerfile to use, and it will construct the docker command to build and/or launch it. The following devcontainer.json options are supported:

1. "remoteUser": "user" will map to "-u user" in the docker command
2. "forwardPorts": [p1, p2]  will map to "-p p1:p1 -p p2:p2"
3. "remoteEnv" entries are passed to the docker command.
4. The local working directory is mapped to "workspaceFolder", and defaults to /workspaces/{project-name} similar to how Codespaces works.
5. You can use "workspaceMount" to finetune the mount behavior.
6. "build.args" are supported
7. You can provide an alternative entrypoint at the command line, e.g. `devcontainer bash` to start the container at a bash prompt.

# Known limitations

The devcontainer.json options that are supported are mainly driven by the ones I have used and can test in some way. Please file an issue at https://github.com/jkitchin/devcontainer/issues, or create a pull request for new features.

