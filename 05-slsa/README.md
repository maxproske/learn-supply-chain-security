# SLSA

**SLSA** (pronounced "salsa") is an approachable security framework designed to protect the integrity of software supply chains that you can **incrementally** implement, starting from level 1.

- **SLSA 2 would have been enough** to help prevent the **xz** attack, since the tarballs contained extra code not present in the commit.
- SLSA 4 would have made the social engineering part of the xz attack dramatically harder, since it requires 2 person code review.

Modern software is built on complex supply chains, making it vulnerable to attacks such as build system compromises, say if someone has the build server under their desk.

- **SLSA 1: Documentation of the build process** Requires that the build process is fully scripted and automated.
- **SLSA 2: Tamper-evident build service** Requires version control and provenance (metadata about how the artifact was built).
- **SLSA 3: Non-falsifiable provenance** Requires a build service that is resistant to tampering and can generate verifiable provenance.
- **SLSA 4: Two-person review and hermetic builds** Requires the highest level of security, including two-person review and isolated, reproducible builds.
