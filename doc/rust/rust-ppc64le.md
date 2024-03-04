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
tag = ["latest", "2024-03-04", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2024-03-04_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "db0143d65202089f27abda5276c8dfb749ea4b443f77e3290121bceffe615fb7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1728902656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 234217509

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_ppc64el_2023-11-27_03-02-rootfs.tar.zst"
previous_sha256 = "b1ada3fb2e8f52a1963baf5be5bff055e54e7ab0805baa0a309c6b77a9998b55"

current_version = "latest02"
current_date = "20240304"
old_file = "rust_ppc64el_2023-11-24_03-02-rootfs.tar.zst"
old_sha256 = "a81223bcdb5870598ca1c4a4db2222404549b763a08f7760e1ccfc21edd1917b"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2024-03-04_03-03-rootfs.tar.zst
# SHA256SUM=db0143d65202089f27abda5276c8dfb749ea4b443f77e3290121bceffe615fb7
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest02
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 02:52:31.281038530+00:00
start-sync_0 = 02:57:49
start-zstd = 02:58:35
start-sync_1 = 03:03:00
end-sync_1 = 03:03:14
end = 2024-03-04 03:03:14.940406201+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15.1) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.78.0-nightly (f772ec022 2024-03-01)'
rustc = 'rustc 1.78.0-nightly (516b6162a 2024-03-03)'
cc = 'cc (Debian 13.2.0-18) 13.2.0'
cargo_verbose = '''
cargo 1.78.0-nightly (f772ec022 2024-03-01)
release: 1.78.0-nightly
commit-hash: f772ec0224d3755ce52ac5128a80319fb2eb45d0
commit-date: 2024-03-01
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.2 (sys:0.18.2 vendored)
libcurl: 8.6.0-DEV (sys:0.4.72+curl-8.6.0 vendored ssl:OpenSSL/3.2.1)
ssl: OpenSSL 3.2.1 30 Jan 2024
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.78.0-nightly (516b6162a 2024-03-03)
binary: rustc
commit-hash: 516b6162a2ea8e66678c09e8243ebd83e4b8eeea
commit-date: 2024-03-03
host: powerpc64le-unknown-linux-gnu
release: 1.78.0-nightly
LLVM version: 18.1.0
'''
```
