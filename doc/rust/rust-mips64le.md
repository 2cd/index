# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-12-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-12-19_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "db365b169b8639ec68a171bc6ac55aa0930ea9692ab9104a384c0f54e1caac56"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1675984384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "195M"
zstd_bytes = 203539339

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221216"
previous_tag = "2022-12-16"
previous_file = "rust_mips64el_2022-12-16_03-05-rootfs.tar.zst"
previous_sha256 = "28c4087a433b1c3112b35074acccf97810f82b23968f168e5f0440b1a17a8970"

current_version = "latest01"
current_date = "20221219"
old_file = "rust_mips64el_2022-12-12_03-07-rootfs.tar.zst"
old_sha256 = "32a7446d767d985905312f7f1b586dfd66fd13b6e038cf71719cf883b892c2c4"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-12-19_03-07-rootfs.tar.zst
# SHA256SUM=db365b169b8639ec68a171bc6ac55aa0930ea9692ab9104a384c0f54e1caac56
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 02:52:35.002159780+00:00
start-sync_0 = 02:59:45
start-zstd = 03:00:55
start-sync_1 = 03:06:49
end-sync_1 = 03:07:10
end = 2022-12-19 03:07:10.594030714+00:00

[server]
repo = "cake233/rust-mips64le"

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
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (d0dc9efff 2022-12-18)
binary: rustc
commit-hash: d0dc9efff14ac0a1eeceffd1e605e37eeb8362a0
commit-date: 2022-12-18
host: mips64el-unknown-linux-gnuabi64
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
