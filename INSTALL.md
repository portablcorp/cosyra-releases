# Install Cosyra CLI

Cosyra CLI connects your terminal to your cloud workspace. This release is
`0.12.0-rc.6`, for macOS and Linux on ARM64 and Intel/AMD64.

## Install

```bash
curl -fsSL https://github.com/portablcorp/cosyra-releases/releases/download/cosyra-v0.12.0-rc.6/install.sh | bash
```

Downloads are public. You need Bash, curl, tar, and `shasum` or `sha256sum`.
No GitHub account, Node, npm, Go, or source checkout is required.

The installer verifies the archive checksum and executable version, then installs
to `~/.local/bin/cosyra`. It adds that directory to your zsh or Bash startup files
if it is missing from PATH. Use `--no-modify-path` to skip PATH setup. It does not
use sudo or replace an existing executable without `--replace`. Checksums detect
damaged downloads; download the installer only from the official Cosyra release
repository.

## Verify and connect

```bash
"$HOME/.local/bin/cosyra" version
"$HOME/.local/bin/cosyra" --help
"$HOME/.local/bin/cosyra" connect --api-url https://api.cosyra.com
```

The first connection opens browser sign-in and checkout if payment is required.
Your login is saved locally. Bare `cosyra` opens the command menu.
`Ctrl+]` detaches; `Ctrl+C` interrupts the remote command.

Open a new terminal after installation and type `cosyra`. To use it in the current
terminal, run the `export PATH=...` command printed by the installer. A piped
installer cannot change its parent shell's environment. If your directory was
already on PATH, no startup files need changing.

PATH setup supports zsh (including exported `ZDOTDIR`) and Bash login and
non-login terminals. Other shells receive manual setup guidance. Existing file
contents and aliases are preserved; repeated installs do not add duplicate
entries. Existing aliases still take precedence, so use the full path if needed.

## Upgrade

```bash
curl -fsSL https://github.com/portablcorp/cosyra-releases/releases/download/cosyra-v0.12.0-rc.6/install.sh | bash -s -- --replace
```

Use the installer linked from the release you want. Failed downloads or
verification preserve the existing executable. Saved credentials are retained.

To uninstall, remove `~/.local/bin/cosyra`. Use `cosyra auth logout` before removing
it if you also want to log out. Windows is not supported in this release.
