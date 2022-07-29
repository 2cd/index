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
tag = ["latest", "2022-07-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-07-29_03-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "99b213551614b324346685332d1aca8463b7d3055538e9bd35d4c491bca4a64e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.0G"
tar_bytes = 2074638848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "331M"
zstd_bytes = 346617415

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_ppc64el_2022-07-18_03-06-rootfs.tar.zst"
previous_sha256 = "924b0069887a7a31c1aa67a2164181f0c143a53b1fc7437f1b8e7eb7a44cb416"

current_version = "latest02"
current_date = "20220729"
old_file = "rust_ppc64el_2022-07-11_03-06-rootfs.tar.zst"
old_sha256 = "0dfa18734990404452821add21721a27096f9c85b06473b19686d45a726c7d6f"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-07-29_03-11-rootfs.tar.zst
# SHA256SUM=99b213551614b324346685332d1aca8463b7d3055538e9bd35d4c491bca4a64e
# BUILD_DATE=20220729
# BUILD_TAG=2022-07-29
# STATUS=completed
# VERSION=latest02
# END_TIME=03:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-29
begin = 2022-07-29 02:52:28.964800422+00:00
start-sync_0 = 03:00:24
start-zstd = 03:01:33
start-sync_1 = 03:11:05
end-sync_1 = 03:11:36
end = 2022-07-29 03:11:36.339972575+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (85b500cca 2022-07-24)'
rustc = 'rustc 1.64.0-nightly (9067d5277 2022-07-28)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (85b500cca 2022-07-24)
release: 1.64.0-nightly
commit-hash: 85b500ccad8cd0b63995fd94a03ddd4b83f7905b
commit-date: 2022-07-24
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (9067d5277 2022-07-28)
binary: rustc
commit-hash: 9067d5277d10f0f32a49ec9c125a33828e26a32b
commit-date: 2022-07-28
host: powerpc64le-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
