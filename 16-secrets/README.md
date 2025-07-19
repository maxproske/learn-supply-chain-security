# Secrets

- The **Codecov** attack showed that a single leaked credential can expose hundreds of orgs.
- If you've ever made this mistake, you'll know bots are constantly scanning public repositories for exactly this. You must consider it compromised instantly.
- Use **pre-commit hooks** or scanners like **git-secrets** or **trufflehog** to check for anything that looks like a secret before it enters git history.
- Use a **secrets manager** instead of scattering `.env` files across developer and staging machines, use a dedicated secrets manager.
- Secrets should be injected at **runtime**, not env variables baked into the image during build.
