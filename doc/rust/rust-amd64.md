# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-09-12", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-09-12_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aa91c818fd8f1083dfdbff28101deb6eb0efefdc6f0646ca4fd19ba3fd6b7a7b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1662327808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258955998

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220909"
previous_tag = "2022-09-09"
previous_file = "rust_amd64_2022-09-09_03-02-rootfs.tar.zst"
previous_sha256 = "8c847a9422556b68809d5387c1d4469505fc8917c3f4e5e80cd2e63563338ef1"

current_version = "latest02"
current_date = "20220912"
old_file = "rust_amd64_2022-09-05_03-01-rootfs.tar.zst"
old_sha256 = "f68c9094f767c8a5f3069c140a5dfc8b87ef25d8b772fcfce3e9a11cfe02a2b9"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-09-12_02-59-rootfs.tar.zst
# SHA256SUM=aa91c818fd8f1083dfdbff28101deb6eb0efefdc6f0646ca4fd19ba3fd6b7a7b
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 02:52:22.238389270+00:00
start-sync_0 = 02:53:57
start-zstd = 02:54:52
start-sync_1 = 02:59:39
end-sync_1 = 02:59:58
end = 2022-09-12 02:59:58.773478353+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.34-8) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (646e9a0b9 2022-09-02)'
rustc = 'rustc 1.65.0-nightly (59e7a308e 2022-09-11)'
cc = 'cc (Debian 12.2.0-2) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (646e9a0b9 2022-09-02)
release: 1.65.0-nightly
commit-hash: 646e9a0b9ea8354cc409d05f10e8dc752c5de78e
commit-date: 2022-09-02
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (59e7a308e 2022-09-11)
binary: rustc
commit-hash: 59e7a308e40fbc6b0901c9a8ee8ed51b17f9e772
commit-date: 2022-09-11
host: x86_64-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
