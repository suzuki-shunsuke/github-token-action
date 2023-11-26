# github-token-action

GitHub Actions to output a GitHub Access Token.

[action.yaml](action.yaml)

## Motivation

This action is used for GitHub Actions Reusable Workflows.
Some GitHub Actions Workflows require GitHub Access token, but there are several types of GitHub Access Token.

1. Personal Access Token
1. GitHub App's Access Token
1. GitHub Actions' Token `${{github.token}}`

This action takes some inputs for them and returns an access token.

## Usage

```yaml
- uses: suzuki-shunsuke/github-token-action@350d7506222e3a0016491abe85b5c4dd475b67d1 # v0.2.1
  with:
    github_token: ${{secrets.GH_TOKEN}}
    github_app_id: ${{secrets.APP_ID}}
    github_app_private_key: ${{secrets.APP_PRIVATE_KEY}}
    default_github_token: ${{github.token}}
    github_app_permissions: >-
      {
        "contents": "write"
      }
    github_app_repositories: >-
      [
        "${{github.event.repository.name}}"
      ]
```

## LICENSE

[MIT](LICENSE)
