# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-07-18", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-07-18_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e4b2c9dbb5e8db4148ff31ef5c89b5a2a75083f215f049990066adc58180078f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "754M"
tar_bytes = 789615104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 162799610

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220715"
previous_tag = "2022-07-15"
previous_file = "rust-musl_amd64_2022-07-15_02-59-rootfs.tar.zst"
previous_sha256 = "6abb66a72a910804a5c49a30e4a00aea63c100a847c8709bc109af72f2bbf413"

current_version = "latest01"
current_date = "20220718"
old_file = "rust-musl_amd64_2022-07-11_03-00-rootfs.tar.zst"
old_sha256 = "7bcb9e6bb4056720fb90152c50ac1cbedc896833782437d90c15ac4d7b2efa01"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-07-18_03-00-rootfs.tar.zst
# SHA256SUM=e4b2c9dbb5e8db4148ff31ef5c89b5a2a75083f215f049990066adc58180078f
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 02:52:34.564385921+00:00
start-sync_0 = 02:53:22
start-zstd = 02:54:16
start-sync_1 = 02:59:53
end-sync_1 = 03:00:13
end = 2022-07-18 03:00:13.851623477+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.25.1 (2022-07-12)'
cargo = 'cargo 1.64.0-nightly (8827baaa7 2022-07-14)'
rustc = 'rustc 1.64.0-nightly (263edd43c 2022-07-17)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.64.0-nightly (8827baaa7 2022-07-14)
release: 1.64.0-nightly
commit-hash: 8827baaa781b37872134c1ba692a6f0aeb37890e
commit-date: 2022-07-14
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (263edd43c 2022-07-17)
binary: rustc
commit-hash: 263edd43c5255084292329423c61a9d69715ebfa
commit-date: 2022-07-17
host: x86_64-unknown-linux-musl
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
