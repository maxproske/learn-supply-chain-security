# Scanners

- Traditional scanners crawl container filesystems and query CVE databases.
- With SBOMs, you can short circuit that step by analyzing the exact packages without unpacking the image. Which makes sense since it's readonly!
- The **National Vulnerability Database** (NVD) is the official CVE source of truth, but it's slow and hard to query. So tools like Trivy, Grype, and Snyk maintain their own curated **indexes**.
- Registries don't know what's running in production. The best way to cut down code is **scan what's in production** or entering production.
