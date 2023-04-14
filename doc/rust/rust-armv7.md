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
tag = ["latest", "2023-04-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-04-14_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cdf04c5d48642d79094bdba4d145e4327a2c401a04bf9d9c9f814194f8b58fa0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1532545536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227661147

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230410"
previous_tag = "2023-04-10"
previous_file = "rust_armhf_2023-04-10_03-06-rootfs.tar.zst"
previous_sha256 = "9d73c4f6b1492496d69a22be32c1360ee427ecb292a6d824f0d0a0094541957a"

current_version = "latest01"
current_date = "20230414"
old_file = "rust_armhf_2023-04-07_03-06-rootfs.tar.zst"
old_sha256 = "b32d3d474b7fe4a01d1048cd54e7a3562141471d1e8facd27f7777d96a7ca1cc"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-04-14_03-04-rootfs.tar.zst
# SHA256SUM=cdf04c5d48642d79094bdba4d145e4327a2c401a04bf9d9c9f814194f8b58fa0
# BUILD_DATE=20230414
# BUILD_TAG=2023-04-14
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-14
begin = 2023-04-14 02:52:31.011254115+00:00
start-sync_0 = 02:58:19
start-zstd = 02:59:16
start-sync_1 = 03:04:00
end-sync_1 = 03:04:20
end = 2023-04-14 03:04:20.282348290+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.70.0-nightly (7bf43f028 2023-04-10)'
rustc = 'rustc 1.70.0-nightly (a41fc00ea 2023-04-13)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (7bf43f028 2023-04-10)
release: 1.70.0-nightly
commit-hash: 7bf43f028ba5eb1f4d70d271c2546c38512c9875
commit-date: 2023-04-10
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.3 (sys:0.17.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (a41fc00ea 2023-04-13)
binary: rustc
commit-hash: a41fc00eaf352541008965fec0dee811e44373b3
commit-date: 2023-04-13
host: armv7-unknown-linux-gnueabihf
release: 1.70.0-nightly
LLVM version: 16.0.2
'''
```
