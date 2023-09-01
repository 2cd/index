# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

## Example

### set env

```sh
_UID="$(id -u)" || _UID=0
_GID="$(id -g)" || _GID=0
```

### create a new project

If "tmp/hello" already exists in the current directory, it can be skipped.

```sh
mkdir -p tmp

docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp:/app \
    -w /app \
    cake233/rust-alpine-arm64 \
    cargo new hello
```

### cargo build

```sh
docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp/hello:/app \
    -w /app \
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2023-09-01", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-09-01_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d72133523517d28bca2cd6763a73fe1232f4e9b58feba601e559a2fee4abec28"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "899M"
tar_bytes = 942213632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 166000137

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "rust-musl_arm64_2023-08-28_03-02-rootfs.tar.zst"
previous_sha256 = "905de104600f4db4e731a72907bcce4c23c67fbdfb2bf399f71aa01c716f7ac6"

current_version = "latest02"
current_date = "20230901"
old_file = "rust-musl_arm64_2023-08-21_03-02-rootfs.tar.zst"
old_sha256 = "83f6f5d98a665bec98add340a918731d9ef97acd08474be362f8a8ac037c8959"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-09-01_03-00-rootfs.tar.zst
# SHA256SUM=d72133523517d28bca2cd6763a73fe1232f4e9b58feba601e559a2fee4abec28
# BUILD_DATE=20230901
# BUILD_TAG=2023-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-01
begin = 2023-09-01 02:52:32.464671631+00:00
start-sync_0 = 02:54:52
start-zstd = 02:55:32
start-sync_1 = 03:00:19
end-sync_1 = 03:00:37
end = 2023-09-01 03:00:37.940532562+00:00

[server]
repo = "cake233/rust-alpine-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (96fe1c9e1 2023-08-29)'
rustc = 'rustc 1.74.0-nightly (2f5df8a94 2023-08-31)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.74.0-nightly (96fe1c9e1 2023-08-29)
release: 1.74.0-nightly
commit-hash: 96fe1c9e1aecd8f57063e3753969bb6418fd2fd5
commit-date: 2023-08-29
host: aarch64-unknown-linux-musl
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (2f5df8a94 2023-08-31)
binary: rustc
commit-hash: 2f5df8a94bb3c5fae4e3fcbfc8ef20f1f976cb19
commit-date: 2023-08-31
host: aarch64-unknown-linux-musl
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
