# Learn Supply Chain Security

![Supply Chain Security](scs.jpg)

> In security, all we can do is raise the bar. Even if the supply chain was secured end-to-end, all you've done is build a secure malware distributor if someone decides to ship you malware.

The idea of a **supply chain** is the long chain of suppliers needs to product a factory's output. Physical supply chains are also a mess since the pandemic! Package managers (`npm` for JavaScript, `pip` for Python, `cargo` for Rust, etc.) automatically pull in hundreds if not thousands of direct and indirect (transitive) packages. Everything from cryptography to datepickers.

If you want to make CVEs disappear, keeping **Alpine and package.json up-to-date** will get you most of the way there. What's left is the hard stuff to get rid of.

Most open source maintainers are overworked volunteers. There are a lot of people you are trusting in that process. MIT: This software is provided "as is". If you use this, I owe you nothing. Don't expect or demand anything in return. All the risks are on you. I am not a supplier. There is no relationship. You are a racoon digging through dumpsters for free code.

## Core concepts

- **Supply Chain Security** protects the code and infrastructure turns an idea into running software.
- Some regulators now demand it: Executive Order (EO) 14028 in the US, Cyber Resilience Act (CRA) in the EU.
- **SLSA** (Supply-chain Levels for Software Artifacts) is a maturity framework. You can start a security noob at level 1, and work your way up.
- **NIST SP 800** is a US enterprise risk-management guidance for security handbooks.
- **CycloneDX** and **SPDX** are **SBOM** (Software Bill Of Materials) formats recommended in CISA.
- **sigstore** and **cosign** are keyless artifact signing.
- **in-toto** is a CNCF Graduated supply chain **attestation** framework.
- **Attestation** is a file format that contains metadata about what happens inside of a build. "The build input was: this repo, this commit, this make command, and got this binary with this hash."
- **Trivy** (Aqua), **Scout** (Docker), and **Grype** (Anchore) are dependency/image scanners.
- **OPA / Conftest**, **Kyverno**, **Enforce** (Chainguard) are used for policy enforcement.
- **FIPS** image variants means the US government is willing to deploy it in their organizations.
- **Distroless** images don't include a package manager, web client (eg. curl), or even a shell.

## A brief history of notable supply-chain attacks

- In 2013, Target was compromised through their third-party HVAC vendor, leaking 40M credit cards.
- In 2017, NotPetya was compromised through malware inserted in their M.E.Doc updater, leading to $10B economic loss.
- In 2020, SolarWinds was compromised through their Orion build server, infecting 18K customers.
- In 2021, Codecov was compromised through their CI bash uploader, leaking the credentials of hundreds of orgs.
- In 2024, **xz** was narrowly thwarted when a malicious open source maintainer attempted to insert a backdoor targetted at OpenSSH. It was only caught because ssh took 0.5 seconds longer, dubbed "500 ms to midnight". Ubuntu 24 LTS had 15 packages that depended on `xz-utils`, including git itself, and was delayed a week while they rebuilt.

## Continuous Security within the SDLC

```mermaid
flowchart LR
    A[Plan, Design & Develop] --> B[Code & Review]
    B --> C[CI Build & Test]
    C --> D[Sign & Push]
    D --> E[Deploy / K8s Admission]
    E --> F[Runtime Monitoring]
    F --> G[Incident Response & Lessons]
    G --> A
```

## Trivia

- Post-quantum signing requirements will likely amend SLSA & EO 14028 guidance by 2027.
- Containers are just tarballs and json. You can compile images without Docker in some programming language. But if you were to build a Node.js app on your Macbook today, there may be some native C libraries that haven't been cross-compiled correctly. There are techniques but it's difficult.

## TODO

- [ ] Chainguard
- [ ] Cloudsmith
- [ ] Scanners (in local, registry, production)

## Resources

- https://www.youtube.com/watch?v=yt0S_xN5b94
