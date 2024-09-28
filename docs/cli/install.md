## `mise install [OPTIONS] [TOOL@VERSION]...`

**Aliases:** `i`

```text
Install a tool version

Installs a tool version to `~/.local/share/mise/installs/<PLUGIN>/<VERSION>`
Installing alone will not activate the tools so they won't be in PATH.
To install and/or activate in one command, use `mise use` which will create a `.mise.toml` file
in the current directory to activate this tool when inside the directory.
Alternatively, run `mise exec <TOOL>@<VERSION> -- <COMMAND>` to execute a tool without creating config files.

Tools will be installed in parallel. To disable, set `--jobs=1` or `MISE_JOBS=1`

Usage: install [OPTIONS] [TOOL@VERSION]...

Arguments:
  [TOOL@VERSION]...
          Tool(s) to install e.g.: node@20

Options:
  -f, --force
          Force reinstall even if already installed

  -j, --jobs <JOBS>
          Number of jobs to run in parallel
          [default: 4]
          
          [env: MISE_JOBS=]

      --raw
          Directly pipe stdin/stdout/stderr from plugin to user Sets --jobs=1

  -v, --verbose...
          Show installation output
          
          This argument will print plugin output such as download, configuration, and compilation output.

Examples:

    $ mise install node@20.0.0  # install specific node version
    $ mise install node@20      # install fuzzy node version
    $ mise install node         # install version specified in .tool-versions or .mise.toml
    $ mise install              # installs everything specified in .tool-versions or .mise.toml
```