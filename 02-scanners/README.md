# Scanners

- A software vulnerability (vulns) is exploitable code that can be abused to compromise a computer system.
- Traditional scanners crawl container filesystems and query CVE databases.
- With SBOMs, you can short circuit that step by analyzing the exact packages without unpacking the image. Which makes sense since it's readonly!
- On any given day, Node, Go, Python, Nginx, and PHP have **more than 100 CVEs**, with dozens of high or criticals.
- Chainguard research shows popular images gain 1 new vulnerability per day on average, making remediation a never ending task.
- The **National Vulnerability Database** (NVD) is the official CVE source of truth, but it's slow and hard to query. So tools like Trivy, Grype, and Snyk maintain their own curated **indexes**.
- Registries don't know what's running in production. The best way to cut down code is **continously scan what's in production** in addition to before deployment.
- They start by pulling and caching an exhaustive list of CVEs from the NVD and **GitHub Advisory Database (GHAD)**
- By some estimates (Scorecard) 84% of all codebases have at least 1 vulnerability, with avg 158 per codebase. Most have been in the code for 2+ years and are fixable.
- **Software dark matter** are contents not tracked by a package manager. That is, the results may not reflect the true contents of the image.
- Scanners work by matching detected package names and versions to known CVEs from multiple databases (NVD, GHAD, vendor advisories).

## Choices

- **Grype** the most popular, open source, can be paired with **Syft** to generate SBOMs to feed into Grype for fast scans on every commit, and is used by Chainguard.
- **Trivy** is open source, and checks for other types of contents relevant to container security.
- **Docker Scout** is easy for local dev checks.
- Scorecard while not specifically a vuln scanner, rates you on your project's security posture.

## False positives vs. false negatives

- Scanners are not infallible
- False positives can happen if scanners detect vulns in unused code, or due to mismatched/incomplete data. False negatives can happen if **software isn't properly detected** or databases are missing info.
- Continuous scanning is important—new CVEs are found every day.
- There are too many vulnerabilities to quickly address, false positives, low severity score, and even some that don't merit the score they’ve been assigned. *COUGH--CURL9.8INTEGEROVERFLOW*
