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
tag = ["alpine", "2022-12-23", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-12-23_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "001a37611c20794139fe9f479491919e1428aea05cb25c850743578a71747779"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "851M"
tar_bytes = 891322880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 161768732

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221219"
previous_tag = "2022-12-19"
previous_file = "rust-musl_arm64_2022-12-19_03-01-rootfs.tar.zst"
previous_sha256 = "c6b391a16464961068405b63f12003bd1ccb4ac22d81048088385503c75d13b9"

current_version = "latest01"
current_date = "20221223"
old_file = "rust-musl_arm64_2022-12-16_03-00-rootfs.tar.zst"
old_sha256 = "d857021bc611568f7ce759900ba73f3fabac9521ea6d5b3658b995934ef6e26f"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-12-23_02-59-rootfs.tar.zst
# SHA256SUM=001a37611c20794139fe9f479491919e1428aea05cb25c850743578a71747779
# BUILD_DATE=20221223
# BUILD_TAG=2022-12-23
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-23
begin = 2022-12-23 02:52:29.774770401+00:00
start-sync_0 = 02:54:23
start-zstd = 02:55:02
start-sync_1 = 02:59:45
end-sync_1 = 02:59:59
end = 2022-12-23 02:59:59.545079712+00:00

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
cargo = 'cargo 1.68.0-nightly (c994a4a63 2022-12-18)'
rustc = 'rustc 1.68.0-nightly (8a97b4812 2022-12-22)'
cc = 'cc (Alpine 12.2.1_git20220924-r6) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.68.0-nightly (c994a4a63 2022-12-18)
release: 1.68.0-nightly
commit-hash: c994a4a638370bc7e0ffcbb0e2865afdfa7d4415
commit-date: 2022-12-18
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (8a97b4812 2022-12-22)
binary: rustc
commit-hash: 8a97b4812a7a46bb5206487c2455b9c5bfcbd1b9
commit-date: 2022-12-22
host: aarch64-unknown-linux-musl
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
