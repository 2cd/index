# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-11-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-11-14_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a0ac289f66744e973671e7b7e7e92834ec826d18d0d63251556a5e6f083a5aa6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1594892288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "230M"
zstd_bytes = 240173308

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221111"
previous_tag = "2022-11-11"
previous_file = "rust_amd64_2022-11-11_03-00-rootfs.tar.zst"
previous_sha256 = "4db7cbab8d65c77af1b29cf95ff73a6cd6651ac8b4664cacb022e6506bd521a9"

current_version = "latest02"
current_date = "20221114"
old_file = "rust_amd64_2022-11-07_03-02-rootfs.tar.zst"
old_sha256 = "503d3398c21136920634a370d17676bff2a66b84d64a1e72737b63d1bd7aa8a5"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-11-14_02-59-rootfs.tar.zst
# SHA256SUM=a0ac289f66744e973671e7b7e7e92834ec826d18d0d63251556a5e6f083a5aa6
# BUILD_DATE=20221114
# BUILD_TAG=2022-11-14
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-14
begin = 2022-11-14 02:52:21.961485050+00:00
start-sync_0 = 02:53:44
start-zstd = 02:54:41
start-sync_1 = 02:59:10
end-sync_1 = 02:59:33
end = 2022-11-14 02:59:33.683905150+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (a3dfea71c 2022-11-11)'
rustc = 'rustc 1.67.0-nightly (e631891f7 2022-11-13)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (a3dfea71c 2022-11-11)
release: 1.67.0-nightly
commit-hash: a3dfea71ca0c888a88111086898aa833c291d497
commit-date: 2022-11-11
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (e631891f7 2022-11-13)
binary: rustc
commit-hash: e631891f7ad40eac3ef58ec3c2b57ecd81e40615
commit-date: 2022-11-13
host: x86_64-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
