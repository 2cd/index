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
tag = ["latest", "2023-01-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-01-06_03-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "eda1fd9a657ff8639710d84c0b6a8b70ad25a1cf2d58610da2d40cb98663684c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1765723648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238387368

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230102"
previous_tag = "2023-01-02"
previous_file = "rust_s390x_2023-01-02_03-06-rootfs.tar.zst"
previous_sha256 = "31a68f71b6860d532fc888294a140169e48bbccc79f16855e2054229307bbe30"

current_version = "latest01"
current_date = "20230106"
old_file = "rust_s390x_2022-12-26_03-05-rootfs.tar.zst"
old_sha256 = "4b686113087d402761442004c05e6410702bdf06d59a3093a901877fac11c3bb"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-01-06_03-11-rootfs.tar.zst
# SHA256SUM=eda1fd9a657ff8639710d84c0b6a8b70ad25a1cf2d58610da2d40cb98663684c
# BUILD_DATE=20230106
# BUILD_TAG=2023-01-06
# STATUS=completed
# VERSION=latest01
# END_TIME=03:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-06
begin = 2023-01-06 02:52:32.117142107+00:00
start-sync_0 = 03:02:47
start-zstd = 03:04:07
start-sync_1 = 03:10:53
end-sync_1 = 03:11:16
end = 2023-01-06 03:11:16.690292081+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-7) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (8c460b223 2023-01-04)'
rustc = 'rustc 1.68.0-nightly (388538fc9 2023-01-05)'
cc = 'cc (Debian 12.2.0-13) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (8c460b223 2023-01-04)
release: 1.68.0-nightly
commit-hash: 8c460b2237a6359a7e3335890db8da049bdd62fc
commit-date: 2023-01-04
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (388538fc9 2023-01-05)
binary: rustc
commit-hash: 388538fc963e07a94e3fc3ac8948627fd2d28d29
commit-date: 2023-01-05
host: s390x-unknown-linux-gnu
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
