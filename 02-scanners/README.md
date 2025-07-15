# Scanners

- A software vulnerability (vulns) is exploitable code that can be abused to compromise a computer system.
- Traditional scanners crawl container filesystems and query CVE databases.
- On any given day, Node, Go, Python, Nginx, and PHP have **more than 100 CVEs**, with dozens of high or criticals.
- Chainguard research shows popular images gain 1 new vulnerability per day on average, making remediation a never ending task.
- With SBOMs, you can short circuit that step by analyzing the exact packages without unpacking the image. Which makes sense since it's readonly!
- The **National Vulnerability Database** (NVD) is the official CVE source of truth, but it's slow and hard to query. So tools like Trivy, Grype, and Snyk maintain their own curated **indexes**.
- Registries don't know what's running in production. The best way to cut down code is **scan what's in production** or entering production.
