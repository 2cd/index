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
tag = ["latest", "2022-09-30", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-09-30_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "03ab726cc4e9300c6cb178e34b831a56fbcc5eb2577f9240137b19f5c680d66b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1783752192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258520125

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220926"
previous_tag = "2022-09-26"
previous_file = "rust_ppc64el_2022-09-26_03-05-rootfs.tar.zst"
previous_sha256 = "3ce3c1a7faad96d43ef10f888f0c3cee863287ad4ea866fe193b3cb7c80df829"

current_version = "latest02"
current_date = "20220930"
old_file = "rust_ppc64el_2022-09-23_03-06-rootfs.tar.zst"
old_sha256 = "944035f79fa233f380b9883242ce8c053d972f2d218e5905d2eb46340d202b00"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-09-30_03-10-rootfs.tar.zst
# SHA256SUM=03ab726cc4e9300c6cb178e34b831a56fbcc5eb2577f9240137b19f5c680d66b
# BUILD_DATE=20220930
# BUILD_TAG=2022-09-30
# STATUS=completed
# VERSION=latest02
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-30
begin = 2022-09-30 02:52:30.745774889+00:00
start-sync_0 = 03:01:52
start-zstd = 03:03:05
start-sync_1 = 03:10:09
end-sync_1 = 03:10:36
end = 2022-09-30 03:10:36.648832364+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-1) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (f5fed93ba 2022-09-27)'
rustc = 'rustc 1.66.0-nightly (9c56d9d6f 2022-09-29)'
cc = 'cc (Debian 12.2.0-3) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (f5fed93ba 2022-09-27)
release: 1.66.0-nightly
commit-hash: f5fed93ba24607980647962c59863bbabb03ce14
commit-date: 2022-09-27
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (9c56d9d6f 2022-09-29)
binary: rustc
commit-hash: 9c56d9d6fec6262bbb1549cfe466a812ae2c6523
commit-date: 2022-09-29
host: powerpc64le-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.0
'''
```
