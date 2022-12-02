# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

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
    cake233/rust-alpine-arm64 \
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
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-12-02", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-12-02_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d82821ca0d81b9cc44faadee5805b220614c823c67bf473c3ba1047b8b4874c4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "852M"
tar_bytes = 892464640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "155M"
zstd_bytes = 162023584

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221128"
previous_tag = "2022-11-28"
previous_file = "rust-musl_arm64_2022-11-28_02-59-rootfs.tar.zst"
previous_sha256 = "5029c6d1708d43953f1c9328c0c646c5248d392ea2cfcb4e52c762d0045b49db"

current_version = "latest01"
current_date = "20221202"
old_file = "rust-musl_arm64_2022-11-25_03-01-rootfs.tar.zst"
old_sha256 = "5e5908db45a206ac510b2a8c5ccafca32a5ec32d1bf3b456d33703629548df34"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-12-02_03-01-rootfs.tar.zst
# SHA256SUM=d82821ca0d81b9cc44faadee5805b220614c823c67bf473c3ba1047b8b4874c4
# BUILD_DATE=20221202
# BUILD_TAG=2022-12-02
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-02
begin = 2022-12-02 02:52:31.670486944+00:00
start-sync_0 = 02:54:41
start-zstd = 02:55:27
start-sync_1 = 03:00:51
end-sync_1 = 03:01:06
end = 2022-12-02 03:01:06.529552848+00:00

[server]
repo = "cake233/rust-alpine-arm64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (aarch64) Version 1.2.3'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (e027c4b5d 2022-11-25)'
rustc = 'rustc 1.67.0-nightly (c090c6880 2022-12-01)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (e027c4b5d 2022-11-25)
release: 1.67.0-nightly
commit-hash: e027c4b5d25af2119b1956fac42863b9b3242744
commit-date: 2022-11-25
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20221110 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (c090c6880 2022-12-01)
binary: rustc
commit-hash: c090c6880c0183ba248bde4a16e29ba29ac4fbba
commit-date: 2022-12-01
host: aarch64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
