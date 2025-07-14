# VEX

- **Vulnerability Exploitability eXchange** (VEX) is a report that gets you down to the vulnerabilities you actually care about.
- Scanners that only check package version=CVE contain a lot of red herrings.
- SBOM reports what contents you ship, VEX reports whether each CVE actually matters inside your product.

Docker Scout shows ALL CVEs by default. To generate a report containing VEX affected CVEs only:

```sh
docker scout cves ubuntu --only-vex-affected
```

## Status

- NOT AFFECTED: The vulnerable code is present but can’t be reached, or has been removed/mitigated.	No. Safe to ignore.
- AFFECTED: Vulnerability is exploitable in this product/version. Yes – patch, upgrade, etc.
- FIXED: This version contains the patch. Already addressed.
- UNDER INVESTIGATION: Vendor hasn’t finished assessing impact. Watch for an update.