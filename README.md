# github-workflows
Reusable Workflows

Сopy this code to workflow.yml in the repository calling workflow

```
name: Init workflow

on:
  push:
    branches:
      - develop
      - master
  create:
    tags:
       - '**' 

jobs:
  # call-workflow-test:
  #   uses: alexisapp/alexis-github-workflows/.github/workflows/test.yaml@master
  #   secrets: inherit
  #   with:
  #     migrations: false
  #     workers: false
  
  call-workflow-sentry:
    uses: alexisapp/alexis-github-workflows/.github/workflows/sentry.yml@master
    secrets: inherit

  call-workflow-deploy:
    uses: alexisapp/alexis-github-workflows/.github/workflows/build_and_deploy_image.yaml@master
    secrets: inherit
    with:
      migrations: false
      workers: false
```      