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
tag = ["latest", "2022-04-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust_mips64el_2022-04-16_17-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "15a2055b3718f740abd5db8a7b1ebf175994abcf37f0e5028dc631513323016d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1660023296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "210M"
zstd_bytes = 219719450

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220415"
previous_tag = "2022-04-15"
previous_file = "rust_mips64el_2022-04-15_03-09-rootfs.tar.zst"
previous_sha256 = "0e47b962cabb425274884cd671f3a9b6ce1034fbee7fd7f81db07f5e982496c2"

current_version = "latest01"
current_date = "20220416"
old_file = "rust_mips64el_2022-04-11_02-09-rootfs.tar.zst"
old_sha256 = "1254be7608efa73a1dd8b5fc1a7a5701853c26849698d78ed0c9045f2d9bb193"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-04-16_17-07-rootfs.tar.zst
# SHA256SUM=15a2055b3718f740abd5db8a7b1ebf175994abcf37f0e5028dc631513323016d
# BUILD_DATE=20220416
# BUILD_TAG=2022-04-16
# STATUS=completed
# VERSION=latest01
# END_TIME=17:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-16
begin = 2022-04-16 16:55:12.892891803+00:00
start-sync_0 = 17:01:24
start-zstd = 17:02:23
start-sync_1 = 17:07:28
end-sync_1 = 17:07:48
end = 2022-04-16 17:07:48.147760869+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.62.0-nightly (dba5baf 2022-04-13)'
rustc = 'rustc 1.62.0-nightly (3f391b845 2022-04-15)'
cc = 'cc (Debian 11.2.0-20) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (dba5baf 2022-04-13)
release: 1.62.0-nightly
commit-hash: dba5baf4345858c591517b24801902a062c399f8
commit-date: 2022-04-13
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (3f391b845 2022-04-15)
binary: rustc
commit-hash: 3f391b84552f210adec7893b50c5da74f9362ae4
commit-date: 2022-04-15
host: mips64el-unknown-linux-gnuabi64
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
