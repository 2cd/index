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
tag = ["latest", "2022-04-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust_s390x_2022-04-25_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d9fdd0f11800d0c57e2cae97eb5d47a72374238d94033144f38794883543a4d0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1780488192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "248M"
zstd_bytes = 259335439

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "rust_s390x_2022-04-22_03-07-rootfs.tar.zst"
previous_sha256 = "d6d8dc3b1192608e69f71986b8d4e0bd3805a383ce4c9285cf37243b4ffa902d"

current_version = "latest02"
current_date = "20220425"
old_file = "rust_s390x_2022-04-18_03-07-rootfs.tar.zst"
old_sha256 = "af1c5cacc89b27c0f16b884f13c2ac350b1d35b7bd2f11fab2b7c4caa2e47416"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-04-25_03-07-rootfs.tar.zst
# SHA256SUM=d9fdd0f11800d0c57e2cae97eb5d47a72374238d94033144f38794883543a4d0
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest02
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 02:52:28.457637580+00:00
start-sync_0 = 02:59:52
start-zstd = 03:01:05
start-sync_1 = 03:07:16
end-sync_1 = 03:07:37
end = 2022-04-25 03:07:37.969389097+00:00

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
cargo = 'cargo 1.62.0-nightly (edffc4ada 2022-04-19)'
rustc = 'rustc 1.62.0-nightly (18f314e70 2022-04-24)'
cc = 'cc (Debian 11.2.0-20) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (edffc4ada 2022-04-19)
release: 1.62.0-nightly
commit-hash: edffc4ada3d77799e5a04eeafd9b2f843d29fc23
commit-date: 2022-04-19
host: s390x-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (18f314e70 2022-04-24)
binary: rustc
commit-hash: 18f314e7027fe7084aaab8620c624a0d7bd29e70
commit-date: 2022-04-24
host: s390x-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
