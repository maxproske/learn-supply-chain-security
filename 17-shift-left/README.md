# Shift Left

**"Shifting Left"** is the idea of moving security from the end of the line (the "right" side of the SDLC) to close to the beginning. It's about finding vulns before your code even leaves your machine.

Instead of security being a gate that blocks your release, it becomes a guardrail that keeps you on the right path while you code. Fixing in prod takes longer, it's just good economics.
- **IDE extensions** are the furthest "left" you can get. Snyk Code / Snyk Open Source, SonarLint, and Socker Scout can add the red squiggly under a package the moment you type it.
- **Pre-commit hooks** are the second line of defense before your code hits the repo.
- Lockfiles ensure builds are reproducible and your scans are reliable.
- Scan locally. Don't wait for CI to tell you what you can find out yourself in seconds with `docker scout cves my-app:latest`, `grype .`, or `trivy fs .`
- It's not about asking full stack developers to also become pen testers. It's about being a good devops engineer and giving them **automated tools** that provide **fast, actionable feedback**.
