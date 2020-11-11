# Deploying changes to your Auth0 accounts with GitHub Actions

![Deploy to Auth0 production account](https://github.com/sandrinodimattia/github-actions-deploy-auth0/workflows/Deploy%20to%20Auth0%20production%20account/badge.svg) ![Deploy to Auth0 staging account](https://github.com/sandrinodimattia/github-actions-deploy-auth0/workflows/Deploy%20to%20Auth0%20staging%20account/badge.svg)

This is a sample repository which shows how you can use GitHub & GitHub Actions as an "Infrastructure as Code" solution for Auth0. A full description of how this works can be found on [my blog](https://sandrino.dev/blog/github-actions-deploy-auth0).

## Performing an export

To perform an export you'll run the following command:

```bash
DEV_AUTH0_CLIENT_SECRET=... npm run export:dev
```

> Note that you'll need to update the [/config/dev.json](./config/dev.json) file with your Auth0 account details and the Client ID of the client you created for the Deploy CLI. The Client Secret then needs to be provided as an environment variable in the command above.

## GitHub Actions

In this example each push to `master` or `staging` will result in a workflow being executed which will deploy the changes to your Auth0 account. The settings for these workflows can also be found in the [/config](./config) folder.

The Client Secrets need to be registered as Repository Secrets in your repository with the following names:

- `PROD_AUTH0_CLIENT_SECRET`
- `STAGING_AUTH0_CLIENT_SECRET`
