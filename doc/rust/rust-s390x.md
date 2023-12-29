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
tag = ["latest", "2023-12-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-12-29_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "88c322165a02bbe2e0bdeec7a4aeb33fb24352496279ffb006d217fba8d513e4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1936393728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258994539

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_s390x_2023-11-27_03-03-rootfs.tar.zst"
previous_sha256 = "0f7be992929dc68bf3a61de63f38fb4183872cdd03dc99de79f686900ace3a7a"

current_version = "latest01"
current_date = "20231229"
old_file = "rust_s390x_2023-11-24_03-03-rootfs.tar.zst"
old_sha256 = "01d25ab207a3c75ccb002706693b5dcef13f255f94316f55bf6819ec89a31893"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-12-29_03-03-rootfs.tar.zst
# SHA256SUM=88c322165a02bbe2e0bdeec7a4aeb33fb24352496279ffb006d217fba8d513e4
# BUILD_DATE=20231229
# BUILD_TAG=2023-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-29
begin = 2023-12-29 02:52:32.240747720+00:00
start-sync_0 = 02:57:43
start-zstd = 02:58:38
start-sync_1 = 03:03:36
end-sync_1 = 03:03:52
end = 2023-12-29 03:03:52.208857409+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.77.0-nightly (ac6bbb332 2023-12-26)'
rustc = 'rustc 1.77.0-nightly (fb5ed726f 2023-12-28)'
cc = 'cc (Debian 13.2.0-9) 13.2.0'
cargo_verbose = '''
cargo 1.77.0-nightly (ac6bbb332 2023-12-26)
release: 1.77.0-nightly
commit-hash: ac6bbb33293d8d424c17ecdb42af3aac25fb7295
commit-date: 2023-12-26
host: s390x-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.5.0-DEV (sys:0.4.70+curl-8.5.0 vendored ssl:OpenSSL/1.1.1w)
ssl: OpenSSL 1.1.1w  11 Sep 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.77.0-nightly (fb5ed726f 2023-12-28)
binary: rustc
commit-hash: fb5ed726f72c6d16c788517c60ec00d4564b9348
commit-date: 2023-12-28
host: s390x-unknown-linux-gnu
release: 1.77.0-nightly
LLVM version: 17.0.6
'''
```
