# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-02-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-02-17_10-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4240326ce6f43d4da3f973853614de1f2db064b54a4c910f4891eebf7a299659"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1865457664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "235M"
zstd_bytes = 245819229

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230217"
previous_tag = "2023-02-17"
previous_file = "rust_s390x_2023-02-17_03-06-rootfs.tar.zst"
previous_sha256 = "f590dfa787fd5ae893e73b66501936c9fde32fe48e1fcf73fd1d0568e720f04e"

current_version = "latest02"
current_date = "20230217"
old_file = "rust_s390x_2023-02-13_03-08-rootfs.tar.zst"
old_sha256 = "009baf4016eae9497ec303c8c4a4233d9725c6e491b111fe8168d24157e06832"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-02-17_10-39-rootfs.tar.zst
# SHA256SUM=4240326ce6f43d4da3f973853614de1f2db064b54a4c910f4891eebf7a299659
# BUILD_DATE=20230217
# BUILD_TAG=2023-02-17
# STATUS=completed
# VERSION=latest02
# END_TIME=10:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-17
begin = 2023-02-17 10:25:46.439822824+00:00
start-sync_0 = 10:32:05
start-zstd = 10:33:14
start-sync_1 = 10:38:56
end-sync_1 = 10:39:14
end = 2023-02-17 10:39:14.920599244+00:00

[server]
repo = "cake233/rust-s390x"

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (39c13e67a 2023-02-12)'
rustc = 'rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (39c13e67a 2023-02-12)
release: 1.69.0-nightly
commit-hash: 39c13e67a5962466cc7253d41bc1099bbcb224c3
commit-date: 2023-02-12
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)
binary: rustc
commit-hash: 9a7cc6c32f1a690f86827e4724bcda85e506ef35
commit-date: 2023-02-16
host: s390x-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
