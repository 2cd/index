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
tag = ["alpine", "2022-01-28", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2022-01-28_02-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "bddc729bc2dc7c6a6d76a71aefa53f4788f34e6111f184f09083c66d7189ccd0"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "754M"
tar_bytes = 790572544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "172M"
zstd_bytes = 179824906

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220124"
previous_tag = "2022-01-24"
previous_file = "rust-musl_amd64_2022-01-24_02-57-rootfs.tar.zst"
previous_sha256 = "5b145239924a5dfbe827bede463bb6130f4422e300906becb3bacb28432a4a77"

current_version = "latest02"
current_date = "20220128"
old_file = "rust-musl_amd64_2022-01-14_02-56-rootfs.tar.zst"
old_sha256 = "9a1f5f0c862560e6125388d1beed24c07b5a05fda68a335878aca69b079c5359"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-01-28_02-56-rootfs.tar.zst
# SHA256SUM=bddc729bc2dc7c6a6d76a71aefa53f4788f34e6111f184f09083c66d7189ccd0
# BUILD_DATE=20220128
# BUILD_TAG=2022-01-28
# STATUS=completed
# VERSION=latest02
# END_TIME=02:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-28
begin = 2022-01-28 02:52:24.946796096+00:00
start-sync_0 = 02:53:22
start-zstd = 02:54:10
start-sync_1 = 02:56:38
end-sync_1 = 02:56:56
end = 2022-01-28 02:56:56.321683538+00:00

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.2'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.60.0-nightly (1c03475 2022-01-25)'
rustc = 'rustc 1.60.0-nightly (21b4a9cfd 2022-01-27)'
cc = 'cc (Alpine 11.2.1_git20220117) 11.2.1 20220117'
cargo_verbose = '''
cargo 1.60.0-nightly (1c03475 2022-01-25)
release: 1.60.0-nightly
commit-hash: 1c034752de0df744fcd7788fcbca158830b8bf85
commit-date: 2022-01-25
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (21b4a9cfd 2022-01-27)
binary: rustc
commit-hash: 21b4a9cfdcbb1e76f4b36b5c3cfd64d627285093
commit-date: 2022-01-27
host: x86_64-unknown-linux-musl
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
