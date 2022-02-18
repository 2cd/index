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
tag = ["latest", "2022-02-18", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
x11_or_wayland = false

[file]
name = "rust_ppc64el_2022-02-18_03-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "dcbc11825eaba383890627e72d3db433a83eed9b3fc92f284cc069db224e3fc0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1667293184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238073507

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220214"
previous_tag = "2022-02-14"
previous_file = "rust_ppc64el_2022-02-14_03-05-rootfs.tar.zst"
previous_sha256 = "ab38d056a1a03b52b84f972e30796ef37a250fc672ef4f297800915c95f77d42"

current_version = "latest02"
current_date = "20220218"
old_file = "rust_ppc64el_2022-02-11_03-05-rootfs.tar.zst"
old_sha256 = "3aa961e8d6b06ea99de8c07e2f061bcc0d08618457450e2dc3235c58221f2b48"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-02-18_03-05-rootfs.tar.zst
# SHA256SUM=dcbc11825eaba383890627e72d3db433a83eed9b3fc92f284cc069db224e3fc0
# BUILD_DATE=20220218
# BUILD_TAG=2022-02-18
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-18
begin = 2022-02-18 02:52:29.726530777+00:00
start-sync_0 = 02:58:53
start-zstd = 02:59:45
start-sync_1 = 03:04:56
end-sync_1 = 03:05:18
end = 2022-02-18 03:05:18.679981395+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (ea2a21c 2022-02-15)'
rustc = 'rustc 1.60.0-nightly (30b3f35c4 2022-02-17)'
cc = 'cc (Debian 11.2.0-16) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (ea2a21c 2022-02-15)
release: 1.60.0-nightly
commit-hash: ea2a21c994ca1e4d4c49412827b3cf4dcb158b1d
commit-date: 2022-02-15
host: powerpc64le-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (30b3f35c4 2022-02-17)
binary: rustc
commit-hash: 30b3f35c420694a4f24e5a4df00f06073f4f3a37
commit-date: 2022-02-17
host: powerpc64le-unknown-linux-gnu
release: 1.60.0-nightly
LLVM version: 14.0.0
'''
```
