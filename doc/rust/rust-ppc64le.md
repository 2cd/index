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
tag = ["latest", "2023-09-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-09-11_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3240599cfae1c1e5e374c943b2248e79a4ed4861cc492cee95258f3d83da7b49"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1861315584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 227147561

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230908"
previous_tag = "2023-09-08"
previous_file = "rust_ppc64el_2023-09-08_03-05-rootfs.tar.zst"
previous_sha256 = "3da2bcd326cdcf91bfd6e7db2c88198e406fbf8e725b30d3dfad68b9e9204c2c"

current_version = "latest01"
current_date = "20230911"
old_file = "rust_ppc64el_2023-09-04_03-06-rootfs.tar.zst"
old_sha256 = "979a77608b1638f9b253c0035d5acbe5cf7b4d48f7b59bf74d3f3a627bc06bae"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-09-11_03-08-rootfs.tar.zst
# SHA256SUM=3240599cfae1c1e5e374c943b2248e79a4ed4861cc492cee95258f3d83da7b49
# BUILD_DATE=20230911
# BUILD_TAG=2023-09-11
# STATUS=completed
# VERSION=latest01
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-11
begin = 2023-09-11 02:52:40.682756951+00:00
start-sync_0 = 03:00:31
start-zstd = 03:01:47
start-sync_1 = 03:08:26
end-sync_1 = 03:08:51
end = 2023-09-11 03:08:51.037421221+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-8) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (2fc85d15a 2023-09-09)'
rustc = 'rustc 1.74.0-nightly (030e4d382 2023-09-10)'
cc = 'cc (Debian 13.2.0-3) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (2fc85d15a 2023-09-09)
release: 1.74.0-nightly
commit-hash: 2fc85d15a542bfb610aff7682073412cf635352f
commit-date: 2023-09-09
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (030e4d382 2023-09-10)
binary: rustc
commit-hash: 030e4d382f1df30240408540f25cd1ccc8dbbf50
commit-date: 2023-09-10
host: powerpc64le-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
