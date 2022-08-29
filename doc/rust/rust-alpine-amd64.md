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
tag = ["alpine", "2022-08-29", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-08-29_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a582db03fd8b286f369c15f56081d6e4abd07585376c58c3f06400758c224701"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "789M"
tar_bytes = 826989056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169244463

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220826"
previous_tag = "2022-08-26"
previous_file = "rust-musl_amd64_2022-08-26_02-59-rootfs.tar.zst"
previous_sha256 = "f2e06a45bc71f8571223ab5d6442dda2caa49c865b2b6a6e77f5f87adb7c20b3"

current_version = "latest01"
current_date = "20220829"
old_file = "rust-musl_amd64_2022-08-22_03-00-rootfs.tar.zst"
old_sha256 = "1b5905fae18bed8ac334dfd7e948ad9de1ab98be457247d25298b1c46451814d"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-08-29_03-00-rootfs.tar.zst
# SHA256SUM=a582db03fd8b286f369c15f56081d6e4abd07585376c58c3f06400758c224701
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 02:52:20.123842350+00:00
start-sync_0 = 02:53:34
start-zstd = 02:54:15
start-sync_1 = 02:59:49
end-sync_1 = 03:00:06
end = 2022-08-29 03:00:06.650523484+00:00

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
cargo = 'cargo 1.65.0-nightly (6da726708 2022-08-23)'
rustc = 'rustc 1.65.0-nightly (ce36e8825 2022-08-28)'
cc = 'cc (Alpine 12.1.1_git20220630) 12.1.1 20220630'
cargo_verbose = '''
cargo 1.65.0-nightly (6da726708 2022-08-23)
release: 1.65.0-nightly
commit-hash: 6da726708a4406f31f996d813790818dce837161
commit-date: 2022-08-23
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (ce36e8825 2022-08-28)
binary: rustc
commit-hash: ce36e88256f09078519f8bc6b21e4dc88f88f523
commit-date: 2022-08-28
host: x86_64-unknown-linux-musl
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
