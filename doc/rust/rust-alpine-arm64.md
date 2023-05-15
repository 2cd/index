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
tag = ["alpine", "2023-05-15", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-05-15_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fa64284162b85064e53129f976fc82eb14f53d400f9f4944515d103b9ce5da25"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "860M"
tar_bytes = 901246976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 165530298

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230512"
previous_tag = "2023-05-12"
previous_file = "rust-musl_arm64_2023-05-12_03-01-rootfs.tar.zst"
previous_sha256 = "92102c4ae5509b4acafd09fe76fdeda6a9838a60e7c219fde5abbcb1f844ee71"

current_version = "latest01"
current_date = "20230515"
old_file = "rust-musl_arm64_2023-05-08_03-02-rootfs.tar.zst"
old_sha256 = "2c63c53a1a39d01a4c45027cfb4529bed8c60c2b92ab938f0067e2e572608408"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-05-15_03-01-rootfs.tar.zst
# SHA256SUM=fa64284162b85064e53129f976fc82eb14f53d400f9f4944515d103b9ce5da25
# BUILD_DATE=20230515
# BUILD_TAG=2023-05-15
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-15
begin = 2023-05-15 02:52:53.826752368+00:00
start-sync_0 = 02:55:10
start-zstd = 02:55:59
start-sync_1 = 03:00:56
end-sync_1 = 03:01:15
end = 2023-05-15 03:01:15.058171542+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (13413c64f 2023-05-10)'
rustc = 'rustc 1.71.0-nightly (18bfe5d8a 2023-05-14)'
cc = 'cc (Alpine 13.1.1_git20230513) 13.1.1 20230513'
cargo_verbose = '''
cargo 1.71.0-nightly (13413c64f 2023-05-10)
release: 1.71.0-nightly
commit-hash: 13413c64ff88dd6c2824e9eb9374fc5f10895d28
commit-date: 2023-05-10
host: aarch64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (18bfe5d8a 2023-05-14)
binary: rustc
commit-hash: 18bfe5d8a9ca0e226171e98f8f4ef071790f3352
commit-date: 2023-05-14
host: aarch64-unknown-linux-musl
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
