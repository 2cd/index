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
tag = ["alpine", "2022-09-26", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-09-26_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "51fcbe72a3b25755f95e0f12df1bf338b97c3e75cb73f2e067640a9df01acc0a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "777M"
tar_bytes = 813985792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157669172

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220923"
previous_tag = "2022-09-23"
previous_file = "rust-musl_arm64_2022-09-23_03-00-rootfs.tar.zst"
previous_sha256 = "e948992e1665b146e94470fd557465c9e15c3d8f127298254c29f1867a354778"

current_version = "latest02"
current_date = "20220926"
old_file = "rust-musl_arm64_2022-09-19_03-01-rootfs.tar.zst"
old_sha256 = "04f0c58e256eddc5aa8c8e8f7b4540d54e3e3f6262225f0df0713f861b287db7"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-09-26_02-59-rootfs.tar.zst
# SHA256SUM=51fcbe72a3b25755f95e0f12df1bf338b97c3e75cb73f2e067640a9df01acc0a
# BUILD_DATE=20220926
# BUILD_TAG=2022-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-26
begin = 2022-09-26 02:52:21.550205777+00:00
start-sync_0 = 02:54:25
start-zstd = 02:55:04
start-sync_1 = 02:59:40
end-sync_1 = 02:59:53
end = 2022-09-26 02:59:53.499266145+00:00

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
cargo = 'cargo 1.66.0-nightly (73ba3f35e 2022-09-18)'
rustc = 'rustc 1.66.0-nightly (f5193a9fc 2022-09-25)'
cc = 'cc (Alpine 12.1.1_git20220630-r6) 12.1.1 20220630'
cargo_verbose = '''
cargo 1.66.0-nightly (73ba3f35e 2022-09-18)
release: 1.66.0-nightly
commit-hash: 73ba3f35e0205844418260722c11602113179c4a
commit-date: 2022-09-18
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (f5193a9fc 2022-09-25)
binary: rustc
commit-hash: f5193a9fcc73dc09e41a90c5a2c97fc9acc16032
commit-date: 2022-09-25
host: aarch64-unknown-linux-musl
release: 1.66.0-nightly
LLVM version: 15.0.0
'''
```
