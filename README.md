# Cosyra CLI releases

Official native CLI downloads for [Cosyra](https://cosyra.com).
Connect your terminal to your Cosyra cloud workspace on macOS or Linux,
using ARM64 or Intel/AMD64.

This repository distributes release binaries, checksums, installation
instructions, and release notes. The application source is maintained separately.

## Install the preview

The current public release is **0.12.0-rc.4**, a prerelease.

```bash
curl -fsSL https://github.com/portablcorp/cosyra-releases/releases/download/cosyra-v0.12.0-rc.4/install.sh | bash
```

The installer needs Bash, curl, tar, and `shasum` or `sha256sum`. It installs to
`~/.local/bin/cosyra` after verifying the archive checksum and executable version.
No GitHub account, Node, npm, Go, or source checkout is required. The installer
adds its directory to zsh or Bash startup files when missing from PATH. Open a
new terminal afterward, or use the export command printed for the current one.

```bash
"$HOME/.local/bin/cosyra" version
"$HOME/.local/bin/cosyra" connect --api-url https://api.cosyra.com
```

Complete browser sign-in and any required checkout yourself. Bare `cosyra` opens
the command menu. Press `Ctrl+]` to detach from a workspace.

See [installation instructions](INSTALL.md) for PATH, aliases, upgrades, and
uninstallation. Existing installations require an explicit `--replace`; the
installer preserves existing shell configuration, aliases, and saved credentials.
Use `--no-modify-path` to skip shell startup changes.

## Downloads

Each [release](https://github.com/portablcorp/cosyra-releases/releases) includes:

- Four native `.tar.gz` archives, each containing one `cosyra` executable.
- Individual SHA-256 files and an aggregate `checksums.txt`.
- The versioned `install.sh` and `INSTALL.md`.

Download the platform archive rather than GitHub's automatically generated
source-code ZIP or tarball. Those contain this distribution repository's docs.

Support: [hello@cosyra.com](mailto:hello@cosyra.com).
