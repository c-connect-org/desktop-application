# C-Connect Application Releases

## Overview

C-Connect Application provides a desktop client for the Coffee Connect platform.

The application is distributed as pre-built desktop packages for multiple Linux and Windows environments.

Supported platforms:

* Linux x64

  * Debian package (`.deb`)
  * Snap package (`.snap`)
  * AppImage (`.AppImage`)
* Windows x64

  * Installer (`.exe`)

All releases include verified metadata files containing version information and SHA checksums.

---

# Downloads

## Latest Release

The latest release files are available from the releases directory.

### Windows x64

| Package           | File                        |
| ----------------- | --------------------------- |
| Windows Installer | `c-connect-desktop-x.x.x-setup.exe` |

### Linux x64

| Package        | File                              |
| -------------- | --------------------------------- |
| Debian Package | `c-connect-desktop-x.x.x_amd64.deb`       |
| Snap Package   | `c-connect-desktop-x.x.x_amd64.snap`      |
| AppImage       | `c-connect-desktop-x.x.x.AppImage` |

---

# Release Metadata

## Windows Updates

Windows releases use:

```
latest.yml
```

This file contains:

* Latest application version
* Release files
* File sizes
* SHA512 checksums
* Update metadata

Example:

```yaml
version: 1.0.0
files:
  - url: c-connect-desktop-1.0.0-setup.exe
    sha512: <hash>
    size: <bytes>
path: c-connect-desktop-1.0.0-setup.exe
sha512: <hash>
releaseDate: 2026-08-27T00:00:00.000Z
```

---

## Linux Updates

Linux releases use:

```
latest-linux.yml
```

This file contains Linux package metadata:

* Version information
* Package download paths
* SHA512 checksums
* File sizes

Supported Linux packages:

```
.deb
.snap
.AppImage
```

Example:

```yaml
version: 1.0.0
files:
  - url: c-connect-desktop-1.0.0_amd64.deb
    sha512: <hash>
    size: <bytes>

  - url: c-connect-desktop-1.0.0.AppImage
    sha512: <hash>
    size: <bytes>

releaseDate: 2026-08-27T00:00:00.000Z
```

---

# SHA512 Verification

Every release package includes a SHA512 checksum.

Before installing, verify the downloaded file integrity.

## Linux

```bash
sha512sum c-connect-desktop-1.0.0.AppImage
```

Compare the output with the hash inside:

```
latest-linux.yml
```

## Windows PowerShell

```powershell
Get-FileHash c-connect-desktop-1.0.0-setup.exe -Algorithm SHA512
```

Compare the result with:

```
latest.yml
```

---

# Installation

## Debian / Ubuntu

Install the `.deb` package:

```bash
sudo dpkg install ./c-connect-desktop-x.x.x_amd64.deb
```

---

## Snap

Install the Snap package:

```bash
sudo snap install c-connect-desktop-x.x.x_amd64.snap --dangerous
```

---

## AppImage

Make the file executable:

```bash
chmod +x c-connect-desktop-x.x.x.AppImage
```

Run:

```bash
./c-connect-desktop-x.x.x.AppImage
```

---

## Windows

Run:

```
c-connect-desktop-x.x.x.exe
```

and follow the installation wizard.

---

# Auto Update

The application uses Electron update metadata:

```
latest.yml
latest-linux.yml
```

These files allow the application to:

* Detect new versions
* Verify downloaded files
* Validate SHA512 checksums
* Perform secure updates

---

# System Requirements

## Windows

* Windows 10 or newer
* x64 CPU architecture

## Linux

* x64 CPU architecture
* Debian-based distributions supported through `.deb`
* Snap-compatible systems
* AppImage-compatible systems

---

# License

C-Connect Application is released under the MIT License.
