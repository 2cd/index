# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-04-24", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-04-24_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0b07f54d1854dece664511c00c17701f8f3d3a8cdf8c1c3173f83ee915df4452"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1849012736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "245M"
zstd_bytes = 256462223

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230421"
previous_tag = "2023-04-21"
previous_file = "rust_arm64_2023-04-21_03-06-rootfs.tar.zst"
previous_sha256 = "fec30ceaebfc78efffa69486b7ca9802e639610a586084c769a4979e10792feb"

current_version = "latest01"
current_date = "20230424"
old_file = "rust_arm64_2023-04-07_03-07-rootfs.tar.zst"
old_sha256 = "c4368b451950306984b32fb8116fc538db7bb65d3ddae4d843685434e9cf9ff0"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-04-24_03-06-rootfs.tar.zst
# SHA256SUM=0b07f54d1854dece664511c00c17701f8f3d3a8cdf8c1c3173f83ee915df4452
# BUILD_DATE=20230424
# BUILD_TAG=2023-04-24
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-24
begin = 2023-04-24 02:52:57.812250143+00:00
start-sync_0 = 02:59:10
start-zstd = 03:00:19
start-sync_1 = 03:06:27
end-sync_1 = 03:06:50
end = 2023-04-24 03:06:50.080530786+00:00

[server]
repo = "cake233/rust-arm64"

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
cargo = 'cargo 1.71.0-nightly (de80432f0 2023-04-21)'
rustc = 'rustc 1.71.0-nightly (7f94b314c 2023-04-23)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (de80432f0 2023-04-21)
release: 1.71.0-nightly
commit-hash: de80432f04da61d98dcbbc1572598071718ccfd2
commit-date: 2023-04-21
host: aarch64-unknown-linux-gnu
libgit2: 1.6.3 (sys:0.17.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (7f94b314c 2023-04-23)
binary: rustc
commit-hash: 7f94b314cead7059a71a265a8b64905ef2511796
commit-date: 2023-04-23
host: aarch64-unknown-linux-gnu
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
