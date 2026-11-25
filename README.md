# Sectium DevOps (`awesome-os/sectium-devops`)

Bare-metal / hypervisor provisioning, Ed25519 fingerprint-pinned mTLS peer transport, warm-resume soak verification, and **`holo-compiler`** build & code-signing documentation for **Sectium** and **Awesome-OS**.

## Repository Contents

| Path | Description |
| :--- | :--- |
| `sections/sectium-cloud-control-plane/uefi-setup-tui.mts` | Proxmox / UEFI lo-res (`80x25` serial console & `640x480` framebuffer) setup utility for headless host and control-plane provisioning. |
| `sections/sectium-cloud-control-plane/uefi-setup-tui.test.mts` | Unit tests verifying `80x25` and `640x480` layout, navigation, and configuration emission. |
| `sections/sectium-cloud-control-plane/mtls-transport.mts` | Ed25519 fingerprint-pinned peer authentication and mTLS transport over the Sectium control plane. |
| `sections/sectium-cloud-control-plane/mtls-transport.test.mts` | Peer auth verification and 50-cycle warm-resume soak test suite. |
| `docs/architecture/DEVOPS-BUILD-DISTRIBUTION-AND-SIGNING-GUIDE.md` | Canonical **`holo-compiler`** Tier-A (`< 1 s`) / Tier-B build, sovereign web installer, `RollingReleaseManifest` rollback, and OS vendor code-signing guide. |

## Verification

Run the erasable TypeScript test suites directly on Node 22+:

```powershell
node --test sections/sectium-cloud-control-plane/uefi-setup-tui.test.mts
node --test sections/sectium-cloud-control-plane/mtls-transport.test.mts
```

## License

BSD-3-Clause — see [`LICENSE`](LICENSE).

## Quick Start (Windows / Linux / macOS)

```sh
# Clone & enter repository (all platforms)
git clone https://github.com/awesome-os/sectium-devops.git && cd sectium-devops
```

## Quick Install & Run (Windows / Linux / macOS)

```sh
# Install / hydrate from v11 CAS via holo-pm
holo-pm install repository://github.com/awesome-os/sectium-devops@main

# Or project & run directly via holo-project (0-byte hardlink)
holo-project "project://cpp/sectium-devops?from=repository://github.com/awesome-os/sectium-devops@main"
```
