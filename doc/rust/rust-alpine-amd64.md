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
tag = ["alpine", "2023-01-16", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-01-16_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1596b624bcc7c09d4777b6fd71416dc34fb2b6a59d6895619b81ebb5d95b55f1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "814M"
tar_bytes = 852687360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "165M"
zstd_bytes = 172103305

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230113"
previous_tag = "2023-01-13"
previous_file = "rust-musl_amd64_2023-01-13_02-59-rootfs.tar.zst"
previous_sha256 = "9101f0f3297868acf387cad95a73f7f22b4ac10b18dd6fa45db6137707c2a094"

current_version = "latest01"
current_date = "20230116"
old_file = "rust-musl_amd64_2023-01-09_02-59-rootfs.tar.zst"
old_sha256 = "1ad40ca26d71801d16cf151f291a72d6616ac3f0e8a6f4e87b655ad43454d62f"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-01-16_02-59-rootfs.tar.zst
# SHA256SUM=1596b624bcc7c09d4777b6fd71416dc34fb2b6a59d6895619b81ebb5d95b55f1
# BUILD_DATE=20230116
# BUILD_TAG=2023-01-16
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-16
begin = 2023-01-16 02:52:30.423863270+00:00
start-sync_0 = 02:53:23
start-zstd = 02:54:02
start-sync_1 = 02:59:14
end-sync_1 = 02:59:28
end = 2023-01-16 02:59:28.998486864+00:00

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
cargo = 'cargo 1.68.0-nightly (1cd6d3803 2023-01-12)'
rustc = 'rustc 1.68.0-nightly (9e75dddf6 2023-01-15)'
cc = 'cc (Alpine 12.2.1_git20220924-r8) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.68.0-nightly (1cd6d3803 2023-01-12)
release: 1.68.0-nightly
commit-hash: 1cd6d3803dfb0b342272862a8590f5dfc9f72573
commit-date: 2023-01-12
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (9e75dddf6 2023-01-15)
binary: rustc
commit-hash: 9e75dddf609c0201d03f9792e850f95d6a283d11
commit-date: 2023-01-15
host: x86_64-unknown-linux-musl
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
