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
tag = ["latest", "2022-01-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-01-03_03-01.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5ec18e5d351d476e114def94308c4e1494d66d6d0cb403a67cfc73c5bdb2a300"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "919M"
tar_bytes = 963359232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237180570

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211231"
previous_tag = "2021-12-31"
previous_file = "rust_armhf_2021-12-31_03-03-rootfs.tar.zst"
previous_sha256 = "b72fcb102744445ab88cd1dfdc18a4a237b59852630e0b6ed865fbfbc5c2132c"

current_version = "latest01"
current_date = "20220103"
old_file = "rust_armhf_2021-12-27_03-02-rootfs.tar.zst"
old_sha256 = "6439e7f8a161367634eff7964bff9bc000cf29333f77f41f5e22a702b2437c81"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-01-03_03-01-rootfs.tar.zst
# SHA256SUM=5ec18e5d351d476e114def94308c4e1494d66d6d0cb403a67cfc73c5bdb2a300
# BUILD_DATE=20220103
# BUILD_TAG=2022-01-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-03
begin = 2022-01-03 02:52:21.356302886+00:00
start-sync_0 = 02:57:29
start-zstd = 02:58:07
start-sync_1 = 03:01:31
end-sync_1 = 03:01:48
end = 2022-01-03 03:01:48.725676265+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.59.0-nightly (fcef61230 2021-12-17)'
rustc = 'rustc 1.59.0-nightly (8f3238f89 2022-01-02)'
cc = 'cc (Debian 11.2.0-13) 11.2.0'
cargo_verbose = '''
cargo 1.59.0-nightly (fcef61230 2021-12-17)
release: 1.59.0-nightly
commit-hash: fcef61230c3b6213b6b0d233a36ba4ebd1649ec3
commit-date: 2021-12-17
host: armv7-unknown-linux-gnueabihf
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (8f3238f89 2022-01-02)
binary: rustc
commit-hash: 8f3238f898163f09726c3d2b2cc9bafb09da26f3
commit-date: 2022-01-02
host: armv7-unknown-linux-gnueabihf
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
