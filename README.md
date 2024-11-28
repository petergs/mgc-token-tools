# mgc-token-tools
> Token manipulation tools for the Microsoft Graph CLI (`mgc`)

## Features
- Print an access or refresh token from the OS keychain for a specific client (via the client id) to pass to another tool
- [FOCI client](https://github.com/secureworks/family-of-client-ids-research/tree/main) login similar to `Invoke-RefreshTo<X>` commands provided by [TokenTactics](https://github.com/rvrsh3ll/TokenTactics)
- Store a correctly-formatted access or refresh token sourced outside `mgc` in the `mgc` token cache
- Seamlessly switch between applications without issuing a new `mgc login`
- Provides aliases for commonly used first-party Microsoft clients

## Support
So far, this has been tested with MacOS Keychain and GNOME Keyring on Linux.
