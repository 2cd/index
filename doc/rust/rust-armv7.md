# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

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
    cake233/rust-armv7 \
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
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-01-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-01-13_09-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0f24ce537792d19714d2b781473f1a2219e1fa0eab65cfa5a57dc80ea26a12e5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1566332928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 226835063

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230109"
previous_tag = "2023-01-09"
previous_file = "rust_armhf_2023-01-09_03-08-rootfs.tar.zst"
previous_sha256 = "94e733340d9332ce74cb3f8be2b24593ce06bba80a2b3bcdd7f9d06d2ee5a66b"

current_version = "latest01"
current_date = "20230113"
old_file = "rust_armhf_2023-01-06_03-08-rootfs.tar.zst"
old_sha256 = "efe93d64c259bdba13fbce7e7028079e7f79fbf932996d5487aac82a34eec2b5"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-01-13_09-05-rootfs.tar.zst
# SHA256SUM=0f24ce537792d19714d2b781473f1a2219e1fa0eab65cfa5a57dc80ea26a12e5
# BUILD_DATE=20230113
# BUILD_TAG=2023-01-13
# STATUS=completed
# VERSION=latest01
# END_TIME=09:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-13
begin = 2023-01-13 08:54:30.278914674+00:00
start-sync_0 = 09:00:12
start-zstd = 09:01:09
start-sync_1 = 09:05:35
end-sync_1 = 09:05:53
end = 2023-01-13 09:05:53.224757535+00:00

[server]
repo = "cake233/rust-armv7"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (d992ab4e9 2023-01-10)'
rustc = 'rustc 1.68.0-nightly (61a415be5 2023-01-12)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (d992ab4e9 2023-01-10)
release: 1.68.0-nightly
commit-hash: d992ab4e9034930e7809749f04077045af8f4d79
commit-date: 2023-01-10
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (61a415be5 2023-01-12)
binary: rustc
commit-hash: 61a415be590113b4935464ef0aaf3b4e7713a077
commit-date: 2023-01-12
host: armv7-unknown-linux-gnueabihf
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
