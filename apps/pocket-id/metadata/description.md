# Pocket ID

> On the first install you will have to append `/login/setup` in the Pocket ID URL in order to setup the admin account.

Pocket ID is a simple OIDC provider that allows users to authenticate with their passkeys to your services.

<img src="https://github.com/user-attachments/assets/96ac549d-b897-404a-8811-f42b16ea58e2" width="1200"/>

The goal of Pocket ID is to be a simple and easy-to-use. There are other self-hosted OIDC providers like [Keycloak](https://www.keycloak.org/) or [ORY Hydra](https://www.ory.sh/hydra/) but they are often too complex for simple use cases.

Additionally, what makes Pocket ID special is that it only supports [passkey](https://www.passkeys.io/) authentication, which means you don’t need a password. Some people might not like this idea at first, but I believe passkeys are the future, and once you try them, you’ll love them. For example, you can now use a physical Yubikey to sign in to all your self-hosted services easily and securely.

## Contribute

You're very welcome to contribute to Pocket ID! Please follow the [contribution guide](https://github.com/pocket-id/pocket-id/blob/main/CONTRIBUTING.md) to get started.
