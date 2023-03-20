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
tag = ["latest", "2023-03-20", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-03-20_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7a2b327e191a3a4e8c95e1b172363a6a6c1cb1ab9b4226be7d2baed8596d6bc2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1544061952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225683921

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230317"
previous_tag = "2023-03-17"
previous_file = "rust_armhf_2023-03-17_03-05-rootfs.tar.zst"
previous_sha256 = "e54ed1d8a7c5b01e7b6d431c1a84d70265df48295d046d6dddb3976133d07ba9"

current_version = "latest02"
current_date = "20230320"
old_file = "rust_armhf_2023-03-13_03-05-rootfs.tar.zst"
old_sha256 = "8d6a2891020cd085ab24cec6f55da9efc10e39944546058287c18bfae3153a1d"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-03-20_03-03-rootfs.tar.zst
# SHA256SUM=7a2b327e191a3a4e8c95e1b172363a6a6c1cb1ab9b4226be7d2baed8596d6bc2
# BUILD_DATE=20230320
# BUILD_TAG=2023-03-20
# STATUS=completed
# VERSION=latest02
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-20
begin = 2023-03-20 02:52:29.827726373+00:00
start-sync_0 = 02:58:12
start-zstd = 02:59:06
start-sync_1 = 03:03:29
end-sync_1 = 03:03:46
end = 2023-03-20 03:03:46.773586469+00:00

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
cargo = 'cargo 1.70.0-nightly (4a3c588b1 2023-03-14)'
rustc = 'rustc 1.70.0-nightly (da7c50c08 2023-03-19)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (4a3c588b1 2023-03-14)
release: 1.70.0-nightly
commit-hash: 4a3c588b1f0a8e2dc8dd8789dbf3b6a71b02ed49
commit-date: 2023-03-14
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (da7c50c08 2023-03-19)
binary: rustc
commit-hash: da7c50c089d5db2d3ebaf227fe075bb1346bfaec
commit-date: 2023-03-19
host: armv7-unknown-linux-gnueabihf
release: 1.70.0-nightly
LLVM version: 15.0.7
'''
```
