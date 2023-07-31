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
tag = ["latest", "2023-07-31", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-07-31_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a33ca3f467ca4e9780fae4d78179f65daa54519d95b0e7d259a83db7eeb0fe52"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.0G"
tar_bytes = 2130108928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "320M"
zstd_bytes = 334969079

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230728"
previous_tag = "2023-07-28"
previous_file = "rust_s390x_2023-07-28_03-13-rootfs.tar.zst"
previous_sha256 = "d3185dd17ee00fc2fe4266dcaa279c2f9e6643abff01459deb8481a982b76c36"

current_version = "latest02"
current_date = "20230731"
old_file = "rust_s390x_2023-07-24_03-09-rootfs.tar.zst"
old_sha256 = "7b66fddfc73eb415c6b2cc34bbd844deaba9cbbdf3ecf2e4207676cf5ed97564"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-07-31_03-09-rootfs.tar.zst
# SHA256SUM=a33ca3f467ca4e9780fae4d78179f65daa54519d95b0e7d259a83db7eeb0fe52
# BUILD_DATE=20230731
# BUILD_TAG=2023-07-31
# STATUS=completed
# VERSION=latest02
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-31
begin = 2023-07-31 02:52:32.908873296+00:00
start-sync_0 = 03:00:15
start-zstd = 03:01:29
start-sync_1 = 03:09:06
end-sync_1 = 03:09:31
end = 2023-07-31 03:09:31.623026390+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (7ac9416d8 2023-07-24)'
rustc = 'rustc 1.73.0-nightly (32303b219 2023-07-29)'
cc = 'cc (Debian 13.2.0-1) 13.2.0'
cargo_verbose = '''
cargo 1.73.0-nightly (7ac9416d8 2023-07-24)
release: 1.73.0-nightly
commit-hash: 7ac9416d82cd4fc5e707c9ec3574d22dff6466e5
commit-date: 2023-07-24
host: s390x-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (32303b219 2023-07-29)
binary: rustc
commit-hash: 32303b219d4dffa447aa606bc11c7a648f44a862
commit-date: 2023-07-29
host: s390x-unknown-linux-gnu
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
