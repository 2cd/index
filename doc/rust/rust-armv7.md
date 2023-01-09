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
tag = ["latest", "2023-01-09", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-01-09_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "94e733340d9332ce74cb3f8be2b24593ce06bba80a2b3bcdd7f9d06d2ee5a66b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1565522432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 226801958

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230106"
previous_tag = "2023-01-06"
previous_file = "rust_armhf_2023-01-06_03-08-rootfs.tar.zst"
previous_sha256 = "efe93d64c259bdba13fbce7e7028079e7f79fbf932996d5487aac82a34eec2b5"

current_version = "latest02"
current_date = "20230109"
old_file = "rust_armhf_2023-01-02_03-03-rootfs.tar.zst"
old_sha256 = "3996d961b9f94273fdc29038b2d660f0de886e281805503f55e97db095f73a36"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-01-09_03-08-rootfs.tar.zst
# SHA256SUM=94e733340d9332ce74cb3f8be2b24593ce06bba80a2b3bcdd7f9d06d2ee5a66b
# BUILD_DATE=20230109
# BUILD_TAG=2023-01-09
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-09
begin = 2023-01-09 02:52:27.510178395+00:00
start-sync_0 = 03:01:36
start-zstd = 03:02:43
start-sync_1 = 03:07:44
end-sync_1 = 03:08:07
end = 2023-01-09 03:08:07.286702303+00:00

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
cargo = 'cargo 1.68.0-nightly (8c460b223 2023-01-04)'
rustc = 'rustc 1.68.0-nightly (cc47b0699 2023-01-08)'
cc = 'cc (Debian 12.2.0-13) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (8c460b223 2023-01-04)
release: 1.68.0-nightly
commit-hash: 8c460b2237a6359a7e3335890db8da049bdd62fc
commit-date: 2023-01-04
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (cc47b0699 2023-01-08)
binary: rustc
commit-hash: cc47b069983292e4ee8982d5dabe6301452c5f25
commit-date: 2023-01-08
host: armv7-unknown-linux-gnueabihf
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
