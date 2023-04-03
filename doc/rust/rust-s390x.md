# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-04-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-04-03_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6a3772bd69225471d4e5147bd43c5d7498b89e95f5a484dfc1c373527de163ba"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1880427008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 248838257

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230331"
previous_tag = "2023-03-31"
previous_file = "rust_s390x_2023-03-31_03-10-rootfs.tar.zst"
previous_sha256 = "3274c132813b43b7e953fae3d737d4360b5dc04f2b41894f7ec95b2a7b20f4e9"

current_version = "latest01"
current_date = "20230403"
old_file = "rust_s390x_2023-03-27_03-05-rootfs.tar.zst"
old_sha256 = "ea37818b685faa359041b436239dc9454ecec300312103e1b3dad869adac5dab"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-04-03_03-06-rootfs.tar.zst
# SHA256SUM=6a3772bd69225471d4e5147bd43c5d7498b89e95f5a484dfc1c373527de163ba
# BUILD_DATE=20230403
# BUILD_TAG=2023-04-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-03
begin = 2023-04-03 02:52:27.438493937+00:00
start-sync_0 = 02:58:47
start-zstd = 02:59:54
start-sync_1 = 03:06:28
end-sync_1 = 03:06:46
end = 2023-04-03 03:06:46.485084902+00:00

[server]
repo = "cake233/rust-s390x"

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
cargo = 'cargo 1.70.0-nightly (0e474cfd7 2023-03-31)'
rustc = 'rustc 1.70.0-nightly (3a8a131e9 2023-04-02)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (0e474cfd7 2023-03-31)
release: 1.70.0-nightly
commit-hash: 0e474cfd7b16b018cf46e95da3f6a5b2f1f6a9e7
commit-date: 2023-03-31
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (3a8a131e9 2023-04-02)
binary: rustc
commit-hash: 3a8a131e9509c478ece1c58fe0ea2d49463d2300
commit-date: 2023-04-02
host: s390x-unknown-linux-gnu
release: 1.70.0-nightly
LLVM version: 16.0.0
'''
```
