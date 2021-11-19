## About

GitHub Action to clean `GITHUB_WORKSPACE` to avoid issues with files created by containers on self-hosted runners.

Related issues:

- https://github.com/actions/runner/issues/691
- https://github.com/actions/checkout/issues/211

## Usage

Add this action before `actions/checkout` to clean the workspace.

```
name: ci

on:
  push:
    branches: master

jobs:
  test:
    runs-on: self-hosted
    steps:
      - uses: pgolm/action-clean-workspace@v1
      - uses: actions/checkout@v2
      ...
```
