# Setup Earthly - GitHub Action

This repository contains an action for use with GitHub Actions, which installs [earthly](https://github.com/earthly/earthly) with a semver-compatible version.

The package is installed into `/home/runner/.earthly` (or equivalent on Windows) and the `bin` subdirectory is added to the PATH.

## Usage

Install the latest version of the earthly:

```yaml
- name: Install earthly
  uses: bloominlabs/setup-earthly@v1
```

Install a specific version of the earthly:

```yaml
- name: Install earthly
  uses: bloominlabs/setup-earthly@v1
  with:
    version: 0.6.1
```

Install a version that adheres to a semver range

```yaml
- name: Install earthly
  uses: bloominlabs/setup-earthly@v1
  with:
    version: ^0.6.0
```

### Testing

You can test this action locally using [act](https://github.com/nektos/act). See the repo for more instructions.

## Configuration

The action can be configured with the following arguments:

- `version` - The version of earthly to install. Default is `latest`. Accepts semver style values.
- `github-token` (optional) - Token used to query earthly versions.
