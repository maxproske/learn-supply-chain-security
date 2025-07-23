# Policy

> _Policy tends to be something that comes down from on high._

- Why scan your software? **Because someone told you to.** You had an audit, or went for SOC 2. Someone had to put a policy together on software is being secured.
- **Policy** is the rules of the road.
- Developer approach to policy. Automated approach to policy.
- In the age of microservices, that's a lot of repos and CI/CD pipelines that need policing.

- Your security organization may impose 0 Critical CVEs in production through a **meeting**, **Google Doc**, or **wiki**.
- Imagine you need to make a hotfix, but a policy a medium CVE that already exists in production. The outage lasts for even longer. Your only option is to code in an exception, because if you update that dependency who knows what else will break.

- Docker Scout understands this. Because it understands the context of your whole supply chain, what's deployed, it knows if you've **improved the stance**, made things worse, or stayed the same.
- No bouncing around to a bunch of tools.
