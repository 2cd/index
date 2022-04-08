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
tag = ["latest", "2022-04-08", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false

[file]
name = "rust_mips64el_2022-04-08_02-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "83cd75130f9d27277737136cb4e15f188fc8fe79446052161c97583a79ab4fe8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1660346368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220647558

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "rust_mips64el_2022-04-04_02-05-rootfs.tar.zst"
previous_sha256 = "f45dc2b7c834c5830d21f30d1959922e6a6b22ae8ab6a8f527e911307dc43187"

current_version = "latest02"
current_date = "20220408"
old_file = "rust_mips64el_2022-04-01_02-05-rootfs.tar.zst"
old_sha256 = "8b029293c97af1941f2b2d7aed9737caa86b76e8ea453756eb7e6bb3956b434f"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-04-08_02-07-rootfs.tar.zst
# SHA256SUM=83cd75130f9d27277737136cb4e15f188fc8fe79446052161c97583a79ab4fe8
# BUILD_DATE=20220408
# BUILD_TAG=2022-04-08
# STATUS=completed
# VERSION=latest02
# END_TIME=02:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-08
begin = 2022-04-08 01:52:30.223273822+00:00
start-sync_0 = 01:59:57
start-zstd = 02:01:06
start-sync_1 = 02:07:28
end-sync_1 = 02:07:48
end = 2022-04-08 02:07:48.358505243+00:00

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
cargo = 'cargo 1.62.0-nightly (e2e2ddd 2022-04-05)'
rustc = 'rustc 1.62.0-nightly (e745b4ddb 2022-04-07)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (e2e2ddd 2022-04-05)
release: 1.62.0-nightly
commit-hash: e2e2dddebe66dfc1403a312653557e332445308b
commit-date: 2022-04-05
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (e745b4ddb 2022-04-07)
binary: rustc
commit-hash: e745b4ddbd05026c75aae4506aef39fdfe1603c5
commit-date: 2022-04-07
host: mips64el-unknown-linux-gnuabi64
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
