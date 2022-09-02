# ✍🏽 Output
GitHub Action to output markdown content to pull requests.

## Inputs

### `token`

`string`

Required. GitHub token

### `sources`

`array of strings`

String with folders containing md files separated by commas (Supports glob pattern)
Example : 'projects/app/stats/, projects/embed/errors/'

### `name`

`string`

Required. Name to identify the output entity

### `top`

`string - boolean like`

Optional. set to `true` to position content at the top of the pull requests description


## Usage Example

````yaml
on: [pull_request]

jobs:
  changelog:
    runs-on: ubuntu-latest
    name: Output
    steps:
      - uses: actions/checkout@v2
      - uses: zattoo/output@v1
        with:
          token: ${{github.token}}
          sources: 'src/projects/a/, src/projects/b/'
