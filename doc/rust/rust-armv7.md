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
tag = ["latest", "2022-07-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2022-07-29_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "810bbc5ac3b9b8cfdbbb87684c7bb37528d2a4188029140435fb39f3c01ade31"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1885408256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "335M"
zstd_bytes = 351104034

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_armhf_2022-07-18_03-05-rootfs.tar.zst"
previous_sha256 = "aa4f2e35e46ca5c383a921e5d809c2d643d54d9f6394c63c80490e6022cac261"

current_version = "latest01"
current_date = "20220729"
old_file = "rust_armhf_2022-07-15_03-04-rootfs.tar.zst"
old_sha256 = "ca413c5db8a78fa84f0a6c8ec8adaa0a29cb389a7339265171fd1369aeeb15f5"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-07-29_03-07-rootfs.tar.zst
# SHA256SUM=810bbc5ac3b9b8cfdbbb87684c7bb37528d2a4188029140435fb39f3c01ade31
# BUILD_DATE=20220729
# BUILD_TAG=2022-07-29
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-29
begin = 2022-07-29 02:52:24.784038791+00:00
start-sync_0 = 02:59:26
start-zstd = 03:00:25
start-sync_1 = 03:07:02
end-sync_1 = 03:07:28
end = 2022-07-29 03:07:28.809216902+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (85b500cca 2022-07-24)'
rustc = 'rustc 1.64.0-nightly (9067d5277 2022-07-28)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (85b500cca 2022-07-24)
release: 1.64.0-nightly
commit-hash: 85b500ccad8cd0b63995fd94a03ddd4b83f7905b
commit-date: 2022-07-24
host: armv7-unknown-linux-gnueabihf
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (9067d5277 2022-07-28)
binary: rustc
commit-hash: 9067d5277d10f0f32a49ec9c125a33828e26a32b
commit-date: 2022-07-28
host: armv7-unknown-linux-gnueabihf
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
