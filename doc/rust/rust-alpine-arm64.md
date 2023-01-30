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
tag = ["alpine", "2023-01-30", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-01-30_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "69afa83f17838429970aeb69e3d4d5159110c867cc265b8257867b4029d643d2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "859M"
tar_bytes = 899805184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 162827154

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230127"
previous_tag = "2023-01-27"
previous_file = "rust-musl_arm64_2023-01-27_03-00-rootfs.tar.zst"
previous_sha256 = "f68d73b9c03a9a2caf9929d65e39d037782bb58cd650917c3b3e52bb15f2cd17"

current_version = "latest01"
current_date = "20230130"
old_file = "rust-musl_arm64_2023-01-23_03-00-rootfs.tar.zst"
old_sha256 = "f834e6955966a3d9ff3ef6ea9d3a4c40d8deb2c732dc9ff3e273fa3181116d79"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-01-30_03-02-rootfs.tar.zst
# SHA256SUM=69afa83f17838429970aeb69e3d4d5159110c867cc265b8257867b4029d643d2
# BUILD_DATE=20230130
# BUILD_TAG=2023-01-30
# STATUS=completed
# VERSION=latest01
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-30
begin = 2023-01-30 02:52:30.474485330+00:00
start-sync_0 = 02:55:04
start-zstd = 02:55:56
start-sync_1 = 03:01:42
end-sync_1 = 03:02:01
end = 2023-01-30 03:02:01.887672782+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.69.0-nightly (3c5af6bed 2023-01-24)'
rustc = 'rustc 1.69.0-nightly (e972bc808 2023-01-29)'
cc = 'cc (Alpine 12.2.1_git20220924-r8) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.69.0-nightly (3c5af6bed 2023-01-24)
release: 1.69.0-nightly
commit-hash: 3c5af6bed9a1a243a693e8e22ee2486bd5b82a6c
commit-date: 2023-01-24
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (e972bc808 2023-01-29)
binary: rustc
commit-hash: e972bc8083d5228536dfd42913c8778b6bb04c8e
commit-date: 2023-01-29
host: aarch64-unknown-linux-musl
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
