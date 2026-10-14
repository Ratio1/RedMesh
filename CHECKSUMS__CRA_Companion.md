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

To check every program at once on Linux, WSL2 or macOS, save the release's file from `checksums/cra-companion/` in the folder where you extracted the release archive (its names start with `windows-x64/`, `linux-x64/` or `macos-arm64/`) and run `sha256sum -c --ignore-missing v<version>.sha256` (Linux, WSL2) or `shasum -a 256 -c --ignore-missing v<version>.sha256` (macOS) there. The list names the programs of every system; `--ignore-missing` skips those that are not in your archive. Each program of your archive must show `OK`.

The Windows programs are also signed by NAEURAL SRL. In File Explorer, open Properties > Digital Signatures: the signer must be "Naeural SRL". The macOS application will be signed and notarized with NAEURAL SRL's Apple Developer ID once that is in place; until then, macOS builds are given only to testers who agreed to use them unsigned.

If a value does not match, do not run the program. Contact redmesh@ratio1.ai.

## Releases

### 0.5.3

| File | System | SHA-256 |
|---|---|---|
| `windows-x64/redmeshcra-gui.exe` | Windows x64 | `52799c9257c15148d82f79b20d0ada00c6412f6dfa11aee3308607b9b98a9972` |
| `windows-x64/redmeshcra.exe` | Windows x64 | `6f89a70728b88e3a12566909f6b446b4544cf266159307443aa9731f8ece2ccc` |
| `linux-x64/redmeshcra` | Linux x64 and WSL2 | `f729c034187f8ba44f3481abe609e36a361ca365f124db6821ced6673addbd16` |
| `macos-arm64/RedMesh CRA Companion.app/Contents/MacOS/redmeshcra` | macOS on Apple silicon | `c9a35a22b252eddc66f811a752dcc27eb4ede589dbdd3f2281e89ae43b55a103` |
| `macos-arm64/redmeshcra` | macOS on Apple silicon | `73f213f3f9703c3d09c8e2dec720504282244da92ce88576c4e595f4844bd5dc` |

For `sha256sum -c`: [checksums/cra-companion/v0.5.3.sha256](checksums/cra-companion/v0.5.3.sha256)

The macOS programs (Apple Silicon, M1 and later) are ad-hoc signed only, not yet signed or notarized by Apple. 0.5.3 is one build for all three systems, from commit 35592e0. There is no 0.5.2 release.

### 0.5.1

| File | System | SHA-256 |
|---|---|---|
| `windows-x64/redmeshcra-gui.exe` | Windows x64 | `7a710b9529c32668790b4471ce4562f846226733b78268d19ed1a3b5aec0d39b` |
| `windows-x64/redmeshcra.exe` | Windows x64 | `c526ccab5e96d72bc9959b9e2ae70d7b5fde007ca432676455623d539ced712a` |
| `linux-x64/redmeshcra` | Linux x64 and WSL2 | `b4e38f67a6eab7cb9c1b5407210749a220b38b954c65ae78dde00860f2abd6c3` |
| `macos-arm64/RedMesh CRA Companion.app/Contents/MacOS/redmeshcra` | macOS on Apple silicon | `979958bcaec61557b6ad234de6c59e95644d998af114c7842056562e76c08482` |
| `macos-arm64/redmeshcra` | macOS on Apple silicon | `ec718e69d50bd3087b811d1967b5860b4592c0a1d4c58d3efc601c1343742d7d` |

For `sha256sum -c`: [checksums/cra-companion/v0.5.1.sha256](checksums/cra-companion/v0.5.1.sha256)

The macOS programs (Apple Silicon, M1 and later) are a build for testers. It is ad-hoc signed only, not yet signed or notarized by Apple, and comes from commit 4d3686b: 0.5.1 plus two macOS fixes, a layout loop and a crash at start. It replaces the first macOS build of 2026-10-10 (commit 6596274), which closed at start.
