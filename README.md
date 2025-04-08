# Golang deadcode action

Run go's deadcode checker.

- [Finding unreachable functions with deadcode](https://go.dev/blog/deadcode)

# Usage

See [action.yml](action.yml)

## Basic
<!-- x-release-please-start-version -->
```yaml
name: Go deadcode check
on: [ push ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: check for deadcode
        uses: opzkit/godeadcode-action@v1.0.0
        # optional
        with:
          go-version: '1.19'
          godeadcode-version: 'latest'
          packages: './...'
```
<!-- x-release-please-end-->

### Inputs

| Input                             | Description                                                                                             |
|-----------------------------------|---------------------------------------------------------------------------------------------------------|
| `package` _(optional)_            | The package you want to scan, default: "./..."                                                          |
| `go-version` _(optional)_         | The go version to use by the [actions/setup-go](https://github.com/actions/setup-go) action to setup go |
| `go-version-file` _(optional)_    | Path to the go.mod file to use for determining go version                                               |
| `check-latest` _(optional)_       | Check for latest available go version that satisfies the version spec, default default: "false"         |
| `godeadcode-version` _(optional)_ | The govuln version to use, default: "latest"                                                            |
