# Install Cosyra CLI

Cosyra CLI connects your terminal to your cloud workspace. This release is
`0.12.0-rc.2`, for macOS and Linux on ARM64 and Intel/AMD64.

## Install

```bash
curl -fsSL https://github.com/portablcorp/cosyra-releases/releases/download/cosyra-v0.12.0-rc.2/install.sh | bash
```

Downloads are public. You need Bash, curl, tar, and `shasum` or `sha256sum`.
No GitHub account, Node, npm, Go, or source checkout is required.

The installer verifies the archive checksum and executable version, then installs
to `~/.local/bin/cosyra`. It does not use sudo, change shell files, or replace an
existing executable without `--replace`. Checksums detect damaged downloads;
download the installer only from the official Cosyra release repository.

## Verify and connect

```bash
"$HOME/.local/bin/cosyra" version
"$HOME/.local/bin/cosyra" --help
"$HOME/.local/bin/cosyra" connect --api-url https://api.cosyra.com
```

The first connection opens browser sign-in and checkout if payment is required.
Your login is saved locally. Bare `cosyra` opens the command menu.
`Ctrl+]` detaches; `Ctrl+C` interrupts the remote command.

If `~/.local/bin` is already on PATH and you have no conflicting alias or function,
use `cosyra` directly. Otherwise use the absolute path shown above. To add it for
the current shell, run `export PATH="$HOME/.local/bin:$PATH"`. Existing aliases
still take precedence; preserve them and use the full path if needed.

## Upgrade

```bash
curl -fsSL https://github.com/portablcorp/cosyra-releases/releases/download/cosyra-v0.12.0-rc.2/install.sh | bash -s -- --replace
```

Use the installer linked from the release you want. Failed downloads or
verification preserve the existing executable. Saved credentials are retained.

To uninstall, remove `~/.local/bin/cosyra`. Use `cosyra auth logout` before removing
it if you also want to log out. Windows is not supported in this release.
