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
tag = ["alpine", "2022-03-07", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "go-musl_armhf_2022-03-07_12-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "369722d929287032e43fa8ebcaca6caa5ee966457110071a51a69765b4148a69"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "317M"
tar_bytes = 331996672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "77M"
zstd_bytes = 80515424

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "go-musl_armhf_2022-03-01_18-57-rootfs.tar.zst"
previous_sha256 = "7009c30efde8726b1a9480bee47806abdc15f44809106d794a384710f82e1db8"

current_version = "latest02"
current_date = "20220307"
old_file = "go-musl_armhf_2022-02-07_12-05-rootfs.tar.zst"
old_sha256 = "3a5f33ba597364af4ed697627a002c7b7790db2776940d6e032d29cd122d5d95"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-03-07_12-07-rootfs.tar.zst
# SHA256SUM=369722d929287032e43fa8ebcaca6caa5ee966457110071a51a69765b4148a69
# BUILD_DATE=20220307
# BUILD_TAG=2022-03-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-07
begin = 2022-03-07 12:02:37.176542287+00:00
start-sync_0 = 12:03:41
start-zstd = 12:03:57
start-sync_1 = 12:06:57
end-sync_1 = 12:07:12
end = 2022-03-07 12:07:12.410522452+00:00

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
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
go = 'go version go1.18rc1 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.18rc1'

[other]
workdir = "/go"
```
