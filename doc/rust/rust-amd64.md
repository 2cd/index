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
tag = ["latest", "2022-08-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-08-29_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "98537f4b8c49515acabc61ff22db2cbabe862ca11b216e1fd9b637dd87b49a03"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1615854592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258195868

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220826"
previous_tag = "2022-08-26"
previous_file = "rust_amd64_2022-08-26_03-00-rootfs.tar.zst"
previous_sha256 = "5640889167fcb932c1dd4b4fe1d0155ed43e930b51baca6177d990a7257f5a07"

current_version = "latest02"
current_date = "20220829"
old_file = "rust_amd64_2022-08-22_03-03-rootfs.tar.zst"
old_sha256 = "d14a90c07ae4eaace7bed0b34db5e72212ee86e20e5f8a55c257cacf66e2fb2d"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-08-29_03-00-rootfs.tar.zst
# SHA256SUM=98537f4b8c49515acabc61ff22db2cbabe862ca11b216e1fd9b637dd87b49a03
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 02:52:19.947075742+00:00
start-sync_0 = 02:54:02
start-zstd = 02:54:56
start-sync_1 = 02:59:57
end-sync_1 = 03:00:19
end = 2022-08-29 03:00:19.372868775+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (6da726708 2022-08-23)'
rustc = 'rustc 1.65.0-nightly (ce36e8825 2022-08-28)'
cc = 'cc (Debian 12.2.0-1) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (6da726708 2022-08-23)
release: 1.65.0-nightly
commit-hash: 6da726708a4406f31f996d813790818dce837161
commit-date: 2022-08-23
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (ce36e8825 2022-08-28)
binary: rustc
commit-hash: ce36e88256f09078519f8bc6b21e4dc88f88f523
commit-date: 2022-08-28
host: x86_64-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
