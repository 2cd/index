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
tag = ["latest", "2023-11-27"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2023-11-27_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9c7f8f5c686d7d622eec4e0054e9039fff84d62820555bcc6604d825890ed796"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "836M"
tar_bytes = 876145664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 166594696

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231016"
previous_tag = "2023-10-16"
previous_file = "go_arm64_2023-10-16_12-11-rootfs.tar.zst"
previous_sha256 = "57199e6530806143529f184fdb303a7bec0592b638b17da15636a2bace370d4e"

current_version = "latest01"
current_date = "20231127"
old_file = "go_arm64_2023-10-02_12-10-rootfs.tar.zst"
old_sha256 = "c910ffa78584589912c4ab8d35235a9a300cafbe9f866cc987bea85088fb708d"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2023-11-27_12-09-rootfs.tar.zst
# SHA256SUM=9c7f8f5c686d7d622eec4e0054e9039fff84d62820555bcc6604d825890ed796
# BUILD_DATE=20231127
# BUILD_TAG=2023-11-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-27
begin = 2023-11-27 12:02:36.006103559+00:00
start-sync_0 = 12:05:00
start-zstd = 12:05:11
start-sync_1 = 12:09:29
end-sync_1 = 12:09:41
end = 2023-11-27 12:09:41.764058876+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
go = 'go version go1.21.4 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.4'

[other]
workdir = "/go"
```
