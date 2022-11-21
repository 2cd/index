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
tag = ["alpine", "2022-11-21", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-11-21_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c4af50619252b15cab0b0bf6cf21e6a63ee1b63b49c1800416ce47251605477e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "838M"
tar_bytes = 878681600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 160871170

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221118"
previous_tag = "2022-11-18"
previous_file = "rust-musl_arm64_2022-11-18_02-59-rootfs.tar.zst"
previous_sha256 = "aa4d338a814536e3db3bdd41bf8f4cfaf29d02c213a4c6ea5d03deb2cdd2f850"

current_version = "latest02"
current_date = "20221121"
old_file = "rust-musl_arm64_2022-11-14_03-01-rootfs.tar.zst"
old_sha256 = "c4c7a8c6c776433895d2470a52fc8c1ac4d6dc0754fd7cd9d7e06319a37851ee"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-11-21_03-01-rootfs.tar.zst
# SHA256SUM=c4af50619252b15cab0b0bf6cf21e6a63ee1b63b49c1800416ce47251605477e
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 02:52:25.693463843+00:00
start-sync_0 = 02:54:56
start-zstd = 02:55:45
start-sync_1 = 03:01:11
end-sync_1 = 03:01:28
end = 2022-11-21 03:01:28.382177951+00:00

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
cargo = 'cargo 1.67.0-nightly (eb5d35917 2022-11-17)'
rustc = 'rustc 1.67.0-nightly (a28f3c88e 2022-11-20)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (eb5d35917 2022-11-17)
release: 1.67.0-nightly
commit-hash: eb5d35917b2395194593c9ca70c3778f60c1573b
commit-date: 2022-11-17
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (a28f3c88e 2022-11-20)
binary: rustc
commit-hash: a28f3c88e50a77bc2a91889241248c4543854e61
commit-date: 2022-11-20
host: aarch64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
