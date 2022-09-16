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
tag = ["latest", "2022-09-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-09-16_03-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "239695b6d09cbae3c0e60adf860fa469dc925885baa59d0585e55956ef5f7ecd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1709792256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 226796036

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220912"
previous_tag = "2022-09-12"
previous_file = "rust_mips64el_2022-09-12_03-08-rootfs.tar.zst"
previous_sha256 = "565ae4cc4417074b6e4fe205308b58ab786ba38f39d39478c68e69339709d837"

current_version = "latest01"
current_date = "20220916"
old_file = "rust_mips64el_2022-09-09_03-06-rootfs.tar.zst"
old_sha256 = "0db138ef3f4e74c9d6aab7270c11b8bf97fc378e3089cd27851ad5db8d3bba7c"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-09-16_03-11-rootfs.tar.zst
# SHA256SUM=239695b6d09cbae3c0e60adf860fa469dc925885baa59d0585e55956ef5f7ecd
# BUILD_DATE=20220916
# BUILD_TAG=2022-09-16
# STATUS=completed
# VERSION=latest01
# END_TIME=03:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-16
begin = 2022-09-16 02:52:24.026265201+00:00
start-sync_0 = 03:01:30
start-zstd = 03:02:50
start-sync_1 = 03:10:59
end-sync_1 = 03:11:20
end = 2022-09-16 03:11:20.488875491+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-8) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (082503982 2022-09-13)'
rustc = 'rustc 1.65.0-nightly (cf9ed0dd5 2022-09-15)'
cc = 'cc (Debian 12.2.0-2) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (082503982 2022-09-13)
release: 1.65.0-nightly
commit-hash: 082503982ea0fb7a8fd72210427d43a2e2128a63
commit-date: 2022-09-13
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (cf9ed0dd5 2022-09-15)
binary: rustc
commit-hash: cf9ed0dd5836201843d28bbad50abfbe1913af2a
commit-date: 2022-09-15
host: mips64el-unknown-linux-gnuabi64
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
