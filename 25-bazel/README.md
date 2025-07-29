# Bazel

- **Bazel** (Google) is a **build tool** that allows you to bring your own base image and **hack things out**.
- Phenominally powerful, phenomially confusing. Not for faint-hearted. Don't bother running `bazel --help`.
- `shasum -a 256 <image>.tar` gives the hash
- Also see `rules_apko` and `rules_docker` for a fully heremetic build from scratch.