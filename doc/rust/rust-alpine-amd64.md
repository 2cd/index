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
tag = ["alpine", "2023-07-28", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-07-28_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c17fcba64cd44455a782869a5d6d8eff19b1dee7f11a1434aa7c0f74236729aa"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "820M"
tar_bytes = 859804160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169778749

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "rust-musl_amd64_2023-07-24_02-59-rootfs.tar.zst"
previous_sha256 = "a12fe5a1ca951c51963c8c888c931622f2f660b09c5a28a485c8615d95051f70"

current_version = "latest02"
current_date = "20230728"
old_file = "rust-musl_amd64_2023-07-21_03-00-rootfs.tar.zst"
old_sha256 = "279b7e8aaffa5311b81fa5f945eca5b2dea58d7c3c9c67f178574440aa3b48c6"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-07-28_02-59-rootfs.tar.zst
# SHA256SUM=c17fcba64cd44455a782869a5d6d8eff19b1dee7f11a1434aa7c0f74236729aa
# BUILD_DATE=20230728
# BUILD_TAG=2023-07-28
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-28
begin = 2023-07-28 02:52:31.692309071+00:00
start-sync_0 = 02:53:20
start-zstd = 02:54:04
start-sync_1 = 02:58:55
end-sync_1 = 02:59:11
end = 2023-07-28 02:59:11.894574021+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (2023-04-05)'
cargo = 'cargo 1.73.0-nightly (7ac9416d8 2023-07-24)'
rustc = 'rustc 1.73.0-nightly (500647fd8 2023-07-27)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.73.0-nightly (7ac9416d8 2023-07-24)
release: 1.73.0-nightly
commit-hash: 7ac9416d82cd4fc5e707c9ec3574d22dff6466e5
commit-date: 2023-07-24
host: x86_64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (500647fd8 2023-07-27)
binary: rustc
commit-hash: 500647fd8138cc09e87edb08d62f81654fbf6ef8
commit-date: 2023-07-27
host: x86_64-unknown-linux-musl
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
