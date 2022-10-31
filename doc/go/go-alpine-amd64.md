# go-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it go-alpine-amd64 bash
```

## example

```sh
docker run \
    -t \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    -e GOOS=linux \
    -e CGO_ENABLED=0 \
    cake233/go-alpine-amd64 \
    go build -trimpath --ldflags "-s -w -buildid=" -v -o main.bin
```

## readme.go
```go
// go run readme.go
package main

import "fmt"

func main() {
	var (
		country, proxy_site string
	)

	country = "China"
	proxy_site = "https://goproxy.cn"
	fmt.Printf("If you live in\x1b[%dm %v. \x1b[0m\n", 32, country)
	fmt.Printf("Then you can run the following\x1b[%dm commands. \x1b[0m\n", 31)

	fmt.Println("go env -w GO111MODULE=on")
	fmt.Printf("go env -w GOPROXY=%v,direct\n", proxy_site)
}
```

## go-alpine-amd64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-10-31", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2022-10-31_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "89cba05fd3be1bfe24839715c1c8292adba55c53c2921b2ed10b1eee439f610b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "361M"
tar_bytes = 377882624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "86M"
zstd_bytes = 89389879

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221017"
previous_tag = "2022-10-17"
previous_file = "go-musl_amd64_2022-10-17_12-07-rootfs.tar.zst"
previous_sha256 = "a2f2ad73111786e7f53d4e9a80953ee5b66f11b40008f310345d9a77469b813a"

current_version = "latest02"
current_date = "20221031"
old_file = "go-musl_amd64_2022-10-03_12-07-rootfs.tar.zst"
old_sha256 = "46e9ed56537f8200aff67885310bfeccd914bd308cbdf510a109d7f8381051d7"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-10-31_12-06-rootfs.tar.zst
# SHA256SUM=89cba05fd3be1bfe24839715c1c8292adba55c53c2921b2ed10b1eee439f610b
# BUILD_DATE=20221031
# BUILD_TAG=2022-10-31
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-31
begin = 2022-10-31 12:02:27.987031210+00:00
start-sync_0 = 12:03:12
start-zstd = 12:03:22
start-sync_1 = 12:05:57
end-sync_1 = 12:06:07
end = 2022-10-31 12:06:07.771496584+00:00

[server]
repo = "cake233/go-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
go = 'go version go1.19.2 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.2'

[other]
workdir = "/go"
```
