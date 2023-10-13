# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-10-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-10-13_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3e9559c59fcfb479e5815380f95c6898dd409896665e2a6a41e1970acb1ac32"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1849904640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226470644

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231009"
previous_tag = "2023-10-09"
previous_file = "rust_ppc64el_2023-10-09_03-06-rootfs.tar.zst"
previous_sha256 = "085921aa479ac641642f142b39bf28d517d45616bebb73aec805f936349ac208"

current_version = "latest02"
current_date = "20231013"
old_file = "rust_ppc64el_2023-10-06_03-06-rootfs.tar.zst"
old_sha256 = "84263f2a81f8a6736ea67b89d15c6548430b49e5cd85dd82db00a30d4ce1ffc1"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-10-13_03-06-rootfs.tar.zst
# SHA256SUM=f3e9559c59fcfb479e5815380f95c6898dd409896665e2a6a41e1970acb1ac32
# BUILD_DATE=20231013
# BUILD_TAG=2023-10-13
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-13
begin = 2023-10-13 02:52:41.177857208+00:00
start-sync_0 = 02:58:57
start-zstd = 03:00:02
start-sync_1 = 03:05:53
end-sync_1 = 03:06:16
end = 2023-10-13 03:06:16.823516556+00:00

[server]
repo = "cake233/rust-ppc64le"

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
cargo = 'cargo 1.75.0-nightly (6fa6fdc76 2023-10-10)'
rustc = 'rustc 1.75.0-nightly (e20cb7702 2023-10-12)'
cc = 'cc (Debian 13.2.0-5) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (6fa6fdc76 2023-10-10)
release: 1.75.0-nightly
commit-hash: 6fa6fdc7606cfa664f9bee2fb33ee2ed904f4e88
commit-date: 2023-10-10
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.3.0-DEV (sys:0.4.66+curl-8.3.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (e20cb7702 2023-10-12)
binary: rustc
commit-hash: e20cb7702117f1ad8127a16406ba9edd230c4f65
commit-date: 2023-10-12
host: powerpc64le-unknown-linux-gnu
release: 1.75.0-nightly
LLVM version: 17.0.2
'''
```
