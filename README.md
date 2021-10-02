## GitHub Pages Deploy Composite Action

This composite action will deploy specified directory to GitHub Pages.

## Inputs

### `folder`

**Required** A folder used as the publishing source of GitHub Pages.

This folder should exist on the branch which workflows are triggered on, otherwise it should be created within the job steps before this action is used.

### `branch`

A branch used as the publishing source of GitHub Pages. Default is `gh-pages`.

If the branch does not exist in your repository, this action will create an orphan branch.

## Example

```yml
name: deploy

on:
  push:
    branches:
      - 'master'
    paths:
      - 'foo'

jobs:
  deploy-to-github-pages:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: pione30/github-pages-deploy-composite-action@v1
        with:
          folder: foo
```

## License

MIT
