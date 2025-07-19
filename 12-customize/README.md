# Customize

- Chainguard maintains a private APK repo to **build directly from source**.
- A platform or SRE team will pull zero-image and install some packages for developer experience (bash, curl). Then, application teams have no rules to what they pull in to make the application run.
- Imagine you have a binary with curl as a dependency
- Installing them via wolfi-base, which has apk, sacrifices distroless
- Instead, Chainguard recommends using tooling like **melange** and **apko** to customize base images.
- **Assemble** is Chainguard's commercial offering.
- You can bring your own OCI layers.
- Post-GA directory, entrypoint, users, custom packages and certificates
- It can even pull a driver, extract the binaries, create an APK package, and drop it into the container as an OCI layer.

## EOL Grace Period

- End of Life (EOL) means it's no longer receivng updates from the open source community, which means it is vulnerable to CVEs
- Sometimes this isn't possible for companies. Increases your timeline but is still inherently risky.
- Chainguard will attempt to patch dependencies for 6 months or until the build fails.

## Chainguard VMs

- Just add a kernel
- 