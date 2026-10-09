# RedMesh CRA Companion: changelog

RedMesh CRA Companion is a desktop application for readiness self-assessments under the EU Cyber Resilience Act, Regulation (EU) 2024/2847. It is part of the RedMesh Mobile Security Operations Center by NAEURAL SRL (Ratio1.ai).

- It works offline. Assessments, evidence and reports stay on the user's computer.
- It is a readiness self-assessment tool. It is not a certification, a conformity assessment, an EU declaration of conformity or legal advice.
- To check a downloaded program, compare its SHA-256 with the values in [CHECKSUMS__CRA_Companion.md](CHECKSUMS__CRA_Companion.md).
- Contact: redmesh@ratio1.ai

## Unreleased: 0.5.1

The first release for partners. Partners receive it as a download from their RedMesh Navigator account.

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
