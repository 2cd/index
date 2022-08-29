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
tag = ["latest", "2022-08-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-08-29_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7320fbec174c31b463a10a49c45847def2090551dba963d5f45d36c301261535"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1673795584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226323004

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220826"
previous_tag = "2022-08-26"
previous_file = "rust_mips64el_2022-08-26_03-06-rootfs.tar.zst"
previous_sha256 = "3f9e675ee8a0e002569434294ba10407a0fcf50d7c411683b3c72cc1e69125d2"

current_version = "latest02"
current_date = "20220829"
old_file = "rust_mips64el_2022-08-22_03-12-rootfs.tar.zst"
old_sha256 = "3d1a442e568eaf3d27f0f95f61618b3ea6b9f0b43fa3fac57d6a48b6aa051384"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-08-29_03-05-rootfs.tar.zst
# SHA256SUM=7320fbec174c31b463a10a49c45847def2090551dba963d5f45d36c301261535
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 02:52:20.445162361+00:00
start-sync_0 = 02:58:46
start-zstd = 02:59:42
start-sync_1 = 03:05:18
end-sync_1 = 03:05:36
end = 2022-08-29 03:05:36.936641831+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (6da726708 2022-08-23)'
rustc = 'rustc 1.65.0-nightly (ce36e8825 2022-08-28)'
cc = 'cc (Debian 12.2.0-1) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (6da726708 2022-08-23)
release: 1.65.0-nightly
commit-hash: 6da726708a4406f31f996d813790818dce837161
commit-date: 2022-08-23
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (ce36e8825 2022-08-28)
binary: rustc
commit-hash: ce36e88256f09078519f8bc6b21e4dc88f88f523
commit-date: 2022-08-28
host: mips64el-unknown-linux-gnuabi64
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
