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
tag = ["latest", "2023-06-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-06-23_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "974a05034abb1f4d73411dd2bb7c0060dc4edfaa9ef4c19dd9decf8f92eb714d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1525791744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227899293

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230619"
previous_tag = "2023-06-19"
previous_file = "rust_armhf_2023-06-19_03-03-rootfs.tar.zst"
previous_sha256 = "786dbbc4210e51340bc2f92fe844b319ea6deb55c1542e65e4e1ad730d01c2b7"

current_version = "latest02"
current_date = "20230623"
old_file = "rust_armhf_2023-06-16_03-04-rootfs.tar.zst"
old_sha256 = "5356d3f30179437800e3de63ca73278c96e14e2f8fbf4330563400a1f6f9878a"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-06-23_03-05-rootfs.tar.zst
# SHA256SUM=974a05034abb1f4d73411dd2bb7c0060dc4edfaa9ef4c19dd9decf8f92eb714d
# BUILD_DATE=20230623
# BUILD_TAG=2023-06-23
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-23
begin = 2023-06-23 02:52:38.459906688+00:00
start-sync_0 = 02:59:28
start-zstd = 03:00:23
start-sync_1 = 03:04:55
end-sync_1 = 03:05:14
end = 2023-06-23 03:05:14.737929317+00:00

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
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (dead4b874 2023-06-20)'
rustc = 'rustc 1.72.0-nightly (065a1f5df 2023-06-21)'
cc = 'cc (Debian 12.3.0-4) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (dead4b874 2023-06-20)
release: 1.72.0-nightly
commit-hash: dead4b8740c4b6a8ed5211e37c99cf81d01c3b1c
commit-date: 2023-06-20
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (065a1f5df 2023-06-21)
binary: rustc
commit-hash: 065a1f5df9c2f1d93269e4d25a2acabbddb0db8d
commit-date: 2023-06-21
host: armv7-unknown-linux-gnueabihf
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
