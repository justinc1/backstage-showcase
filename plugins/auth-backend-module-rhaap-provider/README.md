# @internal/backstage-plugin-auth-backend-module-rhaap-provider

The rhaap-provider backend module for the auth plugin.

_This plugin was created through the Backstage CLI_

To use set in `app-config.yaml`:

```yaml
signInPage: rhaap
auth:
  environment: development
  providers:
    rhaap:
      development:
        host: ${RHAAP_HOST} # e.g. https://my-aap.example.com
        clientId: ${RHAAP_OAUTH_CLIENT_ID}
        clientSecret: ${RHAAP_OAUTH_CLIENT_SECRET}
        signIn:
          resolvers:
            - resolver: usernameMatchingUser
enableExperimentalRedirectFlow: true
```

The AAP OAuth application should be created as:

1. Authorization Grant Type: `authorization-code`
2. Client Type: `confidential`
3. Redirect URIs: `<BACKSTAGE_URL>/api/auth/rhaap/handler/frame`
