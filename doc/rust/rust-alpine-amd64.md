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
tag = ["alpine", "2022-11-25", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-11-25_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "35b20df0f60cedc79dc7b30ad45ca4d161bfbbb10c2e08a84e745bac1e582e4b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "814M"
tar_bytes = 852848128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 171576710

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221121"
previous_tag = "2022-11-21"
previous_file = "rust-musl_amd64_2022-11-21_02-59-rootfs.tar.zst"
previous_sha256 = "8edf5eb8a3f530f01f6dc65bb056bee973c83d862d30b01d08a4f7fa4d24c67e"

current_version = "latest02"
current_date = "20221125"
old_file = "rust-musl_amd64_2022-11-18_03-00-rootfs.tar.zst"
old_sha256 = "3c3d0504e176614c572e115a60e8e3328cba75eb30d6d626d47945f679488635"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-11-25_02-59-rootfs.tar.zst
# SHA256SUM=35b20df0f60cedc79dc7b30ad45ca4d161bfbbb10c2e08a84e745bac1e582e4b
# BUILD_DATE=20221125
# BUILD_TAG=2022-11-25
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-25
begin = 2022-11-25 02:52:27.938224243+00:00
start-sync_0 = 02:53:26
start-zstd = 02:54:10
start-sync_1 = 02:59:26
end-sync_1 = 02:59:44
end = 2022-11-25 02:59:44.379533496+00:00

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
cargo = 'cargo 1.67.0-nightly (ba607b23d 2022-11-22)'
rustc = 'rustc 1.67.0-nightly (b3bc6bf31 2022-11-24)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (ba607b23d 2022-11-22)
release: 1.67.0-nightly
commit-hash: ba607b23db8398723d659249d9abf5536bc322e5
commit-date: 2022-11-22
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (b3bc6bf31 2022-11-24)
binary: rustc
commit-hash: b3bc6bf31265ac10946a0832092dbcedf9b26805
commit-date: 2022-11-24
host: x86_64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
