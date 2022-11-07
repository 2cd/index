# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-11-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2022-11-07_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "381f28ec05ca3d94487c4f8f005e57249b0a0006ba178e8898c6fb3897d5ec3c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1823553024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "248M"
zstd_bytes = 259963928

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221104"
previous_tag = "2022-11-04"
previous_file = "rust_s390x_2022-11-04_03-05-rootfs.tar.zst"
previous_sha256 = "fe5d4b8a2f7c9336fe14ea41b8b940590631b9cf10f259cfe5b2a7855208b344"

current_version = "latest01"
current_date = "20221107"
old_file = "rust_s390x_2022-10-31_03-07-rootfs.tar.zst"
old_sha256 = "fea0a82d37ec14a1dcd4566d2aef6c6784c51045ffe789279b449f4a73747440"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-11-07_03-06-rootfs.tar.zst
# SHA256SUM=381f28ec05ca3d94487c4f8f005e57249b0a0006ba178e8898c6fb3897d5ec3c
# BUILD_DATE=20221107
# BUILD_TAG=2022-11-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-07
begin = 2022-11-07 02:52:26.316524551+00:00
start-sync_0 = 02:58:50
start-zstd = 02:59:53
start-sync_1 = 03:06:11
end-sync_1 = 03:06:34
end = 2022-11-07 03:06:34.104926411+00:00

[server]
repo = "cake233/rust-s390x"

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (9286a1beb 2022-11-04)'
rustc = 'rustc 1.67.0-nightly (7eef946fc 2022-11-06)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (9286a1beb 2022-11-04)
release: 1.67.0-nightly
commit-hash: 9286a1beba5b28b115bad67de2ae91fb1c61eb0b
commit-date: 2022-11-04
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (7eef946fc 2022-11-06)
binary: rustc
commit-hash: 7eef946fc0e0eff40e588eab77b09b287accbec3
commit-date: 2022-11-06
host: s390x-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
