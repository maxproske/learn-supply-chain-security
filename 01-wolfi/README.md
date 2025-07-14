# Wolfi

> The Wolfi octopus is the smallest known octopus.
> 
> ![Wolfi Octopus](https://i.imgur.com/C0Cynytm.jpeg)

- The `FROM` line of your Dockerfile does not tell you what's inside.
- No base image is perfect. To reduce risk, organizations will add layers to harden a **golden base image** they maintain and scan. This is like doing the **plumbing** in your own house.
- **Noisy scans** lead to **alert fatigue**. I would say 20 CVEs is the theoretical maximum for a team. If a scan returns 50+ CVEs, nobody will deal with it. Studies show 1% of CVEs are actually exploitable in real-world apps, so teams start to doubt if it's even a real threat.
- The solution? **Quiet base images**.

## What is distroless?

- A **Linux distribution** is the Linux kernel plus a bunch of third-party packages. When you use OpenSSL on alpine, you aren't getting that from directly from the OpenSSL maintainers, you're getting that from a distribution that may have applied a few patches and thrown it into their package manager.
- Containers don't package a Linux kernel (it uses the host's), therefore it's a distribution without Linux. It's **everything without Linux**. That gets into the "What is Linux? The kernel? The distribution? The package manager?" coversation which we'll skip.
- Distroless claim to be super secure, but they are notoriously difficult to debug.
- Chainguard like to think of wolfi as all the good of alpine, debian, and distroless, without any of the bad.
- Wolfi doesn't have desktop packages (KDE) or drivers. In fact, it defines one yaml file per package.

- If you scan and get 50, nobody deals with that well if at all, and people will get numb to it. Well how many of those are real. I heard only 1% of CVEs in the wild can affect you.
