# MundusX distributions

This repository publishes compiled MundusX installers and command-line binaries. Product source
code remains in private development repositories.

## Release organization

Artifacts are grouped by product and version on the [Releases](../../releases) page. Each release
contains OS-qualified assets rather than maintaining a branch per operating system:

- `*-windows-x86_64.exe` or `*-x86_64-pc-windows-msvc.exe`
- `*-x86_64-unknown-linux-gnu`
- `*-aarch64-apple-darwin`

Every published binary is accompanied by a SHA-256 checksum. Products that support signed release
metadata also include `release-manifest.json` and `release-manifest.json.sig`.

## Security boundary

This repository must contain distributable binaries, checksums, signed manifests, and end-user
installation instructions only. Do not commit application source, credentials, private keys,
environment files, logs, user data, or internal deployment configuration.

Report security concerns privately to the MundusX maintainers. Do not disclose a suspected
vulnerability in a public issue.
