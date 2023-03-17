# Lua Lint - Github Action

This action lints all changed lua files using [kong/lualint](https://github.com/kong/lualint).

## Inputs

### `kong_gh_app_id`

**Required** The app ID of the GitHub app used to generate a token.

### `kong_gh_app_private_key`

**Required** The private key of the GitHub app used to generate a token.

### `rules`

A JSON string of the rules to use for linting. Default: `'{"max_column_width": {}, "one_line_before_else": {}, "eof_blank_line": {}, "table_ctor_comma": {}, "func_separation": {}}'`.

## Example usage

```yaml
uses: Kong/public-shared-actions/code-check-actions/lualint@feat-lualint
with:
  kong_gh_app_id: ${{ secrets.KONG_GH_APP_ID }}
  kong_gh_app_private_key: ${{ secrets.KONG_GH_APP_PRIVATE_KEY }}
  rules: '{"max_column_width": {"width": 80}, "one_line_before_else": {}, "eof_blank_line": {}, "table_ctor_comma": {"style":"trailing"}, "func_separation": {}}'
  extra_args: ''
```