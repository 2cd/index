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
tag = ["latest", "2022-02-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-02-11_03-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "27bca8ca1fc69377b871b2c47f9c894c2eaf13fe365e89e887f68fbf5f8ad446"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1494333952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "230M"
zstd_bytes = 240783147

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220207"
previous_tag = "2022-02-07"
previous_file = "rust_armhf_2022-02-07_03-04-rootfs.tar.zst"
previous_sha256 = "bed12768238f9ce323ec2f078ad611dcead7b6814ada8723d3d97f8532a395ab"

current_version = "latest01"
current_date = "20220211"
old_file = "rust_armhf_2022-02-04_03-03-rootfs.tar.zst"
old_sha256 = "251699756a6d12a698f4717bbc1fef6cd1c33ef5bbca75fdd59fb71358cd71e5"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-02-11_03-04-rootfs.tar.zst
# SHA256SUM=27bca8ca1fc69377b871b2c47f9c894c2eaf13fe365e89e887f68fbf5f8ad446
# BUILD_DATE=20220211
# BUILD_TAG=2022-02-11
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-11
begin = 2022-02-11 02:52:28.105086343+00:00
start-sync_0 = 02:58:23
start-zstd = 02:59:16
start-sync_1 = 03:03:41
end-sync_1 = 03:04:01
end = 2022-02-11 03:04:01.805978031+00:00

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (c082648 2022-02-08)'
rustc = 'rustc 1.60.0-nightly (e646f3d2a 2022-02-10)'
cc = 'cc (Debian 11.2.0-16) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (c082648 2022-02-08)
release: 1.60.0-nightly
commit-hash: c082648646cbb2be266df9ecbcdc253058158d68
commit-date: 2022-02-08
host: armv7-unknown-linux-gnueabihf
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (e646f3d2a 2022-02-10)
binary: rustc
commit-hash: e646f3d2a9541952310778288854943678738ea9
commit-date: 2022-02-10
host: armv7-unknown-linux-gnueabihf
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
