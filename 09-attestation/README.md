# Artifact attestations

- **SHA-256** only verifies that a file hasn't changed.
- An **attestation** answers "who, what, where, why, when?" questions that a simple hash can't.
- The link to the source commit, build instructions, dependencies, or build environment.
- Think of it like a **notarized affidavit**.

## Provenance

- The word comes from the art world. It's the "chain of custody" or record of every owner, sale, and exhibition in between back to the original artist's studio.
- In software, the origin is the repo, commit, and author that created it.
  - Who? (Michelangelo, Max)
  - What? (color from bazaar, SBOM)
  - Where? (on canvas, GitHub Actions)
  - Why? (commission, commit #123 to resolve issue #7)
  - When? (Early Renaissance, 1752725636)

- With proper provenance, you can instantly query your records to find every single piece of software that was built with the vulnerable version of log4j
- Ideally this is **attached during build time**.
- **Sigstore** helps with keyless artifact signing!
