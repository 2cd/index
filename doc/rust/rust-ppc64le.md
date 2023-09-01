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
tag = ["latest", "2023-09-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-09-01_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "254ec2c2adfe1abe743393a5ce570531c2b3e06d0d354a3aef999371437fe4ae"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1746721792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 226792057

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "rust_ppc64el_2023-08-28_03-09-rootfs.tar.zst"
previous_sha256 = "de76d65f00f680918ee3aa8b34c1b17a7d2513614dd35cc2f32af477d257636b"

current_version = "latest02"
current_date = "20230901"
old_file = "rust_ppc64el_2023-08-21_03-07-rootfs.tar.zst"
old_sha256 = "19059a2d3ba0f513d434354ef58e6e67ab78d72a490eb6012543d52ac5583c81"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-09-01_03-09-rootfs.tar.zst
# SHA256SUM=254ec2c2adfe1abe743393a5ce570531c2b3e06d0d354a3aef999371437fe4ae
# BUILD_DATE=20230901
# BUILD_TAG=2023-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-01
begin = 2023-09-01 02:52:32.681514002+00:00
start-sync_0 = 03:01:17
start-zstd = 03:02:27
start-sync_1 = 03:09:07
end-sync_1 = 03:09:29
end = 2023-09-01 03:09:29.129002269+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (96fe1c9e1 2023-08-29)'
rustc = 'rustc 1.74.0-nightly (2f5df8a94 2023-08-31)'
cc = 'cc (Debian 13.2.0-2) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (96fe1c9e1 2023-08-29)
release: 1.74.0-nightly
commit-hash: 96fe1c9e1aecd8f57063e3753969bb6418fd2fd5
commit-date: 2023-08-29
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (2f5df8a94 2023-08-31)
binary: rustc
commit-hash: 2f5df8a94bb3c5fae4e3fcbfc8ef20f1f976cb19
commit-date: 2023-08-31
host: powerpc64le-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
