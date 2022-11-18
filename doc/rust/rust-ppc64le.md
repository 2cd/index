# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-11-18", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-11-18_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "36dfb74fad384496749037733bdae5a92dafed192e0ebb3e00cd427b3390f1f0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1657229312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227936291

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221114"
previous_tag = "2022-11-14"
previous_file = "rust_ppc64el_2022-11-14_03-05-rootfs.tar.zst"
previous_sha256 = "3e2f6bf0a555f72e14588f5faeec4e30dc3e46f906ef703f59d36e3352030a48"

current_version = "latest02"
current_date = "20221118"
old_file = "rust_ppc64el_2022-11-11_03-05-rootfs.tar.zst"
old_sha256 = "d590fcb1ef0aee278f4d7f602c2705cd5f07e6ffdee8d000f4ee9d07363d61e8"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-11-18_03-08-rootfs.tar.zst
# SHA256SUM=36dfb74fad384496749037733bdae5a92dafed192e0ebb3e00cd427b3390f1f0
# BUILD_DATE=20221118
# BUILD_TAG=2022-11-18
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-18
begin = 2022-11-18 02:52:25.095325279+00:00
start-sync_0 = 03:00:14
start-zstd = 03:01:28
start-sync_1 = 03:08:01
end-sync_1 = 03:08:21
end = 2022-11-18 03:08:21.873620745+00:00

[server]
repo = "cake233/rust-ppc64le"

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
cargo = 'cargo 1.67.0-nightly (16b097879 2022-11-14)'
rustc = 'rustc 1.67.0-nightly (83356b78c 2022-11-17)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (16b097879 2022-11-14)
release: 1.67.0-nightly
commit-hash: 16b097879b6f117c8ae698aab054c87f26ff325e
commit-date: 2022-11-14
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (83356b78c 2022-11-17)
binary: rustc
commit-hash: 83356b78c4ff3e7d84e977aa6143793545967301
commit-date: 2022-11-17
host: powerpc64le-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
