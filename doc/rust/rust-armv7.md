# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

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
    cake233/rust-armv7 \
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
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-04-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-04-07_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b32d3d474b7fe4a01d1048cd54e7a3562141471d1e8facd27f7777d96a7ca1cc"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1547830272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227980781

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230403"
previous_tag = "2023-04-03"
previous_file = "rust_armhf_2023-04-03_03-03-rootfs.tar.zst"
previous_sha256 = "546dbb73bfa83b2ef0934868f3b8b923923f6ce51caa119895fe8dc116fed8d0"

current_version = "latest01"
current_date = "20230407"
old_file = "rust_armhf_2023-03-31_03-07-rootfs.tar.zst"
old_sha256 = "0e1a74c808a0d94b5c2fad0a5214f05208c39549d1cd5a355c60a267799e2b62"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-04-07_03-06-rootfs.tar.zst
# SHA256SUM=b32d3d474b7fe4a01d1048cd54e7a3562141471d1e8facd27f7777d96a7ca1cc
# BUILD_DATE=20230407
# BUILD_TAG=2023-04-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-07
begin = 2023-04-07 02:52:30.848555468+00:00
start-sync_0 = 02:59:37
start-zstd = 03:00:43
start-sync_1 = 03:05:58
end-sync_1 = 03:06:20
end = 2023-04-07 03:06:20.158449248+00:00

[server]
repo = "cake233/rust-armv7"

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.70.0-nightly (0e474cfd7 2023-03-31)'
rustc = 'rustc 1.70.0-nightly (28a29282f 2023-04-06)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (0e474cfd7 2023-03-31)
release: 1.70.0-nightly
commit-hash: 0e474cfd7b16b018cf46e95da3f6a5b2f1f6a9e7
commit-date: 2023-03-31
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (28a29282f 2023-04-06)
binary: rustc
commit-hash: 28a29282f6dde2e4aba6e1e4cfea5c9430a00217
commit-date: 2023-04-06
host: armv7-unknown-linux-gnueabihf
release: 1.70.0-nightly
LLVM version: 16.0.2
'''
```
