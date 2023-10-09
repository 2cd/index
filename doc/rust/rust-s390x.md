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
tag = ["latest", "2023-10-09", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-10-09_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fd3d13343b899915de7951f57bb3c40ae386c7e6a7632703c2441be7a5a737c9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 2030974976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 254611998

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231006"
previous_tag = "2023-10-06"
previous_file = "rust_s390x_2023-10-06_03-10-rootfs.tar.zst"
previous_sha256 = "a0bc0d2e1a0a0a96dd2b40e3dbd853c53260f9326c8d5b5dde40363cb8fe60f1"

current_version = "latest02"
current_date = "20231009"
old_file = "rust_s390x_2023-10-02_03-10-rootfs.tar.zst"
old_sha256 = "715da9daad3f70541d9386ac11d6dc8ad2f678cb0925390028d8bfd8330826f4"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-10-09_03-07-rootfs.tar.zst
# SHA256SUM=fd3d13343b899915de7951f57bb3c40ae386c7e6a7632703c2441be7a5a737c9
# BUILD_DATE=20231009
# BUILD_TAG=2023-10-09
# STATUS=completed
# VERSION=latest02
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-09
begin = 2023-10-09 02:52:40.659294686+00:00
start-sync_0 = 02:59:31
start-zstd = 03:00:49
start-sync_1 = 03:07:30
end-sync_1 = 03:07:53
end = 2023-10-09 03:07:53.847072697+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.75.0-nightly (794d0a825 2023-10-03)'
rustc = 'rustc 1.75.0-nightly (bf9a1c8a1 2023-10-08)'
cc = 'cc (Debian 13.2.0-5) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (794d0a825 2023-10-03)
release: 1.75.0-nightly
commit-hash: 794d0a82547f3081044c0aca7b6083733ce51344
commit-date: 2023-10-03
host: s390x-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.3.0-DEV (sys:0.4.66+curl-8.3.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (bf9a1c8a1 2023-10-08)
binary: rustc
commit-hash: bf9a1c8a193fc373897196321215794c8bebbeec
commit-date: 2023-10-08
host: s390x-unknown-linux-gnu
release: 1.75.0-nightly
LLVM version: 17.0.2
'''
```
