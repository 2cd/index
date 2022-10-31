# go-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it go-alpine-arm64 bash
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
    cake233/go-alpine-arm64 \
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

## go-alpine-arm64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-10-31", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2022-10-31_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "be0a78eb07d173650b14108022a2c8fb8dc589e069f43b5a93172292cea76081"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "357M"
tar_bytes = 373375488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "82M"
zstd_bytes = 85686711

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221017"
previous_tag = "2022-10-17"
previous_file = "go-musl_arm64_2022-10-17_12-06-rootfs.tar.zst"
previous_sha256 = "6100a810d660fbb0b6a7d840dde0e3822dac7eaab1ed458a611448909e0bbee4"

current_version = "latest01"
current_date = "20221031"
old_file = "go-musl_arm64_2022-10-03_12-07-rootfs.tar.zst"
old_sha256 = "71ab9af147da0ec1570fe3e348723f71d0de74211e213a2c43a2063f2c5e8aa4"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-10-31_12-06-rootfs.tar.zst
# SHA256SUM=be0a78eb07d173650b14108022a2c8fb8dc589e069f43b5a93172292cea76081
# BUILD_DATE=20221031
# BUILD_TAG=2022-10-31
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-31
begin = 2022-10-31 12:02:27.178039964+00:00
start-sync_0 = 12:03:08
start-zstd = 12:03:16
start-sync_1 = 12:06:26
end-sync_1 = 12:06:41
end = 2022-10-31 12:06:41.785106420+00:00

[server]
repo = "cake233/go-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
go = 'go version go1.19.2 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.2'

[other]
workdir = "/go"
```
