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
tag = ["latest", "2022-06-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2022-06-17_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "962f586c7247dfda14bdd3db0a6fef7216e1020c459831e6a006d7159b92870f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1563500032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "235M"
zstd_bytes = 245721159

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220613"
previous_tag = "2022-06-13"
previous_file = "rust_armhf_2022-06-13_03-04-rootfs.tar.zst"
previous_sha256 = "3f8b36c2e181bd272e30325e96fa4123108868ae1bf67533a9eae0a04b3015a4"

current_version = "latest02"
current_date = "20220617"
old_file = "rust_armhf_2022-06-10_03-05-rootfs.tar.zst"
old_sha256 = "f9db25e4e32b68306e293b912a4a951e61085d7edc6b9fcc4faa572e4ce28909"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-06-17_03-05-rootfs.tar.zst
# SHA256SUM=962f586c7247dfda14bdd3db0a6fef7216e1020c459831e6a006d7159b92870f
# BUILD_DATE=20220617
# BUILD_TAG=2022-06-17
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-17
begin = 2022-06-17 02:52:37.104229431+00:00
start-sync_0 = 02:58:53
start-zstd = 02:59:50
start-sync_1 = 03:04:41
end-sync_1 = 03:05:02
end = 2022-06-17 03:05:02.349757633+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (4d92f07f3 2022-06-09)'
rustc = 'rustc 1.63.0-nightly (cacc75c82 2022-06-16)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (4d92f07f3 2022-06-09)
release: 1.63.0-nightly
commit-hash: 4d92f07f34ba7fb7d7f207564942508f46c225d3
commit-date: 2022-06-09
host: armv7-unknown-linux-gnueabihf
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (cacc75c82 2022-06-16)
binary: rustc
commit-hash: cacc75c82ebe15cf63d31034fcf7f1016cddf0e2
commit-date: 2022-06-16
host: armv7-unknown-linux-gnueabihf
release: 1.63.0-nightly
LLVM version: 14.0.5
'''
```
