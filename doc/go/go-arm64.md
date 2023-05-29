# go-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-arm64 \
    cake233/go-arm64
```

## How to exec shell?

```sh
docker exec -it go-arm64 bash
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
    cake233/go-arm64 \
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

## go-arm64.toml

```toml
[main]
name = "go"
tag = ["latest", "2023-05-29"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2023-05-29_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6f15dccd920ee6283f36a5242a1cc00e6e1cae8dc271854493104a948c6f3101"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "760M"
tar_bytes = 796810752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "182M"
zstd_bytes = 190527598

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230515"
previous_tag = "2023-05-15"
previous_file = "go_arm64_2023-05-15_12-11-rootfs.tar.zst"
previous_sha256 = "36afd5810baf84eefe20eacb7e82e244bd4beb3f6f60c61b23dccd3fee09d4dd"

current_version = "latest02"
current_date = "20230529"
old_file = "go_arm64_2023-05-01_12-12-rootfs.tar.zst"
old_sha256 = "47880ab0f392628eccb8619796a4c8bc3ccff40825b515c0204da08be86c01b7"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2023-05-29_12-10-rootfs.tar.zst
# SHA256SUM=6f15dccd920ee6283f36a5242a1cc00e6e1cae8dc271854493104a948c6f3101
# BUILD_DATE=20230529
# BUILD_TAG=2023-05-29
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-29
begin = 2023-05-29 12:02:40.325784363+00:00
start-sync_0 = 12:04:54
start-zstd = 12:05:07
start-sync_1 = 12:09:55
end-sync_1 = 12:10:10
end = 2023-05-29 12:10:10.605853444+00:00

[server]
repo = "cake233/go-arm64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
go = 'go version go1.20.4 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.4'

[other]
workdir = "/go"
```
