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
tag = ["latest", "2022-08-26", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2022-08-26_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f4048c13da212713d19f70920136ea1d1d08849e137a8dd5cd66364da4d046c9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1768863744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "254M"
zstd_bytes = 265346754

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220822"
previous_tag = "2022-08-22"
previous_file = "rust_s390x_2022-08-22_03-12-rootfs.tar.zst"
previous_sha256 = "4e182b311e40ee3122b34a9c0479d6ad0e6f1c462c80713decc92fc914bf0ab7"

current_version = "latest02"
current_date = "20220826"
old_file = "rust_s390x_2022-08-19_03-12-rootfs.tar.zst"
old_sha256 = "ce2d9975f32c944d485f009c564778527dc0acd4276746108ba477c9e1a2e2ba"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-08-26_03-06-rootfs.tar.zst
# SHA256SUM=f4048c13da212713d19f70920136ea1d1d08849e137a8dd5cd66364da4d046c9
# BUILD_DATE=20220826
# BUILD_TAG=2022-08-26
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-26
begin = 2022-08-26 02:52:21.392601623+00:00
start-sync_0 = 02:59:04
start-zstd = 03:00:11
start-sync_1 = 03:06:05
end-sync_1 = 03:06:24
end = 2022-08-26 03:06:24.785086882+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-6) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (6da726708 2022-08-23)'
rustc = 'rustc 1.65.0-nightly (748038961 2022-08-25)'
cc = 'cc (Debian 12.2.0-1) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (6da726708 2022-08-23)
release: 1.65.0-nightly
commit-hash: 6da726708a4406f31f996d813790818dce837161
commit-date: 2022-08-23
host: s390x-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (748038961 2022-08-25)
binary: rustc
commit-hash: 7480389611f9d04bd34adf41a2b3029be4eb815e
commit-date: 2022-08-25
host: s390x-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
