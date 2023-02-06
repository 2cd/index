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
tag = ["latest", "2023-02-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-02-06_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "468b9a8b0b3d60c74178e46900931d6b123a43392fc1a198316a3f5cf811542b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1874586624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246995168

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230130"
previous_tag = "2023-01-30"
previous_file = "rust_s390x_2023-01-30_03-09-rootfs.tar.zst"
previous_sha256 = "69c412a32abe1069a4e53de93cf74645c1bf0ed5be666a359d344c90d716467c"

current_version = "latest02"
current_date = "20230206"
old_file = "rust_s390x_2023-01-27_03-08-rootfs.tar.zst"
old_sha256 = "9a361abac5cf3934070ae7f3ab19e6afac96972e6eec2577d9fb1de1e9c8f15e"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-02-06_03-09-rootfs.tar.zst
# SHA256SUM=468b9a8b0b3d60c74178e46900931d6b123a43392fc1a198316a3f5cf811542b
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest02
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 02:52:26.865880721+00:00
start-sync_0 = 03:01:05
start-zstd = 03:02:27
start-sync_1 = 03:09:10
end-sync_1 = 03:09:34
end = 2023-02-06 03:09:34.450962938+00:00

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (e84a7928d 2023-01-31)'
rustc = 'rustc 1.69.0-nightly (75a0be98f 2023-02-05)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (e84a7928d 2023-01-31)
release: 1.69.0-nightly
commit-hash: e84a7928d93a31f284b497c214a2ece69b4d7719
commit-date: 2023-01-31
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (75a0be98f 2023-02-05)
binary: rustc
commit-hash: 75a0be98f25a4b9de5afa0e15eb016e7f9627032
commit-date: 2023-02-05
host: s390x-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
