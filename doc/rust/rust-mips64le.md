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
tag = ["latest", "2022-10-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-10-17_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2b41cc833108a630f6dc2db6d0469cae1c26d22e6d8d77dea0fc0a6edf48373f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1695581184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220824613

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221014"
previous_tag = "2022-10-14"
previous_file = "rust_mips64el_2022-10-14_03-05-rootfs.tar.zst"
previous_sha256 = "9753d62a9f4c8cbcf54887d6c656600b80d1c0f04632a52542b39ee16d4c7093"

current_version = "latest02"
current_date = "20221017"
old_file = "rust_mips64el_2022-10-10_03-05-rootfs.tar.zst"
old_sha256 = "7daed8909bc17a624a31185bc34cf20c355e0cf39d03fdd76e34dc4ab57e519e"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-10-17_03-08-rootfs.tar.zst
# SHA256SUM=2b41cc833108a630f6dc2db6d0469cae1c26d22e6d8d77dea0fc0a6edf48373f
# BUILD_DATE=20221017
# BUILD_TAG=2022-10-17
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-17
begin = 2022-10-17 02:52:27.595618856+00:00
start-sync_0 = 03:00:38
start-zstd = 03:01:45
start-sync_1 = 03:08:05
end-sync_1 = 03:08:28
end = 2022-10-17 03:08:28.790541438+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (b332991a5 2022-10-13)'
rustc = 'rustc 1.66.0-nightly (b8b5caee0 2022-10-16)'
cc = 'cc (Debian 12.2.0-3) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (b332991a5 2022-10-13)
release: 1.66.0-nightly
commit-hash: b332991a57c9d055f1864de1eed93e2178d49440
commit-date: 2022-10-13
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (b8b5caee0 2022-10-16)
binary: rustc
commit-hash: b8b5caee04116c7383eb1c6470fcf15c437a60d4
commit-date: 2022-10-16
host: mips64el-unknown-linux-gnuabi64
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
