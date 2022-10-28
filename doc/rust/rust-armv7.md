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
tag = ["latest", "2022-10-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2022-10-28_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9f4c84eb21942dd716b94ba06be7b2e84128768759c017991294c06629372bd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1598814208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 247218200

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221024"
previous_tag = "2022-10-24"
previous_file = "rust_armhf_2022-10-24_03-05-rootfs.tar.zst"
previous_sha256 = "364add5a80fa80c555e46211f022eb8eaa69242bb9597195bb63e4adf502259e"

current_version = "latest01"
current_date = "20221028"
old_file = "rust_armhf_2022-10-21_03-05-rootfs.tar.zst"
old_sha256 = "5fe215182e2c35e6dd585b3605c5db1e448474ea019f9e97c6e996f2128159d1"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-10-28_03-07-rootfs.tar.zst
# SHA256SUM=f9f4c84eb21942dd716b94ba06be7b2e84128768759c017991294c06629372bd
# BUILD_DATE=20221028
# BUILD_TAG=2022-10-28
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-28
begin = 2022-10-28 02:52:25.353609370+00:00
start-sync_0 = 03:00:41
start-zstd = 03:01:51
start-sync_1 = 03:07:36
end-sync_1 = 03:07:59
end = 2022-10-28 03:07:59.927338024+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-4) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (9210810d1 2022-10-25)'
rustc = 'rustc 1.66.0-nightly (0da281b60 2022-10-27)'
cc = 'cc (Debian 12.2.0-7) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (9210810d1 2022-10-25)
release: 1.66.0-nightly
commit-hash: 9210810d1fd7b51ae0439a0a363cc50e36963455
commit-date: 2022-10-25
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (0da281b60 2022-10-27)
binary: rustc
commit-hash: 0da281b6068a7d889ae89a9bd8991284cc9b7535
commit-date: 2022-10-27
host: armv7-unknown-linux-gnueabihf
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
