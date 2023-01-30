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
tag = ["latest", "2023-01-30", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-01-30_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "69c412a32abe1069a4e53de93cf74645c1bf0ed5be666a359d344c90d716467c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1877943296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 247401935

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230127"
previous_tag = "2023-01-27"
previous_file = "rust_s390x_2023-01-27_03-08-rootfs.tar.zst"
previous_sha256 = "9a361abac5cf3934070ae7f3ab19e6afac96972e6eec2577d9fb1de1e9c8f15e"

current_version = "latest01"
current_date = "20230130"
old_file = "rust_s390x_2023-01-23_03-06-rootfs.tar.zst"
old_sha256 = "516b0bc7a7a07a8f599ad97c4fa98db36d1c846f9fdd9f6f40c731b8154da7ce"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-01-30_03-09-rootfs.tar.zst
# SHA256SUM=69c412a32abe1069a4e53de93cf74645c1bf0ed5be666a359d344c90d716467c
# BUILD_DATE=20230130
# BUILD_TAG=2023-01-30
# STATUS=completed
# VERSION=latest01
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-30
begin = 2023-01-30 02:52:29.051695888+00:00
start-sync_0 = 03:00:53
start-zstd = 03:02:16
start-sync_1 = 03:09:14
end-sync_1 = 03:09:38
end = 2023-01-30 03:09:38.478084352+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.69.0-nightly (3c5af6bed 2023-01-24)'
rustc = 'rustc 1.69.0-nightly (e972bc808 2023-01-29)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (3c5af6bed 2023-01-24)
release: 1.69.0-nightly
commit-hash: 3c5af6bed9a1a243a693e8e22ee2486bd5b82a6c
commit-date: 2023-01-24
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (e972bc808 2023-01-29)
binary: rustc
commit-hash: e972bc8083d5228536dfd42913c8778b6bb04c8e
commit-date: 2023-01-29
host: s390x-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
