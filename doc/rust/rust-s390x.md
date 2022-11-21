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
tag = ["latest", "2022-11-21", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2022-11-21_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "035fca242c7231dccb89260426c21e2aa563ede7043d0e13968b9d002e47f4a2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1768160768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239423140

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221118"
previous_tag = "2022-11-18"
previous_file = "rust_s390x_2022-11-18_03-05-rootfs.tar.zst"
previous_sha256 = "dd701591299bd6472fc727ca1b3a077b5020ee13e57be6cfd383360aa60c351f"

current_version = "latest01"
current_date = "20221121"
old_file = "rust_s390x_2022-11-14_03-08-rootfs.tar.zst"
old_sha256 = "8665be3e28d16b9264d032c8ace983e8e03fed8a0f96bb2994bff9793cf31e52"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-11-21_03-07-rootfs.tar.zst
# SHA256SUM=035fca242c7231dccb89260426c21e2aa563ede7043d0e13968b9d002e47f4a2
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 02:52:28.000582721+00:00
start-sync_0 = 02:59:34
start-zstd = 03:00:53
start-sync_1 = 03:07:00
end-sync_1 = 03:07:24
end = 2022-11-21 03:07:24.151567667+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (eb5d35917 2022-11-17)'
rustc = 'rustc 1.67.0-nightly (a28f3c88e 2022-11-20)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (eb5d35917 2022-11-17)
release: 1.67.0-nightly
commit-hash: eb5d35917b2395194593c9ca70c3778f60c1573b
commit-date: 2022-11-17
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (a28f3c88e 2022-11-20)
binary: rustc
commit-hash: a28f3c88e50a77bc2a91889241248c4543854e61
commit-date: 2022-11-20
host: s390x-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
