# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-02-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-02-17_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8774b28400f7ae8ef16a19663b3e532135fed48eef9de18fe4cece3ad7b2932f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1563743744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 234432082

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230210"
previous_tag = "2023-02-10"
previous_file = "rust_amd64_2023-02-10_02-59-rootfs.tar.zst"
previous_sha256 = "e4f9e448b674b09e37a75e7b3804dcfb1833709ec943e7adb261a71995359968"

current_version = "latest02"
current_date = "20230217"
old_file = "rust_amd64_2023-02-06_02-59-rootfs.tar.zst"
old_sha256 = "64998712f4e25e9e8e00113c803b46e685572a3c3ddd47e12fb90864e4fb76e4"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-02-17_03-00-rootfs.tar.zst
# SHA256SUM=8774b28400f7ae8ef16a19663b3e532135fed48eef9de18fe4cece3ad7b2932f
# BUILD_DATE=20230217
# BUILD_TAG=2023-02-17
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-17
begin = 2023-02-17 02:52:30.274046774+00:00
start-sync_0 = 02:53:52
start-zstd = 02:54:48
start-sync_1 = 02:59:47
end-sync_1 = 03:00:07
end = 2023-02-17 03:00:07.926064236+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (39c13e67a 2023-02-12)'
rustc = 'rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (39c13e67a 2023-02-12)
release: 1.69.0-nightly
commit-hash: 39c13e67a5962466cc7253d41bc1099bbcb224c3
commit-date: 2023-02-12
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)
binary: rustc
commit-hash: 9a7cc6c32f1a690f86827e4724bcda85e506ef35
commit-date: 2023-02-16
host: x86_64-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
