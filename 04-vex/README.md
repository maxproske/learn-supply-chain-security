# VEX

- The missing link between SBOMs and actionable security.
- **VEX** (Vulnerability Exploitability eXchange) tells you which CVEs you should actually care about enough. No manual **triaging**.
- Most scanners just **match package versions** to CVEs. VEX adds real-world context by leeting software suppliers say "yes, the code is there, but it's not reachable" or "already fixed."
- Cuts through the noise: 1000 CVEs in your SBOM? VEX might show only 10 are real risks.
- **Machine-readable** and designed for automation—triage at scale, not by hand.
- VEX status: **affected**, **not affected**, **fixed**, **under investigation**.
- Tools like Docker Scout and OpenVEX/vexctl help generate and consume VEX data.

Docker Scout shows ALL CVEs by default. To generate a report containing VEX affected CVEs only:

```sh
docker scout cves ubuntu --only-vex-affected
```

## vexctl

- **vexctl** is a CLI for working with VEX data
- **OpenVEX** (Chainguard, 2023) is a Go implementation of vexctl.
- The following command outputs valid VEX json that claims that APK package wolfi/git v2.38.1-r0 is NOT affected by CVE-2014-123456.

```sh
vexctl create --product="pkg:apk/wolfi/git@2.38.1-r0?arch=x86_64" \
                --vuln="CVE-2014-123456" \
                --status="not_affected" \
                --justification="inline_mitigations_already_exist"
```

Or simply,

```sh
vexctl create "pkg:apk/wolfi/git@2.39.0-r1?arch=x86_64" CVE-2023-12345 fixed
```