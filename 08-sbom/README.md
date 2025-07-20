# SBOM

- A **Software Bill of Materials (SBOM)** lists every library and dependency that goes into your app.
- Can't stop cyber attacks on their own.
- **Machine-readable**. Allows scanners to streamline the process to **quickly identify** packages with known vulnerabilities. No scanning the container filesystem.
- Have been around since the early 2000s, but Google Trends skyrocketed in 2021 when an Executive Order was signed that **required** SBOMs for **selling software to the US government**.
- 2 big standards: **SPDX** (Linux Foundation, 2011) and **CycloneDX**. SPDX started for license tracking, but now covers security and supply chain info too.
- Remember you're not delivering a checkbox. Where does it go? Is it being checked after?
- Most SBOMs are still pretty rough—Chainguard Labs found only 1% of SBOMs from popular Docker containers met minimum requirements.
- Some folks think SBOMs are too much work for too little gain, but adoption is growing fast. 88% of companies planned to use them by 2023.
- SBOMs don’t fix vulnerabilities, but they make it way easier to find and fix what matters.
- SBOMs should be generated **during build** rather than from records. GitHub Actions is one of few that provide support for this approach.

## Fun facts

- SBOMs are required when selling to a federal agency or **network‑connected medical devices**.
- SPDX's original purpose was to track OSS license compliance, so companies that wanted to do the right thing — like being "all MIT" or "no GPL" didn't find themselves in hot water. 
- Given OSS incorporate countless dependencies, it make sense to have trust issues! Devs and the US quickly recognized SBOMs could support other use cases
- In 2008, Cisco was violating free software licenses by distributing software in its Linksys routers

## SBOM drama!

- The **SolarWinds** hack (2020) showed how hard it is to track what's running where. If SBOMs were prevalent (no pun intended), finding and patching affected systems would have been much faster.

## Are you a SBOM pessimist, optimist, or optimist?

- I'm a **cautious optimist**. Are SBOMs the answer, or just more **digital paperwork**? Either way, they're here to stay. :)

## SBOM Quality

- **Not all SBOMs are created equal**.
- Chainguard abalyzed 3,000 popular Docker containers and found 1% of SBOMs met the **minimum required elements**.
  - All 7 **data fields** (Author, timestamp, etc.)
  - **Automation support** (1 of 3 SBOM formats that are machine readable _and_ human readable)
  - **Practices and processes** including transitive dependencies and organizational documentation of any "known unknowns"
- The minimum elements, judging on analysis of this dataset, are a high bar and no tools appear to consistently create minimum elements-compliant SBOMs.

## Resources

- https://github.com/spdx/ntia-conformance-checker
- https://github.com/eBay/sbom-scorecard (Abandoned by eBay)