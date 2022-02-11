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
tag = ["latest", "2022-02-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false

[file]
name = "rust_mips64el_2022-02-11_03-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "27aee45d19b58d42032ed732f483692b8cc029de73ed55e97dad8a1cb8d2df2e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1584601088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "204M"
zstd_bytes = 213498955

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220207"
previous_tag = "2022-02-07"
previous_file = "rust_mips64el_2022-02-07_03-08-rootfs.tar.zst"
previous_sha256 = "c315ccea25e79afff6d8ab078216f5965a045f90c3f9d3b279ff0d71f95df445"

current_version = "latest02"
current_date = "20220211"
old_file = "rust_mips64el_2022-02-04_03-07-rootfs.tar.zst"
old_sha256 = "9808623a9c79d5a1a1d22a6be549b02bd7632f296bc3cb03b6db9acf52529262"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-02-11_03-05-rootfs.tar.zst
# SHA256SUM=27aee45d19b58d42032ed732f483692b8cc029de73ed55e97dad8a1cb8d2df2e
# BUILD_DATE=20220211
# BUILD_TAG=2022-02-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-11
begin = 2022-02-11 02:52:27.823560556+00:00
start-sync_0 = 02:58:48
start-zstd = 02:59:47
start-sync_1 = 03:05:23
end-sync_1 = 03:05:46
end = 2022-02-11 03:05:46.225452519+00:00

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
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (e646f3d2a 2022-02-10)
binary: rustc
commit-hash: e646f3d2a9541952310778288854943678738ea9
commit-date: 2022-02-10
host: mips64el-unknown-linux-gnuabi64
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
