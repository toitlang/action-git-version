# action-git-version

A GitHub action to build a version number based on the Git tags and branches

Only uses CMake and Git to build the version number.

## Basic usage

See [action.yml](action.yml) for a complete list of options and outputs.

```yaml
steps:
- uses: actions/checkout@v4

- name: Run GitVersion
  id: gitversion
  uses: toitlang/action-git-version@v1.0.0

- name: Use the version
  shell: bash
  run: |
    echo ${{ steps.gitversion.outputs.version }}
```
