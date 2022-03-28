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
tag = ["latest", "2022-03-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false

[file]
name = "rust_s390x_2022-03-28_02-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f77c3a521e2dad6a10f4b1001807be4644e7afe2396dda0d945e8ca2451c2aef"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1720494080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 254726254

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220325"
previous_tag = "2022-03-25"
previous_file = "rust_s390x_2022-03-25_03-05-rootfs.tar.zst"
previous_sha256 = "8046a3d1e6ff1495113b32c140e0e992c3da7248603fc60e81110485d4c5987b"

current_version = "latest02"
current_date = "20220328"
old_file = "rust_s390x_2022-03-21_03-09-rootfs.tar.zst"
old_sha256 = "317aa68338e6189d11525304f7a6a03b5a6326961d02b700597b038273af69ea"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-03-28_02-07-rootfs.tar.zst
# SHA256SUM=f77c3a521e2dad6a10f4b1001807be4644e7afe2396dda0d945e8ca2451c2aef
# BUILD_DATE=20220328
# BUILD_TAG=2022-03-28
# STATUS=completed
# VERSION=latest02
# END_TIME=02:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-28
begin = 2022-03-28 01:52:29.790114741+00:00
start-sync_0 = 01:59:49
start-zstd = 02:01:07
start-sync_1 = 02:07:26
end-sync_1 = 02:07:49
end = 2022-03-28 02:07:49.318056287+00:00

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
cargo = 'cargo 1.61.0-nightly (109bfbd05 2022-03-17)'
rustc = 'rustc 1.61.0-nightly (ab0c2e18d 2022-03-27)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (109bfbd05 2022-03-17)
release: 1.61.0-nightly
commit-hash: 109bfbd055325ef87a6e7f63d67da7e838f8300b
commit-date: 2022-03-17
host: s390x-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (ab0c2e18d 2022-03-27)
binary: rustc
commit-hash: ab0c2e18dceb7140626a158affb983ae81039bd0
commit-date: 2022-03-27
host: s390x-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
