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
tag = ["alpine", "2022-07-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2022-07-11_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4a8104552141724063ea84e21b473b14d2b03bcbccaa9d759bb8cddc8c583723"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "337M"
tar_bytes = 353206272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84582833

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "go-musl_amd64_2022-06-27_12-06-rootfs.tar.zst"
previous_sha256 = "c7c9dd13b4ab744e6f160225df3baa1e381993b88073d13eadb15ec906b71e13"

current_version = "latest01"
current_date = "20220711"
old_file = "go-musl_amd64_2022-06-13_12-06-rootfs.tar.zst"
old_sha256 = "7d48e3312b54baf16436f0790811b8ff7b97b360c986e11adb5f86a477fe4543"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2022-07-11_12-07-rootfs.tar.zst
# SHA256SUM=4a8104552141724063ea84e21b473b14d2b03bcbccaa9d759bb8cddc8c583723
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:30.791819270+00:00
start-sync_0 = 12:03:10
start-zstd = 12:03:24
start-sync_1 = 12:06:53
end-sync_1 = 12:07:06
end = 2022-07-11 12:07:06.425319128+00:00

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
go = 'go version go1.18.3 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.3'

[other]
workdir = "/go"
```
