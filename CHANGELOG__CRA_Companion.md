# RedMesh CRA Companion: changelog

RedMesh CRA Companion is a desktop application for readiness self-assessments under the EU Cyber Resilience Act, Regulation (EU) 2024/2847. It is part of the RedMesh Mobile Security Operations Center by NAEURAL SRL (Ratio1.ai).

- It works offline. Assessments, evidence and reports stay on the user's computer.
- It is a readiness self-assessment tool. It is not a certification, a conformity assessment, an EU declaration of conformity or legal advice.
- To check a downloaded program, compare its SHA-256 with the values in [CHECKSUMS__CRA_Companion.md](CHECKSUMS__CRA_Companion.md).
- Contact: redmesh@ratio1.ai

## 1.0.2 (2026-10-30)

The release after 0.5.4: the version numbers continue with 1.0.2, 1.0.3 and on, one version per build. There is no 1.0.1 release: that version was built and not released, and 1.0.2 is that build with two fixes: one test, and the dialog that attaches a code scan to a Draft on macOS. One build for Linux, Windows and macOS (Apple Silicon).

- **New data format:** what 1.0.2 saves cannot be used by 0.5.4 or earlier. Before its first save on a data folder of an earlier version, 1.0.2 asks, so that the folder can be copied first; a way back is 0.5.4 with that copy. The partner key file is not in that copy, and 0.5.4 reads only key files without a licence: keep the key file that 0.5.4 used before a key file with a licence is imported, and import it again in 0.5.4 after going back.
- **Scan limits:** every scan has limits of time (30 minutes), memory, bytes read, files and folder depth. A scan that a limit stopped or cut short is marked "partial" with the reason and what its results cover, and is never shown as complete.
- **SBOM scans, reviewed and improved:**
  - each component states how its version is known: from a lock file, an installed package or a built file, or only from a manifest;
  - dependency links appear only where a manifest or a lock file shows them, and more lock-file layouts are read;
  - packages that it recognises as taken from git or from a registry other than the public one are listed, but not sent to the optional known-issue lookup, whose confirmation lists every identifier it sends;
  - login details written in a package address are kept out of the SBOM.
- **Code scans, reviewed and improved:** configuration files are read by their layout, more forms of secrets are masked (passwords on command lines and default values after an environment lookup too), and each scan states the rules it ran and the files it did not read. Code scans recorded by earlier versions should be run again before an assessment is finalised.
- **Code analysis:** a second tab of the SBOM Analyzer runs the code scan on a folder without an assessment, keeps its runs, runs them again, exports their SARIF files and can attach a run to a Draft.
- **Licence in the partner key:** NAEURAL SRL can issue a partner's key file with a licence that names its key. The application checks it offline at every start and shows "Licensed until <date>". A key without a licence keeps signing as before. A licence that has ended gives a warning, and work continues.
- **Checks:** Settings, Checks and `redmeshcra --check` check the partner key, its licence and the computer's set-up, each with what to do. No check stops work, except that a program file whose SHA-256 differs from the public list opens no data, as since 0.5.1, and that on Linux and macOS a data folder that other accounts can open, or whose `.redmesh` folder they can change, is used read-only until it is restricted, as before.
- **Online when available:** the application works offline. When a connection is available, it uses it for its start-up check against [CHECKSUMS__CRA_Companion.md](CHECKSUMS__CRA_Companion.md), the optional known-issue lookups and, with a partner key that holds a licence, NAEURAL SRL's public list of withdrawn keys in this repository (`keys/cra-companion/withdrawn-keys.json`). The start-up check and that request carry no partner, key or customer information, and the known-issue lookups send a scan's package identifiers only after the user confirms them; without a connection the list is shown as not checked.
- **Content:** question sets 2026.10.6, unchanged, and Knowledge Base 2026.10.13, whose entry on what leaves the computer now also names the licence check and what it sends; legal basis as of 2026-10-23, to be reviewed by 2026-11-27. Content not legally reviewed.

## 0.5.4 (2026-10-23)

One build for Linux, Windows and macOS (Apple Silicon).

- **Draft reports:** the Companion makes drafts of the readiness report and of the Executive summary, marked "DRAFT" on every page. The full report is produced in the partner's own RedMesh Navigator from the uploaded Assessment JSON and its hash file.
- **Partner key:** with the partner's key imported in Settings, the Assessment JSON and the drafts each get a `_signature.json` file that RedMesh Navigator checks. Without a key they are written as before, and the result says "Not signed".
- **Content:** question sets 2026.10.6 and Knowledge Base 2026.10.12, with a legal basis as of 2026-10-23, to be reviewed by 2026-11-27. A Draft made with an older question set can move to the new one with "Update question set".
- **Security fixes** from NAEURAL SRL's security reviews: archives used as product sources, limits on large or hostile files, the privacy of the optional known-issue lookup, and library loading on Windows.
- **Delivery:** the release files can be handed over as a download or on a drive. The application works offline; it uses the internet when it is available, for its start-up check and the optional known-issue lookups.
- **macOS:** signed ad hoc with the hardened runtime, and started on macOS 14, 15, 26 and 27 before it was published.

## 0.5.3 (2026-10-13)

0.5.1 with the macOS fixes, built from one commit for Linux, Windows and macOS (Apple Silicon). There is no 0.5.2 release: that version was built and not released.

- **macOS:** the application starts. The first macOS build of 0.5.1 closed at start. Each release's application is now started on macOS 15 and macOS 27 before it is published.
- **Drop-down lists** keep their width on every system.
- **One version per build:** from 0.5.3 on, every new build gets a new version on all three systems, and a published version never changes. The checksums of each version stay as published.

## 0.5.1 (2026-10-10)

The first release for partners. Partners receive it as a download from their RedMesh Navigator account. A macOS build for Apple Silicon (M1 and later) is available to testers. It is not yet signed by Apple, and it fixes two macOS-only faults: a layout loop in the assessment wizard and, in the build of 2026-10-12, a crash at start.

- **Product sources:** each product version records where its software is: a folder, a file or a git address.
  - Folders, files and archives are scanned for a software bill of materials (SBOM) automatically.
  - A version needs a scanned build of its software before its assessment can be finalised.
- **Code scan (R1CodeChecker):** source-code folders are scanned with NAEURAL SRL's own pattern rules.
  - It looks for secrets, dangerous calls, weak cryptography, disabled TLS checks and debug settings.
  - Secrets are masked as soon as they are found.
  - It matches patterns one file at a time and does not analyse data flow. A scan with no findings does not mean the code has no weaknesses.
- **Evidence library:** files, links, notes and security test reports, recorded against the requirements they support. The application records evidence; it does not verify it.
- **Action plan:** an owner, a due date, a status and the effort for each gap, also exported as CSV.
- **Hand-over:** Finish, then an evidence bundle.
  - The bundle holds the report, an Executive summary of at most two pages, the Assessment JSON and the evidence files.
  - Each main file has a `_hash.json`, and a `SHA256SUMS` file covers the whole bundle, so anyone can check it with standard tools.
- **Sources:** questions, help texts and reports link to the official texts they rest on, and to Knowledge Base entries that cite them.
- **Content:** the question sets and the Knowledge Base, with a legal basis as of 2026-10-08.
- **Knowledge Base:** reference entries for security tools and standards, with a filter.
- **Windows:** the programs are signed by NAEURAL SRL.
- **Self-check at every start:** the program compares its own SHA-256 with the public list in this repository. It stops on a mismatch, and when it cannot check it shows a warning and counts the start.
- **Public checksums:** the SHA-256 of every published program is listed in this repository, with a one-command check for each system.

## 0.4.4 (2026-10-01)

- **Copy an assessment** to another organisation, product or version, with each copied answer confirmed before finalisation.
- **Report** as a PDF, with an HTML version as the accessible version.
- **Hash file:** each report and Assessment JSON has a `_hash.json` holding the file's SHA-256, which anyone can recompute.
- **Navigation:** completed stages are marked, and navigation is simpler.
- **Knowledge Base:** entries for the terms the assessment uses.

## 0.4.0 to 0.4.3 (2026-09-29 to 2026-10-01)

- **Windows:** programs signed by NAEURAL SRL.
- **Installers:** self-updating installers for Windows and Linux.
- **Diagnostics:** an exportable diagnostics file for support, holding no assessment content.
- **Reliability:** fixes on Windows.

## 0.1.0 to 0.3.2 (2026-09-27 to 2026-09-29)

- **First releases:**
  - the CRA readiness assessment wizard;
  - the HTML report and Assessment JSON export;
  - the SBOM Analyzer;
  - the local data folder with crash-safe saving.
