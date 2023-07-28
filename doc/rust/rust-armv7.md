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
tag = ["latest", "2023-07-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-07-28_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6e392e4b2cb44b46feb17726faf07e64e1b7dd90919a2422b0807d8e24b3d42d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1811505664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "308M"
zstd_bytes = 322604628

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "rust_armhf_2023-07-24_03-06-rootfs.tar.zst"
previous_sha256 = "2ee07b3e8f21fb2453c20ac683a06f2b58446647f6dbf2f496e747b08d65a50e"

current_version = "latest02"
current_date = "20230728"
old_file = "rust_armhf_2023-07-21_03-10-rootfs.tar.zst"
old_sha256 = "54dfa574305e2d91c8b02ba819b10501032d6a78c64db9b35fb66989361d3d30"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-07-28_03-08-rootfs.tar.zst
# SHA256SUM=6e392e4b2cb44b46feb17726faf07e64e1b7dd90919a2422b0807d8e24b3d42d
# BUILD_DATE=20230728
# BUILD_TAG=2023-07-28
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-28
begin = 2023-07-28 02:52:34.284013072+00:00
start-sync_0 = 02:59:52
start-zstd = 03:01:04
start-sync_1 = 03:07:48
end-sync_1 = 03:08:19
end = 2023-07-28 03:08:19.733244398+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (7ac9416d8 2023-07-24)'
rustc = 'rustc 1.73.0-nightly (500647fd8 2023-07-27)'
cc = 'cc (Debian 13.1.0-9) 13.1.0'
cargo_verbose = '''
cargo 1.73.0-nightly (7ac9416d8 2023-07-24)
release: 1.73.0-nightly
commit-hash: 7ac9416d82cd4fc5e707c9ec3574d22dff6466e5
commit-date: 2023-07-24
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (500647fd8 2023-07-27)
binary: rustc
commit-hash: 500647fd8138cc09e87edb08d62f81654fbf6ef8
commit-date: 2023-07-27
host: armv7-unknown-linux-gnueabihf
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
