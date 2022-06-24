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
tag = ["alpine", "2022-06-24", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-06-24_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "44d664a1a888d8602622dff2c42c6aedd252f9819d46894f7ceabe47eea2c298"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "730M"
tar_bytes = 764977664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156350656

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220620"
previous_tag = "2022-06-20"
previous_file = "rust-musl_amd64_2022-06-20_02-59-rootfs.tar.zst"
previous_sha256 = "be90cf41d8cd184a92f84f8a154ee6c2923e3353c09194944f1e0b888586da5e"

current_version = "latest02"
current_date = "20220624"
old_file = "rust-musl_amd64_2022-06-17_03-00-rootfs.tar.zst"
old_sha256 = "d5bc9cdda8f3d62a19576e667cb793a1b3be9eafbedd8933a50ba74ac051e8ea"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-06-24_02-59-rootfs.tar.zst
# SHA256SUM=44d664a1a888d8602622dff2c42c6aedd252f9819d46894f7ceabe47eea2c298
# BUILD_DATE=20220624
# BUILD_TAG=2022-06-24
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-24
begin = 2022-06-24 02:52:28.922905606+00:00
start-sync_0 = 02:53:30
start-zstd = 02:54:13
start-sync_1 = 02:58:58
end-sync_1 = 02:59:14
end = 2022-06-24 02:59:14.102542278+00:00

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
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.63.0-nightly (03a849043 2022-06-19)'
rustc = 'rustc 1.63.0-nightly (43347397f 2022-06-23)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.63.0-nightly (03a849043 2022-06-19)
release: 1.63.0-nightly
commit-hash: 03a849043e25104e8b7ad0d4a96c525787b69379
commit-date: 2022-06-19
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (43347397f 2022-06-23)
binary: rustc
commit-hash: 43347397f7c5ca9a670a3bb3890c7187e24a52ab
commit-date: 2022-06-23
host: x86_64-unknown-linux-musl
release: 1.63.0-nightly
LLVM version: 14.0.5
'''
```
