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
tag = ["latest", "2023-12-22", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-12-22_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "27abc94020c53bdfc619f6162710e6524249649be11909d822f5546b57954a43"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1578492416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "223M"
zstd_bytes = 233596510

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_armhf_2023-11-27_03-02-rootfs.tar.zst"
previous_sha256 = "0fed4547656ffd8ba7829cb3754201131b84bb21d9852dfd826a3e5f7f445bf3"

current_version = "latest02"
current_date = "20231222"
old_file = "rust_armhf_2023-11-24_03-02-rootfs.tar.zst"
old_sha256 = "045c23aa187a1eb0db2ae0d392d33e253adfbb5eda7332c3ccf056a969e646a6"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-12-22_03-02-rootfs.tar.zst
# SHA256SUM=27abc94020c53bdfc619f6162710e6524249649be11909d822f5546b57954a43
# BUILD_DATE=20231222
# BUILD_TAG=2023-12-22
# STATUS=completed
# VERSION=latest02
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-22
begin = 2023-12-22 02:52:33.818531316+00:00
start-sync_0 = 02:57:20
start-zstd = 02:58:02
start-sync_1 = 03:01:53
end-sync_1 = 03:02:07
end = 2023-12-22 03:02:07.477439937+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.77.0-nightly (1a2666ddd 2023-12-17)'
rustc = 'rustc 1.77.0-nightly (3d0e6bed6 2023-12-21)'
cc = 'cc (Debian 13.2.0-9) 13.2.0'
cargo_verbose = '''
cargo 1.77.0-nightly (1a2666ddd 2023-12-17)
release: 1.77.0-nightly
commit-hash: 1a2666ddd14cf0a255d4ddb61c63531c259a7b39
commit-date: 2023-12-17
host: armv7-unknown-linux-gnueabihf
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.5.0-DEV (sys:0.4.70+curl-8.5.0 vendored ssl:OpenSSL/1.1.1w)
ssl: OpenSSL 1.1.1w  11 Sep 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.77.0-nightly (3d0e6bed6 2023-12-21)
binary: rustc
commit-hash: 3d0e6bed600c0175628e96f1118293cf44fb97bd
commit-date: 2023-12-21
host: armv7-unknown-linux-gnueabihf
release: 1.77.0-nightly
LLVM version: 17.0.6
'''
```
