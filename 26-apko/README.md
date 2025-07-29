# Apko

- **Apko** (Chainguard) is a simple, declarative YAML-to-OCI builder that assembles apk packages into a single‑layer image, then signs SBOM & provenance
- Think of it like a Dockerfile without RUN commands.
- You can choose wolfi or alpine, but you can't mix and match them since wolfi uses glibc and alpine uses muscl (pronounced "muzzle")
- Everything has to come from apk, you don't drop in random `.dll`s.
- `shasum -a 256 <image>.tgz` gives the checksum.
- Chainguard creates apk packages with **melange**
- Also see rules_apko for Bazel and rules_docker for Docker