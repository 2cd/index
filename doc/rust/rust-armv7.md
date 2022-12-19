# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

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
    cake233/rust-armv7 \
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
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-12-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2022-12-19_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9264d16ad8a2ecb3ec80b2d0465d3bb75b98c7c5cb3044917e56119ce05d3999"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1573890560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 228628313

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221216"
previous_tag = "2022-12-16"
previous_file = "rust_armhf_2022-12-16_03-03-rootfs.tar.zst"
previous_sha256 = "7ec625824eebd9d3606c2360a2cba12a0a0592e992b24830544cee7995e57c9a"

current_version = "latest02"
current_date = "20221219"
old_file = "rust_armhf_2022-12-12_03-03-rootfs.tar.zst"
old_sha256 = "9ba6d486390e59cd4679c3f4c78b548fab842320b556e3599246994e82713e83"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-12-19_03-04-rootfs.tar.zst
# SHA256SUM=9264d16ad8a2ecb3ec80b2d0465d3bb75b98c7c5cb3044917e56119ce05d3999
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 02:52:31.633788402+00:00
start-sync_0 = 02:58:09
start-zstd = 02:59:03
start-sync_1 = 03:03:41
end-sync_1 = 03:04:00
end = 2022-12-19 03:04:00.513851348+00:00

[server]
repo = "cake233/rust-armv7"

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
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (d0dc9efff 2022-12-18)
binary: rustc
commit-hash: d0dc9efff14ac0a1eeceffd1e605e37eeb8362a0
commit-date: 2022-12-18
host: armv7-unknown-linux-gnueabihf
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
