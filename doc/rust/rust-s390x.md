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
tag = ["latest", "2023-02-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-02-13_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "009baf4016eae9497ec303c8c4a4233d9725c6e491b111fe8168d24157e06832"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1868393472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246948415

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230210"
previous_tag = "2023-02-10"
previous_file = "rust_s390x_2023-02-10_03-06-rootfs.tar.zst"
previous_sha256 = "3007b88182d9b102aafcdd8c8b86b3a0bd18ee3313fd39b00251b3a8620d1e70"

current_version = "latest02"
current_date = "20230213"
old_file = "rust_s390x_2023-02-06_03-09-rootfs.tar.zst"
old_sha256 = "468b9a8b0b3d60c74178e46900931d6b123a43392fc1a198316a3f5cf811542b"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-02-13_03-08-rootfs.tar.zst
# SHA256SUM=009baf4016eae9497ec303c8c4a4233d9725c6e491b111fe8168d24157e06832
# BUILD_DATE=20230213
# BUILD_TAG=2023-02-13
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-13
begin = 2023-02-13 02:52:27.818302621+00:00
start-sync_0 = 03:00:41
start-zstd = 03:02:05
start-sync_1 = 03:08:33
end-sync_1 = 03:08:57
end = 2023-02-13 03:08:57.368751977+00:00

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
cargo = 'cargo 1.69.0-nightly (82c3bb79e 2023-02-04)'
rustc = 'rustc 1.69.0-nightly (5b8f28453 2023-02-12)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (82c3bb79e 2023-02-04)
release: 1.69.0-nightly
commit-hash: 82c3bb79e3a19a5164e33819ef81bfc2c984bc56
commit-date: 2023-02-04
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (5b8f28453 2023-02-12)
binary: rustc
commit-hash: 5b8f284536d00ba649ca968584bedab4820d8527
commit-date: 2023-02-12
host: s390x-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
