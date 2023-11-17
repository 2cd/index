# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-11-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-11-17_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1dcd916aebc77fd074b5f98e6b9d3dab3ce019cb42d937e651092aab7edeae75"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1929548800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "245M"
zstd_bytes = 256435296

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231113"
previous_tag = "2023-11-13"
previous_file = "rust_arm64_2023-11-13_03-13-rootfs.tar.zst"
previous_sha256 = "cc4fee1cc029d3a581e0b06207aa70f5b61182eaf4e71547576deb5ae2c321a4"

current_version = "latest01"
current_date = "20231117"
old_file = "rust_arm64_2023-11-10_03-15-rootfs.tar.zst"
old_sha256 = "6352d7aa7b167129795fc1d228ae454f8caac9f8e799f910363e97eafe27827e"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-11-17_03-08-rootfs.tar.zst
# SHA256SUM=1dcd916aebc77fd074b5f98e6b9d3dab3ce019cb42d937e651092aab7edeae75
# BUILD_DATE=20231117
# BUILD_TAG=2023-11-17
# STATUS=completed
# VERSION=latest01
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-17
begin = 2023-11-17 02:52:33.081180657+00:00
start-sync_0 = 03:02:17
start-zstd = 03:03:21
start-sync_1 = 03:07:56
end-sync_1 = 03:08:14
end = 2023-11-17 03:08:14.683475276+00:00

[server]
repo = "cake233/rust-arm64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.76.0-nightly (2c03e0e2d 2023-11-16)'
rustc = 'rustc 1.76.0-nightly (a57770440 2023-11-16)'
cc = 'cc (Debian 13.2.0-6) 13.2.0'
cargo_verbose = '''
cargo 1.76.0-nightly (2c03e0e2d 2023-11-16)
release: 1.76.0-nightly
commit-hash: 2c03e0e2dcd05dd064fcf10cc1050d342eaf67e3
commit-date: 2023-11-16
host: aarch64-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (a57770440 2023-11-16)
binary: rustc
commit-hash: a57770440f1ebe5b992551d3bcc489ae211908d4
commit-date: 2023-11-16
host: aarch64-unknown-linux-gnu
release: 1.76.0-nightly
LLVM version: 17.0.5
'''
```
