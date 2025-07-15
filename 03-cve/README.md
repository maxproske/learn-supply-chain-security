# CVE

- A CVE, **Common Vulnerabilities and Exposures**, is a vulnerability that has been reported and accepted by the CVE Program.
- There are over **200K CVEs** as of 2025.
- Over 300 **CVE Numbering Authorities (CNA)** like Apple or Microsoft issue **CVE IDs**, the unique identifier that details the product impacted, version of the product, and vulnerability iteself with a **criticallity score**.
- The **Common Vulnerability Scoring System (CVSS)** assess the severity on a scale of 0-10 and was launched in 2005 by the non-profit Forum of Incident Response and Security Teams (FIRST).
- The format is CVE-YYYY-NNNNN, where YYYY stand for the year, and NNNNN is a unique sequential number.
- The CVE Program was founded by non-profit **MITRE** in 1999 as a free database for security researchers to understand the impact of vulnerabilities deployed in their network.
- Funding is provided by the **Cybersecurity & Infrastructure Security Agency (CISA)** and **US Department of Homeland Security (DHS)**. 

## CVE drama alert!

- In 2025, the program was 24 hours from shutdown from a last-minute 11 month contract extension from CISA.
- Without them, third-parties would scramble to fill the power vaccuum with paid databases, fracturing identifiers and terminology.

## More CVE drama!!

- CVSS 3, which was in place from 2015-2023, faced backlash from OSS maintainers for its subjectiveness and lack of context.
- In 2023, NVD scorers assigned an anonymous 1-line report of a benign integer overflow in curl. When the `--retry-delay` option would multiply seconds to milliseconds, it would rollover on a 64-bit machine. Instead of waiting until the end of the universe, it might retry in a second. 
- They assigned 9.8 CRITICAL without involving the curl team, spreading disinformation across the world.
- Since it was reported on HackerOne in 2019, they assigned the YYYY as 2020. Wtf? 
- The maintainer of curl even responded to the original 2019 HackerOne report after 2 days, fixed, closed it while the reporter said it can't be exploited. It had been dealt with.
- It's still worth putting it in the CVE database, since people could be running a 4 year old version of curl. But wtf it's not a security issue?!
- MITRE eventually dropped it to a 3.3 LOW.
