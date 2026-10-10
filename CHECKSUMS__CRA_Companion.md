# RedMesh CRA Companion: checksums

The SHA-256 of every RedMesh CRA Companion program that NAEURAL SRL (Ratio1.ai) publishes. Compare a program you received with the value listed here before you run it. Each release also has a machine-readable file in [checksums/cra-companion/](checksums/cra-companion/).

## How to check (one command)

Run the command for your system in the folder that holds the program, then compare the result with the line for that file below. The values must match exactly; letter case does not matter.

| System | Command |
|---|---|
| Windows (PowerShell) | `Get-FileHash .\redmeshcra-gui.exe -Algorithm SHA256` |
| Windows (Command Prompt) | `certutil -hashfile redmeshcra-gui.exe SHA256` |
| Linux and WSL2 | `sha256sum redmeshcra` |
| macOS | `shasum -a 256 "RedMesh CRA Companion.app/Contents/MacOS/redmeshcra"` |

To check every program at once on Linux, WSL2 or macOS, save the release's file from `checksums/cra-companion/` in the folder where you extracted the release archive (its names start with `windows-x64/` or `linux-x64/`) and run `sha256sum -c v<version>.sha256` (Linux, WSL2) or `shasum -a 256 -c v<version>.sha256` (macOS) there.

The Windows programs are also signed by NAEURAL SRL. In File Explorer, open Properties > Digital Signatures: the signer must be "Naeural SRL". The macOS application will be signed and notarized with NAEURAL SRL's Apple Developer ID once that is in place; until then, macOS builds are given only to testers who agreed to use them unsigned.

If a value does not match, do not run the program. Contact redmesh@ratio1.ai.

## Releases

### 0.5.1

| File | System | SHA-256 |
|---|---|---|
| `windows-x64/redmeshcra-gui.exe` | Windows x64 | `7a710b9529c32668790b4471ce4562f846226733b78268d19ed1a3b5aec0d39b` |
| `windows-x64/redmeshcra.exe` | Windows x64 | `c526ccab5e96d72bc9959b9e2ae70d7b5fde007ca432676455623d539ced712a` |
| `linux-x64/redmeshcra` | Linux x64 and WSL2 | `b4e38f67a6eab7cb9c1b5407210749a220b38b954c65ae78dde00860f2abd6c3` |
| `macos-arm64/RedMesh CRA Companion.app/Contents/MacOS/redmeshcra` | macOS on Apple silicon | `36f961c36dd51770b0cf543ba48da979915260963f53e66ad2fadfd11d075a65` |
| `macos-arm64/redmeshcra` | macOS on Apple silicon | `ed5b0bf0226b4e06b11a059d240c2dd76c7f7a34b985ff389c06724eb816a61e` |

For `sha256sum -c`: [checksums/cra-companion/v0.5.1.sha256](checksums/cra-companion/v0.5.1.sha256)

The macOS programs (Apple Silicon, M1 and later) are a build for testers. It is ad-hoc signed only, not yet signed or notarized by Apple, and comes from commit 6596274: 0.5.1 plus a macOS layout fix.
