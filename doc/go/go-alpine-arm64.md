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
tag = ["alpine", "2023-08-07", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2023-08-07_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f13054a931eae38bfba23a84d1f779786c3fe252e2abb1f45bb13c94e651d6f7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "272M"
tar_bytes = 284506624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 73237193

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230724"
previous_tag = "2023-07-24"
previous_file = "go-musl_arm64_2023-07-24_12-07-rootfs.tar.zst"
previous_sha256 = "1a132bcd91635d422d93edaeaeb59f7119d8563985278238bc4b46de1bdcafb9"

current_version = "latest02"
current_date = "20230807"
old_file = "go-musl_arm64_2023-06-26_12-06-rootfs.tar.zst"
old_sha256 = "a85fcb62736029e901f3aefb7c012a0199a750ff2d2c35f0162092d17c31e546"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2023-08-07_12-07-rootfs.tar.zst
# SHA256SUM=f13054a931eae38bfba23a84d1f779786c3fe252e2abb1f45bb13c94e651d6f7
# BUILD_DATE=20230807
# BUILD_TAG=2023-08-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-07
begin = 2023-08-07 12:02:43.565937546+00:00
start-sync_0 = 12:04:19
start-zstd = 12:04:34
start-sync_1 = 12:07:20
end-sync_1 = 12:07:36
end = 2023-08-07 12:07:36.564172227+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
go = 'go version go1.20.7 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.7'

[other]
workdir = "/go"
```
