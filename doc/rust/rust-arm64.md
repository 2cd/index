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
tag = ["latest", "2023-06-02", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-06-02_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "23b3e7f39262b4b1ae4e72ea7faff61a5ee81c8cdc89886c73fd1f062cc8f53b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1857374720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 253837314

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230529"
previous_tag = "2023-05-29"
previous_file = "rust_arm64_2023-05-29_03-05-rootfs.tar.zst"
previous_sha256 = "3511da09ce8549ce38967e514642716eb335873888b47557130227a58f0cbae3"

current_version = "latest02"
current_date = "20230602"
old_file = "rust_arm64_2023-05-22_03-05-rootfs.tar.zst"
old_sha256 = "bab6418666a7f470883ad65cfb547e43a452c3822378b92e43c9d5f7baaf6d78"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-06-02_03-05-rootfs.tar.zst
# SHA256SUM=23b3e7f39262b4b1ae4e72ea7faff61a5ee81c8cdc89886c73fd1f062cc8f53b
# BUILD_DATE=20230602
# BUILD_TAG=2023-06-02
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-02
begin = 2023-06-02 02:52:32.272152788+00:00
start-sync_0 = 02:58:25
start-zstd = 02:59:34
start-sync_1 = 03:05:02
end-sync_1 = 03:05:21
end = 2023-06-02 03:05:21.385575905+00:00

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
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (f7b95e316 2023-05-30)'
rustc = 'rustc 1.72.0-nightly (d59363ad0 2023-06-01)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.72.0-nightly (f7b95e316 2023-05-30)
release: 1.72.0-nightly
commit-hash: f7b95e31642e09c2b6eabb18ed75007dda6677a0
commit-date: 2023-05-30
host: aarch64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (d59363ad0 2023-06-01)
binary: rustc
commit-hash: d59363ad0b6391b7fc5bbb02c9ccf9300eef3753
commit-date: 2023-06-01
host: aarch64-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.4
'''
```
