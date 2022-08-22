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
tag = ["alpine", "2022-08-22", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2022-08-22_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2bf7ff8aff63670798f43ea80ddc568424ac2638b88611d854f85fa391f4bbba"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "340M"
tar_bytes = 356387328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "82M"
zstd_bytes = 85217545

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220808"
previous_tag = "2022-08-08"
previous_file = "go-musl_armhf_2022-08-08_12-07-rootfs.tar.zst"
previous_sha256 = "0adf746fed71e5e8bb6226ac853d7d2d206b35a57bb5d29499384644c543684f"

current_version = "latest02"
current_date = "20220822"
old_file = "go-musl_armhf_2022-07-11_12-06-rootfs.tar.zst"
old_sha256 = "c895f101617104e354e3aec221ae650f3608a805ed032f10877b85bc07bcf014"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-08-22_12-07-rootfs.tar.zst
# SHA256SUM=2bf7ff8aff63670798f43ea80ddc568424ac2638b88611d854f85fa391f4bbba
# BUILD_DATE=20220822
# BUILD_TAG=2022-08-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-22
begin = 2022-08-22 12:02:25.556531859+00:00
start-sync_0 = 12:03:36
start-zstd = 12:03:49
start-sync_1 = 12:07:21
end-sync_1 = 12:07:35
end = 2022-08-22 12:07:35.263276986+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
go = 'go version go1.19 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.19'

[other]
workdir = "/go"
```
