# In-toto

> _in-toto is Latin for "in total", as a common format to cover the whole supply chain._

- **in‑toto** or a **DSSE envelope** is common format for signed **attestations** that bind to a build artifact's sha256 digest as an OCI like so: `my-app@<sha256>.intoto.jsonl`
- Think of it like inserting written statements into an envelope at the **notary** and stapling it to a document.
  - As you can imagine, stapling SBOM and in-toto is annoying to carry around.
- Each step contains 2 fields each: the **subject** which identifies the artifact, and the **predicate** which contains the metadata.
- SLSA provenance is a common **predicate**, but we also attest SBOMs, unit test results, vulnerabilities, etc.

> _SLSA Level 4: I need 2 people to sign off on this step using in-toto._

- Created in 2016 by a NYU professor. Now a CNCF Graduated project.
- **Cosign** is a widely‑used tool to **generate and verify** those attestations, but the concept and spec are tool‑agnostic.
- Bridges the gap between "I reviewed the source code" to "I'm going to run this .exe someone said was from the source code"
- Information collection (SPXD, CycloneDX) and discovery (Sigstore) all use this common format.

# Legacy "layout & links" workflow

- The newer DSSE envelope workflow doesn't require this.
- An in-toto **layout** is the policy created by the release manager
- An in-toto **link** is created by the worker (CI)

## Provenance

- Provenance is carried _inside_ an attestation.
- **Provenance** answers "who, what, where, why, when?" questions that a simple hash can't.
  - **SHA-256** only verifies that a file hasn't changed.
- The word comes from the art world. It's the "chain of custody" or record of every owner, sale, and exhibition in between back to the original artist's studio.
- In software, the origin is the link to the repo, commit, and author that created it.
  - Who? (Michelangelo, Max)
  - What? (color from bazaar, SBOM)
  - Where? (on canvas, GitHub Actions)
  - Why? (commission, commit #123 to resolve issue #7)
  - When? (Early Renaissance, 1752725636)

- Provenance is obtained from attestation.
- With proper provenance, you can instantly query your records to find every single piece of software that was built with the vulnerable version of log4j
- Ideally this is **attached during build time**.
- **Sigstore** helps with keyless artifact signing!
