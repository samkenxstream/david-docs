# Integrating a new Stamp

### Implement a new IAM Provider

In the `iam` package, all Provider implementations are in `iam/src/providers`.&#x20;

Providers must implement a `verify()` method that receives a proof payload, and verifies it.&#x20;

The verification process could involve requests to external servers, reading on-chain data from a smart contract, etc. The proof payload could contain an access token, a blockchain address, etc.

### Implement a new Provider Card in the Passport dapp

In the `app` package, each Provider is represented as a ProviderCard in `app/components/ProviderCards`.&#x20;

Each Provider also has an entry in the `STAMP_PROVIDERS` constant in`app/config/providers` specifying the name, description, and icon.&#x20;

Each ProviderCard will implement custom logic for the Verify button, which should request and collect proof data from the user to be submitted to the IAM server.&#x20;

This process could involve initiating an OAuth flow, requesting a signed message from the user's wallet, etc.

### Submit a PR

To be added as a new Stamp Provider for the Gitcoin Passport, please submit a PR to [https://github.com/gitcoinco/passport](https://github.com/gitcoinco/dPopp) implementing the `iam` and `app` changes described above.



For reference, here are past PRs implementing the current stamp providers:

* [Google OAuth Stamp](https://github.com/gitcoinco/dPopp/pull/31)
* [ENS Stamp](https://github.com/gitcoinco/dPopp/pull/71)
* [Proof of Humanity Stamp](https://github.com/gitcoinco/dPopp/pull/75)
* [Twitter OAuth Stamp](https://github.com/gitcoinco/dPopp/pull/87)
* [POAP Stamp](https://github.com/gitcoinco/dPopp/pull/93)
* [Facebook Stamp](https://github.com/gitcoinco/dPopp/pull/94)
* [BrightId Stamp](https://github.com/gitcoinco/dPopp/pull/126)

****