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

### 1.0.2

| File | System | SHA-256 |
|---|---|---|
| `windows-x64/redmeshcra-gui.exe` | Windows x64 | `79e1bc2f04a0de4c2e3699e05df13741016c2e0964c70b98a936be3bbcca86ef` |
| `windows-x64/redmeshcra.exe` | Windows x64 | `cf47843c79e641873559c7d17c58f5311e2daacada531bcc69be6252c28ccec9` |
| `linux-x64/redmeshcra` | Linux x64 and WSL2 | `1fff0f3277de9e8824385e1b35a8e170a9be54ccd87333fa3ca117e12fa0a82a` |
| `macos-arm64/RedMesh CRA Companion.app/Contents/MacOS/redmeshcra` | macOS on Apple silicon | `da3394679260483f7809ded4579937ec1920bcd26dd0445b917c4d974fa5384f` |
| `macos-arm64/redmeshcra` | macOS on Apple silicon | `ccc8fde431157674960a02943393b991f47167b47268cbf0e5c71e58436ec5d9` |

For `sha256sum -c`: [checksums/cra-companion/v1.0.2.sha256](checksums/cra-companion/v1.0.2.sha256)

The macOS programs (Apple Silicon, M1 and later) are ad-hoc signed only, not yet signed or notarized by Apple. 1.0.2 is one build for all three systems, from commit f47ee7b. There is no 1.0.1 release.

### 0.5.4

| File | System | SHA-256 |
|---|---|---|
| `windows-x64/redmeshcra-gui.exe` | Windows x64 | `e3d381dd92a78d6e502f12f6a656e1dd845409f4d76f0901c00cfd18f77d8a38` |
| `windows-x64/redmeshcra.exe` | Windows x64 | `d3863ae48d849dec8cad289bac8d836041da5b338b1294a04863ff5bcdc34e96` |
| `linux-x64/redmeshcra` | Linux x64 and WSL2 | `9def5c98d50faf29e6f71ad00089c353c96c23e582d7691bb8edb8704f446266` |
| `macos-arm64/RedMesh CRA Companion.app/Contents/MacOS/redmeshcra` | macOS on Apple silicon | `451211a203e8f8e1be3e59e6ae7c0cd01664873824351ac4933da7c7d554073a` |
| `macos-arm64/redmeshcra` | macOS on Apple silicon | `02aedfc79bd7aa1428256ec09b90e4bc377e77d2f68af40c3f614c04b659953f` |

For `sha256sum -c`: [checksums/cra-companion/v0.5.4.sha256](checksums/cra-companion/v0.5.4.sha256)

The macOS programs (Apple Silicon, M1 and later) are ad-hoc signed only, not yet signed or notarized by Apple. 0.5.4 is one build for all three systems, from commit 63b5755.

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
