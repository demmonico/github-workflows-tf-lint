# Github workflows action: Run tflint check

## Usage

`.github/workflows/tf-tests.yml`

```terraform
name: TF tests
description: Runs a Terraform tests

on:
  push:
    branches: [ master ]
  pull_request:
    types : [ opened, synchronize, reopened ]

jobs:
  tf_fmt:
    name: Terraform Format checks
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: terraform fmt
        uses: dflook/terraform-fmt-check@v1

  tf_validate:
    name: Terraform Validate
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: terraform validate
        uses: dflook/terraform-validate@v1

  tf_lint:
    name: Terraform tflint checks
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: terraform lint
        uses: demmonico/github-workflows-tf-tests@master
```
