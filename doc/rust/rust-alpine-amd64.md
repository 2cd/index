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
tag = ["alpine", "2023-02-17", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-02-17_10-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b5744d612e7e1bc7531a428422e232e46e7781106ed130c3740661e264be3d6c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "808M"
tar_bytes = 847218176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170713679

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230217"
previous_tag = "2023-02-17"
previous_file = "rust-musl_amd64_2023-02-17_02-59-rootfs.tar.zst"
previous_sha256 = "61041bcc99614ccd4061f4c619bdd2c034bceaf6d68ae96b4bc02df2b9a302ac"

current_version = "latest01"
current_date = "20230217"
old_file = "rust-musl_amd64_2023-02-13_03-00-rootfs.tar.zst"
old_sha256 = "f09ed0e1247a679243bebf76f2fbf5a49f6b75f28b92536b4516320a298d5c29"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-02-17_10-33-rootfs.tar.zst
# SHA256SUM=b5744d612e7e1bc7531a428422e232e46e7781106ed130c3740661e264be3d6c
# BUILD_DATE=20230217
# BUILD_TAG=2023-02-17
# STATUS=completed
# VERSION=latest01
# END_TIME=10:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-17
begin = 2023-02-17 10:25:46.589632189+00:00
start-sync_0 = 10:26:30
start-zstd = 10:27:16
start-sync_1 = 10:32:53
end-sync_1 = 10:33:09
end = 2023-02-17 10:33:09.531211991+00:00

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
rustup = 'rustup 1.25.2 (2023-02-01)'
cargo = 'cargo 1.69.0-nightly (39c13e67a 2023-02-12)'
rustc = 'rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)'
cc = 'cc (Alpine 12.2.1_git20220924-r9) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.69.0-nightly (39c13e67a 2023-02-12)
release: 1.69.0-nightly
commit-hash: 39c13e67a5962466cc7253d41bc1099bbcb224c3
commit-date: 2023-02-12
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.18_alpha20230208 [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)
binary: rustc
commit-hash: 9a7cc6c32f1a690f86827e4724bcda85e506ef35
commit-date: 2023-02-16
host: x86_64-unknown-linux-musl
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
