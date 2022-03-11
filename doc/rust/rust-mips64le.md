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
tag = ["latest", "2022-03-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false

[file]
name = "rust_mips64el_2022-03-11_03-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "edcf68d0d7e598b830ffdc0985fa119f56824d2310b780c701cd3006e5efa028"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1606587904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "207M"
zstd_bytes = 216333609

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "rust_mips64el_2022-03-07_03-05-rootfs.tar.zst"
previous_sha256 = "a2c27576fd87f6ee322bc17362027ad3e83a20e17ac39723c6a0100e801bdcde"

current_version = "latest02"
current_date = "20220311"
old_file = "rust_mips64el_2022-03-04_03-05-rootfs.tar.zst"
old_sha256 = "d80f58b58cfdfa6b7e2e1035f03ea980eb0a83c6ff9387047e349fb049956881"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-03-11_03-08-rootfs.tar.zst
# SHA256SUM=edcf68d0d7e598b830ffdc0985fa119f56824d2310b780c701cd3006e5efa028
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 02:52:36.236013760+00:00
start-sync_0 = 03:00:43
start-zstd = 03:01:52
start-sync_1 = 03:08:00
end-sync_1 = 03:08:24
end = 2022-03-11 03:08:24.868977287+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (65c8266 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (5f4e06771 2022-03-10)'
cc = 'cc (Debian 11.2.0-16) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (65c8266 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (5f4e06771 2022-03-10)
binary: rustc
commit-hash: 5f4e0677190b82e61dc507e3e72caf89da8e5e28
commit-date: 2022-03-10
host: mips64el-unknown-linux-gnuabi64
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
