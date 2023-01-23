# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-01-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2023-01-23_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "204663ff038ade7d01dadfa422be47660c04d8d27ea583e4ce48c6133e5096b8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1665590784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 201880825

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230116"
previous_tag = "2023-01-16"
previous_file = "rust_mips64el_2023-01-16_03-07-rootfs.tar.zst"
previous_sha256 = "16fca4aff0399d01ed83cd91cfa9e099e8488afd0f9147b088b72e41277d9614"

current_version = "latest01"
current_date = "20230123"
old_file = "rust_mips64el_2023-01-09_03-06-rootfs.tar.zst"
old_sha256 = "d9af3c36b360e5f27bc7ec120b2799c4d7c3f041eb9860fb29a6144b1ee272ab"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2023-01-23_03-04-rootfs.tar.zst
# SHA256SUM=204663ff038ade7d01dadfa422be47660c04d8d27ea583e4ce48c6133e5096b8
# BUILD_DATE=20230123
# BUILD_TAG=2023-01-23
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-23
begin = 2023-01-23 02:52:27.139431409+00:00
start-sync_0 = 02:58:40
start-zstd = 02:59:39
start-sync_1 = 03:04:38
end-sync_1 = 03:04:56
end = 2023-01-23 03:04:56.102414508+00:00

[server]
repo = "cake233/rust-mips64le"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.69.0-nightly (985d561f0 2023-01-20)'
rustc = 'rustc 1.69.0-nightly (5e37043d6 2023-01-22)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (985d561f0 2023-01-20)
release: 1.69.0-nightly
commit-hash: 985d561f0bb9b76ec043a2b12511790ec7a2b954
commit-date: 2023-01-20
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.1 (sys:0.16.1 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (5e37043d6 2023-01-22)
binary: rustc
commit-hash: 5e37043d63bfe2f3be8fa5a05b07d6c0dad5775d
commit-date: 2023-01-22
host: mips64el-unknown-linux-gnuabi64
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
