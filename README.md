# github-token-action

GitHub Actions to output a GitHub Access Token.

## Motivation

This action is used for GitHub Actions Reusable Workflows.
Some GitHub Actions Workflows require GitHub Access token, but there are several types of GitHub Access Token.

1. Personal Access Token
1. GitHub App's Access Token
1. GitHub Actions' Token `${{github.token}}`

This action takes some inputs for them and returns an access token.

## Usage

```yaml
- uses: suzuki-shunsuke/github-token-action@main
  with:
    github_token: ${{secrets.GH_TOKEN}}
    github_app_id: ${{secrets.APP_ID}}
    github_app_private_key: ${{secrets.APP_PRIVATE_KEY}}
```

## Inputs

* github_token
* github_app_id
* github_app_private_key

## Outputs

* token: GitHub Access Token

If `github_token` isn't empty, `token` is `github_token`.
If `github_app_id` isn't empty, this action issues an access token of GitHub App.
If both `github_token` and `github_app_id` are empty, `token` is `${{github.token}}`.

## LICENSE

[MIT](LICENSE)
