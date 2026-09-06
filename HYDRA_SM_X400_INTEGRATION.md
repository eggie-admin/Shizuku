# Hydra SM-X400 integration lane

This branch is an **integration-only fork lane** for Project Hydra's Samsung SM-X400 development target.

It does not modify Shizuku's upstream implementation. The purpose is to pin the Hydra privilege-broker contract next to the exact Shizuku source fork used for Android development.

## Provenance

- Hydra integration repo: `eggie-admin/hydra-shell-android`
- Hydra integration branch: `sm-x400-widget-shizuku`
- Cathedral source repo: `eggie-admin/vue-headless-cms`
- Cathedral source branch: `samsung-sm-x400-build-candidate`
- Cathedral source head: `215310cff47d65311d6e7ff60eb63d6f176a444b`
- Hydra widget supervisor merge baseline: `0f7a58a52a832a2eb04c24f45fde6ded4974ec43`

## Trust policy

### Stock / Knox-capable target

Preferred mode is Shizuku started through ADB or Android wireless debugging.

- Developer Options required
- operator-controlled debugging
- explicit per-app authorization
- root disabled for this trust lane
- Sui disabled for this trust lane
- missing Shizuku is a capability downgrade, not a build failure

### Rooted laboratory target

Shizuku root mode or Sui may be used only as a separate lab target. It must not claim Secure Folder or Knox trust.

## Hydra safety boundary

- no arbitrary model-authored shell execution
- privileged operations must be typed and allow-listed
- no secret storage in broker manifests
- no public network listener
- direct package-manager mutation, cross-user actions, and root-only actions remain gated behind an explicit architecture review

## License boundary

The Shizuku source in this repository remains under its existing Apache License 2.0. Hydra-specific integration metadata on this branch does not alter the upstream Shizuku license or claim ownership of upstream code.
