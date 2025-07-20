# Bazel

- **Bazel** is Google's build tool that is the gold standard for creating **hermetic (reproducible) builds** by isolating dependencies and build environments.
- **Hermetic builds** mean the same inputs always produce the same outputs, regardless of the machine or environment.
- Bazel achieves this by **sandboxing** each build step, ensuring it only sees the dependencies it should.
- Bazel tracks exactly what dependencies went into each build, creating a clear audit trail.
