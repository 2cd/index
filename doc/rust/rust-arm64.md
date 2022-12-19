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
tag = ["latest", "2022-12-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-12-19_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "17bc7ce16d801ae9f54944a0bb57b456e7fbefef4797cd5b76d1b5d2f39c5b43"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1878565888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "246M"
zstd_bytes = 257389819

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221216"
previous_tag = "2022-12-16"
previous_file = "rust_arm64_2022-12-16_03-07-rootfs.tar.zst"
previous_sha256 = "4c7a801497621a6c64870f74bf7b1bad0a27266ea209a329cf3d98d7b314a152"

current_version = "latest01"
current_date = "20221219"
old_file = "rust_arm64_2022-12-12_03-08-rootfs.tar.zst"
old_sha256 = "a10eb58093e840ee9c2c56b0a23d91bfeaf122d382e14f9f23a1746a0ae8a871"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-12-19_03-05-rootfs.tar.zst
# SHA256SUM=17bc7ce16d801ae9f54944a0bb57b456e7fbefef4797cd5b76d1b5d2f39c5b43
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 02:52:31.721524124+00:00
start-sync_0 = 02:58:35
start-zstd = 02:59:39
start-sync_1 = 03:05:31
end-sync_1 = 03:05:49
end = 2022-12-19 03:05:49.791332477+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (cc0a32087 2022-12-14)'
rustc = 'rustc 1.68.0-nightly (d0dc9efff 2022-12-18)'
cc = 'cc (Debian 12.2.0-10) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (cc0a32087 2022-12-14)
release: 1.68.0-nightly
commit-hash: cc0a320879c17207bbfb96b5d778e28a2c62030d
commit-date: 2022-12-14
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (d0dc9efff 2022-12-18)
binary: rustc
commit-hash: d0dc9efff14ac0a1eeceffd1e605e37eeb8362a0
commit-date: 2022-12-18
host: aarch64-unknown-linux-gnu
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
