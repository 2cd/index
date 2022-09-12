# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-09-12", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-09-12_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "046c7d2893c98fa86f08d3ef8bdfcd51662044ce14ea0c048f7d66f74c55b47c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1922782208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "272M"
zstd_bytes = 284785221

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220909"
previous_tag = "2022-09-09"
previous_file = "rust_arm64_2022-09-09_03-10-rootfs.tar.zst"
previous_sha256 = "da9b9ec2def0b51a325105118b7dd2bba195c79ac363e384d31abb82843e631e"

current_version = "latest02"
current_date = "20220912"
old_file = "rust_arm64_2022-09-05_03-09-rootfs.tar.zst"
old_sha256 = "938d0e6a93aff91dde2f839e4bc7801b9fc0d409da4c6dd52c475c28ec18aeb5"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-09-12_03-06-rootfs.tar.zst
# SHA256SUM=046c7d2893c98fa86f08d3ef8bdfcd51662044ce14ea0c048f7d66f74c55b47c
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 02:52:22.301271349+00:00
start-sync_0 = 02:58:39
start-zstd = 02:59:42
start-sync_1 = 03:05:49
end-sync_1 = 03:06:11
end = 2022-09-12 03:06:11.739944873+00:00

[server]
repo = "cake233/rust-arm64"

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
ldd = 'ldd (Debian GLIBC 2.34-8) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (646e9a0b9 2022-09-02)'
rustc = 'rustc 1.65.0-nightly (59e7a308e 2022-09-11)'
cc = 'cc (Debian 12.2.0-2) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (646e9a0b9 2022-09-02)
release: 1.65.0-nightly
commit-hash: 646e9a0b9ea8354cc409d05f10e8dc752c5de78e
commit-date: 2022-09-02
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (59e7a308e 2022-09-11)
binary: rustc
commit-hash: 59e7a308e40fbc6b0901c9a8ee8ed51b17f9e772
commit-date: 2022-09-11
host: aarch64-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
