# Image Builder

- Our image should only have our application and its immediate dependencies. Not a lot of OS components bloating the image.
- Docker is fairly reproducable, but it's **not bitwise** because of timestamps and build IDs.

Level 1. Old school (100 MB+)

```Dockerfile
FROM golang
WORKDIR /app
COPY . .
RUN go build -o hello .
CMD hello
```

Level 2. Multistage builds (10 MB). Gives you a user and /tmp directory to run a **static binary**.

```Dockerfile
FROM golang as builder
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 build -o hello . # Static binary

FROM scratch # Missing TLS certs for HTTPS but whatever
COPY --from=builder /app/hello .
CMD hello
```

If you use Node.js, Java, Python project, you need a different minimal rutime image...

3. KO Punch. No Docker, uses Chainguard static image by default.

```sh
ko build .
```

4. **GCT Distroless** is built with **Bazel**. Basically took Debian and hacked things out.

5. Chainguard uses their own build tool **Apko** with the Wolfi (and Alpine) OS

6. **Buildkit** is the engine underpinning docker build. It's powerful but Dockerfile frontends just scratch the surface.

7. **Dagger** is built ontop of Buildkit and takes full advantage. Designed for CI/CD but it works differently locally. 20 commits later and you're pulling your hair out.

Allows you to define your build pipeline as code.