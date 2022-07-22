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
tag = ["alpine", "2022-07-22", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-07-22_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bb1aecd82d853b9419455db14339f8f8715e0354820ab6a8ec5bddb418e9e2d5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "769M"
tar_bytes = 806099456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156189614

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust-musl_arm64_2022-07-18_03-01-rootfs.tar.zst"
previous_sha256 = "111e61e4abbf16d13070dddb22a833d7a8b8b838ed5523f6b06b5f28fdaf4db7"

current_version = "latest01"
current_date = "20220722"
old_file = "rust-musl_arm64_2022-07-15_03-00-rootfs.tar.zst"
old_sha256 = "62cb52291cc239a8d90765767240c6689654cfa6d04b34ad2723887c340bd423"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-07-22_02-59-rootfs.tar.zst
# SHA256SUM=bb1aecd82d853b9419455db14339f8f8715e0354820ab6a8ec5bddb418e9e2d5
# BUILD_DATE=20220722
# BUILD_TAG=2022-07-22
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-22
begin = 2022-07-22 02:52:25.671464351+00:00
start-sync_0 = 02:54:16
start-zstd = 02:54:57
start-sync_1 = 02:59:27
end-sync_1 = 02:59:41
end = 2022-07-22 02:59:41.695303444+00:00

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
cargo = 'cargo 1.64.0-nightly (d8d30a753 2022-07-19)'
rustc = 'rustc 1.64.0-nightly (62b272d25 2022-07-21)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.64.0-nightly (d8d30a753 2022-07-19)
release: 1.64.0-nightly
commit-hash: d8d30a75376f78bb0fabe3d28ee9d87aa8035309
commit-date: 2022-07-19
host: aarch64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (62b272d25 2022-07-21)
binary: rustc
commit-hash: 62b272d25c5bb8b6bb8ac73797d82b8b9a1eabda
commit-date: 2022-07-21
host: aarch64-unknown-linux-musl
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
