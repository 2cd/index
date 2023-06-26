# go-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-amd64 \
    cake233/go-amd64
```

## How to exec shell?

```sh
docker exec -it go-amd64 bash
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
    cake233/go-amd64 \
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

## go-amd64.toml

```toml
[main]
name = "go"
tag = ["latest", "2023-06-26"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2023-06-26_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e77bb683ff84db71b9911e7f4d83f38a2aeee9df63ce10e33754b338b02e3650"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "857M"
tar_bytes = 897852928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198822283

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230612"
previous_tag = "2023-06-12"
previous_file = "go_amd64_2023-06-12_12-09-rootfs.tar.zst"
previous_sha256 = "c2f703cfaa2c1167c55e4d871305f49aeda3016115a7be06b41e121352eb90c8"

current_version = "latest02"
current_date = "20230626"
old_file = "go_amd64_2023-05-15_12-09-rootfs.tar.zst"
old_sha256 = "544b738be7bab6bdaa130bfe2c8c5be5467ee8fda85525c4e6b9657d4aeb5a99"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2023-06-26_12-09-rootfs.tar.zst
# SHA256SUM=e77bb683ff84db71b9911e7f4d83f38a2aeee9df63ce10e33754b338b02e3650
# BUILD_DATE=20230626
# BUILD_TAG=2023-06-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-26
begin = 2023-06-26 12:02:41.532913604+00:00
start-sync_0 = 12:03:45
start-zstd = 12:04:38
start-sync_1 = 12:09:39
end-sync_1 = 12:09:55
end = 2023-06-26 12:09:55.779324390+00:00

[server]
repo = "cake233/go-amd64"

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
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
go = 'go version go1.20.5 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.5'

[other]
workdir = "/go"
```
