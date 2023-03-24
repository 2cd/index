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
tag = ["latest", "2023-03-24", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-03-24_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0783a9e448d876a1e46840efd020f501b1eddb79e5d1b260fd6565507179e6f3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1546369536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226411325

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "rust_armhf_2023-03-20_03-03-rootfs.tar.zst"
previous_sha256 = "7a2b327e191a3a4e8c95e1b172363a6a6c1cb1ab9b4226be7d2baed8596d6bc2"

current_version = "latest01"
current_date = "20230324"
old_file = "rust_armhf_2023-03-17_03-05-rootfs.tar.zst"
old_sha256 = "e54ed1d8a7c5b01e7b6d431c1a84d70265df48295d046d6dddb3976133d07ba9"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-03-24_03-04-rootfs.tar.zst
# SHA256SUM=0783a9e448d876a1e46840efd020f501b1eddb79e5d1b260fd6565507179e6f3
# BUILD_DATE=20230324
# BUILD_TAG=2023-03-24
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-24
begin = 2023-03-24 02:52:33.067348077+00:00
start-sync_0 = 02:58:17
start-zstd = 02:59:18
start-sync_1 = 03:03:41
end-sync_1 = 03:04:05
end = 2023-03-24 03:04:05.611066219+00:00

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
cargo = 'cargo 1.70.0-nightly (15d090969 2023-03-21)'
rustc = 'rustc 1.70.0-nightly (1459b3128 2023-03-23)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (15d090969 2023-03-21)
release: 1.70.0-nightly
commit-hash: 15d090969743630bff549a1b068bcaa8174e5ee3
commit-date: 2023-03-21
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (1459b3128 2023-03-23)
binary: rustc
commit-hash: 1459b3128e288a85fcc4dd1fee7ada2cdcf28794
commit-date: 2023-03-23
host: armv7-unknown-linux-gnueabihf
release: 1.70.0-nightly
LLVM version: 15.0.7
'''
```
