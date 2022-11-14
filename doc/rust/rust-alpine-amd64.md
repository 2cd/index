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
tag = ["alpine", "2022-11-14", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-11-14_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1ef743dbf088881c0690d61ec256e0210b0a9f6514b7edde88e8758b88525563"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "811M"
tar_bytes = 849850368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 170927458

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221111"
previous_tag = "2022-11-11"
previous_file = "rust-musl_amd64_2022-11-11_02-59-rootfs.tar.zst"
previous_sha256 = "a0987dcd8095a3068ce1fed5c1f5410f8b1ffcf34e5be17597d54da2d14427d9"

current_version = "latest01"
current_date = "20221114"
old_file = "rust-musl_amd64_2022-11-07_02-59-rootfs.tar.zst"
old_sha256 = "d07ca9368f026e0131fa2ad27a7ac97b54c24b619b0832e330b4345db1fb82ca"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-11-14_02-59-rootfs.tar.zst
# SHA256SUM=1ef743dbf088881c0690d61ec256e0210b0a9f6514b7edde88e8758b88525563
# BUILD_DATE=20221114
# BUILD_TAG=2022-11-14
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-14
begin = 2022-11-14 02:52:25.159325489+00:00
start-sync_0 = 02:53:35
start-zstd = 02:54:20
start-sync_1 = 02:59:14
end-sync_1 = 02:59:30
end = 2022-11-14 02:59:30.801456964+00:00

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
cargo = 'cargo 1.67.0-nightly (a3dfea71c 2022-11-11)'
rustc = 'rustc 1.67.0-nightly (e631891f7 2022-11-13)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (a3dfea71c 2022-11-11)
release: 1.67.0-nightly
commit-hash: a3dfea71ca0c888a88111086898aa833c291d497
commit-date: 2022-11-11
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (e631891f7 2022-11-13)
binary: rustc
commit-hash: e631891f7ad40eac3ef58ec3c2b57ecd81e40615
commit-date: 2022-11-13
host: x86_64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
