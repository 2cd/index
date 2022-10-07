# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-10-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-10-07_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1ba7bd59f57879e6fb62c48b9d6b63ddfde23bd5bc9fd4a4343216a724e132b5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1666106880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "248M"
zstd_bytes = 259213751

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221003"
previous_tag = "2022-10-03"
previous_file = "rust_amd64_2022-10-03_03-00-rootfs.tar.zst"
previous_sha256 = "83e71ca178d9b3356cc10dc3d5373736fa42aa2f02f910e65eafb983547accb1"

current_version = "latest01"
current_date = "20221007"
old_file = "rust_amd64_2022-09-30_03-02-rootfs.tar.zst"
old_sha256 = "93ad151d2eb9cebcafca4377264b9a4c1f01079297a8f9a6c4120a0d0e85fc06"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-10-07_03-00-rootfs.tar.zst
# SHA256SUM=1ba7bd59f57879e6fb62c48b9d6b63ddfde23bd5bc9fd4a4343216a724e132b5
# BUILD_DATE=20221007
# BUILD_TAG=2022-10-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-07
begin = 2022-10-07 02:52:25.265129320+00:00
start-sync_0 = 02:54:01
start-zstd = 02:55:02
start-sync_1 = 03:00:15
end-sync_1 = 03:00:36
end = 2022-10-07 03:00:36.608370124+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.35-2) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (0b84a35c2 2022-10-03)'
rustc = 'rustc 1.66.0-nightly (0ca356586 2022-10-06)'
cc = 'cc (Debian 12.2.0-5) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (0b84a35c2 2022-10-03)
release: 1.66.0-nightly
commit-hash: 0b84a35c2c7d70df4875a03eb19084b0e7a543ef
commit-date: 2022-10-03
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (0ca356586 2022-10-06)
binary: rustc
commit-hash: 0ca356586fed56002b10920fd21ddf6fb12de797
commit-date: 2022-10-06
host: x86_64-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
