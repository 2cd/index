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
tag = ["latest", "2022-11-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2022-11-28_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c392a580738283c52ac692b2616dca3d32f90bf35633b989f195f5f064261ee"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1562637824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227859782

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221125"
previous_tag = "2022-11-25"
previous_file = "rust_armhf_2022-11-25_03-06-rootfs.tar.zst"
previous_sha256 = "0a0b8306e4f2916227dc278b45cb9df5bfc3b287df2bb47d7d0591eb5e561706"

current_version = "latest02"
current_date = "20221128"
old_file = "rust_armhf_2022-11-21_03-05-rootfs.tar.zst"
old_sha256 = "ff9775ced194659e98a019baa53cc26f3fd34c4e97e0e713601fe099501e0e04"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-11-28_03-01-rootfs.tar.zst
# SHA256SUM=1c392a580738283c52ac692b2616dca3d32f90bf35633b989f195f5f064261ee
# BUILD_DATE=20221128
# BUILD_TAG=2022-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-28
begin = 2022-11-28 02:52:24.757729711+00:00
start-sync_0 = 02:56:55
start-zstd = 02:57:39
start-sync_1 = 03:01:20
end-sync_1 = 03:01:35
end = 2022-11-28 03:01:35.900877214+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (ba607b23d 2022-11-22)'
rustc = 'rustc 1.67.0-nightly (1eb62b123 2022-11-27)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (ba607b23d 2022-11-22)
release: 1.67.0-nightly
commit-hash: ba607b23db8398723d659249d9abf5536bc322e5
commit-date: 2022-11-22
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (1eb62b123 2022-11-27)
binary: rustc
commit-hash: 1eb62b1235fd77200e6bd967d70e83c0f2497233
commit-date: 2022-11-27
host: armv7-unknown-linux-gnueabihf
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
