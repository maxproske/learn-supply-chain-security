# TUF

- **The Update Framework (TUF)** (concept) is a generic way of establishing trust via signing, like a browser CA store. No Google or GitHub. Designed to protect software update systems from supply chain attacks.
- **Docker Content Trust (DCT)**, in-toto, and Sigstore **implement** TUF (concept).
- Signing establishes **integrity** (artifact checksum) and **identity** (signed by who created it).
- "This thing was signed by a private key that is associated with the public key I know about."
- 