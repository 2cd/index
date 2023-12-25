# go-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-armv7 \
    cake233/go-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it go-alpine-armv7 bash
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
    cake233/go-alpine-armv7 \
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

## go-alpine-armv7.toml

```toml
[main]
name = "go"
tag = ["alpine", "2023-12-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2023-12-25_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "00f7b8084acdae36df5dd5b4a2b175065a144125244df27abb3eb1bb9a04f6b2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "231M"
tar_bytes = 241531392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41413991

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "go-musl_armhf_2023-11-27_12-06-rootfs.tar.zst"
previous_sha256 = "b526094b211062849f45d1cf4bee4f1eed5127547966d56ce50883f751d5f189"

current_version = "latest01"
current_date = "20231225"
old_file = "go-musl_armhf_2023-11-13_12-06-rootfs.tar.zst"
old_sha256 = "0efa788337d9d1cf3c7e7c5bcd5a8a0e3c88d6137b9bdcb97b8924eb49a6d411"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2023-12-25_12-06-rootfs.tar.zst
# SHA256SUM=00f7b8084acdae36df5dd5b4a2b175065a144125244df27abb3eb1bb9a04f6b2
# BUILD_DATE=20231225
# BUILD_TAG=2023-12-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-25
begin = 2023-12-25 12:02:36.887769736+00:00
start-sync_0 = 12:03:56
start-zstd = 12:04:07
start-sync_1 = 12:06:14
end-sync_1 = 12:06:24
end = 2023-12-25 12:06:24.818031970+00:00

[server]
repo = "cake233/go-alpine-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.4_git20230717'
go = 'go version go1.21.5 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.21.5'

[other]
workdir = "/go"
```
