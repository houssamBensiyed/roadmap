# 🐧 THE ULTIMATE LINUX ROADMAP
### From Zero to Linux Systems Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~8-12 Months (Dedicated Study)
> **Prerequisite:** None — starts from absolute zero
> *Linux runs 96% of the world's top servers, powers every Android phone, runs the international space station, and is the backbone of cloud computing. If you work in tech, you WILL encounter Linux.*

---

## ⚡ PHASE 0 — ORIENTATION & ENVIRONMENT SETUP
> *"Linux is not just an operating system. It's a philosophy of openness, modularity, and control."*

---

### 📦 Module 0.1: Understanding Linux's Identity

#### § 0.1.1 — What is Linux
  - Linux is a **kernel**, not a complete operating system
  - GNU/Linux: the kernel (Linux) + userland tools (GNU) = a complete OS
  - Created by Linus Torvalds in 1991 as a free alternative to MINIX
  - Open source: licensed under GPLv2 — anyone can view, modify, and distribute
  - Monolithic kernel with loadable modules

#### § 0.1.2 — Why Linux Matters
  - Servers: 96%+ of the world's top 1 million web servers run Linux
  - Cloud: AWS, GCP, Azure — Linux is the default
  - Containers: Docker and Kubernetes run on Linux
  - Supercomputers: 100% of the top 500 supercomputers run Linux
  - Android: built on the Linux kernel (3+ billion devices)
  - Embedded: routers, smart TVs, IoT devices, cars, medical devices
  - DevOps/SRE: the platform for CI/CD, infrastructure, automation
  - Developer workstations: increasingly popular among software engineers

#### § 0.1.3 — The Unix Philosophy
  - "Do one thing and do it well" — small, focused programs
  - "Everything is a file" — devices, sockets, processes exposed as files
  - "Text streams as universal interface" — programs communicate via text
  - Composability: combine small tools with pipes to build complex workflows
  - Silence is golden: no output means success
  - These principles are 50+ years old — and still guide Linux design today

#### § 0.1.4 — Linux vs Other Operating Systems
  - Linux vs Windows: open source vs proprietary, CLI-first vs GUI-first, package managers vs installers
  - Linux vs macOS: fully open vs partially open, runs everywhere vs Apple hardware only
  - Linux vs BSD (FreeBSD, OpenBSD): different kernels, different licenses (GPL vs BSD), different communities
  - Linux vs Unix: Linux is Unix-like, not Unix (no certification, but POSIX-compatible)

---

### 📦 Module 0.2: Linux Distributions

#### § 0.2.1 — What is a Distribution
  - Kernel + package manager + init system + default software + configuration = distribution
  - All distributions use the same Linux kernel (with patches)
  - Differences: package format, package manager, default desktop, philosophy, release cycle

#### § 0.2.2 — Distribution Families
  - **Debian family**: Debian → Ubuntu → Linux Mint, Pop!_OS, Zorin
    - Package format: `.deb`
    - Package manager: `apt` (APT)
    - Stability-focused, enormous package repository
  - **Red Hat family**: Fedora → RHEL → CentOS Stream, Rocky Linux, AlmaLinux, Oracle Linux
    - Package format: `.rpm`
    - Package manager: `dnf` (formerly `yum`)
    - Enterprise-focused, SELinux integration
  - **Arch family**: Arch Linux → Manjaro, EndeavourOS
    - Package manager: `pacman`
    - Rolling release, bleeding-edge, DIY philosophy, AUR (Arch User Repository)
  - **SUSE family**: openSUSE Tumbleweed/Leap → SUSE Linux Enterprise
    - Package manager: `zypper`
    - Enterprise and community editions, YaST configuration tool
  - **Independent**: Gentoo (source-based), Void Linux, NixOS (declarative), Alpine (minimal, Docker favorite), Slackware (oldest active)

#### § 0.2.3 — Choosing a Distribution
  - Beginners: Ubuntu, Linux Mint, Fedora
  - Servers/Enterprise: Ubuntu Server, RHEL/Rocky Linux, Debian
  - DevOps/Containers: Alpine (minimal), Ubuntu Server, Fedora CoreOS
  - Learning/Advanced: Arch Linux (forces you to understand everything)
  - Security: Kali Linux (pentesting), Tails (privacy), Qubes OS (isolation)
  - Recommendation: start with **Ubuntu** (largest community, most tutorials), move to **Arch** when comfortable

#### § 0.2.4 — Release Models
  - **Point release**: major versions with long support (Ubuntu LTS: 5 years, RHEL: 10 years)
  - **Rolling release**: continuous updates, always latest (Arch, openSUSE Tumbleweed)
  - **LTS (Long Term Support)**: security patches for years, no new features
  - Choosing: servers → LTS/point release, workstations → rolling or latest release

---

### 📦 Module 0.3: Setting Up Your Linux Environment

#### § 0.3.1 — Installation Options
  - **Virtual Machine**: VirtualBox, VMware Workstation/Fusion, GNOME Boxes, UTM (macOS ARM)
  - **Dual Boot**: Linux alongside Windows/macOS (resize partitions)
  - **WSL2 (Windows Subsystem for Linux)**: Linux inside Windows (great for development)
  - **Cloud VM**: AWS EC2, DigitalOcean, Linode, Vultr — spin up a Linux server in minutes
  - **Live USB**: try without installing (boot from USB drive)
  - **Bare metal**: dedicated Linux installation (the full experience)
  - Recommended for learning: **VM** (safe to break), then **VPS** (real server experience)

#### § 0.3.2 — Installation Process
  - Downloading ISO images and verifying checksums
  - Bootable USB creation: Rufus (Windows), Balena Etcher, `dd` (Linux/macOS)
  - Installation wizard: language, timezone, keyboard, partitioning, user creation
  - Partition schemes: guided (automatic) vs manual
  - UEFI vs BIOS boot modes
  - Post-installation: update system, install essential software

#### § 0.3.3 — Desktop Environments (Optional for Servers)
  - **GNOME**: modern, clean, default on Ubuntu and Fedora
  - **KDE Plasma**: feature-rich, customizable, Windows-like
  - **XFCE**: lightweight, fast, traditional
  - **Cinnamon**: traditional desktop (Linux Mint default)
  - **i3/Sway**: tiling window managers (keyboard-driven, advanced users)
  - **Hyprland**: modern Wayland compositor (eye candy + productivity)
  - Servers: no desktop environment (CLI only — saves resources)

> ### 🛠️ Phase 0 Project: **"Linux Lab Setup"**
> Set up THREE Linux environments:
> 1. **Ubuntu Desktop** in a VM — full GUI experience, explore the desktop, file manager, settings
> 2. **Ubuntu Server** on a cloud VPS (DigitalOcean/Linode free tier) — SSH-only, no GUI
> 3. **Arch Linux** in a VM — install from scratch following the Arch Wiki (the ultimate learning experience)
> - Document the entire installation process for each with screenshots
> - Compare: package managers, boot time, memory usage, disk usage
> - SSH from your local machine into the VPS — verify connectivity
> - Write a summary: what's the same across distros, what's different

---

## ⚡ PHASE 1 — THE COMMAND LINE (THE HEART OF LINUX)
> *"The terminal is not a relic of the past. It's the most powerful interface ever designed."*

---

### 📦 Module 1.1: Terminal & Shell Basics

#### § 1.1.1 — The Terminal Emulator
  - Terminal emulator vs shell vs console — different things
  - Terminal emulators: GNOME Terminal, Konsole, Alacritty, Kitty, WezTerm, Windows Terminal (WSL)
  - The prompt: `username@hostname:directory$` — anatomy of the prompt
  - Customizing the prompt: `PS1` variable

#### § 1.1.2 — The Shell
  - **Bash** (Bourne Again Shell): the default on most distributions
  - **Zsh**: more features, better completions (default on macOS)
  - **Fish**: user-friendly, auto-suggestions (not POSIX-compatible)
  - **Dash**: minimal, fast (used for system scripts on Debian/Ubuntu)
  - `echo $SHELL` — check current shell
  - `chsh -s /bin/zsh` — change default shell
  - Shell vs kernel: shell is the user interface TO the kernel

#### § 1.1.3 — Command Structure
  - `command [options] [arguments]`
  - Short options: `-l`, `-a`, `-h` (can combine: `-lah`)
  - Long options: `--long-option`, `--help`, `--version`
  - Arguments: files, directories, strings, patterns
  - Case sensitivity: `file.txt` ≠ `File.txt` (Linux is case-sensitive!)

#### § 1.1.4 — Getting Help
  - `man command` — manual pages (the definitive reference)
  - `man` sections: 1 (commands), 2 (syscalls), 3 (library), 5 (file formats), 8 (admin)
  - `command --help` — quick help
  - `info command` — GNU info pages (more detailed than man for GNU tools)
  - `whatis command` — one-line description
  - `apropos keyword` — search for commands by keyword
  - `type command` — is it a built-in, alias, or external program?
  - `which command` — location of executable
  - `tldr command` — community-maintained simplified man pages

---

### 📦 Module 1.2: Navigation & File Operations

#### § 1.2.1 — The Linux Filesystem Hierarchy
  - `/` — root of everything (NOT like Windows drives)
  - `/home/username/` — user home directories (~)
  - `/root/` — root user's home
  - `/etc/` — system configuration files
  - `/var/` — variable data (logs, caches, databases)
  - `/var/log/` — system logs
  - `/tmp/` — temporary files (cleared on reboot)
  - `/usr/` — user programs and data
  - `/usr/bin/` — user command binaries
  - `/usr/sbin/` — system administration binaries
  - `/usr/local/` — locally installed software
  - `/bin/`, `/sbin/` — essential system binaries (often symlinks to `/usr/bin/`)
  - `/opt/` — optional/third-party software
  - `/dev/` — device files (disks, terminals, null, random)
  - `/proc/` — virtual filesystem for process information
  - `/sys/` — virtual filesystem for kernel/hardware information
  - `/mnt/`, `/media/` — mount points for external filesystems
  - `/boot/` — bootloader files (kernel, initramfs, GRUB)
  - Everything is a file: devices, processes, sockets

#### § 1.2.2 — Navigation Commands
  - `pwd` — print working directory
  - `cd /path/to/dir` — change directory
  - `cd ~` or `cd` — go to home directory
  - `cd -` — go to previous directory
  - `cd ..` — go up one level
  - `cd ../..` — go up two levels
  - Absolute paths (`/home/user/docs`) vs relative paths (`./docs` or `docs`)
  - `.` (current directory), `..` (parent directory), `~` (home directory)

#### § 1.2.3 — Listing & Inspecting
  - `ls` — list directory contents
  - `ls -l` — long format (permissions, owner, size, date)
  - `ls -a` — show hidden files (dotfiles)
  - `ls -lh` — human-readable sizes
  - `ls -ltr` — sort by modification time (oldest first)
  - `ls -R` — recursive listing
  - `ls -la /etc/` — list specific directory
  - `file filename` — determine file type
  - `stat filename` — detailed file metadata (inode, timestamps, blocks)
  - `tree` — directory tree visualization
  - `du -sh directory/` — directory size
  - `df -h` — disk space usage

#### § 1.2.4 — File & Directory Operations
  - `touch file.txt` — create empty file (or update timestamp)
  - `mkdir dirname` — create directory
  - `mkdir -p path/to/nested/dir` — create nested directories
  - `cp source dest` — copy file
  - `cp -r source_dir dest_dir` — copy directory recursively
  - `mv source dest` — move or rename
  - `rm file.txt` — remove file (no trash — GONE forever!)
  - `rm -r directory/` — remove directory recursively
  - `rm -rf directory/` — force remove (DANGEROUS — no confirmation!)
  - `ln -s target linkname` — create symbolic link
  - `ln target linkname` — create hard link
  - Symbolic vs hard links: symlinks are pointers (can break), hard links share inode (can't break)
  - `rmdir dirname` — remove empty directory

#### § 1.2.5 — Globbing & Wildcards
  - `*` — matches any number of characters
  - `?` — matches exactly one character
  - `[abc]` — matches any one of a, b, c
  - `[a-z]` — matches any lowercase letter
  - `[!abc]` or `[^abc]` — matches any character NOT in set
  - `{file1,file2}` — brace expansion
  - `{1..10}` — sequence expansion
  - `**` — recursive globbing (with `globstar` option in Bash)

---

### 📦 Module 1.3: Viewing & Manipulating Text

#### § 1.3.1 — Viewing File Contents
  - `cat file.txt` — display entire file
  - `less file.txt` — paginated viewer (scroll with arrows, search with `/`, quit with `q`)
  - `more file.txt` — older paginated viewer
  - `head -n 20 file.txt` — first 20 lines
  - `tail -n 20 file.txt` — last 20 lines
  - `tail -f logfile` — follow file in real-time (monitoring logs!)
  - `tail -F logfile` — follow file even if rotated
  - `wc file.txt` — word count (lines, words, characters)
  - `wc -l` — line count only

#### § 1.3.2 — Text Processing Commands
  - `grep pattern file` — search for pattern in file
  - `grep -i` — case-insensitive
  - `grep -r pattern directory/` — recursive search
  - `grep -n` — show line numbers
  - `grep -v pattern` — invert match (lines NOT matching)
  - `grep -c` — count matches
  - `grep -l` — show only filenames with matches
  - `grep -E` / `egrep` — extended regex
  - `grep -P` — Perl-compatible regex
  - `sed 's/old/new/g' file` — stream editor (find and replace)
  - `sed -i 's/old/new/g' file` — in-place editing
  - `sed -n '5,10p' file` — print lines 5-10
  - `awk '{print $1, $3}' file` — column-based text processing
  - `awk -F: '{print $1}' /etc/passwd` — specify delimiter
  - `awk '/pattern/ {print}' file` — pattern matching
  - `cut -d: -f1 /etc/passwd` — extract fields by delimiter
  - `sort file` — sort lines alphabetically
  - `sort -n` — numeric sort
  - `sort -r` — reverse sort
  - `sort -k2 -t:` — sort by field 2, delimiter `:`
  - `sort -u` — sort and remove duplicates
  - `uniq` — remove adjacent duplicates (use after `sort`)
  - `uniq -c` — count occurrences
  - `tr 'a-z' 'A-Z'` — translate characters (lowercase → uppercase)
  - `tr -d 'chars'` — delete characters
  - `tee file` — read from stdin, write to stdout AND file simultaneously
  - `diff file1 file2` — compare files line by line
  - `diff -u file1 file2` — unified diff format
  - `comm file1 file2` — compare sorted files (common/unique lines)
  - `paste file1 file2` — merge lines side by side
  - `column -t` — format into aligned columns
  - `rev` — reverse each line
  - `nl` — number lines

---

### 📦 Module 1.4: I/O Redirection & Pipes

#### § 1.4.1 — Standard Streams
  - `stdin` (fd 0) — standard input (keyboard by default)
  - `stdout` (fd 1) — standard output (terminal by default)
  - `stderr` (fd 2) — standard error (terminal by default)
  - Every process has these three streams

#### § 1.4.2 — Output Redirection
  - `command > file` — redirect stdout to file (overwrite)
  - `command >> file` — redirect stdout to file (append)
  - `command 2> file` — redirect stderr to file
  - `command 2>&1` — redirect stderr to stdout
  - `command > file 2>&1` — redirect both to file
  - `command &> file` — redirect both to file (Bash shorthand)
  - `command > /dev/null 2>&1` — discard all output (silence everything)
  - `/dev/null` — the "black hole" — discards everything written to it

#### § 1.4.3 — Input Redirection
  - `command < file` — read stdin from file
  - `command << EOF ... EOF` — here document (inline multiline input)
  - `command <<< "string"` — here string (single line input)

#### § 1.4.4 — Pipes
  - `command1 | command2` — send stdout of command1 to stdin of command2
  - Unlimited chaining: `cmd1 | cmd2 | cmd3 | cmd4`
  - `|&` — pipe both stdout and stderr (Bash 4+)
  - Power of pipes: compose simple commands into complex workflows
  - Examples: `cat access.log | grep "404" | awk '{print $1}' | sort | uniq -c | sort -rn | head`

#### § 1.4.5 — `xargs` — Building Commands from Input
  - `find . -name "*.log" | xargs rm` — delete all log files
  - `xargs -I {} command {}` — placeholder for each input item
  - `xargs -P 4` — parallel execution (4 processes)
  - `xargs -0` — handle null-delimited input (with `find -print0`)

---

### 📦 Module 1.5: Finding Files & Data

#### § 1.5.1 — `find` — The File Finder
  - `find /path -name "*.txt"` — find by name
  - `find . -type f` — find files only
  - `find . -type d` — find directories only
  - `find . -size +10M` — larger than 10MB
  - `find . -mtime -7` — modified in last 7 days
  - `find . -user username` — owned by user
  - `find . -perm 755` — specific permissions
  - `find . -empty` — empty files/directories
  - `find . -name "*.log" -exec rm {} \;` — execute command on each result
  - `find . -name "*.log" -exec rm {} +` — batch execution (more efficient)
  - `find . -name "*.tmp" -delete` — delete found files
  - `find . -maxdepth 2` — limit directory depth

#### § 1.5.2 — Modern Find Alternatives
  - `fd` — simpler, faster alternative to `find` (Rust-based)
  - `locate` / `mlocate` / `plocate` — database-based search (instant, but not real-time)
  - `updatedb` — update the locate database
  - `which command` — find executable location
  - `whereis command` — find binary, source, and man page

#### § 1.5.3 — Modern Grep Alternatives
  - `ripgrep` (`rg`) — extremely fast recursive search (Rust-based, respects .gitignore)
  - `ag` (The Silver Searcher) — fast grep alternative
  - `rg pattern -t py` — search only Python files
  - `rg pattern --json` — structured output

> ### 🛠️ Phase 1 Project: **"Log Analyzer Pipeline"**
> Build a set of command-line pipelines to analyze web server logs:
> - Download or generate a sample Apache/Nginx access log (100K+ lines)
> - **Pipeline 1**: Extract all unique IP addresses, count occurrences, show top 20
> - **Pipeline 2**: Find all 404 errors, extract URLs, count and sort by frequency
> - **Pipeline 3**: Calculate requests per hour, display as a simple bar chart using `printf` and `seq`
> - **Pipeline 4**: Find the largest responses, show corresponding URLs and IPs
> - **Pipeline 5**: Extract all user agents, categorize (browser, bot, mobile), count each
> - **Find task**: Use `find` to locate all log files on the system older than 30 days and larger than 100MB
> - Save each pipeline as a documented script with comments explaining each step
> - Compare performance: `grep` vs `ripgrep` on a large file — document the difference

---

## ⚡ PHASE 2 — USERS, PERMISSIONS & FILE SYSTEM
> *"In Linux, security starts with permissions. Every file has an owner, a group, and a set of permissions."*

---

### 📦 Module 2.1: Users & Groups

#### § 2.1.1 — User Concepts
  - `root` — the superuser (UID 0) — can do ANYTHING (handle with extreme care)
  - Regular users — limited privileges (UIDs typically 1000+)
  - System users — for services/daemons (UIDs typically 1-999)
  - `whoami` — current username
  - `id` — current user's UID, GID, and group memberships
  - `who` / `w` — who is logged in
  - `last` — login history
  - `/etc/passwd` — user database (name, UID, GID, home, shell)
  - `/etc/shadow` — encrypted passwords (root-readable only)

#### § 2.1.2 — User Management
  - `sudo command` — run command as root (requires sudoer privileges)
  - `sudo -i` / `sudo su -` — become root (interactive shell)
  - `useradd username` — create user (low-level)
  - `adduser username` — create user (interactive, Debian/Ubuntu)
  - `usermod -aG groupname username` — add user to group
  - `userdel -r username` — delete user and home directory
  - `passwd username` — change password
  - `/etc/sudoers` — sudo configuration (edit with `visudo` ONLY)
  - `NOPASSWD` directive for passwordless sudo (automation)

#### § 2.1.3 — Group Management
  - Primary group: assigned at user creation
  - Supplementary groups: additional group memberships
  - `groups username` — list user's groups
  - `groupadd groupname` — create group
  - `groupdel groupname` — delete group
  - `/etc/group` — group database
  - `newgrp groupname` — temporarily switch primary group

---

### 📦 Module 2.2: File Permissions

#### § 2.2.1 — Permission Model
  - Three permission categories: **Owner (u)**, **Group (g)**, **Others (o)**
  - Three permission types: **Read (r=4)**, **Write (w=2)**, **Execute (x=1)**
  - `ls -l` output: `-rwxr-xr--` → type + owner + group + others
  - File types: `-` (regular), `d` (directory), `l` (symlink), `c` (character device), `b` (block device), `p` (pipe), `s` (socket)
  - Permissions on directories: `r` = list contents, `w` = create/delete files, `x` = enter directory

#### § 2.2.2 — Changing Permissions
  - Symbolic mode: `chmod u+x file` — add execute for owner
  - `chmod g-w file` — remove write for group
  - `chmod o=r file` — set others to read-only
  - `chmod a+r file` — add read for all
  - Octal mode: `chmod 755 file` — rwxr-xr-x
  - `chmod 644 file` — rw-r--r--
  - `chmod 600 file` — rw------- (private)
  - `chmod -R 755 directory/` — recursive
  - Common patterns: `755` (directories, scripts), `644` (regular files), `600` (secrets), `700` (private directories)

#### § 2.2.3 — Changing Ownership
  - `chown user:group file` — change owner and group
  - `chown user file` — change owner only
  - `chown :group file` — change group only
  - `chown -R user:group directory/` — recursive
  - `chgrp group file` — change group only

#### § 2.2.4 — Special Permissions
  - **SUID (Set User ID)**: `chmod u+s file` — execute as file owner (e.g., `passwd` runs as root)
  - **SGID (Set Group ID)**: `chmod g+s dir` — new files inherit directory's group
  - **Sticky Bit**: `chmod +t dir` — only owner can delete their files (used on `/tmp`)
  - Octal: SUID=4, SGID=2, Sticky=1 (prepended: `chmod 1755`, `chmod 4755`)
  - Security implications: SUID/SGID binaries are privilege escalation risks

#### § 2.2.5 — `umask` — Default Permissions
  - `umask` — display current mask
  - `umask 022` — set default (files: 644, directories: 755)
  - `umask 077` — restrictive default (files: 600, directories: 700)
  - Calculation: default permissions minus umask value
  - Set in `~/.bashrc` or `/etc/profile` for persistence

---

### 📦 Module 2.3: Advanced Permissions — ACLs

#### § 2.3.1 — Access Control Lists
  - Standard permissions are limited (one owner, one group)
  - ACLs allow fine-grained permissions for multiple users and groups
  - `getfacl file` — view ACL
  - `setfacl -m u:username:rwx file` — grant user-specific permissions
  - `setfacl -m g:groupname:rx file` — grant group-specific permissions
  - `setfacl -d -m u:username:rwx directory/` — default ACL for new files
  - `setfacl -x u:username file` — remove ACL entry
  - `setfacl -b file` — remove all ACLs
  - `+` in `ls -l` indicates ACLs are set

---

### 📦 Module 2.4: File System Concepts

#### § 2.4.1 — Filesystem Types
  - **ext4** — the default Linux filesystem (journaling, mature, reliable)
  - **XFS** — high-performance, good for large files (default on RHEL/Rocky)
  - **Btrfs** — modern, copy-on-write, snapshots, compression (default on Fedora/openSUSE)
  - **ZFS** — advanced features, not in mainline kernel (licensing)
  - **tmpfs** — RAM-based filesystem (`/tmp`, `/run`)
  - **vfat/FAT32** — cross-platform (USB drives, EFI partitions)
  - **NTFS** — Windows filesystem (read/write support via `ntfs-3g`)
  - **NFS** — Network File System (sharing over network)

#### § 2.4.2 — Disks, Partitions & Mounting
  - Block devices: `/dev/sda` (SATA), `/dev/nvme0n1` (NVMe), `/dev/vda` (virtual)
  - Partitions: `/dev/sda1`, `/dev/sda2`
  - `lsblk` — list block devices and partitions
  - `fdisk -l` — detailed partition information
  - `parted` — advanced partition management
  - `mount /dev/sda1 /mnt/data` — mount a filesystem
  - `umount /mnt/data` — unmount
  - `/etc/fstab` — permanent mount configuration (filesystem table)
  - `blkid` — show filesystem UUIDs and types
  - Mount by UUID: more reliable than device names (device names can change)

#### § 2.4.3 — Filesystem Operations
  - `mkfs.ext4 /dev/sda1` — create ext4 filesystem
  - `mkfs.xfs /dev/sda1` — create XFS filesystem
  - `fsck /dev/sda1` — filesystem check and repair (unmount first!)
  - `resize2fs` — resize ext4 filesystem
  - `xfs_growfs` — grow XFS filesystem
  - `tune2fs -l /dev/sda1` — ext4 filesystem info

#### § 2.4.4 — LVM (Logical Volume Manager)
  - Physical Volumes (PV) → Volume Groups (VG) → Logical Volumes (LV)
  - `pvcreate`, `vgcreate`, `lvcreate` — create LVM components
  - `lvextend`, `lvreduce` — resize volumes
  - `lvs`, `vgs`, `pvs` — display information
  - Advantages: easy resizing, snapshots, spanning multiple disks

#### § 2.4.5 — Inodes & Links
  - Inodes: metadata structure for every file (permissions, timestamps, block pointers)
  - `ls -i` — show inode numbers
  - `df -i` — inode usage (can run out of inodes before disk space!)
  - Hard links: multiple directory entries pointing to same inode
  - Symbolic links: file pointing to another path (can break)

> ### 🛠️ Phase 2 Project: **"Multi-User Development Server"**
> Configure a development server with proper user management:
> - Create 5 users: 2 developers, 2 designers, 1 admin
> - Create groups: `developers`, `designers`, `admins`, `project-alpha`
> - Create a shared project directory `/srv/projects/alpha/`
>   - Developers: read/write, Designers: read-only, Admins: full access
>   - SGID set so all new files belong to `project-alpha` group
>   - Sticky bit on shared directories so users can't delete each other's files
> - Create private home directories (700 permissions)
> - Configure ACLs for a shared tools directory where one specific user gets special access
> - Set appropriate `umask` for each group in their profile
> - Create an LVM setup: physical volume → volume group → two logical volumes (data + backup)
> - Format and mount the logical volumes, add to `/etc/fstab`
> - Document the complete permission scheme in a README

---

## ⚡ PHASE 3 — TEXT EDITORS & SHELL SCRIPTING
> *"If the CLI is the heart of Linux, shell scripting is its soul."*

---

### 📦 Module 3.1: Text Editors

#### § 3.1.1 — Nano (Beginner-Friendly)
  - `nano file.txt` — open file
  - On-screen keyboard shortcuts: `^O` (save), `^X` (exit), `^K` (cut), `^U` (paste)
  - Search: `^W`, Replace: `^\`
  - Good for quick edits, not for heavy work

#### § 3.1.2 — Vim (The Power Editor)
  - Modal editing: **Normal**, **Insert**, **Visual**, **Command** modes
  - Normal mode: navigation and commands (default mode)
  - Insert mode: `i`, `a`, `o`, `A` — actually typing text
  - Visual mode: `v` (character), `V` (line), `Ctrl+v` (block) — selection
  - Command mode: `:` — ex commands
  - Essential commands: `:w` (save), `:q` (quit), `:wq` (save+quit), `:q!` (force quit)
  - Navigation: `h/j/k/l`, `w/b` (word), `0/$` (line start/end), `gg/G` (file start/end)
  - Editing: `dd` (delete line), `yy` (yank/copy line), `p` (paste), `u` (undo), `Ctrl+r` (redo)
  - Search: `/pattern`, `n` (next), `N` (previous)
  - Replace: `:%s/old/new/g` (global), `:%s/old/new/gc` (with confirmation)
  - `vimtutor` — built-in tutorial (30 minutes, do it!)
  - Why Vim: available on every Linux system, extremely efficient once mastered, highly configurable

#### § 3.1.3 — Neovim (Modern Vim)
  - Drop-in Vim replacement with better defaults
  - Lua-based configuration and plugin system
  - Built-in LSP client, Tree-sitter for syntax highlighting
  - Plugin managers: `lazy.nvim`
  - Popular distributions: LazyVim, NvChad, AstroNvim, kickstart.nvim

---

### 📦 Module 3.2: Bash Scripting Fundamentals

#### § 3.2.1 — Script Basics
  - Shebang line: `#!/bin/bash` — first line of every script
  - Making scripts executable: `chmod +x script.sh`
  - Running: `./script.sh` or `bash script.sh`
  - Comments: `# this is a comment`
  - `set -euo pipefail` — strict mode (exit on error, unset vars, pipe failures)
  - `set -x` — debug mode (print each command before execution)

#### § 3.2.2 — Variables
  - Assignment: `name="Alice"` (NO spaces around `=`!)
  - Usage: `$name` or `${name}` (braces for disambiguation)
  - Quoting: `"$var"` (preserves spaces, expands vars), `'$var'` (literal, no expansion)
  - Command substitution: `$(command)` — capture command output
  - Arithmetic: `$((a + b))` — integer arithmetic
  - Default values: `${var:-default}` — use default if unset
  - String operations: `${#var}` (length), `${var:0:5}` (substring), `${var/old/new}` (replace)
  - Environment variables: `export VAR=value` — make available to child processes
  - Special variables: `$0` (script name), `$1-$9` (arguments), `$#` (arg count), `$@` (all args), `$?` (exit code), `$$` (PID)

#### § 3.2.3 — Conditionals
  - `if [ condition ]; then ... elif ... else ... fi`
  - `[[ condition ]]` — extended test (Bash-specific, supports regex, safer)
  - String tests: `=`, `!=`, `-z` (empty), `-n` (not empty)
  - Numeric tests: `-eq`, `-ne`, `-lt`, `-gt`, `-le`, `-ge`
  - File tests: `-f` (file exists), `-d` (directory), `-e` (exists), `-r` (readable), `-w` (writable), `-x` (executable), `-s` (non-empty)
  - Logical: `&&` (AND), `||` (OR), `!` (NOT)
  - `case $var in pattern1) ... ;; pattern2) ... ;; *) default ;; esac`

#### § 3.2.4 — Loops
  - `for item in list; do ... done`
  - `for file in *.txt; do ... done` — iterate over files
  - `for i in {1..10}; do ... done` — range
  - `for ((i=0; i<10; i++)); do ... done` — C-style
  - `while [ condition ]; do ... done`
  - `while read -r line; do ... done < file` — read file line by line
  - `until [ condition ]; do ... done`
  - `break`, `continue` — loop control

#### § 3.2.5 — Functions
  - `function_name() { ... }` — define function
  - Arguments: `$1`, `$2`, etc. inside function
  - Return value: `return 0` (exit code), `echo "result"` (output capture)
  - Local variables: `local var=value`
  - Call: `function_name arg1 arg2`

#### § 3.2.6 — Arrays
  - Declaration: `arr=(one two three)`
  - Access: `${arr[0]}`, `${arr[1]}`
  - All elements: `${arr[@]}`
  - Length: `${#arr[@]}`
  - Append: `arr+=(four)`
  - Associative arrays (Bash 4+): `declare -A dict; dict[key]=value`

---

### 📦 Module 3.3: Advanced Shell Scripting

#### § 3.3.1 — Input/Output & Interaction
  - `read -p "Enter name: " name` — prompt user for input
  - `read -s` — silent input (passwords)
  - `read -t 10` — timeout after 10 seconds
  - `select choice in options; do ... done` — menu selection
  - Here documents for multi-line strings
  - `echo`, `printf` — output formatting

#### § 3.3.2 — Error Handling
  - Exit codes: `0` = success, non-zero = failure
  - `$?` — last command's exit code
  - `set -e` — exit on first error
  - `trap 'cleanup' EXIT` — run cleanup function on exit
  - `trap 'echo "Error on line $LINENO"' ERR` — error handler
  - `|| true` — suppress error for specific command
  - Validation: checking arguments, files, permissions before proceeding

#### § 3.3.3 — Process Substitution & Advanced Features
  - `<(command)` — process substitution (treat command output as a file)
  - `diff <(cmd1) <(cmd2)` — compare outputs of two commands
  - `command1 && command2` — run second only if first succeeds
  - `command1 || command2` — run second only if first fails
  - `{ cmd1; cmd2; }` — command grouping (same shell)
  - `(cmd1; cmd2)` — subshell (separate environment)
  - `eval "string"` — execute string as command (use cautiously!)

#### § 3.3.4 — Regular Expressions in Bash
  - Basic regex: `.` (any char), `*` (zero or more), `^` (start), `$` (end)
  - Extended regex (ERE): `+` (one or more), `?` (optional), `|` (alternation), `()` (grouping)
  - Character classes: `[0-9]`, `[a-zA-Z]`, `[[:digit:]]`, `[[:alpha:]]`, `[[:space:]]`
  - `[[ $string =~ regex ]]` — Bash regex matching
  - `BASH_REMATCH` — captured groups from regex match
  - `grep -E`, `sed -E`, `awk` — tools using regex

#### § 3.3.5 — Script Best Practices
  - Always use `set -euo pipefail` (strict mode)
  - Always quote variables: `"$var"` not `$var`
  - Use `[[ ]]` instead of `[ ]` in Bash
  - Use `$(command)` instead of backticks
  - ShellCheck: the essential shell script linter (`shellcheck script.sh`)
  - Meaningful exit codes: use different codes for different errors
  - Logging: write to stderr for diagnostics, stdout for data
  - Documentation: header comment with description, usage, dependencies

> ### 🛠️ Phase 3 Project: **"SysAdmin Toolkit — A Shell Script Suite"**
> Build a collection of production-quality shell scripts:
> - **System health check**: CPU usage, memory usage, disk usage, load average, top processes — output as formatted report, alert if thresholds exceeded
> - **User audit**: list all users, their groups, login status, shell, home directory size — export as CSV
> - **Backup script**: backup specified directories to compressed tarball with timestamp, rotate old backups (keep last 7), log all operations, email notification on failure
> - **Log rotator**: compress logs older than N days, delete logs older than M days, maintain metadata
> - **Service monitor**: check if a list of services are running, restart if down, send notification, log events
> - All scripts: use `set -euo pipefail`, pass ShellCheck, include usage/help text, accept command-line arguments, have proper error handling with `trap`

---

## ⚡ PHASE 4 — PROCESS MANAGEMENT & SYSTEM MONITORING
> *"Understanding processes is understanding how Linux works."*

---

### 📦 Module 4.1: Process Fundamentals

#### § 4.1.1 — What is a Process
  - A running instance of a program
  - Every process has: PID (Process ID), PPID (Parent PID), UID/GID, state, priority
  - PID 1: `init` / `systemd` — the first process, parent of all others
  - Process tree: every process has a parent (except PID 1)
  - `pstree` — visualize process tree

#### § 4.1.2 — Viewing Processes
  - `ps` — snapshot of current processes
  - `ps aux` — all processes, all users, full format
  - `ps -ef` — every process, full format (POSIX style)
  - `ps aux --sort=-%mem` — sort by memory usage (descending)
  - `ps -p PID` — info about specific process
  - `top` — real-time process viewer (interactive)
  - `htop` — better `top` (colored, mouse support, tree view)
  - `btop` — modern, beautiful system monitor
  - `pgrep process_name` — find PID by name
  - `pidof process_name` — get PID

#### § 4.1.3 — Process States
  - **Running (R)** — executing on CPU or ready to execute
  - **Sleeping (S)** — waiting for an event (interruptible)
  - **Uninterruptible Sleep (D)** — waiting for I/O (cannot be killed)
  - **Stopped (T)** — paused (Ctrl+Z or signal)
  - **Zombie (Z)** — terminated but parent hasn't read exit status
  - **Dead (X)** — final state before removal

---

### 📦 Module 4.2: Process Control

#### § 4.2.1 — Job Control
  - `command &` — run in background
  - `Ctrl+Z` — suspend foreground process
  - `Ctrl+C` — interrupt (kill) foreground process
  - `jobs` — list background/suspended jobs
  - `fg %n` — bring job n to foreground
  - `bg %n` — resume job n in background
  - `disown %n` — detach job from shell (survives shell exit)

#### § 4.2.2 — Signals
  - `kill PID` — send SIGTERM (graceful termination, signal 15)
  - `kill -9 PID` — send SIGKILL (forced termination, cannot be caught)
  - `kill -HUP PID` — send SIGHUP (hangup, often used for config reload)
  - `kill -STOP PID` — pause process
  - `kill -CONT PID` — resume paused process
  - `killall process_name` — kill all processes by name
  - `pkill pattern` — kill by pattern matching
  - Common signals: SIGTERM (15), SIGKILL (9), SIGHUP (1), SIGINT (2, Ctrl+C), SIGSTOP (19), SIGCONT (18)
  - `trap` in scripts: handle signals gracefully

#### § 4.2.3 — Process Priority
  - Nice values: -20 (highest priority) to 19 (lowest priority)
  - `nice -n 10 command` — start with lower priority
  - `renice -n 5 -p PID` — change running process priority
  - Only root can set negative nice values (increase priority)

#### § 4.2.4 — Long-Running Processes
  - `nohup command &` — immune to hangup signal (survives logout)
  - `screen` — terminal multiplexer (detach/reattach sessions)
  - `tmux` — modern terminal multiplexer (preferred over screen)
  - `tmux` essentials: new session, detach (`Ctrl+b d`), reattach (`tmux attach`), windows, panes
  - `systemd` services — the proper way to run daemons (covered in Phase 5)

---

### 📦 Module 4.3: System Monitoring

#### § 4.3.1 — CPU & Memory
  - `uptime` — load average (1min, 5min, 15min)
  - `free -h` — memory usage (total, used, free, available, buffers/cache)
  - `vmstat 1` — virtual memory statistics (updated every second)
  - `mpstat -P ALL 1` — per-CPU statistics
  - `/proc/cpuinfo` — CPU details
  - `/proc/meminfo` — detailed memory info
  - Load average: 1.0 per CPU core = fully loaded
  - Buffers vs cache: Linux uses free RAM for disk caching (this is GOOD, not wasted)

#### § 4.3.2 — Disk I/O
  - `iostat -xz 1` — disk I/O statistics
  - `iotop` — disk I/O by process (like `top` for disk)
  - `df -h` — disk space usage by filesystem
  - `du -sh *` — disk usage by directory
  - `du -sh * | sort -rh | head` — largest directories
  - `ncdu` — interactive disk usage analyzer (excellent TUI)

#### § 4.3.3 — Network Monitoring
  - `ss -tuln` — listening ports (replacement for `netstat`)
  - `ss -tp` — established connections with process info
  - `netstat -tuln` — legacy but still common
  - `iftop` — real-time network bandwidth by connection
  - `nload` — real-time network bandwidth per interface
  - `nethogs` — bandwidth usage per process
  - `sar -n DEV 1` — network interface statistics

#### § 4.3.4 — System Logs
  - `journalctl` — systemd journal viewer
  - `journalctl -u service_name` — logs for specific service
  - `journalctl -f` — follow logs in real-time
  - `journalctl --since "1 hour ago"` — time-based filtering
  - `journalctl -p err` — filter by priority (emerg, alert, crit, err, warning, notice, info, debug)
  - `/var/log/` — traditional log directory
  - `/var/log/syslog` (Debian/Ubuntu) or `/var/log/messages` (RHEL)
  - `/var/log/auth.log` — authentication logs
  - `dmesg` — kernel ring buffer (hardware, driver messages)
  - `dmesg -T` — with human-readable timestamps

#### § 4.3.5 — Performance Analysis Tools
  - `sar` — system activity reporter (historical data)
  - `perf` — Linux profiling framework
  - `strace command` — trace system calls (debugging)
  - `ltrace command` — trace library calls
  - `lsof` — list open files (every file, socket, device)
  - `lsof -i :80` — who's using port 80?
  - `lsof +D /path` — who's using files in directory?

> ### 🛠️ Phase 4 Project: **"SysWatch — A Real-Time System Monitor Dashboard"**
> Build a comprehensive monitoring script:
> - Real-time dashboard using `tput` for terminal positioning and colors
> - Display: CPU usage per core, memory usage (with buffer/cache breakdown), swap usage, load average
> - Top 10 processes by CPU and memory
> - Disk usage for all mounted filesystems with color-coded thresholds (green/yellow/red)
> - Network bandwidth (in/out) for all active interfaces
> - Active connections count and top talkers
> - Recent authentication events (last 10 logins, failed attempts)
> - Alert system: log warnings when any metric exceeds threshold
> - Refresh every N seconds (configurable)
> - Output to both terminal AND a log file simultaneously
> - Background daemon mode with `nohup` support
> - Run in a `tmux` session for persistence

---

## ⚡ PHASE 5 — SERVICE MANAGEMENT & SYSTEMD
> *"systemd is the init system of modern Linux. Love it or hate it, you must understand it."*

---

### 📦 Module 5.1: systemd Fundamentals

#### § 5.1.1 — What is systemd
  - Init system: PID 1, starts and manages all other processes
  - Replaced SysVinit and Upstart on most distributions
  - Not just init: manages services, logging, networking, timers, mounts, and more
  - Unit files: configuration for everything systemd manages
  - Controversial: does many things (violates Unix philosophy), but powerful and ubiquitous

#### § 5.1.2 — Unit Types
  - `.service` — daemons and services (most common)
  - `.socket` — socket activation
  - `.timer` — scheduled tasks (replaces cron for systemd)
  - `.mount` / `.automount` — filesystem mounting
  - `.target` — grouping unit (like runlevels)
  - `.path` — path-based activation
  - `.device` — hardware device management
  - `.scope` / `.slice` — resource management

#### § 5.1.3 — Service Management Commands
  - `systemctl start service_name` — start service
  - `systemctl stop service_name` — stop service
  - `systemctl restart service_name` — restart service
  - `systemctl reload service_name` — reload configuration without restart
  - `systemctl status service_name` — view status, recent logs, PID
  - `systemctl enable service_name` — start on boot
  - `systemctl disable service_name` — don't start on boot
  - `systemctl is-active service_name` — check if running
  - `systemctl is-enabled service_name` — check if enabled on boot
  - `systemctl list-units --type=service` — list all services
  - `systemctl list-units --type=service --state=running` — running services only
  - `systemctl list-unit-files --type=service` — all installed service files
  - `systemctl daemon-reload` — reload unit files after changes

---

### 📦 Module 5.2: Writing Service Files

#### § 5.2.1 — Unit File Structure
  - Location: `/etc/systemd/system/` (custom), `/usr/lib/systemd/system/` (package-installed)
  - Three sections: `[Unit]`, `[Service]`, `[Install]`
  - `[Unit]`: Description, Documentation, After, Requires, Wants
  - `[Service]`: Type, ExecStart, ExecReload, ExecStop, Restart, User, Group, WorkingDirectory, Environment
  - `[Install]`: WantedBy (target to enable under)

#### § 5.2.2 — Service Types
  - `Type=simple` — main process is the ExecStart process (default)
  - `Type=forking` — process forks and parent exits (traditional daemons)
  - `Type=oneshot` — for scripts that run and exit
  - `Type=notify` — service notifies systemd when ready
  - `Type=idle` — wait until all other jobs finish

#### § 5.2.3 — Restart Policies
  - `Restart=always` — restart on any exit
  - `Restart=on-failure` — restart only on non-zero exit
  - `Restart=on-abnormal` — restart on crash/signal
  - `RestartSec=5` — wait 5 seconds before restarting
  - `StartLimitBurst`, `StartLimitIntervalSec` — rate limiting restarts

#### § 5.2.4 — Security Hardening
  - `User=`, `Group=` — run as non-root user
  - `ProtectSystem=strict` — read-only filesystem
  - `ProtectHome=true` — no access to home directories
  - `NoNewPrivileges=true` — prevent privilege escalation
  - `PrivateTmp=true` — private /tmp
  - `ReadOnlyPaths=`, `ReadWritePaths=` — filesystem restrictions
  - `CapabilityBoundingSet=` — limit Linux capabilities
  - `systemd-analyze security service_name` — audit security settings

---

### 📦 Module 5.3: Timers & Scheduled Tasks

#### § 5.3.1 — systemd Timers
  - Replacement for `cron` (more powerful, integrated with journald)
  - Timer unit (`.timer`) + service unit (`.service`) — paired
  - `OnCalendar=daily` — calendar-based scheduling
  - `OnCalendar=*-*-* 03:00:00` — every day at 3 AM
  - `OnBootSec=5min` — 5 minutes after boot
  - `OnUnitActiveSec=1h` — every hour after last activation
  - `Persistent=true` — run missed events after downtime
  - `systemctl list-timers` — list all active timers

#### § 5.3.2 — Cron (Traditional Scheduling)
  - `crontab -e` — edit user's cron jobs
  - `crontab -l` — list cron jobs
  - Format: `minute hour day_of_month month day_of_week command`
  - `0 3 * * * /path/to/script.sh` — daily at 3 AM
  - `*/5 * * * *` — every 5 minutes
  - `@reboot command` — run at startup
  - `/etc/cron.d/`, `/etc/cron.daily/`, `/etc/cron.hourly/` — system-wide cron
  - Cron vs systemd timers: timers have better logging, dependencies, and randomized delay

---

### 📦 Module 5.4: Boot Process

#### § 5.4.1 — Linux Boot Sequence
  - **BIOS/UEFI** — hardware initialization, find bootloader
  - **GRUB** (Grand Unified Bootloader) — load kernel + initramfs
  - **Kernel** — hardware detection, mount root filesystem
  - **initramfs** — temporary root filesystem for early boot
  - **systemd (PID 1)** — start services, reach target
  - **Login** — display manager (GUI) or `getty` (TTY)

#### § 5.4.2 — systemd Targets (Runlevels)
  - `multi-user.target` — text mode, networking, services (like runlevel 3)
  - `graphical.target` — GUI desktop (like runlevel 5)
  - `rescue.target` — single-user mode (like runlevel 1)
  - `emergency.target` — minimal shell (root only)
  - `systemctl get-default` — current default target
  - `systemctl set-default multi-user.target` — boot to CLI
  - `systemctl isolate rescue.target` — switch to rescue mode (now)

#### § 5.4.3 — GRUB Configuration
  - `/etc/default/grub` — GRUB settings
  - `update-grub` (Debian) / `grub2-mkconfig` (RHEL) — regenerate configuration
  - Kernel parameters: `quiet`, `splash`, `nomodeset`, `single` (rescue)
  - Editing boot parameters at GRUB menu for troubleshooting

#### § 5.4.4 — Boot Diagnostics
  - `systemd-analyze` — boot time analysis
  - `systemd-analyze blame` — slowest services during boot
  - `systemd-analyze critical-chain` — critical path in boot
  - `systemd-analyze plot > boot.svg` — visual boot timeline

> ### 🛠️ Phase 5 Project: **"Custom Service Deployment"**
> Deploy and manage a custom application as a systemd service:
> - Write a simple web application (Python Flask or Node.js) or use a pre-built one
> - Create a systemd service unit file:
>   - Run as a dedicated non-root user
>   - Automatic restart on failure with rate limiting
>   - Environment variables from an environment file
>   - Security hardening (ProtectSystem, NoNewPrivileges, PrivateTmp)
>   - Proper logging to journal
> - Create a systemd timer for a scheduled maintenance task (database cleanup, log rotation)
> - Set up socket activation for the web service
> - Test: `systemctl start/stop/restart/status`, verify logs with `journalctl`
> - Simulate failures: kill the process, verify auto-restart
> - Audit security: `systemd-analyze security your_service`
> - Document the entire setup process and configuration choices

---

## ⚡ PHASE 6 — NETWORKING
> *"Linux is the backbone of the internet. Understanding Linux networking is understanding the internet."*

---

### 📦 Module 6.1: Network Configuration

#### § 6.1.1 — Network Interfaces
  - `ip addr` / `ip a` — show all interfaces and IP addresses (modern)
  - `ip link` — show interface status (up/down)
  - `ifconfig` — legacy but still common (replaced by `ip`)
  - Interface naming: `eth0` (legacy), `enp0s3` (predictable naming), `wlan0` (wireless)
  - Loopback: `lo` — `127.0.0.1` (localhost)
  - `ip addr add 192.168.1.100/24 dev eth0` — add IP address
  - `ip link set eth0 up/down` — enable/disable interface

#### § 6.1.2 — Network Configuration Methods
  - **NetworkManager**: GUI and CLI (`nmcli`, `nmtui`) — default on desktops and many servers
  - **systemd-networkd**: lightweight, server-focused
  - **Netplan** (Ubuntu): YAML-based network configuration
  - `/etc/network/interfaces` — Debian legacy configuration
  - `/etc/sysconfig/network-scripts/` — RHEL legacy configuration
  - `nmcli con show` — list connections
  - `nmcli con mod "connection" ipv4.addresses 192.168.1.100/24` — set static IP
  - `nmtui` — text-based UI for NetworkManager

#### § 6.1.3 — Routing
  - `ip route` / `ip r` — show routing table
  - `ip route add 10.0.0.0/8 via 192.168.1.1` — add route
  - `ip route add default via 192.168.1.1` — set default gateway
  - `/etc/resolv.conf` — DNS resolver configuration
  - `/etc/hosts` — static hostname resolution (before DNS)
  - `hostname` — show/set system hostname
  - `hostnamectl set-hostname myserver` — set hostname permanently

---

### 📦 Module 6.2: Network Diagnostics

#### § 6.2.1 — Connectivity Testing
  - `ping host` — ICMP echo request (test reachability)
  - `ping -c 4 host` — send 4 pings only
  - `traceroute host` / `tracepath host` — trace route to destination
  - `mtr host` — combined ping + traceroute (real-time)
  - `curl -I https://example.com` — HTTP headers
  - `curl -v https://example.com` — verbose HTTP request
  - `wget https://example.com/file` — download file

#### § 6.2.2 — DNS Diagnostics
  - `dig domain.com` — DNS query (detailed)
  - `dig domain.com A` — query specific record type
  - `dig +short domain.com` — concise output
  - `dig @8.8.8.8 domain.com` — query specific DNS server
  - `nslookup domain.com` — older DNS lookup tool
  - `host domain.com` — simple DNS lookup
  - `resolvectl status` — systemd-resolved status

#### § 6.2.3 — Port & Connection Analysis
  - `ss -tuln` — listening TCP/UDP ports
  - `ss -tp` — established TCP connections with processes
  - `ss -s` — socket statistics summary
  - `netstat -tuln` — legacy (still widely used)
  - `nmap host` — port scanner (external scanning)
  - `nmap -sV host` — detect service versions
  - `nc -zv host port` — test specific port (netcat)
  - `nc -l 8080` — listen on port (simple server)
  - `tcpdump` — packet capture on the command line
  - `tcpdump -i eth0 port 80` — capture HTTP traffic
  - `tcpdump -w capture.pcap` — save capture to file
  - `tshark` — command-line Wireshark

---

### 📦 Module 6.3: Firewall

#### § 6.3.1 — iptables (Legacy but Fundamental)
  - Chains: INPUT, OUTPUT, FORWARD
  - Tables: filter (default), nat, mangle
  - `iptables -L -n -v` — list rules
  - `iptables -A INPUT -p tcp --dport 22 -j ACCEPT` — allow SSH
  - `iptables -A INPUT -j DROP` — drop all other input
  - Understanding: default policy, chain processing, rule order matters

#### § 6.3.2 — nftables (Modern Replacement)
  - Successor to iptables (unified framework)
  - `nft list ruleset` — show all rules
  - `nft add rule inet filter input tcp dport 22 accept`
  - More expressive syntax, better performance
  - Preferred on newer distributions

#### § 6.3.3 — `firewalld` (RHEL/Fedora)
  - `firewall-cmd --state` — check status
  - `firewall-cmd --list-all` — show current rules
  - `firewall-cmd --add-service=http --permanent` — allow HTTP
  - `firewall-cmd --add-port=8080/tcp --permanent` — allow specific port
  - `firewall-cmd --reload` — apply changes
  - Zones: public, internal, dmz, trusted

#### § 6.3.4 — `ufw` (Ubuntu)
  - `ufw enable` — enable firewall
  - `ufw allow 22/tcp` — allow SSH
  - `ufw allow from 192.168.1.0/24` — allow subnet
  - `ufw deny 80/tcp` — deny HTTP
  - `ufw status verbose` — show rules
  - Simple frontend for iptables

---

### 📦 Module 6.4: SSH (Secure Shell)

#### § 6.4.1 — SSH Client
  - `ssh user@host` — connect to remote server
  - `ssh -p 2222 user@host` — non-standard port
  - `ssh -i ~/.ssh/key.pem user@host` — specific key
  - `ssh -L 8080:localhost:80 user@host` — local port forwarding (tunnel)
  - `ssh -R 8080:localhost:80 user@host` — remote port forwarding
  - `ssh -D 1080 user@host` — SOCKS proxy (dynamic forwarding)
  - `ssh -J jumphost user@destination` — jump/bastion host
  - `~/.ssh/config` — SSH client configuration file (aliases, default options)

#### § 6.4.2 — SSH Keys
  - `ssh-keygen -t ed25519 -C "comment"` — generate key pair (Ed25519, preferred)
  - `ssh-keygen -t rsa -b 4096` — RSA key (wider compatibility)
  - `ssh-copy-id user@host` — copy public key to server
  - `~/.ssh/authorized_keys` — server-side authorized keys
  - Key-based authentication: more secure than passwords, required for automation
  - `ssh-agent` — key management agent
  - Passphrase-protected keys: add a passphrase for extra security

#### § 6.4.3 — SSH Server Configuration
  - `/etc/ssh/sshd_config` — server configuration
  - `PermitRootLogin no` — disable root login (critical!)
  - `PasswordAuthentication no` — force key-based auth (after setting up keys)
  - `Port 2222` — change default port (security through obscurity, minimal benefit)
  - `AllowUsers user1 user2` — restrict who can SSH
  - `MaxAuthTries 3` — limit authentication attempts
  - `systemctl restart sshd` — apply changes

#### § 6.4.4 — File Transfer
  - `scp source user@host:destination` — secure copy (legacy, use `rsync` or `sftp`)
  - `rsync -avz source/ user@host:destination/` — efficient file sync (only transfers differences)
  - `rsync -avz --delete source/ dest/` — mirror (delete extra files at dest)
  - `sftp user@host` — interactive file transfer
  - `rsync` is THE tool for backups, deployments, and file synchronization

> ### 🛠️ Phase 6 Project: **"Secure Network Infrastructure"**
> Set up a complete network infrastructure:
> - **VPS setup**: configure static IP, hostname, DNS resolution
> - **SSH hardening**: key-only auth, disable root login, change port, set up `~/.ssh/config` with aliases
> - **Firewall**: configure `ufw` or `firewalld`:
>   - Allow SSH from specific IPs only
>   - Allow HTTP/HTTPS from anywhere
>   - Block everything else
>   - Rate limit SSH connections
> - **SSH tunneling**: set up local port forward to access a remote database securely
> - **Jump host**: configure SSH jump through a bastion server to reach a private network
> - **Monitoring**: set up a script that checks open ports, logs connection attempts, alerts on suspicious activity
> - **Backup**: use `rsync` over SSH to backup the server to a second machine with incremental backups
> - **DNS**: configure `/etc/hosts` and DNS resolution, test with `dig`
> - Document the entire network architecture with a diagram

---

## ⚡ PHASE 7 — PACKAGE MANAGEMENT & SOFTWARE INSTALLATION
> *"Package managers are Linux's greatest advantage over Windows. No more downloading installers from random websites."*

---

### 📦 Module 7.1: Package Management Systems

#### § 7.1.1 — Debian/Ubuntu (APT)
  - `apt update` — refresh package lists (ALWAYS do first)
  - `apt upgrade` — upgrade all installed packages
  - `apt full-upgrade` — upgrade with dependency changes
  - `apt install package` — install package
  - `apt remove package` — remove package (keep config)
  - `apt purge package` — remove package AND config
  - `apt autoremove` — remove unneeded dependencies
  - `apt search keyword` — search for packages
  - `apt show package` — package details
  - `apt list --installed` — list installed packages
  - `dpkg -i package.deb` — install local `.deb` file
  - `dpkg -l` — list all installed packages
  - `/etc/apt/sources.list` — repository configuration
  - PPAs (Personal Package Archives): `add-apt-repository ppa:name`

#### § 7.1.2 — RHEL/Fedora (DNF)
  - `dnf update` / `dnf upgrade` — update all packages
  - `dnf install package` — install
  - `dnf remove package` — remove
  - `dnf search keyword` — search
  - `dnf info package` — package details
  - `dnf list installed` — list installed
  - `dnf groupinstall "Development Tools"` — install package group
  - `rpm -ivh package.rpm` — install local `.rpm` file
  - `rpm -qa` — list all installed RPM packages
  - `/etc/yum.repos.d/` — repository configuration

#### § 7.1.3 — Arch (Pacman)
  - `pacman -Syu` — full system upgrade
  - `pacman -S package` — install
  - `pacman -R package` — remove
  - `pacman -Ss keyword` — search
  - `pacman -Qi package` — query installed package info
  - `pacman -Ql package` — list files owned by package
  - AUR (Arch User Repository): `yay` or `paru` helpers

---

### 📦 Module 7.2: Alternative Installation Methods

#### § 7.2.1 — Universal Package Formats
  - **Snap** (Canonical): `snap install package` — sandboxed, auto-updating
  - **Flatpak** (Red Hat): `flatpak install flathub package` — sandboxed desktop apps
  - **AppImage**: self-contained executable, no installation
  - Pros: cross-distro compatibility, sandboxing
  - Cons: larger size, slower startup, less system integration

#### § 7.2.2 — Compiling from Source
  - Download source code (tarball or git clone)
  - `./configure` — check dependencies and configure
  - `make` — compile
  - `sudo make install` — install (usually to `/usr/local/`)
  - `checkinstall` — create a `.deb`/`.rpm` from `make install` (proper tracking)
  - Build dependencies: `apt install build-essential` (Debian) / `dnf groupinstall "Development Tools"` (RHEL)
  - When to compile from source: latest version not in repos, custom configuration, patches

#### § 7.2.3 — Language-Specific Package Managers
  - Python: `pip`, `pipx` (for CLI tools), `uv`
  - Node.js: `npm`, `pnpm`, `yarn`
  - Rust: `cargo install`
  - Go: `go install`
  - These install to user space — don't conflict with system packages

---

### 📦 Module 7.3: Repository Management

#### § 7.3.1 — Adding Third-Party Repositories
  - GPG key verification: always verify repository authenticity
  - Debian: add `.list` file or use `add-apt-repository`
  - RHEL: add `.repo` file to `/etc/yum.repos.d/`
  - Security: only add trusted repositories
  - Pinning: prioritize package versions from specific repos

#### § 7.3.2 — Automatic Updates
  - `unattended-upgrades` (Debian/Ubuntu) — automatic security updates
  - `dnf-automatic` (RHEL/Fedora) — automatic updates
  - Configure: security-only vs all updates, auto-reboot, notification

> ### 🛠️ Phase 7 Project: **"Development Environment Automation"**
> Create a script that fully provisions a development server:
> - Accept a distro flag (`--ubuntu` or `--fedora`) and adjust package manager commands
> - Install: Git, Docker, Nginx, PostgreSQL, Redis, Python 3, Node.js, Go, Rust
> - Configure each service with sensible defaults
> - Add third-party repositories where needed (Docker, Node.js)
> - Set up automatic security updates
> - Compile one tool from source (e.g., Neovim nightly)
> - Install CLI tools via `cargo install` and `pipx`
> - Verify all installations and print a summary report
> - Make the script idempotent (running twice doesn't break anything)

---

## ⚡ PHASE 8 — WEB SERVERS, DATABASES & APPLICATION DEPLOYMENT
> *"This is where Linux becomes a production platform."*

---

### 📦 Module 8.1: Web Servers

#### § 8.1.1 — Nginx
  - Installation, starting, enabling
  - Configuration: `/etc/nginx/nginx.conf`, `/etc/nginx/sites-available/`, `/etc/nginx/sites-enabled/`
  - Server blocks (virtual hosts): serving multiple domains
  - Static file serving: `root` directive, `index` directive
  - Reverse proxy: `proxy_pass http://localhost:3000;`
  - Load balancing: upstream blocks with multiple backends
  - SSL/TLS: Let's Encrypt with Certbot
  - Security headers: HSTS, X-Frame-Options, Content-Security-Policy
  - Rate limiting: `limit_req_zone`, `limit_req`
  - Logging: access log, error log, custom log formats
  - `nginx -t` — test configuration before reload
  - `systemctl reload nginx` — apply changes without downtime

#### § 8.1.2 — Apache (httpd)
  - Configuration: `/etc/apache2/` (Debian) or `/etc/httpd/` (RHEL)
  - Virtual hosts, modules, `.htaccess`
  - `a2ensite`, `a2dissite`, `a2enmod`, `a2dismod` (Debian)
  - Reverse proxy with `mod_proxy`
  - When to use Apache vs Nginx: Apache for `.htaccess` compatibility, Nginx for everything else

#### § 8.1.3 — SSL/TLS with Let's Encrypt
  - `certbot` — automatic certificate management
  - `certbot --nginx` / `certbot --apache` — auto-configure web server
  - Auto-renewal: certbot timer/cron
  - Certificate types: domain validated (DV), wildcard
  - `certbot certonly --standalone` — standalone mode
  - `certbot renew --dry-run` — test renewal

---

### 📦 Module 8.2: Databases

#### § 8.2.1 — PostgreSQL
  - Installation and initialization
  - `psql` — interactive client
  - User management: `createuser`, `ALTER ROLE`
  - Database management: `createdb`, `dropdb`
  - `pg_hba.conf` — client authentication configuration
  - `postgresql.conf` — server configuration tuning
  - Backup: `pg_dump`, `pg_dumpall`
  - Restore: `pg_restore`, `psql < dump.sql`
  - Replication: streaming replication basics

#### § 8.2.2 — MySQL / MariaDB
  - Installation and `mysql_secure_installation`
  - `mysql` — interactive client
  - User management: `CREATE USER`, `GRANT`
  - Backup: `mysqldump`
  - Configuration: `/etc/mysql/my.cnf` or `/etc/my.cnf`

#### § 8.2.3 — Redis
  - Installation and configuration
  - `redis-cli` — interactive client
  - Configuration: `/etc/redis/redis.conf`
  - Persistence: RDB snapshots, AOF (Append Only File)
  - Security: requirepass, bind address
  - Memory management: maxmemory, eviction policies

#### § 8.2.4 — SQLite
  - File-based database: no server required
  - `sqlite3 database.db` — interactive client
  - Use case: development, embedded applications, small projects

---

### 📦 Module 8.3: Application Deployment

#### § 8.3.1 — Deployment Strategies
  - Direct deployment: copy files, restart service
  - Reverse proxy: Nginx → application server (Node.js, Python, Go, Rust)
  - Process managers: systemd (preferred), PM2 (Node.js), Gunicorn (Python)
  - Blue-green deployment: two environments, switch traffic
  - Rolling deployment: update instances one at a time

#### § 8.3.2 — Environment Management
  - Environment variables: `.env` files, systemd `EnvironmentFile=`
  - Configuration management: separating config from code
  - Secrets management: never commit secrets to version control
  - Logging: application logs to journal via stdout/stderr

#### § 8.3.3 — Deployment Automation
  - Git hooks: post-receive hook for auto-deployment
  - `rsync` for file deployment
  - CI/CD: GitHub Actions, GitLab CI → SSH deploy
  - Ansible for configuration management (covered in Phase 11)

> ### 🛠️ Phase 8 Project: **"Production Stack Deployment"**
> Deploy a complete web application stack:
> - **Application**: deploy a web application (Node.js, Python, or Go)
> - **Reverse proxy**: Nginx with SSL/TLS (Let's Encrypt)
> - **Database**: PostgreSQL with proper user, database, and access configuration
> - **Cache**: Redis for session storage or caching
> - **Process management**: systemd service file for the application
> - **Security**: firewall rules, SSL, security headers, database access restrictions
> - **Monitoring**: set up log monitoring with `journalctl`, Nginx access log analysis
> - **Backup**: automated PostgreSQL backup script with `pg_dump`, retention policy, backup to remote server via `rsync`
> - **Load test**: use `wrk` or `ab` to benchmark the setup, document results
> - Document the entire architecture with a diagram and runbook

---

## ⚡ PHASE 9 — CONTAINERIZATION & DOCKER
> *"Containers changed how we deploy software. Docker democratized containers. Linux made it all possible."*

---

### 📦 Module 9.1: Container Fundamentals

#### § 9.1.1 — What are Containers
  - Lightweight, isolated processes sharing the host kernel
  - NOT virtual machines — no hypervisor, no guest OS
  - Linux kernel features: namespaces (isolation), cgroups (resource limits), overlay filesystems
  - Container vs VM: containers are lighter, faster, but less isolated

#### § 9.1.2 — Linux Kernel Features Behind Containers
  - **Namespaces**: PID, Network, Mount, UTS, User, IPC — process isolation
  - **cgroups** (Control Groups): CPU, memory, I/O, network limits
  - **Union filesystems**: overlay layers for efficient image storage
  - **seccomp**: system call filtering
  - **AppArmor / SELinux**: mandatory access control

---

### 📦 Module 9.2: Docker

#### § 9.2.1 — Docker Fundamentals
  - `docker run image` — run a container
  - `docker run -it ubuntu bash` — interactive terminal
  - `docker run -d -p 8080:80 nginx` — detached with port mapping
  - `docker ps` — list running containers
  - `docker ps -a` — list all containers (including stopped)
  - `docker stop container_id` — stop gracefully
  - `docker rm container_id` — remove container
  - `docker logs container_id` — view logs
  - `docker exec -it container_id bash` — execute command in running container
  - `docker inspect container_id` — detailed container info

#### § 9.2.2 — Images
  - `docker images` — list local images
  - `docker pull image:tag` — download image
  - `docker rmi image` — remove image
  - `docker build -t name:tag .` — build image from Dockerfile
  - `docker tag source target` — tag image
  - `docker push image` — push to registry
  - Image layers: each instruction creates a layer (cached for performance)
  - Docker Hub, GitHub Container Registry, private registries

#### § 9.2.3 — Dockerfile Best Practices
  - `FROM` — base image (use specific tags, not `latest`)
  - `RUN` — execute commands (combine with `&&` to reduce layers)
  - `COPY` / `ADD` — copy files into image
  - `WORKDIR` — set working directory
  - `EXPOSE` — document ports
  - `CMD` / `ENTRYPOINT` — default command
  - `ENV` — environment variables
  - `USER` — run as non-root
  - `.dockerignore` — exclude files from build context
  - Multi-stage builds: build in one stage, copy artifacts to minimal runtime stage
  - Layer ordering: least-changing layers first (cache optimization)
  - Minimize image size: Alpine base, multi-stage, no unnecessary packages

#### § 9.2.4 — Volumes & Data Persistence
  - `docker volume create mydata` — create named volume
  - `-v mydata:/app/data` — mount named volume
  - `-v /host/path:/container/path` — bind mount
  - `docker volume ls`, `docker volume rm` — management
  - Data persistence: containers are ephemeral, volumes survive container removal

#### § 9.2.5 — Networking
  - `docker network create mynet` — create network
  - `--network mynet` — connect container to network
  - Bridge (default), Host, None, Overlay (Swarm)
  - Containers on same network: communicate by container name (DNS)
  - `-p host_port:container_port` — port mapping

---

### 📦 Module 9.3: Docker Compose

#### § 9.3.1 — Multi-Container Applications
  - `docker-compose.yml` / `compose.yaml` — define multi-container app
  - `services`, `volumes`, `networks` — top-level keys
  - `docker compose up -d` — start all services
  - `docker compose down` — stop and remove all
  - `docker compose logs -f service` — follow logs
  - `docker compose exec service bash` — shell into service
  - `docker compose build` — rebuild images
  - `depends_on` — service startup order
  - Environment variables: `.env` file, `environment:` key
  - Health checks: `healthcheck:` — verify service readiness
  - Profiles: group services for different environments

---

### 📦 Module 9.4: Container Security

#### § 9.4.1 — Security Best Practices
  - Run as non-root user (`USER` instruction)
  - Use minimal base images (Alpine, distroless, scratch)
  - Don't store secrets in images (use environment variables, Docker secrets)
  - Scan images for vulnerabilities: `trivy`, `grype`, `docker scout`
  - Read-only root filesystem: `--read-only`
  - Drop capabilities: `--cap-drop=ALL --cap-add=NET_BIND_SERVICE`
  - Resource limits: `--memory`, `--cpus`
  - Use specific image tags (not `latest`)
  - Regularly update base images

> ### 🛠️ Phase 9 Project: **"Containerized Microservices Platform"**
> Build a multi-service application with Docker Compose:
> - **Services**:
>   - API backend (Node.js or Python)
>   - PostgreSQL database
>   - Redis cache
>   - Nginx reverse proxy with SSL termination
>   - Adminer (database admin UI)
> - **Dockerfile**: multi-stage build for the API backend
> - **Compose**: all services orchestrated with proper networking, volumes, health checks
> - **Data**: named volumes for database and Redis persistence
> - **Networking**: internal network for services, only Nginx exposed externally
> - **Security**: non-root users, read-only filesystems, dropped capabilities, resource limits
> - **Image scanning**: run `trivy` on all images, fix vulnerabilities
> - **Monitoring**: container resource usage monitoring script
> - **Development vs Production**: separate compose files or profiles

---

## ⚡ PHASE 10 — SECURITY & HARDENING
> *"A server on the internet is under attack from the moment it has an IP address."*

---

### 📦 Module 10.1: System Security Fundamentals

#### § 10.1.1 — Security Principles
  - Principle of least privilege: minimum necessary access
  - Defense in depth: multiple layers of security
  - Minimize attack surface: disable unused services, close unused ports
  - Keep systems updated: security patches are critical
  - Audit and monitor: know what's happening on your systems

#### § 10.1.2 — System Updates & Patching
  - Automatic security updates: `unattended-upgrades`, `dnf-automatic`
  - Kernel live patching: `kpatch`, `livepatch` — patch kernel without reboot
  - Vulnerability tracking: CVE databases, distribution security advisories
  - Reboot requirements: `needs-restarting` (RHEL), `/var/run/reboot-required` (Ubuntu)

---

### 📦 Module 10.2: Access Control & Authentication

#### § 10.2.1 — PAM (Pluggable Authentication Modules)
  - `/etc/pam.d/` — PAM configuration per service
  - Password policies: `pam_pwquality` — enforce password complexity
  - Account lockout: `pam_faillock` — lock after failed attempts
  - Two-factor authentication: `pam_google_authenticator`

#### § 10.2.2 — sudo Configuration
  - `/etc/sudoers` — ALWAYS edit with `visudo`
  - User-specific rules, group-specific rules
  - Command restrictions: allow specific commands only
  - `NOPASSWD` for automation (use judiciously)
  - Logging: sudo logs all commands to syslog/journal

#### § 10.2.3 — SELinux (Security-Enhanced Linux)
  - Mandatory Access Control (MAC) — beyond standard permissions
  - Modes: Enforcing, Permissive, Disabled
  - `getenforce`, `setenforce` — check/set mode
  - `ls -Z` — view SELinux contexts
  - `chcon`, `restorecon` — change/restore contexts
  - `setsebool` — toggle SELinux booleans
  - `audit2allow` — generate policy from denials
  - Default on RHEL/Fedora, critical for enterprise security

#### § 10.2.4 — AppArmor
  - Default on Ubuntu/Debian
  - Profile-based mandatory access control
  - `aa-status` — view loaded profiles
  - `aa-enforce`, `aa-complain` — set profile mode
  - Profiles in `/etc/apparmor.d/`
  - Easier to manage than SELinux, less granular

---

### 📦 Module 10.3: Network Security

#### § 10.3.1 — SSH Hardening (Deep Dive)
  - Disable root login, password authentication
  - Use Ed25519 keys exclusively
  - `fail2ban` — ban IPs after failed login attempts
  - SSH certificate authentication (advanced)
  - Port knocking (advanced, niche)
  - SSH bastion/jump hosts for network segmentation

#### § 10.3.2 — `fail2ban` Configuration
  - Installation and configuration
  - Jails: SSH, Nginx, Apache, custom
  - Ban time, find time, max retry configuration
  - Custom filters for application-specific logs
  - Monitoring: `fail2ban-client status sshd`

#### § 10.3.3 — Intrusion Detection
  - `rkhunter` — rootkit detection
  - `chkrootkit` — rootkit checking
  - `AIDE` — file integrity monitoring (Advanced Intrusion Detection Environment)
  - `auditd` — Linux audit framework
  - `aureport` — audit report generation
  - `ausearch` — search audit logs

---

### 📦 Module 10.4: Encryption

#### § 10.4.1 — Disk Encryption
  - LUKS (Linux Unified Key Setup): full disk encryption
  - `cryptsetup luksFormat /dev/sdX` — encrypt partition
  - `cryptsetup luksOpen /dev/sdX name` — unlock
  - Encrypting during installation (recommended for laptops)

#### § 10.4.2 — File & Communication Encryption
  - GPG (GNU Privacy Guard): file encryption, signing
  - `gpg --gen-key` — generate key pair
  - `gpg -c file` — symmetric encryption
  - `gpg -e -r recipient file` — asymmetric encryption
  - SSH key management and rotation
  - Certificate management: OpenSSL for creating/managing certificates

---

### 📦 Module 10.5: Auditing & Compliance

#### § 10.5.1 — Security Auditing Tools
  - `lynis` — comprehensive system audit tool
  - `OpenSCAP` — security compliance scanning (STIG, CIS benchmarks)
  - CIS Benchmarks: industry-standard hardening guidelines
  - `oscap` — scan against security profiles
  - Regular security audits: schedule and document

#### § 10.5.2 — Log Management & Analysis
  - Centralized logging: `rsyslog`, `syslog-ng`
  - Log rotation: `logrotate` configuration
  - Log analysis: `grep`, `awk`, `journalctl` queries
  - Security-relevant logs: auth, sudo, firewall, application logs
  - Log forwarding to SIEM (ELK Stack, Splunk, Graylog)

> ### 🛠️ Phase 10 Project: **"Fortress Server — Complete Security Hardening"**
> Take a fresh server and harden it completely:
> - **Access control**: SSH hardening (keys only, no root, custom port), `fail2ban` with aggressive settings
> - **Firewall**: strict iptables/nftables rules, only necessary ports open, rate limiting
> - **Updates**: automatic security updates configured and tested
> - **MAC**: enable and configure SELinux (RHEL) or AppArmor (Ubuntu) in enforcing mode
> - **Audit**: install and run `lynis`, score > 80, document all findings and remediations
> - **Integrity**: set up AIDE for file integrity monitoring, baseline scan, scheduled checks
> - **Encryption**: LUKS-encrypted data partition, GPG-encrypted backups
> - **Logging**: centralized log management, `auditd` rules for sensitive files, log rotation
> - **PAM**: password complexity policy, account lockout after 5 failures
> - **Documentation**: complete security runbook documenting every hardening measure, why it was applied, and how to verify it

---

## ⚡ PHASE 11 — AUTOMATION, CONFIGURATION MANAGEMENT & IaC
> *"If you do it twice, automate it."*

---

### 📦 Module 11.1: Ansible (Configuration Management)

#### § 11.1.1 — Ansible Fundamentals
  - Agentless: connects via SSH (nothing to install on target)
  - Inventory: hosts and groups (`/etc/ansible/hosts` or custom)
  - Ad-hoc commands: `ansible all -m ping`, `ansible all -a "uptime"`
  - Modules: `apt`, `yum`, `copy`, `file`, `service`, `user`, `template`, `command`, `shell`
  - Idempotent: running the same playbook twice produces the same result

#### § 11.1.2 — Playbooks
  - YAML-based automation scripts
  - Tasks, handlers, variables, templates, conditionals, loops
  - Roles: reusable, organized collections of tasks
  - Ansible Galaxy: community-shared roles
  - `ansible-playbook playbook.yml` — execute playbook
  - `--check` (dry run), `--diff` (show changes), `-v` (verbose)

#### § 11.1.3 — Advanced Ansible
  - Templates: Jinja2 templates for configuration files
  - Variables: host vars, group vars, role vars, extra vars
  - Vault: encrypt sensitive data (`ansible-vault encrypt/decrypt`)
  - Tags: run specific parts of a playbook
  - Roles directory structure: `tasks/`, `handlers/`, `templates/`, `vars/`, `defaults/`, `files/`
  - Best practices: role-based organization, version-controlled playbooks

---

### 📦 Module 11.2: Infrastructure as Code

#### § 11.2.1 — Terraform Basics
  - Declarative infrastructure: describe desired state, Terraform creates it
  - Providers: AWS, GCP, Azure, DigitalOcean, and hundreds more
  - Resources: `resource "aws_instance" "web" { ... }`
  - State: `terraform.tfstate` — tracks current infrastructure
  - `terraform init` → `terraform plan` → `terraform apply` → `terraform destroy`
  - Variables, outputs, modules
  - Remote state: S3 backend for team collaboration

#### § 11.2.2 — Cloud-Init
  - Cloud instance initialization standard
  - User data scripts: run on first boot
  - `cloud-config` YAML: users, packages, files, commands
  - Works with: AWS, GCP, Azure, OpenStack, DigitalOcean

---

### 📦 Module 11.3: CI/CD on Linux

#### § 11.3.1 — CI/CD Pipeline Implementation
  - GitHub Actions: YAML-based workflows running on Linux VMs
  - GitLab CI/CD: `.gitlab-ci.yml` pipelines
  - Jenkins: self-hosted CI/CD server
  - Pipeline stages: build → test → lint → deploy
  - Self-hosted runners: run CI on your own Linux servers
  - Docker in CI: building and testing in containers
  - Deployment: SSH-based deploy scripts, Ansible deployment, container deployment

---

### 📦 Module 11.4: Monitoring Infrastructure

#### § 11.4.1 — Prometheus + Grafana
  - Prometheus: pull-based metrics collection and storage
  - Node Exporter: Linux system metrics (CPU, memory, disk, network)
  - Grafana: visualization dashboards
  - Alert Manager: alerting based on metrics thresholds
  - PromQL: Prometheus query language for metric analysis

#### § 11.4.2 — ELK Stack / Loki
  - Elasticsearch + Logstash + Kibana: centralized log management
  - Grafana Loki: lightweight log aggregation (pairs with Grafana)
  - Promtail: log shipping agent for Loki
  - Structured logging and log analysis

#### § 11.4.3 — Other Monitoring Tools
  - Nagios / Icinga: traditional monitoring
  - Zabbix: enterprise monitoring
  - Netdata: real-time performance monitoring (beautiful dashboards, zero config)
  - Uptime Kuma: self-hosted uptime monitoring

> ### 🛠️ Phase 11 Project: **"Infrastructure Automation Platform"**
> Build a complete automated infrastructure:
> - **Terraform**: provision 3 VPS instances (web server, database server, monitoring server)
> - **Ansible playbooks**:
>   - `common` role: base packages, users, SSH hardening, firewall, fail2ban
>   - `web` role: Nginx, application deployment, SSL
>   - `database` role: PostgreSQL installation, configuration, backup schedule
>   - `monitoring` role: Prometheus, Node Exporter, Grafana
> - **Cloud-init**: base configuration on first boot
> - **Monitoring**: Prometheus scraping all nodes, Grafana dashboards for CPU/memory/disk/network, alerts for high usage
> - **CI/CD**: GitHub Actions pipeline that runs Ansible playbooks on push
> - **Secrets**: Ansible Vault for passwords and API keys
> - **Testing**: `ansible-lint`, dry-run mode, verify idempotency (run twice, same result)
> - **Documentation**: complete architecture diagram, runbook, disaster recovery procedure

---

## ⚡ PHASE 12 — KUBERNETES, ADVANCED TOPICS & LINUX INTERNALS
> *"This is where Linux stops being a tool and becomes a superpower."*

---

### 📦 Module 12.1: Kubernetes on Linux

#### § 12.1.1 — Kubernetes Fundamentals
  - Pods, Deployments, Services, Ingress
  - `kubectl` — the Kubernetes CLI
  - Namespaces, ConfigMaps, Secrets
  - Persistent Volumes and Claims
  - Health probes: liveness, readiness, startup

#### § 12.1.2 — Running Kubernetes
  - Local: `minikube`, `kind`, `k3s`
  - Production: `kubeadm`, managed services (EKS, GKE, AKS)
  - `k3s` — lightweight Kubernetes (perfect for learning on a VPS)

#### § 12.1.3 — Kubernetes Operations
  - Deploying applications from YAML manifests
  - Scaling: horizontal pod autoscaler
  - Rolling updates and rollbacks
  - Monitoring: Prometheus Operator, Grafana dashboards
  - Logging: centralized logging with Loki/ELK
  - Helm: Kubernetes package manager

---

### 📦 Module 12.2: Linux Kernel Concepts

#### § 12.2.1 — Kernel Architecture
  - Monolithic vs microkernel: Linux is monolithic (with loadable modules)
  - Kernel space vs user space
  - System calls: the interface between user programs and the kernel
  - Kernel modules: `lsmod`, `modprobe`, `modinfo`, `rmmod`
  - `/proc` filesystem: process and kernel information
  - `/sys` filesystem: device and driver information

#### § 12.2.2 — Kernel Tuning
  - `sysctl` — runtime kernel parameter configuration
  - `/etc/sysctl.conf` — persistent kernel parameters
  - Network tuning: `net.core.somaxconn`, `net.ipv4.tcp_max_syn_backlog`
  - Memory tuning: `vm.swappiness`, `vm.overcommit_memory`
  - File descriptor limits: `fs.file-max`, `ulimit -n`
  - Security: `kernel.randomize_va_space` (ASLR), `kernel.dmesg_restrict`

#### § 12.2.3 — Kernel Compilation (Advanced)
  - Downloading kernel source
  - `make menuconfig` — configure kernel options
  - `make -j$(nproc)` — compile
  - Installing custom kernel
  - Use case: custom drivers, performance optimization, learning

---

### 📦 Module 12.3: Advanced Networking

#### § 12.3.1 — Network Namespaces & Virtual Networking
  - `ip netns` — network namespace management
  - `veth` pairs — virtual ethernet connections
  - Linux bridges: `brctl`, `ip link add type bridge`
  - VLAN tagging: `ip link add link eth0 name eth0.100 type vlan id 100`
  - These are the building blocks of container networking

#### § 12.3.2 — VPN
  - WireGuard: modern, fast, simple VPN (built into Linux kernel)
  - `wg-quick up wg0` — start WireGuard interface
  - OpenVPN: traditional, widely supported
  - IPsec / StrongSwan: enterprise VPN
  - WireGuard configuration: keys, peers, allowed IPs, endpoints

#### § 12.3.3 — Advanced Routing & Load Balancing
  - Policy-based routing
  - `ip rule`, `ip route` — multiple routing tables
  - HAProxy: TCP/HTTP load balancer
  - Keepalived: high availability (VRRP, floating IPs)
  - IPVS: in-kernel load balancing (used by Kubernetes)

---

### 📦 Module 12.4: Performance Tuning & Troubleshooting

#### § 12.4.1 — Performance Analysis Methodology
  - USE method: Utilization, Saturation, Errors for each resource
  - RED method: Rate, Errors, Duration for each service
  - Brendan Gregg's Linux Performance Tools diagram
  - `perf` — the Linux profiler (CPU profiling, flame graphs)
  - `bpftrace` — eBPF-based tracing (advanced)
  - `eBPF` — extended Berkeley Packet Filter (programmable kernel tracing)

#### § 12.4.2 — Troubleshooting Methodology
  - Systematic approach: observe → hypothesize → test → resolve
  - `dmesg` — kernel messages (hardware, driver issues)
  - `journalctl` — service and system logs
  - `strace` — trace system calls of a process
  - `lsof` — open files and sockets
  - `ss` — socket statistics
  - Core dumps: enabling, analyzing with `gdb`
  - Common issues: disk full, memory leak, zombie processes, DNS resolution, permission denied

---

### 📦 Module 12.5: High Availability & Disaster Recovery

#### § 12.5.1 — High Availability Patterns
  - Active/passive failover with Keepalived
  - Active/active load balancing with HAProxy
  - Database replication: PostgreSQL streaming replication, MySQL replication
  - Shared storage: NFS, GlusterFS, Ceph
  - Clustering: Pacemaker + Corosync

#### § 12.5.2 — Backup & Disaster Recovery
  - Backup strategies: full, incremental, differential
  - Tools: `rsync`, `borgbackup`, `restic`, `duplicity`
  - `borgbackup`: deduplication, compression, encryption (excellent for servers)
  - 3-2-1 rule: 3 copies, 2 different media, 1 offsite
  - Disaster recovery planning: RTO (Recovery Time Objective), RPO (Recovery Point Objective)
  - Testing backups: a backup not tested is not a backup

> ### 🛠️ Phase 12 Capstone Project: **"Production Linux Platform"**
> Build a complete, production-grade Linux platform:
>
> - **Infrastructure** (Terraform):
>   - 3 application servers, 1 database server, 1 monitoring server, 1 load balancer
>   - WireGuard VPN between all servers (private network)
>
> - **Configuration** (Ansible):
>   - Base hardening on all servers (SSH, firewall, fail2ban, automatic updates)
>   - Application deployment with Nginx reverse proxy and SSL
>   - PostgreSQL with streaming replication (primary + standby)
>   - HAProxy load balancing across application servers
>   - Keepalived for HAProxy high availability
>
> - **Containers**:
>   - Application deployed as Docker containers
>   - Docker Compose on each app server (or k3s cluster for extra credit)
>
> - **Monitoring**:
>   - Prometheus + Node Exporter on all servers
>   - Grafana dashboards: system metrics, application metrics, database metrics
>   - AlertManager: email/Slack alerts for critical thresholds
>   - Loki for centralized log aggregation
>
> - **Security**:
>   - Full security hardening checklist applied
>   - Lynis audit score > 85 on all servers
>   - AIDE file integrity monitoring
>   - fail2ban on all SSH ports
>
> - **Backup**:
>   - Automated daily backups with `borgbackup` (encrypted, deduplicated)
>   - Database backups with `pg_dump` + offsite copy
>   - Tested restore procedure documented
>
> - **Performance**:
>   - Kernel tuning for web workload (`sysctl` settings)
>   - Load test with `wrk` — document throughput and latency
>
> - **CI/CD**:
>   - GitHub Actions pipeline: lint Ansible → test → deploy to staging → deploy to production
>
> - **Documentation**:
>   - Complete architecture diagram
>   - Runbook: common operations (deploy, rollback, scale, backup, restore)
>   - Incident response plan
>   - Disaster recovery procedure with tested restore

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Orientation & Environment Setup
Phase 1   ████░░░░░░░░░░░░░░  The Command Line (Navigation, Text, Pipes)
Phase 2   ██████░░░░░░░░░░░░  Users, Permissions & File System
Phase 3   ████████░░░░░░░░░░  Text Editors & Shell Scripting
Phase 4   █████████░░░░░░░░░  Process Management & System Monitoring
Phase 5   ██████████░░░░░░░░  Service Management & systemd
Phase 6   ███████████░░░░░░░  Networking (SSH, Firewalls, DNS)
Phase 7   ████████████░░░░░░  Package Management & Software Installation
Phase 8   █████████████░░░░░  Web Servers, Databases & Deployment
Phase 9   ██████████████░░░░  Containerization & Docker
Phase 10  ███████████████░░░  Security & Hardening
Phase 11  ████████████████░░  Automation, Ansible & IaC
Phase 12  ██████████████████  Kubernetes, Internals & Production
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 4     │──────▶│   Phase 8    │──────▶│   Phase 11   │
    │  Phase 1   │        │    Phase 5     │       │   Phase 9    │       │   Phase 12   │
    │  Phase 2   │        │    Phase 6     │       │   Phase 10   │       │              │
    │  Phase 3   │        │    Phase 7     │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can navigate        "I manage services,     "I deploy secure,       "I architect
     the CLI, write         configure networking,   containerized           production
     scripts, and           and install software"   production systems"     infrastructure
     manage files"                                                          at scale"
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification |
|-------|--------------|
| 0 – 3 | **Linux Essentials (LPI 010-160)** |
| 0 – 6 | **CompTIA Linux+ (XK0-005)** |
| 0 – 7 | **LPIC-1 (101-500 + 102-500)** |
| 4 – 10 | **LPIC-2 (201-450 + 202-450)** |
| 0 – 8 | **RHCSA (Red Hat Certified System Administrator — EX200)** |
| 6 – 12 | **RHCE (Red Hat Certified Engineer — EX294)** |
| 9 – 12 | **CKA (Certified Kubernetes Administrator)** |
| 10 – 12 | **LPIC-3 (Security, Virtualization, Mixed Environments)** |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| *The Linux Command Line* — William Shotts (free online) | 📖 Book (START HERE) | 0–3 |
| *How Linux Works* — Brian Ward (3rd Ed.) | 📖 Book (How things work) | 0–6 |
| *UNIX and Linux System Administration Handbook* — Nemeth et al. (5th Ed.) | 📖 Book (The Bible) | 4–12 |
| *Linux Bible* — Christopher Negus | 📖 Book (Comprehensive) | 0–8 |
| *The Linux Programming Interface* — Michael Kerrisk | 📖 Book (Kernel/syscalls) | 12 |
| *Linux Pocket Guide* — Daniel Barrett | 📖 Book (Quick ref) | ALL |
| *Efficient Linux at the Command Line* — Daniel Barrett | 📖 Book | 1–3 |
| *Systems Performance* — Brendan Gregg (2nd Ed.) | 📖 Book (Performance) | 12 |
| *Ansible for DevOps* — Jeff Geerling | 📖 Book | 11 |
| *Docker Deep Dive* — Nigel Poulton | 📖 Book | 9 |
| **Linux Journey** (linuxjourney.com) | 🌐 Interactive | 0–5 |
| **OverTheWire: Bandit** (overthewire.org) | 🧪 Wargame | 1–3 |
| **Linux Upskill Challenge** (Reddit) | 🌐 Free Course | 0–7 |
| **Arch Wiki** (wiki.archlinux.org) | 🌐 The Best Wiki | ALL |
| **DistroWatch** (distrowatch.com) | 🌐 Distro info | 0 |
| **LearnLinuxTV** (YouTube) | 🎥 Video | 0–9 |
| **NetworkChuck** (YouTube) | 🎥 Video | 0–6 |
| **tutoriaLinux** (YouTube) | 🎥 Video | 4–12 |
| **Brendan Gregg's Blog** (brendangregg.com) | 🌐 Performance | 12 |
| **Exercism — Bash Track** | 🧪 Practice | 3 |
| **SadServers** (sadservers.com) | 🧪 Troubleshooting | 4–10 |
| **KodeKloud** | 🧪 Interactive Labs | 5–12 |
| **Linux Foundation Training** | 🌐 Official Training | ALL |

---

## 🗺️ WHERE LINUX TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   System Administration   │
                           ┌─────▶│   (Sysadmin, Linux Admin) │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   DevOps / SRE            │
                   ┌───────┤─────▶│   (CI/CD, Automation,     │
                   │       │      │    Reliability)            │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Cloud Engineering       │
   │            │  │       ├─────▶│   (AWS, GCP, Azure,       │
   │  Master    ├──┤       │      │    Infrastructure)         │
   │  Linux     │  │       │      └───────────────────────────┘
   │            │  │       │      ┌───────────────────────────┐
   └────────────┘  │       │      │   Platform Engineering    │
                   │       ├─────▶│   (Kubernetes, Containers, │
                   │       │      │    Service Mesh)            │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Cybersecurity           │
                   │       ├─────▶│   (Pentesting, Security   │
                   │       │      │    Engineering, SOC)        │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Embedded / IoT          │
                   └───────┴─────▶│   (Firmware, Yocto,       │
                                  │    Buildroot, Automotive)   │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"Linux mastery is not about memorizing commands. It's about understanding the system deeply enough to solve any problem."**
>
> Five non-negotiable rules for your Linux journey:
>
> 1. **Use Linux daily** — switch your development machine, or at minimum, always have an SSH session to a Linux server. Daily use builds muscle memory faster than any course.
>
> 2. **Read *The Linux Command Line* by William Shotts** — it's free, it's brilliant, and it will give you the CLI fluency that everything else builds upon. Then read *How Linux Works* by Brian Ward for understanding WHY things work.
>
> 3. **Break things on purpose — then fix them** — the fastest way to learn Linux is to break your system and restore it. This is why VMs and cloud VPSes exist. Delete a critical config file, corrupt GRUB, fill up the disk, kill PID 1 — then recover. **SadServers.com** is perfect for this.
>
> 4. **Learn Vim** — it's on every Linux system ever, and once you're proficient (2-3 weeks of daily use), you'll edit at the speed of thought. Run `vimtutor` today.
>
> 5. **Get a VPS and run a real service** — theory is nothing without practice. Get a $5/month VPS, deploy a web application, secure it, monitor it, back it up, break it, fix it. A server you're responsible for teaches more than any course.
>
> The difference between a *Linux user* and a *Linux engineer* is:
> - **Understanding what happens beneath the surface** (processes, syscalls, namespaces, cgroups)
> - **Automating everything** (if you typed it twice, script it)
> - **Security-first thinking** (least privilege, defense in depth, audit everything)
> - **Being comfortable when everything is on fire** (troubleshooting methodology, not panic)

---

*This roadmap takes you from "What's a terminal?" to "I can architect, deploy, secure, monitor, and automate production-grade Linux infrastructure at scale — and I can do it all from a blinking cursor."* 🐧🚀