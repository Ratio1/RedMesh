# RedMesh CRA Companion: checksums

The SHA-256 of every RedMesh CRA Companion program that NAEURAL SRL (Ratio1.ai) publishes. Compare a program you received with the value listed here before you run it. Each release also has a machine-readable file in [checksums/cra-companion/](checksums/cra-companion/).

## How to check (one command)

Run the command for your system in the folder that holds the program, then compare the result with the line for that file below. The values must match exactly; letter case does not matter.

| System | Command |
|---|---|
| Windows (PowerShell) | `Get-FileHash .\redmeshcra-gui.exe -Algorithm SHA256` |
| Windows (Command Prompt) | `certutil -hashfile redmeshcra-gui.exe SHA256` |
| Linux and WSL2 | `sha256sum redmeshcra` |
| macOS | `shasum -a 256 <file>` (the file names are in the release's list below) |

To check every program at once on Linux, WSL2 or macOS, save the release's file from `checksums/cra-companion/` in the folder where you extracted the release archive (its names start with `windows-x64/` or `linux-x64/`) and run `sha256sum -c v<version>.sha256` (Linux, WSL2) or `shasum -a 256 -c v<version>.sha256` (macOS) there.

The Windows programs are also signed by NAEURAL SRL. In File Explorer, open Properties > Digital Signatures: the signer must be "Naeural SRL". The macOS application will be signed and notarized with NAEURAL SRL's Apple Developer ID once that is in place; until then, macOS builds are given only to testers who agreed to use them unsigned.

If a value does not match, do not run the program. Contact redmesh@ratio1.ai.

## Releases

No release is listed yet. The first entry comes with release 0.5.1.
