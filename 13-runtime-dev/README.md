# Runtime & Dev variants

- Because distroless images don't include a **package manager** or **shell**, debugging requires a different approach.
- The **runtime** variant (eg. latest) is the production version.
- The **dev** variant (eg. latest-dev) includes tools like bash, git, and apk for easier debugging.
- You might also be able to use **Docker Debug** to attach to the runtime container.
