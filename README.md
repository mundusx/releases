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

The current production channel is the
[`opengpu-prod` release](../../releases/tag/opengpu-prod).

## Install OpenGPU

Windows PowerShell:

```powershell
$script = Join-Path $env:TEMP "mundusx-install.ps1"; Invoke-WebRequest -Uri "https://github.com/mundusx/releases/releases/download/opengpu-prod/install.ps1" -OutFile $script; powershell -NoProfile -ExecutionPolicy Bypass -File $script
```

Linux x86_64, Linux ARM64 (including GX10), or Apple Silicon macOS:

```bash
curl -fsSL https://github.com/mundusx/releases/releases/download/opengpu-prod/install.sh | bash
```

Apple Silicon users can alternatively download the
[`MundusX-OpenGPU-Apple-Silicon.pkg`](../../releases/download/opengpu-prod/MundusX-OpenGPU-Apple-Silicon.pkg).
The current package is checksum-verified but not yet Apple Developer ID signed
or notarized, so macOS may require an explicit Open action.

After installation, contributors run `opengpu install` to choose their own
contribution cap, concurrency, runtime, and model. Cargo and Rust are not
required.

## Security boundary

This repository must contain distributable binaries, checksums, signed manifests, and end-user
installation instructions only. Do not commit application source, credentials, private keys,
environment files, logs, user data, or internal deployment configuration.

Report security concerns privately to the MundusX maintainers. Do not disclose a suspected
vulnerability in a public issue.
