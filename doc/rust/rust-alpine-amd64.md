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
tag = ["alpine", "2022-04-15", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust-musl_amd64_2022-04-15_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0ccd3a8b178fba07ce0e2f0f4d3075ac5375258aaf57125014ed238cf097fd20"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "746M"
tar_bytes = 781741568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "153M"
zstd_bytes = 160306823

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "rust-musl_amd64_2022-04-11_01-59-rootfs.tar.zst"
previous_sha256 = "e8798d54e68097f8423c40640508cf885c066423fe95525111f1d7c0d74e801e"

current_version = "latest01"
current_date = "20220415"
old_file = "rust-musl_amd64_2022-04-08_01-58-rootfs.tar.zst"
old_sha256 = "abd8fe8ced4b07ba9148348a987fb1afa1ab6b61ec5f53ec2fff039cfd4b7f3b"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-04-15_03-00-rootfs.tar.zst
# SHA256SUM=0ccd3a8b178fba07ce0e2f0f4d3075ac5375258aaf57125014ed238cf097fd20
# BUILD_DATE=20220415
# BUILD_TAG=2022-04-15
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-15
begin = 2022-04-15 02:52:26.848884771+00:00
start-sync_0 = 02:53:11
start-zstd = 02:53:57
start-sync_1 = 03:00:00
end-sync_1 = 03:00:15
end = 2022-04-15 03:00:15.902058887+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.62.0-nightly (dba5baf43 2022-04-13)'
rustc = 'rustc 1.62.0-nightly (e7575f967 2022-04-14)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.62.0-nightly (dba5baf43 2022-04-13)
release: 1.62.0-nightly
commit-hash: dba5baf4345858c591517b24801902a062c399f8
commit-date: 2022-04-13
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (e7575f967 2022-04-14)
binary: rustc
commit-hash: e7575f9670f3c837def3d186ae09366c75c7632e
commit-date: 2022-04-14
host: x86_64-unknown-linux-musl
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
