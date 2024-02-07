# action-git-version

A GitHub action to build a version number based on the Git tags and branches

Only uses CMake and Git to build the version number.

## Basic usage

See [action.yml](action.yml) for a complete list of options and outputs.

```yaml
steps:
- uses: actions/checkout@v4
  # This action needs access to the history and tags.
  # You can also limit the depth to a smaller number and run 'git fetch --tags',
  # but the generated version might not be accurate.
  depth: 0

- name: Run Git Version
  id: gitversion
  uses: toitlang/action-git-version@v1.0.0

- name: Use the version
  shell: bash
  run: |
    echo ${{ steps.gitversion.outputs.version }}
```
