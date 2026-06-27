# Codex Desktop Linux

Automation-only repository for building Codex Desktop Linux packages.

This repository intentionally does not vendor or mirror the upstream packaging
source. GitHub Actions checks out `ilysenko/codex-desktop-linux` at build time,
downloads the official upstream `Codex.dmg`, builds the Linux app, creates a
Debian package, and publishes the package as a GitHub Release asset.

## Manual Build

Run the `Build and release Debian package` workflow from the Actions tab.

Inputs:

- `force`: rebuild and update the release even when the release tag already
  exists.
- `upstream_ref`: branch, tag, or commit from `ilysenko/codex-desktop-linux`
  to use for the packaging source. Defaults to `main`.

## Release Naming

Release tags include the upstream DMG timestamp, the upstream DMG SHA-256 short
ID, and the upstream packaging source commit. A new package is produced when the
official DMG content changes or the packaging source changes.
