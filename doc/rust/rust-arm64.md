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
tag = ["latest", "2022-07-22", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-07-22_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b0650ac5c3b01f1f3a085934e567a5092f316a2e0182e4ebea03e01e51a17175"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1863550976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "263M"
zstd_bytes = 275017902

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_arm64_2022-07-18_03-06-rootfs.tar.zst"
previous_sha256 = "42127f7a33fa7f5a17c5d27d1b0c97cd09d035a4468b5653f2cd746e78d55934"

current_version = "latest01"
current_date = "20220722"
old_file = "rust_arm64_2022-07-15_03-05-rootfs.tar.zst"
old_sha256 = "92087e52ec74618869f1e823fafaac103b8b38ab209d1f2e949163db2accbe42"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-07-22_03-10-rootfs.tar.zst
# SHA256SUM=b0650ac5c3b01f1f3a085934e567a5092f316a2e0182e4ebea03e01e51a17175
# BUILD_DATE=20220722
# BUILD_TAG=2022-07-22
# STATUS=completed
# VERSION=latest01
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-22
begin = 2022-07-22 02:52:27.214439264+00:00
start-sync_0 = 03:00:48
start-zstd = 03:02:13
start-sync_1 = 03:10:01
end-sync_1 = 03:10:29
end = 2022-07-22 03:10:29.769653767+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (d8d30a753 2022-07-19)'
rustc = 'rustc 1.64.0-nightly (62b272d25 2022-07-21)'
cc = 'cc (Debian 11.3.0-5) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (d8d30a753 2022-07-19)
release: 1.64.0-nightly
commit-hash: d8d30a75376f78bb0fabe3d28ee9d87aa8035309
commit-date: 2022-07-19
host: aarch64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (62b272d25 2022-07-21)
binary: rustc
commit-hash: 62b272d25c5bb8b6bb8ac73797d82b8b9a1eabda
commit-date: 2022-07-21
host: aarch64-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
