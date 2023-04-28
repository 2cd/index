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
tag = ["latest", "2023-04-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-04-28_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "69aace6d05d3edb26cfda084faeef69702ba527a875bd081a37f4e43c59a8c41"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1866453504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 248381843

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230424"
previous_tag = "2023-04-24"
previous_file = "rust_s390x_2023-04-24_03-07-rootfs.tar.zst"
previous_sha256 = "36b559a16358b6b2c4af6bdd5bbcf16487b6828de18583de6d9d28ba7dd9613e"

current_version = "latest01"
current_date = "20230428"
old_file = "rust_s390x_2023-04-21_03-09-rootfs.tar.zst"
old_sha256 = "199b139339a0b860c590286ff9230d39f7f30617ac6237afe7478f98ee054154"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-04-28_03-06-rootfs.tar.zst
# SHA256SUM=69aace6d05d3edb26cfda084faeef69702ba527a875bd081a37f4e43c59a8c41
# BUILD_DATE=20230428
# BUILD_TAG=2023-04-28
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-28
begin = 2023-04-28 02:52:37.069066386+00:00
start-sync_0 = 02:59:18
start-zstd = 03:00:29
start-sync_1 = 03:06:21
end-sync_1 = 03:06:41
end = 2023-04-28 03:06:41.459548513+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (9e586fbd8 2023-04-25)'
rustc = 'rustc 1.71.0-nightly (1a6ae3d69 2023-04-27)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (9e586fbd8 2023-04-25)
release: 1.71.0-nightly
commit-hash: 9e586fbd8b931494067144623b76c37d213b1ab6
commit-date: 2023-04-25
host: s390x-unknown-linux-gnu
libgit2: 1.6.3 (sys:0.17.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (1a6ae3d69 2023-04-27)
binary: rustc
commit-hash: 1a6ae3d692cfb52b21d0f45ba50b659486e53d6c
commit-date: 2023-04-27
host: s390x-unknown-linux-gnu
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
