# 🐳 THE ULTIMATE DOCKER ROADMAP
### From Zero to Container Orchestration Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~4-7 Months (Dedicated Study)
> **Prerequisite:** Basic Linux CLI knowledge (Phase 0-3 of the Linux roadmap)
> *Docker didn't invent containers. It made them accessible to every developer on earth. Understanding Docker is no longer optional — it's table stakes.*

---

## ⚡ PHASE 0 — ORIENTATION & THE CONTAINER REVOLUTION
> *"Before Docker, deploying software was like moving a house. After Docker, it's like shipping a container."*

---

### 📦 Module 0.1: Understanding Containers

#### § 0.1.1 — The Problem Docker Solves
  - "It works on my machine" — the classic deployment nightmare
  - Environment inconsistency: development, staging, production all different
  - Dependency conflicts: multiple apps needing different versions of the same library
  - Slow onboarding: new developers spending days setting up their environment
  - Inconsistent deployments: manual server configuration, configuration drift
  - Docker's solution: package the application WITH its environment into a portable, reproducible unit

#### § 0.1.2 — What is a Container
  - A lightweight, isolated, portable unit of software
  - Contains: application code, runtime, libraries, system tools, configuration — everything needed to run
  - Shares the host OS kernel — NOT a virtual machine
  - Process-level isolation, not hardware-level isolation
  - Starts in milliseconds (not minutes like VMs)
  - Consistent across environments: same container runs identically everywhere

#### § 0.1.3 — Containers vs Virtual Machines
  - VMs: full OS per instance, hypervisor, gigabytes of overhead, minutes to start
  - Containers: shared kernel, container runtime, megabytes of overhead, milliseconds to start
  - VMs provide stronger isolation (separate kernel), containers provide better efficiency
  - VMs: hardware-level virtualization, Containers: OS-level virtualization
  - Not mutually exclusive: containers often run INSIDE VMs in production (cloud instances)
  - Use cases: VMs for multi-OS workloads, strong isolation; containers for microservices, CI/CD, development

#### § 0.1.4 — A Brief History of Containers
  - `chroot` (1979) — change root directory (earliest isolation)
  - FreeBSD Jails (2000) — process isolation
  - Linux VServer (2001) — OS-level virtualization
  - Solaris Zones (2004) — container-like isolation
  - LXC (Linux Containers, 2008) — first true Linux containers
  - **Docker (2013)** — made containers accessible with tooling, images, and registry
  - OCI (Open Container Initiative, 2015) — standardized container format and runtime
  - Kubernetes (2014, GA 2015) — container orchestration at scale
  - Containerd (2017) — Docker's runtime extracted as a standalone project (now the industry standard)

---

### 📦 Module 0.2: Docker's Architecture

#### § 0.2.1 — Docker Components
  - **Docker Engine**: the core software (daemon + CLI + REST API)
  - **Docker Daemon** (`dockerd`): background service managing containers, images, networks, volumes
  - **Docker CLI** (`docker`): command-line client that talks to the daemon
  - **Docker Desktop**: GUI application for macOS/Windows (includes Linux VM, Docker Engine, Docker Compose, Kubernetes)
  - **containerd**: container runtime (manages container lifecycle)
  - **runc**: low-level OCI container runtime (creates and runs containers)
  - Stack: Docker CLI → Docker Daemon → containerd → runc → container

#### § 0.2.2 — Docker Objects
  - **Images**: read-only templates for creating containers (like a class)
  - **Containers**: running instances of images (like an object)
  - **Volumes**: persistent data storage outside the container filesystem
  - **Networks**: communication channels between containers
  - **Registries**: storage and distribution of images (Docker Hub, GitHub Container Registry, private)

#### § 0.2.3 — The OCI (Open Container Initiative)
  - Industry standard for container formats and runtimes
  - OCI Image Specification: how images are built and structured
  - OCI Runtime Specification: how containers are created and run
  - OCI Distribution Specification: how images are distributed (registries)
  - Docker, Podman, containerd, CRI-O — all OCI-compliant
  - Portability: OCI images run on any OCI-compliant runtime

#### § 0.2.4 — Docker Alternatives (Awareness)
  - **Podman**: daemonless, rootless, CLI-compatible with Docker (Red Hat)
  - **nerdctl**: containerd-native CLI (Docker-compatible)
  - **Buildah**: OCI image building without a daemon
  - **Kaniko**: build images in Kubernetes (no Docker daemon)
  - **Colima**: lightweight Docker Desktop alternative for macOS/Linux
  - **Rancher Desktop**: Kubernetes and container management (alternative to Docker Desktop)
  - All produce OCI-compatible images — the ecosystem is interchangeable

---

### 📦 Module 0.3: The Linux Kernel Features Behind Docker

#### § 0.3.1 — Namespaces (Isolation)
  - **PID namespace**: process ID isolation (container sees its own PID 1)
  - **Network namespace**: isolated network stack (own IP, ports, routing)
  - **Mount namespace**: isolated filesystem view
  - **UTS namespace**: isolated hostname and domain name
  - **User namespace**: map container root to unprivileged host user
  - **IPC namespace**: isolated inter-process communication
  - **Cgroup namespace**: isolated cgroup view
  - Each container gets its own set of namespaces — complete isolation

#### § 0.3.2 — Control Groups (cgroups — Resource Limits)
  - CPU limits: how much CPU time a container can use
  - Memory limits: maximum memory allocation
  - I/O limits: disk read/write throttling
  - PID limits: maximum number of processes
  - cgroups v1 vs cgroups v2: v2 is unified, simpler, increasingly default
  - Without cgroups: a container could consume all host resources

#### § 0.3.3 — Union Filesystems (Layered Storage)
  - Images are composed of stacked read-only layers
  - Container adds a thin read-write layer on top
  - Copy-on-Write (CoW): files only copied to writable layer when modified
  - Storage drivers: `overlay2` (default, recommended), `btrfs`, `zfs`, `devicemapper`
  - Layer sharing: multiple containers from the same image share read-only layers (space efficient)

#### § 0.3.4 — Security Features
  - **Seccomp**: system call filtering (restrict which syscalls containers can make)
  - **AppArmor/SELinux**: mandatory access control profiles
  - **Capabilities**: fine-grained Linux capabilities (instead of full root)
  - **Read-only filesystems**: prevent container from writing to its filesystem
  - Default security: Docker applies reasonable defaults, but understanding these is critical

---

### 📦 Module 0.4: Installing Docker

#### § 0.4.1 — Installation Methods
  - **Linux**: install Docker Engine directly (preferred for servers)
    - Ubuntu: official Docker repository + `apt install docker-ce`
    - Fedora/RHEL: official Docker repository + `dnf install docker-ce`
    - Arch: `pacman -S docker`
  - **macOS**: Docker Desktop (includes Linux VM via Apple Hypervisor)
  - **Windows**: Docker Desktop (WSL2 backend recommended)
  - **Colima** (macOS/Linux alternative): `brew install colima && colima start`
  - Post-installation: add user to `docker` group (`sudo usermod -aG docker $USER`) — avoids `sudo` for every command

#### § 0.4.2 — Verifying Installation
  - `docker --version` — check CLI version
  - `docker info` — detailed system information
  - `docker run hello-world` — verify everything works (pulls image, creates container, runs, exits)
  - `docker compose version` — check Compose version (v2, integrated into Docker CLI)

#### § 0.4.3 — Docker Desktop vs Docker Engine
  - Docker Desktop: GUI, Docker Engine + Compose + Kubernetes, easy setup, license requirements for large companies
  - Docker Engine: CLI-only, free for all uses, Linux-native
  - Development: Docker Desktop for convenience
  - Servers/CI: Docker Engine (no desktop needed)
  - Docker Desktop license: free for personal/small business, paid for large organizations

> ### 🛠️ Phase 0 Project: **"Container vs VM Deep Dive"**
> Explore containers at a fundamental level:
> - Install Docker Engine on a Linux VM (not Docker Desktop — understand the raw engine)
> - Run `docker run hello-world` — read and annotate every line of output
> - Run `docker run -it ubuntu bash` — explore the container: check PID 1, hostname, network, filesystem, users
> - From the HOST, inspect the container's namespaces: `ls -la /proc/$(docker inspect --format '{{.State.Pid}}' container_id)/ns/`
> - Compare: run the same application in a container and directly on the host — measure startup time, memory usage, disk usage
> - Draw a diagram showing: Docker CLI → Docker Daemon → containerd → runc → container (with namespaces, cgroups, overlay filesystem)
> - Document the kernel features used: identify which namespace and cgroup each `docker run` flag maps to

---

## ⚡ PHASE 1 — DOCKER FUNDAMENTALS
> *"Learn to run containers before you learn to build them."*

---

### 📦 Module 1.1: Working with Containers

#### § 1.1.1 — Running Containers
  - `docker run image_name` — create and start a container
  - `docker run -it image bash` — interactive terminal (stdin + TTY)
  - `docker run -d image` — detached mode (background)
  - `docker run --name myapp image` — assign a name
  - `docker run --rm image` — auto-remove when container stops
  - `docker run -p 8080:80 image` — port mapping (host:container)
  - `docker run -e VAR=value image` — set environment variable
  - `docker run -v /host/path:/container/path image` — bind mount
  - `docker run --restart unless-stopped image` — restart policy
  - Understanding: each `docker run` creates a NEW container

#### § 1.1.2 — Container Lifecycle
  - States: Created → Running → Paused → Stopped → Removed
  - `docker create image` — create without starting
  - `docker start container` — start a stopped container
  - `docker stop container` — graceful stop (SIGTERM, then SIGKILL after 10s)
  - `docker kill container` — immediate stop (SIGKILL)
  - `docker restart container` — stop + start
  - `docker pause container` / `docker unpause container` — freeze/unfreeze
  - `docker rm container` — remove stopped container
  - `docker rm -f container` — force remove (even if running)
  - `docker container prune` — remove all stopped containers

#### § 1.1.3 — Inspecting Containers
  - `docker ps` — list running containers
  - `docker ps -a` — list ALL containers (including stopped)
  - `docker ps -q` — only container IDs (for scripting)
  - `docker logs container` — view stdout/stderr output
  - `docker logs -f container` — follow logs in real-time
  - `docker logs --tail 100 container` — last 100 lines
  - `docker logs --since 1h container` — logs from last hour
  - `docker inspect container` — full JSON metadata (networking, mounts, state, config)
  - `docker inspect --format '{{.State.Status}}' container` — query specific fields
  - `docker stats` — live resource usage (CPU, memory, network, I/O)
  - `docker stats --no-stream` — single snapshot
  - `docker top container` — running processes inside container
  - `docker diff container` — filesystem changes since image

#### § 1.1.4 — Interacting with Running Containers
  - `docker exec -it container bash` — shell into running container
  - `docker exec container command` — run a command inside container
  - `docker exec -u root container command` — run as specific user
  - `docker attach container` — attach to container's PID 1 (stdin/stdout)
  - `docker cp file.txt container:/path/` — copy file into container
  - `docker cp container:/path/file.txt .` — copy file from container
  - `docker attach` vs `docker exec`: attach connects to PID 1, exec starts a new process

---

### 📦 Module 1.2: Working with Images

#### § 1.2.1 — Image Fundamentals
  - An image is a read-only template with layers
  - Image naming: `registry/repository:tag` — `docker.io/library/nginx:1.25`
  - Default registry: Docker Hub (`docker.io`)
  - Default tag: `latest` (avoid in production — not a version guarantee!)
  - Image ID: SHA-256 hash of image configuration
  - Images are immutable — changing anything creates a new image

#### § 1.2.2 — Image Operations
  - `docker pull image:tag` — download image from registry
  - `docker images` / `docker image ls` — list local images
  - `docker image inspect image` — detailed image metadata
  - `docker image history image` — show image layers and their sizes
  - `docker rmi image` / `docker image rm image` — remove image
  - `docker image prune` — remove dangling images (untagged)
  - `docker image prune -a` — remove all unused images
  - `docker tag source:tag target:tag` — create a new tag for an image
  - `docker save image > file.tar` — export image to tarball
  - `docker load < file.tar` — import image from tarball

#### § 1.2.3 — Image Layers & Caching
  - Each instruction in a Dockerfile creates a layer
  - Layers are cached — unchanged layers are reused
  - Layer order matters: most frequently changing content should be in later layers
  - `docker image history image` — visualize layers
  - Shared layers: multiple images based on the same base share layers on disk
  - Dangling images: layers not referenced by any tagged image (`<none>:<none>`)

#### § 1.2.4 — Docker Hub & Registries
  - Docker Hub: the default public registry
  - Official images: `nginx`, `postgres`, `node`, `python` — maintained by Docker and partners
  - Verified publishers: organizations with verified content
  - Community images: user-contributed (vet carefully!)
  - `docker login` — authenticate with a registry
  - `docker push image:tag` — push image to registry
  - Private registries: GitHub Container Registry (`ghcr.io`), AWS ECR, Google Artifact Registry, Harbor (self-hosted)

---

### 📦 Module 1.3: Resource Management

#### § 1.3.1 — CPU Limits
  - `--cpus 2.0` — limit to 2 CPU cores
  - `--cpu-shares 512` — relative CPU weight (default 1024)
  - `--cpuset-cpus "0,1"` — pin to specific CPU cores
  - Without limits: container can consume all available CPU

#### § 1.3.2 — Memory Limits
  - `--memory 512m` — hard memory limit (container is killed if exceeded)
  - `--memory-swap 1g` — memory + swap limit
  - `--memory-reservation 256m` — soft limit (target, not enforced)
  - `--oom-kill-disable` — prevent OOM killer (dangerous — can freeze host)
  - Without limits: container can consume all available memory

#### § 1.3.3 — I/O & PID Limits
  - `--device-read-bps /dev/sda:10mb` — limit disk read speed
  - `--device-write-bps /dev/sda:10mb` — limit disk write speed
  - `--pids-limit 100` — maximum number of processes in container
  - `--blkio-weight 500` — relative block I/O weight

#### § 1.3.4 — System Cleanup
  - `docker system df` — show Docker disk usage (images, containers, volumes, build cache)
  - `docker system prune` — remove stopped containers, dangling images, unused networks
  - `docker system prune -a` — remove ALL unused data (including unused images)
  - `docker system prune --volumes` — include volumes (DATA LOSS — be careful!)
  - `docker builder prune` — clear build cache

> ### 🛠️ Phase 1 Project: **"Container Operations Mastery"**
> Complete a comprehensive container operations exercise:
> - **Run** 5 different containers: Nginx (web), PostgreSQL (database), Redis (cache), Python (script), Alpine (utility)
> - For each container: configure port mapping, environment variables, proper naming, restart policy
> - **Inspect**: extract IP address, port mappings, and environment variables from a running container using `docker inspect` with Go template format
> - **Logs**: set up a container that generates logs, practice filtering by time, following live, and extracting specific patterns
> - **Resource limits**: run a container with CPU and memory limits, stress-test it, observe behavior when limits are exceeded
> - **Exec**: shell into each container, explore the filesystem, check running processes, verify environment variables
> - **Lifecycle**: practice the full lifecycle for each container (create, start, pause, unpause, stop, start, remove)
> - **Cleanup**: use `docker system df` to audit space, then clean up with appropriate prune commands
> - Document everything: create a reference sheet of the 30 most useful Docker commands with examples

---

## ⚡ PHASE 2 — BUILDING IMAGES WITH DOCKERFILE
> *"A Dockerfile is a recipe. The image is the dish. The container is someone eating it."*

---

### 📦 Module 2.1: Dockerfile Fundamentals

#### § 2.1.1 — Dockerfile Structure
  - Plain text file named `Dockerfile` (no extension)
  - Instructions are UPPERCASE by convention: `FROM`, `RUN`, `COPY`, `CMD`
  - Each instruction creates a new layer in the image
  - Instructions executed in order, top to bottom
  - Comments: `# this is a comment`
  - Build context: the directory sent to the daemon for building (`.` in `docker build .`)

#### § 2.1.2 — Essential Instructions
  - `FROM image:tag` — base image (MUST be the first instruction)
  - `FROM scratch` — empty base image (for static binaries)
  - `RUN command` — execute a command during build (creates a layer)
  - `RUN ["executable", "param1"]` — exec form (no shell)
  - `COPY source destination` — copy files from build context into image
  - `ADD source destination` — like COPY but handles URLs and auto-extracts archives (prefer COPY)
  - `WORKDIR /app` — set working directory (creates if doesn't exist)
  - `ENV KEY=value` — set environment variable (persists in running container)
  - `ARG KEY=default` — build-time variable (NOT available at runtime)
  - `EXPOSE 80` — document which ports the container listens on (does NOT publish)
  - `VOLUME /data` — create a mount point for external volumes
  - `USER username` — set the user for subsequent instructions and container runtime

#### § 2.1.3 — `CMD` vs `ENTRYPOINT`
  - `CMD ["executable", "param"]` — default command (can be overridden at `docker run`)
  - `ENTRYPOINT ["executable"]` — fixed executable (arguments appended)
  - Shell form: `CMD command param` — runs in `/bin/sh -c` (PID 1 is shell, not your process!)
  - Exec form: `CMD ["command", "param"]` — runs directly (PID 1 is your process — preferred!)
  - Combined: `ENTRYPOINT ["python"]` + `CMD ["app.py"]` — `python` is fixed, `app.py` is default but overridable
  - Rule: use exec form for both, use `ENTRYPOINT` for the main executable, `CMD` for default arguments
  - PID 1 signal handling: exec form receives `SIGTERM` properly (graceful shutdown)

#### § 2.1.4 — `.dockerignore` File
  - Excludes files from the build context (like `.gitignore`)
  - Essential entries: `.git`, `node_modules`, `__pycache__`, `*.pyc`, `.env`, `*.md`, `Dockerfile`, `docker-compose.yml`
  - Reduces build context size → faster builds
  - Prevents secrets from being accidentally copied into images
  - Place in the same directory as the Dockerfile

---

### 📦 Module 2.2: Building Images

#### § 2.2.1 — Build Commands
  - `docker build -t name:tag .` — build from current directory
  - `docker build -t name:tag -f custom.Dockerfile .` — specify Dockerfile
  - `docker build --no-cache -t name:tag .` — rebuild without cache
  - `docker build --build-arg KEY=value .` — pass build arguments
  - `docker build --target stage_name .` — build specific stage (multi-stage)
  - `docker build --platform linux/amd64,linux/arm64 .` — multi-platform build (with buildx)

#### § 2.2.2 — Build Context
  - Everything in the directory is sent to the Docker daemon
  - Large build context = slow builds (use `.dockerignore`!)
  - Remote context: `docker build https://github.com/user/repo.git`
  - Stdin context: `docker build - < Dockerfile` (no files from disk)

#### § 2.2.3 — BuildKit (Modern Build Engine)
  - Default builder since Docker 23.0
  - `DOCKER_BUILDKIT=1` — enable explicitly on older versions
  - Parallel layer building — significantly faster
  - Better caching: cache mount, secret mount
  - Build secrets: `--mount=type=secret` (never stored in layers)
  - Cache mounts: `--mount=type=cache` (persist package manager caches)
  - SSH forwarding: `--mount=type=ssh` (clone private repos during build)
  - Syntax: `# syntax=docker/dockerfile:1` — opt into latest Dockerfile features

---

### 📦 Module 2.3: Image Optimization

#### § 2.3.1 — Minimizing Image Size
  - Choose minimal base images: `alpine` (5MB), `slim` variants, `distroless` (Google), `scratch` (0 bytes)
  - Alpine Linux: extremely small but uses `musl` libc (compatibility issues sometimes)
  - Debian `slim`: smaller Debian without docs/man pages (good compromise)
  - `distroless`: no shell, no package manager — just your app (most secure)
  - `scratch`: completely empty — for statically compiled binaries (Go, Rust)

#### § 2.3.2 — Reducing Layers
  - Combine `RUN` commands with `&&`: fewer layers, smaller image
  - Clean up in the SAME `RUN` instruction: `apt-get install && rm -rf /var/lib/apt/lists/*`
  - Don't install unnecessary packages: `--no-install-recommends` (apt), `--no-cache` (apk)
  - Remove package manager caches in the same layer

#### § 2.3.3 — Layer Ordering for Cache Efficiency
  - Order from least to most frequently changing
  - System dependencies first (rarely change, cached)
  - Application dependencies next (change occasionally)
  - Application code last (changes frequently)
  - Example: `COPY package.json → RUN npm install → COPY . .` (not `COPY . . → RUN npm install`)
  - Cache busting: changing any layer invalidates all subsequent layers

#### § 2.3.4 — Multi-Stage Builds
  - Multiple `FROM` instructions in one Dockerfile
  - Build stage: compile code, install build tools
  - Production stage: copy ONLY the built artifacts (no compiler, no source, no dev dependencies)
  - `FROM node:20 AS builder` → `FROM node:20-slim AS production` → `COPY --from=builder /app/dist ./dist`
  - Dramatic size reduction: Go app from 1GB → 10MB, Node.js app from 1GB → 200MB
  - Named stages: reference by name with `--from=stage_name`
  - Targeted builds: `docker build --target builder .` — stop at specific stage
  - Use cases: compile languages (Go, Rust, Java, TypeScript), install build dependencies, run tests

#### § 2.3.5 — Analyzing Image Size
  - `docker image history image` — layer sizes
  - `docker image inspect image` — detailed metadata
  - `dive image` — interactive layer explorer (excellent TUI tool)
  - `docker-slim` / `slim` — automatically optimize images (remove unused files)
  - `docker scout cves image` — vulnerability scanning

---

### 📦 Module 2.4: Dockerfile Best Practices

#### § 2.4.1 — Security Best Practices
  - Never run as root: `USER nonroot` or `USER 1000:1000`
  - Don't store secrets in images: no passwords, API keys, certificates in `ENV` or `COPY`
  - Use `.dockerignore` to exclude sensitive files (`.env`, `.git`, SSH keys)
  - Pin base image versions: `FROM node:20.11-slim` not `FROM node:latest`
  - Use official or verified images as bases
  - Scan images for vulnerabilities: `docker scout`, `trivy`, `grype`
  - Multi-stage builds: build tools and source code don't reach production image
  - Read-only root filesystem when possible

#### § 2.4.2 — Reliability Best Practices
  - Use exec form for `CMD` and `ENTRYPOINT` (proper signal handling)
  - `HEALTHCHECK` instruction: define how to check if container is healthy
  - `STOPSIGNAL` instruction: customize the signal for graceful shutdown
  - Handle `SIGTERM` in your application (graceful shutdown)
  - Don't use `latest` tag: it's not "the latest version" — it's "the default tag" (ambiguous)
  - Pin dependency versions: reproducible builds
  - One process per container: separation of concerns

#### § 2.4.3 — Operational Best Practices
  - Use `LABEL` for metadata: maintainer, version, description, source URL
  - Log to stdout/stderr (Docker captures and manages these)
  - Don't install editors, debuggers, or unnecessary tools in production images
  - Use `.dockerignore` aggressively
  - Document `EXPOSE` ports even though they're not enforced
  - Use `WORKDIR` instead of `cd` in `RUN` commands

> ### 🛠️ Phase 2 Project: **"Image Optimization Challenge"**
> Build Docker images for FOUR different application types, optimizing each:
> - **Node.js web app**: multi-stage build (install deps → build → production slim image), compare `node:20` vs `node:20-slim` vs `node:20-alpine` sizes
> - **Python API**: multi-stage build (install deps with pip → copy to slim image), virtual environment management, `--no-cache-dir` for pip
> - **Go CLI tool**: multi-stage build (compile → `scratch` image), resulting image under 15MB
> - **Static website**: multi-stage build (build with Node.js → serve with Nginx Alpine), resulting image under 30MB
> - For EACH image, document:
>   - Layer-by-layer size analysis using `dive`
>   - Before vs after optimization (size comparison)
>   - Build time with cold cache vs warm cache
>   - Security scan results with `trivy`
> - Create a `.dockerignore` file for each project
> - Use `HEALTHCHECK` in every Dockerfile
> - Run as non-root in every image
> - Create a comparison table of all approaches

---

## ⚡ PHASE 3 — DATA MANAGEMENT: VOLUMES & BIND MOUNTS
> *"Containers are ephemeral. Data must not be."*

---

### 📦 Module 3.1: The Storage Problem

#### § 3.1.1 — Container Filesystem Behavior
  - Container filesystem is ephemeral: destroyed when container is removed
  - Writable layer: changes stored in copy-on-write layer
  - Performance: writing to the writable layer is slower than native filesystem
  - Data loss: removing a container removes all data in the writable layer
  - Solution: decouple data from the container lifecycle

#### § 3.1.2 — Storage Options
  - **Volumes**: Docker-managed storage (best for persistence)
  - **Bind mounts**: map host directory into container (development workflows)
  - **tmpfs mounts**: in-memory storage (temporary data, no persistence)
  - **Named pipes**: for specialized communication (Windows)
  - Decision: volumes for production data, bind mounts for development, tmpfs for secrets/temp data

---

### 📦 Module 3.2: Docker Volumes

#### § 3.2.1 — Volume Operations
  - `docker volume create mydata` — create a named volume
  - `docker volume ls` — list all volumes
  - `docker volume inspect mydata` — show volume details (mountpoint, driver)
  - `docker volume rm mydata` — remove volume (must not be in use)
  - `docker volume prune` — remove all unused volumes (DATA LOSS!)

#### § 3.2.2 — Using Volumes with Containers
  - `docker run -v volume_name:/container/path image` — mount named volume
  - `docker run --mount source=volume_name,target=/container/path image` — verbose syntax (preferred for clarity)
  - Anonymous volumes: `docker run -v /container/path image` — Docker creates unnamed volume
  - Volume data persists across container restarts and removals
  - Multiple containers can share a volume (concurrent access)
  - First container creates the volume's initial content
  - Volume location on host: `/var/lib/docker/volumes/volume_name/_data/`

#### § 3.2.3 — Volume Drivers
  - `local` — default driver (stores on host filesystem)
  - `nfs` — Network File System volumes
  - Third-party: AWS EBS, Azure File Storage, GlusterFS, Portworx
  - `docker volume create --driver driver_name --opt key=value volume_name`
  - Use case: production storage needs (replication, encryption, performance)

---

### 📦 Module 3.3: Bind Mounts

#### § 3.3.1 — Bind Mount Fundamentals
  - Map a host directory/file directly into the container
  - `-v /host/path:/container/path` — bind mount syntax
  - `--mount type=bind,source=/host/path,target=/container/path` — verbose syntax
  - Host filesystem is directly visible inside the container (real-time)
  - Changes in either host or container are immediately reflected in both
  - Performance: native filesystem speed (no overlay overhead)

#### § 3.3.2 — Bind Mount Use Cases
  - **Development**: mount source code into container (hot-reload)
  - **Configuration**: mount config files into container
  - **Logs**: mount host directory for log output
  - **Shared data**: share data between host and container

#### § 3.3.3 — Read-Only Bind Mounts
  - `-v /host/path:/container/path:ro` — read-only mount
  - Container can read but not write
  - Use case: configuration files, certificates, read-only data
  - Security: prevent containers from modifying host files

#### § 3.3.4 — Bind Mount Gotchas
  - Host path must exist (volumes are auto-created)
  - Permission issues: container user may not have access to host files
  - UID/GID mapping: host UID must match container UID for write access
  - Performance on macOS/Windows: significantly slower than Linux (due to filesystem translation)
  - macOS/Windows: use `delegated` or `cached` consistency modes for better performance
  - Docker Desktop: VirtioFS or gRPC-FUSE filesystem options

---

### 📦 Module 3.4: tmpfs Mounts

#### § 3.4.1 — tmpfs Fundamentals
  - Stored in host memory (RAM) only — never written to disk
  - `--tmpfs /container/path` — simple syntax
  - `--mount type=tmpfs,target=/container/path,tmpfs-size=100m` — with size limit
  - Data is lost when container stops
  - Use case: sensitive data (secrets, tokens), temporary computation, caching

---

### 📦 Module 3.5: Data Management Patterns

#### § 3.5.1 — Backup & Restore
  - Backup a volume: run a temporary container that mounts the volume and creates a tarball
  - Restore a volume: run a temporary container that extracts a tarball into a volume
  - Pattern: `docker run --rm -v mydata:/data -v $(pwd):/backup alpine tar czf /backup/backup.tar.gz /data`
  - Restore: `docker run --rm -v mydata:/data -v $(pwd):/backup alpine tar xzf /backup/backup.tar.gz -C /`

#### § 3.5.2 — Data-Only Containers (Legacy Pattern)
  - Container that exists only to hold volumes (no running process)
  - Replaced by named volumes — understand for legacy knowledge
  - `docker create --name datastore -v /data busybox` — legacy pattern

#### § 3.5.3 — Database Volume Patterns
  - Named volumes for database data directories
  - Separate volumes for data, config, and logs
  - Initialization: mounting SQL scripts to init directories (e.g., `/docker-entrypoint-initdb.d/`)
  - Backup strategies: `pg_dump` / `mysqldump` inside container, write to mounted backup volume

> ### 🛠️ Phase 3 Project: **"Persistent Data Architecture"**
> Design and implement a data management strategy:
> - **Database persistence**: PostgreSQL with a named volume for data, run `pgbench` to generate data, stop and remove the container, verify data survives in a new container using the same volume
> - **Development workflow**: Node.js application with source code as bind mount, demonstrate hot-reload (change code on host → reflected immediately in container)
> - **Configuration injection**: Nginx with custom config via read-only bind mount, swap configs without rebuilding image
> - **Secret handling**: sensitive config via tmpfs mount, demonstrate data is never on disk
> - **Backup/Restore**: implement a backup script that creates compressed, timestamped backups of a database volume, then restore to a new volume and verify data integrity
> - **Multi-container shared data**: two containers sharing a named volume (one writes, one reads), demonstrate concurrent access
> - **Volume analysis**: use `docker system df -v` to audit volume usage, identify orphaned volumes, clean up
> - Document the data lifecycle for each pattern: creation, access, backup, migration, deletion

---

## ⚡ PHASE 4 — NETWORKING
> *"Containers that can't communicate are containers that can't do anything useful."*

---

### 📦 Module 4.1: Docker Network Fundamentals

#### § 4.1.1 — Network Drivers
  - **bridge**: default for standalone containers (isolated virtual network)
  - **host**: container shares the host's network stack (no isolation, best performance)
  - **none**: no networking (fully isolated)
  - **overlay**: multi-host networking (Docker Swarm, Kubernetes)
  - **macvlan**: assign MAC address, container appears as physical device on LAN
  - **ipvlan**: similar to macvlan but shares MAC address

#### § 4.1.2 — The Default Bridge Network
  - Created automatically: `bridge` / `docker0`
  - Containers get private IPs (e.g., 172.17.0.x)
  - Containers on default bridge can communicate by IP (but NOT by name!)
  - Port mapping required for external access: `-p host_port:container_port`
  - Default bridge limitations: no DNS resolution between containers, all containers on same network
  - Recommendation: always create custom bridge networks

#### § 4.1.3 — Custom Bridge Networks
  - `docker network create mynetwork` — create custom bridge
  - `docker run --network mynetwork --name myapp image` — attach container
  - **Automatic DNS resolution**: containers can reach each other by name
  - Network isolation: containers on different networks can't communicate
  - Custom subnet: `docker network create --subnet 192.168.100.0/24 mynetwork`
  - Custom gateway: `--gateway 192.168.100.1`
  - Connecting running container: `docker network connect mynetwork container`
  - Disconnecting: `docker network disconnect mynetwork container`

---

### 📦 Module 4.2: Network Operations

#### § 4.2.1 — Network Management Commands
  - `docker network ls` — list all networks
  - `docker network inspect network_name` — detailed network info (connected containers, IPAM)
  - `docker network create [options] name` — create network
  - `docker network rm name` — remove network
  - `docker network prune` — remove unused networks
  - `docker network connect network container` — connect running container
  - `docker network disconnect network container` — disconnect container

#### § 4.2.2 — Port Mapping
  - `-p 8080:80` — map host port 8080 to container port 80
  - `-p 127.0.0.1:8080:80` — bind to specific host interface (localhost only)
  - `-p 8080:80/tcp` — TCP only (default)
  - `-p 8080:80/udp` — UDP only
  - `-P` — publish all exposed ports to random host ports
  - `docker port container` — show port mappings
  - Multiple ports: `-p 8080:80 -p 8443:443`
  - Port ranges: `-p 8000-8010:8000-8010`

#### § 4.2.3 — DNS & Service Discovery
  - Custom networks: built-in DNS server (127.0.0.11)
  - Container name = DNS name within the network
  - Network aliases: `--network-alias alias_name` — additional DNS names
  - Multiple containers with same alias: round-robin DNS (basic load balancing)
  - DNS search domains: container name resolution is scoped to the network

---

### 📦 Module 4.3: Advanced Networking

#### § 4.3.1 — Host Networking
  - `docker run --network host image` — share host's network namespace
  - No port mapping needed (container binds directly to host ports)
  - Best performance (no NAT overhead)
  - No network isolation — container has full access to host network
  - Use case: performance-critical networking, monitoring tools

#### § 4.3.2 — None Networking
  - `docker run --network none image` — no network access at all
  - Only loopback interface available
  - Use case: batch processing, security-sensitive operations, offline computation

#### § 4.3.3 — Macvlan Networks
  - Container gets its own MAC address on the physical network
  - Appears as a separate device on the LAN
  - Direct connection to physical network (no NAT)
  - Use case: legacy applications expecting to be on LAN, network appliances

#### § 4.3.4 — Connecting to External Services
  - Container to host: `host.docker.internal` (Docker Desktop), `172.17.0.1` (Linux default bridge gateway)
  - Container to external services: just use normal networking (DNS resolution, outbound connections)
  - Proxy configuration: `~/.docker/config.json` or container environment variables

#### § 4.3.5 — Network Troubleshooting
  - `docker exec container ping target` — test connectivity
  - `docker exec container nslookup service_name` — test DNS resolution
  - `docker exec container curl -v http://service:port` — test HTTP
  - `docker network inspect network` — verify container IP addresses, connected containers
  - `docker exec container ip addr` — check container network interfaces
  - `docker exec container netstat -tuln` — check listening ports
  - Debug container: run a utility container on the same network with `curl`, `dig`, `nmap`

> ### 🛠️ Phase 4 Project: **"Microservices Networking Lab"**
> Build a multi-service architecture demonstrating Docker networking:
> - **Architecture**: API Gateway (Nginx) → 3 Backend Services → Database → Cache
> - **Networks**:
>   - `frontend` network: Nginx (exposed to host) + API services
>   - `backend` network: API services + Database + Cache
>   - Database and Cache NOT accessible from frontend network (isolation!)
> - **DNS**: all services communicate by container name (no IP addresses)
> - **Port mapping**: only Nginx exposed to the host (port 80)
> - **Load balancing**: Nginx proxying to multiple instances of the same service (using network aliases)
> - **Troubleshooting exercise**: intentionally misconfigure a network, diagnose and fix using Docker network tools
> - **Network policies**: demonstrate that a container on `frontend` cannot reach the database directly
> - **Host networking**: deploy a monitoring container with host networking, explain the tradeoffs
> - Draw a complete network diagram showing all containers, networks, IP ranges, and port mappings

---

## ⚡ PHASE 5 — DOCKER COMPOSE
> *"Docker Compose turns 'read a 50-line docker run command' into 'read a YAML file.'"*

---

### 📦 Module 5.1: Docker Compose Fundamentals

#### § 5.1.1 — What is Docker Compose
  - Tool for defining and running multi-container Docker applications
  - Single YAML file describes entire application stack
  - One command to start everything: `docker compose up`
  - Docker Compose v2: integrated into Docker CLI (`docker compose`, not `docker-compose`)
  - Compose file: `compose.yaml` (preferred) or `docker-compose.yml` (legacy name)

#### § 5.1.2 — Compose File Structure
  - `services:` — container definitions (the core section)
  - `volumes:` — named volume definitions
  - `networks:` — custom network definitions
  - `secrets:` — secret management
  - `configs:` — configuration file management
  - Compose file version: no longer required (versionless is current standard)
  - `name:` — project name (overrides directory-based default)

#### § 5.1.3 — Service Definition
  - `image:` — use a pre-built image
  - `build:` — build from Dockerfile (context, dockerfile, args, target)
  - `container_name:` — explicit container name
  - `ports:` — port mappings (list)
  - `environment:` — environment variables (list or map)
  - `env_file:` — load variables from file
  - `volumes:` — volume and bind mounts
  - `networks:` — connect to specific networks
  - `depends_on:` — service startup order (not readiness!)
  - `restart:` — restart policy (`no`, `always`, `unless-stopped`, `on-failure`)
  - `command:` — override CMD
  - `entrypoint:` — override ENTRYPOINT
  - `working_dir:` — working directory
  - `user:` — user to run as
  - `healthcheck:` — health check configuration
  - `deploy:` — resource limits and placement (replicas, resources)
  - `labels:` — metadata labels
  - `logging:` — logging driver configuration
  - `extra_hosts:` — add entries to /etc/hosts

---

### 📦 Module 5.2: Compose Operations

#### § 5.2.1 — Lifecycle Commands
  - `docker compose up` — create and start all services
  - `docker compose up -d` — detached mode (background)
  - `docker compose up --build` — rebuild images before starting
  - `docker compose up service_name` — start specific service (and its dependencies)
  - `docker compose down` — stop and remove containers, networks
  - `docker compose down -v` — also remove volumes (DATA LOSS!)
  - `docker compose down --rmi all` — also remove images
  - `docker compose stop` — stop without removing
  - `docker compose start` — start stopped services
  - `docker compose restart` — restart all services
  - `docker compose pause` / `docker compose unpause`

#### § 5.2.2 — Inspection & Debugging
  - `docker compose ps` — list services and their states
  - `docker compose logs` — view logs from all services
  - `docker compose logs -f service` — follow specific service logs
  - `docker compose top` — running processes in each service
  - `docker compose exec service command` — execute command in running service
  - `docker compose run service command` — run a one-off command in a new container
  - `docker compose config` — validate and display resolved Compose file
  - `docker compose images` — list images used by services

#### § 5.2.3 — Build & Pull
  - `docker compose build` — build all services with `build:` key
  - `docker compose build --no-cache service` — rebuild without cache
  - `docker compose pull` — pull latest images for all services
  - `docker compose push` — push built images to registry

---

### 📦 Module 5.3: Advanced Compose Features

#### § 5.3.1 — Health Checks & Dependency Management
  - `healthcheck:` — define container health check (test, interval, timeout, retries, start_period)
  - `depends_on:` basic: just startup order (doesn't wait for readiness)
  - `depends_on:` with condition: `condition: service_healthy` — wait for health check to pass
  - `condition: service_completed_successfully` — wait for init container to finish
  - Proper dependency chain: database healthy → API starts → web server starts

#### § 5.3.2 — Environment Management
  - `environment:` — inline environment variables
  - `env_file:` — load from `.env` file
  - Variable substitution: `${VAR:-default}` — use host env variables in Compose file
  - `.env` file: automatically loaded by Compose (project-level defaults)
  - Multiple env files: `env_file: [.env, .env.local]`
  - Precedence: environment → env_file → Dockerfile ENV

#### § 5.3.3 — Profiles
  - `profiles: ["debug"]` — assign services to profiles
  - `docker compose --profile debug up` — start services matching profile
  - Services without profiles always start
  - Use case: debug tools, monitoring, one-off tasks that shouldn't run by default

#### § 5.3.4 — Multiple Compose Files
  - `docker compose -f compose.yaml -f compose.override.yaml up` — merge files
  - `compose.override.yaml` — automatically merged (development overrides)
  - Pattern: base file + environment-specific overrides
  - `compose.yaml` (shared) + `compose.dev.yaml` (development) + `compose.prod.yaml` (production)
  - `include:` — include other Compose files (Compose v2.20+)

#### § 5.3.5 — Secrets & Configs
  - `secrets:` — mount sensitive data into containers (from files)
  - Mounted at `/run/secrets/secret_name` inside container
  - `configs:` — mount configuration files
  - Both avoid baking sensitive data into images or environment variables

#### § 5.3.6 — Resource Limits
  - `deploy.resources.limits.cpus:` — CPU limit
  - `deploy.resources.limits.memory:` — memory limit
  - `deploy.resources.reservations.memory:` — guaranteed memory
  - `deploy.replicas:` — number of instances (used with `docker compose up --scale`)

#### § 5.3.7 — Extensions & Anchors
  - YAML anchors: `x-common: &common` → `<<: *common` — reuse configuration blocks
  - Extension fields: `x-` prefix — ignored by Compose, used for anchors
  - Use case: DRY — shared environment variables, logging config, labels across services

---

### 📦 Module 5.4: Compose Patterns

#### § 5.4.1 — Development vs Production
  - Development: bind mounts for code, debug tools, hot-reload, exposed all ports, verbose logging
  - Production: no bind mounts, minimal images, limited ports, health checks, resource limits, restart policies
  - Pattern: `compose.yaml` (shared base) + `compose.dev.yaml` (dev overrides) + `compose.prod.yaml` (prod overrides)

#### § 5.4.2 — Init Containers
  - Service that runs once and exits (database migration, seed data)
  - `depends_on: migration: condition: service_completed_successfully`
  - Pattern: migration service runs before API service starts

#### § 5.4.3 — Sidecar Pattern
  - Helper container alongside the main service
  - Use case: log shipping, monitoring agent, proxy, cert renewal
  - Share network or volumes with the main service

#### § 5.4.4 — Watch Mode (Compose Watch)
  - `docker compose watch` — automatic rebuild and restart on file changes (Compose v2.22+)
  - `develop.watch:` — configure which paths to sync, rebuild, or restart on
  - Actions: `sync` (hot-reload files), `rebuild` (rebuild image), `sync+restart` (sync and restart)
  - Replacement for bind mounts in many development scenarios

> ### 🛠️ Phase 5 Project: **"Full-Stack Application Platform"**
> Build a complete application platform with Docker Compose:
> - **Services**:
>   - `web` — Nginx reverse proxy (serves static files, proxies API)
>   - `api` — Backend application (Node.js, Python, or Go)
>   - `db` — PostgreSQL database
>   - `cache` — Redis
>   - `adminer` — database admin UI (profile: debug)
>   - `migration` — database migration runner (init container)
>   - `worker` — background job processor
> - **Data management**: named volumes for db and cache, bind mount for development
> - **Networking**: frontend and backend networks with proper isolation
> - **Health checks**: all services with proper health checks, dependency chain with `condition: service_healthy`
> - **Environment**: `.env` file for configuration, secrets for passwords
> - **Multi-environment**: base compose + dev overrides (bind mounts, debug tools) + prod overrides (resource limits, no debug)
> - **Watch mode**: configure `develop.watch` for automatic sync/rebuild during development
> - **Resource limits**: CPU and memory limits on all production services
> - **Logging**: configured logging driver with rotation
> - **One-command startup**: `docker compose up -d` starts everything in correct order
> - README with architecture diagram, setup instructions, and common operations

---

## ⚡ PHASE 6 — SECURITY
> *"A container is only as secure as its weakest layer."*

---

### 📦 Module 6.1: Image Security

#### § 6.1.1 — Base Image Selection
  - Use official images from Docker Hub (verified by Docker)
  - Pin specific versions (not `latest`): `FROM node:20.11.1-slim`
  - Prefer minimal images: `alpine`, `slim`, `distroless`
  - Fewer packages = smaller attack surface
  - Regularly update base images (rebuild with latest patches)
  - Verify image provenance: Docker Content Trust, image signing

#### § 6.1.2 — Vulnerability Scanning
  - `docker scout cves image` — Docker's built-in scanner
  - `trivy image:tag` — comprehensive vulnerability scanner (Aqua Security)
  - `grype image:tag` — vulnerability scanner (Anchore)
  - `snyk container test image:tag` — Snyk scanner
  - Severity levels: Critical, High, Medium, Low, Negligible
  - Zero-tolerance for Critical/High vulnerabilities in production
  - Automated scanning in CI/CD pipeline (block deployment on critical CVEs)
  - SBOM (Software Bill of Materials): `docker sbom image` — list all components

#### § 6.1.3 — Image Signing & Verification
  - Docker Content Trust (DCT): `export DOCKER_CONTENT_TRUST=1`
  - Notary: signing framework for Docker images
  - Cosign (Sigstore): modern container image signing
  - Verify image integrity: prevent tampered images from running
  - Registry-level policies: only allow signed images

---

### 📦 Module 6.2: Container Runtime Security

#### § 6.2.1 — Running as Non-Root
  - Default: containers run as root (UID 0) — dangerous!
  - Dockerfile: `USER nonroot` or `USER 1000:1000`
  - Create user in Dockerfile: `RUN addgroup --system app && adduser --system --ingroup app app`
  - `docker run --user 1000:1000 image` — override at runtime
  - `--userns-remap` — remap container root to unprivileged host user (daemon-level)
  - Rootless Docker: run the Docker daemon itself without root privileges

#### § 6.2.2 — Capabilities
  - Linux capabilities: fine-grained permissions (instead of all-or-nothing root)
  - Docker drops many capabilities by default
  - `--cap-drop ALL` — drop ALL capabilities (start from zero)
  - `--cap-add NET_BIND_SERVICE` — add only what's needed
  - Principle of least privilege: only add capabilities the container actually needs
  - `docker run --cap-drop ALL --cap-add NET_BIND_SERVICE image`

#### § 6.2.3 — Read-Only Filesystem
  - `docker run --read-only image` — prevent writes to container filesystem
  - `--tmpfs /tmp` — writable temp directory in memory
  - Application must handle read-only filesystem (write to volumes/tmpfs only)
  - Prevents: malware installation, config tampering, filesystem-based attacks

#### § 6.2.4 — Security Profiles
  - **Seccomp**: restrict which system calls a container can make
  - Default seccomp profile: blocks ~44 dangerous syscalls
  - Custom seccomp profiles: further restrict based on application needs
  - `--security-opt seccomp=profile.json` — custom profile
  - **AppArmor**: mandatory access control (default on Ubuntu)
  - `--security-opt apparmor=profile_name` — custom AppArmor profile
  - **SELinux**: mandatory access control (default on RHEL/Fedora)
  - `--security-opt label=type:container_t` — SELinux labels
  - `--security-opt no-new-privileges` — prevent privilege escalation

#### § 6.2.5 — Resource Limits as Security
  - Memory limits: prevent DoS via memory exhaustion
  - CPU limits: prevent CPU starvation of other containers/host
  - PID limits: prevent fork bombs (`--pids-limit 100`)
  - Network bandwidth limits: prevent network abuse
  - Disk I/O limits: prevent I/O starvation

---

### 📦 Module 6.3: Network Security

#### § 6.3.1 — Network Isolation
  - Custom networks: containers on different networks can't communicate
  - Internal networks: `docker network create --internal private_net` — no external access
  - Network segmentation: frontend, backend, data tiers on separate networks
  - Only expose necessary ports: limit `-p` to what's required
  - Bind to localhost: `-p 127.0.0.1:8080:80` — not accessible from external network

#### § 6.3.2 — Encrypted Communication
  - TLS between services (mutual TLS in production)
  - Encrypted overlay networks (Swarm mode)
  - TLS termination at reverse proxy (Nginx/Traefik)

---

### 📦 Module 6.4: Secrets Management

#### § 6.4.1 — What NOT to Do
  - Never hardcode secrets in Dockerfiles (`ENV PASSWORD=secret`)
  - Never commit `.env` files with secrets to version control
  - Never pass secrets as build arguments (`--build-arg`) — visible in image history
  - Never store secrets in image layers

#### § 6.4.2 — Secret Management Strategies
  - Docker Compose secrets: mount from files, available at `/run/secrets/`
  - Environment variables: acceptable for non-sensitive config, risky for secrets (visible in `docker inspect`)
  - BuildKit secrets: `--mount=type=secret` — available during build only, never stored in layers
  - Runtime injection: mount secrets from host, external secret managers
  - External secret managers: HashiCorp Vault, AWS Secrets Manager, Azure Key Vault
  - Pattern: fetch secrets at runtime from a secrets manager, not baked into images

---

### 📦 Module 6.5: Docker Daemon Security

#### § 6.5.1 — Daemon Configuration
  - Docker socket: `/var/run/docker.sock` — access = full root access to the host!
  - Never mount Docker socket into containers (except for specific CI/CD use cases with extreme caution)
  - TLS for remote Docker API access
  - Authorization plugins: fine-grained access control
  - User namespace remapping: `userns-remap` in daemon configuration
  - Rootless mode: run Docker daemon as non-root user

#### § 6.5.2 — Audit & Compliance
  - Docker Bench for Security: automated best-practice checks
  - `docker run --rm -it docker/docker-bench-security` — run the audit
  - CIS Docker Benchmark: industry-standard security checklist
  - Regularly audit: running containers, images, volumes, networks
  - Image provenance: track where images come from and when they were last scanned

> ### 🛠️ Phase 6 Project: **"Fortress Containers — Security Hardening"**
> Take the Phase 5 application platform and harden every layer:
> - **Image security**: scan all images with `trivy`, fix all Critical/High vulnerabilities, document results
> - **Non-root**: all containers running as non-root users, verify with `docker exec container whoami`
> - **Capabilities**: drop ALL capabilities, add back only what's needed per service, document each capability
> - **Read-only**: enable read-only filesystem on all containers, use tmpfs for temporary data
> - **Secrets**: migrate all passwords/keys from environment variables to Docker Compose secrets
> - **Network isolation**: implement proper network segmentation (frontend/backend/data), verify containers can't cross boundaries
> - **Resource limits**: CPU and memory limits on every container, test behavior when limits are exceeded
> - **PID limits**: prevent fork bombs in every container
> - **Docker Bench**: run Docker Bench for Security, achieve score > 80%, document all findings and remediations
> - **Security report**: comprehensive document listing every security measure, why it was applied, and verification steps

---

## ⚡ PHASE 7 — CI/CD WITH DOCKER
> *"Docker makes CI/CD reproducible, portable, and fast."*

---

### 📦 Module 7.1: Docker in CI/CD Pipelines

#### § 7.1.1 — Why Docker for CI/CD
  - Reproducible builds: same environment in CI as development and production
  - Isolated test environments: no interference between pipeline runs
  - Consistent tooling: no "install Java, Node, Python" in CI config
  - Fast onboarding: new CI runner just needs Docker installed
  - Artifact: the image IS the deployable artifact (build once, deploy everywhere)

#### § 7.1.2 — CI Pipeline Pattern
  - Stage 1: Lint and type-check (run in container)
  - Stage 2: Build application (multi-stage Dockerfile)
  - Stage 3: Run tests (inside container or with Compose for integration tests)
  - Stage 4: Scan image for vulnerabilities
  - Stage 5: Push image to registry (with proper tags)
  - Stage 6: Deploy (pull image on target, restart service)

#### § 7.1.3 — Image Tagging Strategy
  - Git SHA: `myapp:abc1234` — every commit has a unique image
  - Semantic version: `myapp:1.2.3` — release versions
  - Branch-based: `myapp:main`, `myapp:feature-xyz`
  - Latest: `myapp:latest` — always points to the most recent build (avoid in production)
  - Immutable tags: once pushed, never overwrite (except `latest`)
  - Recommended: `myapp:1.2.3` + `myapp:abc1234` (version + commit)

---

### 📦 Module 7.2: GitHub Actions with Docker

#### § 7.2.1 — Building and Pushing Images
  - `docker/setup-buildx-action` — set up BuildKit
  - `docker/login-action` — authenticate with registry
  - `docker/build-push-action` — build and push in one step
  - `docker/metadata-action` — automatic tag generation (version, SHA, branch)
  - Caching: GitHub Actions cache, registry cache, BuildKit cache

#### § 7.2.2 — Testing with Docker in CI
  - Service containers: `services:` in workflow (spin up databases, caches)
  - Docker Compose in CI: `docker compose up -d && docker compose run tests`
  - Testcontainers: programmatic container management from test code
  - Parallel testing: multiple test containers running simultaneously

#### § 7.2.3 — Multi-Platform Builds
  - `docker buildx build --platform linux/amd64,linux/arm64` — build for multiple architectures
  - QEMU emulation: build ARM images on x86 runners (and vice versa)
  - Manifest lists: single tag references multiple platform-specific images
  - Docker automatically pulls the correct architecture

---

### 📦 Module 7.3: GitLab CI with Docker

#### § 7.3.1 — GitLab Container Registry
  - Built-in container registry per project
  - `$CI_REGISTRY_IMAGE` — automatic image naming
  - `docker:dind` (Docker-in-Docker) — for building images in GitLab CI
  - Kaniko: build images without Docker daemon (more secure)

---

### 📦 Module 7.4: Registry Management

#### § 7.4.1 — Docker Hub
  - Free: 1 private repository, unlimited public
  - Automated builds: build on push (from GitHub/Bitbucket)
  - Organizations and teams
  - Rate limits: 100 pulls/6hrs (anonymous), 200 pulls/6hrs (free authenticated)

#### § 7.4.2 — GitHub Container Registry (ghcr.io)
  - Integrated with GitHub: same authentication
  - Free for public packages, generous free tier for private
  - Recommended for GitHub-hosted projects

#### § 7.4.3 — Self-Hosted Registry
  - `docker run -d -p 5000:5000 registry:2` — run your own registry
  - Harbor: enterprise-grade registry (scanning, replication, RBAC)
  - When: air-gapped environments, compliance requirements, full control

#### § 7.4.4 — Registry Best Practices
  - Enable vulnerability scanning on the registry
  - Image retention policies: delete old images automatically
  - Access control: least-privilege access to push/pull
  - Geo-replication for multi-region deployments
  - Image signing and verification

---

### 📦 Module 7.5: Deployment Strategies with Docker

#### § 7.5.1 — Single Host Deployment
  - SSH into server, pull latest image, restart container
  - Watchtower: automatically update running containers when images change
  - `docker compose pull && docker compose up -d` — manual deployment

#### § 7.5.2 — Blue-Green Deployment
  - Two identical environments: blue (current) and green (new)
  - Deploy to green, verify, switch traffic from blue to green
  - Instant rollback: switch back to blue
  - Implementation: two Compose files, Nginx upstream switching

#### § 7.5.3 — Rolling Deployment
  - Update containers one at a time (no downtime)
  - Health check verification before proceeding
  - Rollback: stop rolling, revert updated containers
  - Docker Swarm and Kubernetes handle this natively

#### § 7.5.4 — Canary Deployment
  - Route small percentage of traffic to new version
  - Monitor errors and performance
  - Gradually increase traffic if healthy
  - Rollback: route all traffic back to old version

> ### 🛠️ Phase 7 Project: **"Complete CI/CD Pipeline"**
> Build an end-to-end CI/CD pipeline:
> - **Application**: choose a simple web application (any language)
> - **Dockerfile**: optimized multi-stage build
> - **GitHub Actions pipeline**:
>   - Lint and test in Docker containers
>   - Build multi-platform image (amd64 + arm64)
>   - Scan with `trivy` (fail on Critical/High)
>   - Push to GitHub Container Registry with semantic versioning tags
>   - Cache optimization: layer cache, BuildKit cache, GitHub cache
> - **Deployment**:
>   - Deploy to a VPS via SSH (pull image, restart with Compose)
>   - Blue-green deployment script: deploy new version alongside old, verify health, switch traffic
>   - Automatic rollback on health check failure
> - **Notifications**: Slack/Discord notification on success/failure
> - **Monitoring**: verify deployment with health check endpoint
> - **Documentation**: pipeline architecture diagram, deployment runbook, rollback procedure
> - Bonus: set up GitLab CI as an alternative pipeline, compare the experience

---

## ⚡ PHASE 8 — PRODUCTION PATTERNS & OPERATIONAL EXCELLENCE
> *"Running containers in production is not the same as running them on your laptop."*

---

### 📦 Module 8.1: Logging

#### § 8.1.1 — Container Logging Architecture
  - Docker captures stdout and stderr from PID 1
  - Applications MUST log to stdout/stderr (not files inside the container)
  - `docker logs container` — view captured logs
  - Log drivers: how Docker stores and forwards logs
  - Twelve-Factor App: "Treat logs as event streams"

#### § 8.1.2 — Logging Drivers
  - `json-file` — default, writes JSON to host filesystem
  - `json-file` options: `max-size`, `max-file` (log rotation — ESSENTIAL in production!)
  - `syslog` — send to syslog daemon
  - `journald` — send to systemd journal
  - `fluentd` — send to Fluentd collector
  - `gelf` — Graylog Extended Log Format
  - `awslogs` — send to AWS CloudWatch
  - `splunk` — send to Splunk
  - `none` — disable logging (never in production!)
  - Configure per container or daemon-wide: `/etc/docker/daemon.json`

#### § 8.1.3 — Centralized Logging Stack
  - **ELK**: Elasticsearch + Logstash + Kibana
  - **EFK**: Elasticsearch + Fluentd + Kibana
  - **Grafana Loki + Promtail**: lightweight, Grafana-integrated
  - **Vector + ClickHouse**: modern, high-performance
  - Pattern: container stdout → log driver → collector → storage → dashboard
  - Structured logging: JSON-formatted logs for easier parsing and querying

---

### 📦 Module 8.2: Monitoring

#### § 8.2.1 — Container Metrics
  - `docker stats` — real-time resource usage
  - Docker Engine metrics: expose via `/metrics` endpoint (Prometheus format)
  - cAdvisor (Container Advisor): detailed per-container metrics
  - Metrics to monitor: CPU usage, memory usage, network I/O, disk I/O, restart count

#### § 8.2.2 — Monitoring Stack
  - **Prometheus**: metrics collection and storage
  - **cAdvisor**: container metrics exporter
  - **Node Exporter**: host system metrics
  - **Grafana**: visualization dashboards
  - **Alertmanager**: alerting based on metric thresholds
  - All run as Docker containers themselves (monitoring monitors itself)

#### § 8.2.3 — Health Checks
  - Dockerfile `HEALTHCHECK`: define how Docker checks if container is healthy
  - `HEALTHCHECK --interval=30s --timeout=3s --retries=3 CMD curl -f http://localhost/ || exit 1`
  - Container states: `starting`, `healthy`, `unhealthy`
  - Compose: `depends_on: condition: service_healthy` — proper startup ordering
  - Application health endpoints: `/health`, `/ready`, `/live`
  - Liveness vs readiness: liveness = "is it alive?", readiness = "can it serve traffic?"

---

### 📦 Module 8.3: Performance Optimization

#### § 8.3.1 — Image Build Performance
  - BuildKit: parallel builds, better caching
  - Layer cache: order instructions from least to most changing
  - Cache mounts: persist package manager caches across builds
  - `.dockerignore`: reduce build context size
  - Multi-stage builds: only copy what's needed
  - Remote caching: `--cache-from` and `--cache-to` registry-based caching

#### § 8.3.2 — Runtime Performance
  - Storage driver: `overlay2` is the default and recommended
  - Logging driver: `json-file` with rotation (prevent disk fill)
  - Network: host networking for maximum performance (when isolation isn't needed)
  - Memory: set appropriate limits (not too low — causes OOM, not too high — wastes resources)
  - CPU: set shares for relative priority, limits for hard caps
  - I/O: use volumes for heavy I/O workloads (not the writable layer)

#### § 8.3.3 — Startup Performance
  - Minimize image size: faster pulls, faster starts
  - Lazy pulling: only pull layers that are actually needed (experimental)
  - Image pre-warming: pre-pull images on hosts before deployment
  - Health check start period: give containers time to initialize before marking unhealthy

---

### 📦 Module 8.4: High Availability Patterns

#### § 8.4.1 — Container Restart Policies
  - `--restart no` — never restart (default)
  - `--restart always` — always restart (including after host reboot)
  - `--restart unless-stopped` — restart unless explicitly stopped
  - `--restart on-failure:5` — restart only on failure, max 5 attempts
  - Production: use `unless-stopped` or `always` with health checks

#### § 8.4.2 — Load Balancing
  - Nginx reverse proxy: upstream blocks with multiple backends
  - Traefik: Docker-native reverse proxy with automatic service discovery
  - HAProxy: high-performance TCP/HTTP load balancer
  - Docker Compose: `deploy.replicas` with a load balancer in front
  - Health-based routing: only route to healthy containers

#### § 8.4.3 — Zero-Downtime Deployments
  - Rolling updates: update one container at a time behind a load balancer
  - Health check gating: new container must be healthy before old one is removed
  - Connection draining: allow existing requests to complete before stopping old container
  - `docker stop --time 30 container` — give container 30 seconds to drain

#### § 8.4.4 — Disaster Recovery
  - Volume backup automation: regular, encrypted, offsite backups
  - Image availability: images in registry (not just local), multiple registries for redundancy
  - Docker Compose files in version control: infrastructure as code
  - Recovery testing: regularly test restoring from backups
  - Runbooks: documented procedures for every failure scenario

---

### 📦 Module 8.5: Reverse Proxies & Service Discovery

#### § 8.5.1 — Traefik (Docker-Native Proxy)
  - Automatic service discovery from Docker labels
  - Automatic SSL with Let's Encrypt
  - Dynamic configuration: add/remove services without restart
  - Dashboard: built-in monitoring UI
  - Middleware: rate limiting, authentication, headers, compression
  - Labels-based configuration: `traefik.http.routers.myapp.rule=Host('example.com')`

#### § 8.5.2 — Nginx Proxy Manager
  - GUI for Nginx reverse proxy configuration
  - Easy SSL certificate management
  - Access lists and security features
  - Good for smaller deployments and less technical teams

#### § 8.5.3 — Caddy
  - Automatic HTTPS by default
  - Simple configuration: `Caddyfile`
  - Docker integration via labels or API
  - Use case: simple deployments, automatic SSL

> ### 🛠️ Phase 8 Project: **"Production-Ready Docker Platform"**
> Build a fully production-ready Docker platform:
> - **Application**: multi-service application (API + worker + scheduler)
> - **Reverse proxy**: Traefik with automatic service discovery, SSL certificates, and dashboard
> - **Monitoring**: Prometheus + cAdvisor + Node Exporter + Grafana stack (all in Docker)
>   - Grafana dashboards: container metrics, host metrics, application metrics
>   - Alertmanager: alerts for high CPU, memory, container restarts, disk usage
> - **Logging**: Grafana Loki + Promtail for centralized logging
>   - JSON-formatted application logs
>   - Log rotation on Docker daemon
>   - Grafana dashboard for log exploration
> - **Health checks**: every container with health checks, proper dependency ordering
> - **High availability**: multiple API replicas behind Traefik, demonstrate zero-downtime deployment
> - **Backup**: automated volume backup with encryption, retention policy, restore testing
> - **Resource management**: CPU and memory limits on every container, monitoring for resource usage trends
> - **Documentation**: complete operations runbook covering deployment, scaling, backup, restore, troubleshooting, and disaster recovery

---

## ⚡ PHASE 9 — CONTAINER ORCHESTRATION & BEYOND
> *"Docker Compose manages containers on one host. Orchestrators manage containers across fleets."*

---

### 📦 Module 9.1: Docker Swarm (Docker's Built-in Orchestrator)

#### § 9.1.1 — Swarm Fundamentals
  - Built into Docker Engine — no additional installation
  - `docker swarm init` — initialize a Swarm cluster
  - Manager nodes: control plane (scheduling, state management)
  - Worker nodes: run containers
  - `docker node ls` — list cluster nodes
  - Services: desired state definitions (replicas, image, ports, networks)

#### § 9.1.2 — Swarm Services
  - `docker service create --name web --replicas 3 -p 80:80 nginx` — create a service
  - `docker service ls` — list services
  - `docker service ps service_name` — show running tasks
  - `docker service scale service_name=5` — scale up/down
  - `docker service update --image nginx:1.25 service_name` — rolling update
  - `docker service rollback service_name` — rollback to previous version

#### § 9.1.3 — Swarm Stack Deployments
  - `docker stack deploy -c compose.yaml stack_name` — deploy Compose file to Swarm
  - Supports most Compose features plus `deploy:` section (replicas, resources, placement, update config, rollback config)
  - `docker stack ls`, `docker stack ps`, `docker stack rm`

#### § 9.1.4 — Swarm Networking
  - Overlay networks: span multiple hosts
  - Routing mesh: any node can accept traffic for any service
  - Encrypted overlay: `--opt encrypted` — data plane encryption
  - Internal networks: services that shouldn't be externally accessible

#### § 9.1.5 — Swarm Secrets & Configs
  - `docker secret create secret_name file` — create a secret
  - Secrets stored encrypted in Raft log, mounted in memory at `/run/secrets/`
  - `docker config create config_name file` — create a config
  - Rotation: update secrets/configs without recreating services

#### § 9.1.6 — When Docker Swarm
  - Simple orchestration needs
  - Small to medium clusters (< 50 nodes)
  - Teams already familiar with Docker Compose
  - No need for the complexity of Kubernetes
  - Built-in: no additional installation or learning curve

---

### 📦 Module 9.2: Kubernetes (Overview — Not a Full K8s Roadmap)

#### § 9.2.1 — Kubernetes Fundamentals
  - Container orchestration at massive scale
  - Key concepts: Pods, Deployments, Services, Ingress, ConfigMaps, Secrets, PersistentVolumeClaims
  - `kubectl` — the Kubernetes CLI
  - Control plane: API server, etcd, scheduler, controller manager
  - Worker nodes: kubelet, container runtime (containerd), kube-proxy

#### § 9.2.2 — Docker to Kubernetes Migration
  - Compose → Kubernetes: `kompose convert` — converts Compose files to K8s manifests
  - Images: same Docker/OCI images work on Kubernetes
  - Networking: different model (flat network, Services, Ingress)
  - Storage: PersistentVolumes and PersistentVolumeClaims
  - Configuration: ConfigMaps and Secrets

#### § 9.2.3 — Kubernetes Distributions for Learning
  - `minikube` — local K8s cluster (VM or Docker-based)
  - `kind` (Kubernetes in Docker) — K8s nodes as Docker containers
  - `k3s` — lightweight K8s (Rancher, great for edge/small clusters)
  - Docker Desktop: built-in Kubernetes (enable in settings)

#### § 9.2.4 — When Kubernetes vs Docker Swarm vs Compose
  - Docker Compose: single host, development, small deployments
  - Docker Swarm: multi-host, simple orchestration, small-medium scale
  - Kubernetes: large scale, complex applications, enterprise, cloud-native ecosystem
  - Kubernetes is the industry standard for production container orchestration

---

### 📦 Module 9.3: Alternative Container Runtimes

#### § 9.3.1 — Podman
  - Daemonless: no background daemon (more secure)
  - Rootless: run containers without root by default
  - CLI-compatible with Docker (`alias docker=podman`)
  - Pod concept: group of containers sharing namespaces (like Kubernetes pods)
  - `podman-compose` or `podman compose` — Compose compatibility
  - Systemd integration: generate systemd units from containers
  - Use case: security-sensitive environments, RHEL-based systems

#### § 9.3.2 — containerd (Direct Usage)
  - `nerdctl` — Docker-compatible CLI for containerd
  - Used directly in Kubernetes (without Docker)
  - Lighter weight than full Docker Engine
  - `ctr` — containerd's native CLI (low-level)

#### § 9.3.3 — WebAssembly Containers (Emerging)
  - Wasm containers: faster startup, smaller size, sandboxed
  - `wasmtime`, `WasmEdge` — Wasm runtimes
  - Docker + Wasm: `docker run --runtime=io.containerd.wasmedge.v1`
  - Use case: edge computing, serverless functions, plugins
  - "If WASM+WASI existed in 2008, we wouldn't have needed to create Docker" — Solomon Hykes (Docker co-founder)

---

### 📦 Module 9.4: The Cloud-Native Ecosystem

#### § 9.4.1 — CNCF (Cloud Native Computing Foundation) Landscape
  - Container runtime: containerd, CRI-O
  - Orchestration: Kubernetes
  - Service mesh: Istio, Linkerd, Cilium
  - Observability: Prometheus, Grafana, Jaeger, OpenTelemetry
  - CI/CD: Argo CD, Flux, Tekton
  - Registry: Harbor
  - Networking: Calico, Cilium, Flannel
  - Storage: Longhorn, Rook, OpenEBS
  - Security: Falco, OPA, Trivy

#### § 9.4.2 — Serverless Containers
  - AWS Fargate: run containers without managing servers
  - Google Cloud Run: serverless container platform
  - Azure Container Instances: on-demand containers
  - Fly.io: run Docker containers on the edge
  - Railway: simple container deployment platform
  - No server management: just push an image, platform handles the rest

> ### 🛠️ Phase 9 Capstone Project: **"Multi-Host Container Platform"**
> Build and compare orchestration approaches:
>
> **Part 1: Docker Swarm Cluster**
> - Set up a 3-node Swarm cluster (1 manager + 2 workers) using VMs or cloud instances
> - Deploy the Phase 8 application as a Swarm stack
> - Overlay networking with encryption
> - Swarm secrets for sensitive configuration
> - Rolling updates: deploy a new version with zero downtime
> - Demonstrate self-healing: kill a container, watch Swarm restart it
> - Scale services up and down, observe load distribution
> - Monitor with Prometheus + Grafana (deployed as Swarm services)
>
> **Part 2: Kubernetes Migration**
> - Set up a k3s cluster (single node or 3-node)
> - Convert the Compose file to Kubernetes manifests (manual or `kompose`)
> - Deploy the same application on Kubernetes
> - Kubernetes Ingress for HTTP routing
> - Horizontal Pod Autoscaler for automatic scaling
> - ConfigMaps and Secrets for configuration
> - PersistentVolumeClaims for database storage
>
> **Part 3: Comparison Report**
> - Document: setup complexity, deployment workflow, scaling, self-healing, monitoring, networking, secrets management
> - Performance comparison: deployment speed, resource overhead, startup time
> - Recommendations: when to use each approach
> - Architecture diagrams for both deployments

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0  ██░░░░░░░░░░░░░░  Orientation & Container Concepts
Phase 1  ████░░░░░░░░░░░░  Docker Fundamentals (Run, Inspect, Manage)
Phase 2  ██████░░░░░░░░░░  Building Images (Dockerfile, Optimization)
Phase 3  ████████░░░░░░░░  Data Management (Volumes, Bind Mounts)
Phase 4  █████████░░░░░░░  Networking (Bridge, Overlay, DNS)
Phase 5  ██████████░░░░░░  Docker Compose (Multi-Container Apps)
Phase 6  ███████████░░░░░  Security (Scanning, Hardening, Secrets)
Phase 7  ████████████░░░░  CI/CD (Pipelines, Registries, Deployment)
Phase 8  █████████████░░░  Production Patterns (Logging, Monitoring, HA)
Phase 9  ██████████████░░  Orchestration (Swarm, Kubernetes, Beyond)
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 3     │──────▶│   Phase 6    │──────▶│   Phase 8    │
    │  Phase 1   │        │    Phase 4     │       │   Phase 7    │       │   Phase 9    │
    │  Phase 2   │        │    Phase 5     │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can run and         "I build multi-          "I secure and          "I orchestrate
     build containers"      container apps           deploy containers      containers at
                            with Compose"            in CI/CD"              scale"
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification |
|-------|--------------|
| 0 – 5 | **Docker Certified Associate (DCA)** |
| 0 – 5 | **KCNA (Kubernetes and Cloud Native Associate)** |
| 6 – 9 | **CKA (Certified Kubernetes Administrator)** — Kubernetes-focused but Docker knowledge is foundational |
| 6 – 9 | **CKAD (Certified Kubernetes Application Developer)** — building containerized applications |
| 8 – 9 | **CKS (Certified Kubernetes Security Specialist)** — container and cluster security |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| **Docker Official Documentation** (docs.docker.com) | 🌐 Official (START HERE) | ALL |
| *Docker Deep Dive* — Nigel Poulton | 📖 Book (Best intro) | 0–5 |
| *Docker in Action* — Jeff Nickoloff (3rd Ed.) | 📖 Book | 0–7 |
| *Docker in Practice* — Ian Miell & Aidan Hobson Sayers | 📖 Book (Patterns) | 5–8 |
| *Container Security* — Liz Rice | 📖 Book (MUST READ for security) | 0, 6 |
| *Learning Docker* — Pethuru Raj et al. | 📖 Book (Beginner) | 0–4 |
| *Kubernetes Up & Running* — Burns, Beda, Hightower | 📖 Book (K8s) | 9 |
| **Play with Docker** (labs.play-with-docker.com) | 🧪 Interactive (Free) | 0–5 |
| **Docker Labs** (github.com/docker/labs) | 🧪 Hands-on | 1–7 |
| **KodeKloud Docker Course** | 🧪 Interactive Labs | 0–7 |
| **TechWorld with Nana** (YouTube) | 🎥 Video | 0–9 |
| **NetworkChuck** (YouTube) | 🎥 Video | 0–5 |
| **Bret Fisher** (YouTube + Udemy) | 🎥 Video (Docker Captain) | 0–9 |
| **That DevOps Guy / Marcel Dempers** (YouTube) | 🎥 Video | 5–9 |
| **Christian Lempa** (YouTube) | 🎥 Video (Self-hosting) | 5–8 |
| **Awesome Docker** (github.com/veggiemonk/awesome-docker) | 🌐 Curated List | ALL |
| **Docker Hub** (hub.docker.com) | 🌐 Image Registry | ALL |
| **CNCF Landscape** (landscape.cncf.io) | 🌐 Ecosystem Map | 9 |
| **SadServers** (sadservers.com) | 🧪 Troubleshooting | 5–8 |
| **Dive** (github.com/wagoodman/dive) | 🧪 Image Analysis Tool | 2 |
| **Trivy** (github.com/aquasecurity/trivy) | 🧪 Security Scanner | 6 |

---

## 🗺️ WHERE DOCKER TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   DevOps Engineering      │
                           ┌─────▶│   (CI/CD, Automation,     │
                           │      │    Infrastructure)         │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Platform Engineering    │
                   ┌───────┤─────▶│   (Kubernetes, Service    │
                   │       │      │    Mesh, Internal Tooling) │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Site Reliability        │
   │            │  │       ├─────▶│   Engineering (SRE)       │
   │  Master    ├──┤       │      │   (Reliability, Scaling,  │
   │  Docker    │  │       │      │    Incident Response)      │
   │            │  │       │      └───────────────────────────┘
   └────────────┘  │       │      ┌───────────────────────────┐
                   │       │      │   Cloud Engineering       │
                   │       ├─────▶│   (AWS/GCP/Azure,         │
                   │       │      │    Serverless, Edge)        │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Backend Development     │
                   │       ├─────▶│   (Containerized APIs,    │
                   │       │      │    Microservices)           │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Security Engineering    │
                   └───────┴─────▶│   (Container Security,    │
                                  │    Supply Chain Security)  │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"Docker is not about running containers. It's about changing how you think about software delivery."**
>
> Five non-negotiable rules for your Docker journey:
>
> 1. **Read *Container Security* by Liz Rice** — it's only 175 pages and it will permanently change how you think about containers. Understanding what a container actually IS (namespaces, cgroups, capabilities) makes everything else click. Without this foundation, you're just typing commands without understanding.
>
> 2. **Build images for EVERYTHING you use** — don't just run other people's images. Write Dockerfiles for your own projects, for your development tools, for your scripts. Building images is the core skill — the rest is operational. Optimize every image: multi-stage builds, minimal bases, non-root users, health checks.
>
> 3. **Never use `latest` in production** — pin every image tag to a specific version. `latest` is not "the latest version" — it's "the default tag," and it can mean anything. Immutable, versioned tags prevent "but it worked yesterday" disasters.
>
> 4. **Security is not optional** — scan every image, run as non-root, drop capabilities, use read-only filesystems, never store secrets in images. Run Docker Bench for Security monthly. The default Docker configuration is NOT secure for production. Every Phase 6 concept should be applied from Phase 2 onward.
>
> 5. **Docker Compose is your best friend** — master Compose before moving to Swarm or Kubernetes. If you can design a clean, well-organized Compose file with proper networking, volumes, health checks, secrets, and environment management, you already understand 80% of what Kubernetes does (just at a single-host level). The concepts translate directly.
>
> The difference between a *Docker user* and a *Docker engineer* is:
> - **Understanding the Linux kernel features** underneath (namespaces, cgroups, overlay filesystems)
> - **Optimizing images** obsessively (every megabyte counts, every layer matters)
> - **Security by default** (non-root, minimal images, scanned, signed, hardened)
> - **Production thinking** (logging, monitoring, health checks, graceful shutdown, backup, disaster recovery)

---

*This roadmap takes you from "What's a container?" to "I can build, secure, deploy, monitor, and orchestrate containerized applications at production scale — and I understand every layer from the Linux kernel to the Grafana dashboard."* 🐳🚀