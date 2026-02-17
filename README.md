# systemd

Recently, I had a hard time finding a trustworthy base image for building an application that requires systemd to run.

This repository contains a fully auditable build pipeline that pushes x86 and ARM images directly to the GitHub Container Registry.

## Usage

### Ubuntu 24.04 LTS (Noble) with Systemd

linux/amd64

```
docker pull ghcr.io/davift/systemd:ubuntu-24
```

linux/arm64

```
docker pull ghcr.io/davift/systemd:ubuntu-24
```

### Debian 13 (Trixie) with Systemd

linux/amd64

```
docker pull ghcr.io/davift/systemd:debian-13
```

linux/arm64

```
docker pull ghcr.io/davift/systemd:debian-13
```

## Manual Local Build

### Ubuntu 24.04 LTS (Noble) with Systemd

```
cd ubuntu-24
docker build -t systemd:ubuntu-24 .
```

### Debian 13 (Trixie) with Systemd

```
cd debian-13
docker build -t systemd:debian-13 .
```

