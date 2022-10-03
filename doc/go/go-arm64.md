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
tag = ["latest", "2022-10-03"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2022-10-03_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "acf92434a0373da3028e86f6d7b9a2efe6c9df8f8637ed3ccd9c723c0fcf354d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "852M"
tar_bytes = 893043200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "194M"
zstd_bytes = 202958746

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220919"
previous_tag = "2022-09-19"
previous_file = "go_arm64_2022-09-19_12-10-rootfs.tar.zst"
previous_sha256 = "92f1ce7420fa96c9d5678fe1b8fd73716bb6936ba5e7c3c5f44774a6f346b25f"

current_version = "latest01"
current_date = "20221003"
old_file = "go_arm64_2022-09-05_12-10-rootfs.tar.zst"
old_sha256 = "b5a073b79421b65a860f9937d6edfc27a34aee6f04f73e43872f80eb042f5e93"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-10-03_12-11-rootfs.tar.zst
# SHA256SUM=acf92434a0373da3028e86f6d7b9a2efe6c9df8f8637ed3ccd9c723c0fcf354d
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 12:02:27.494530265+00:00
start-sync_0 = 12:05:37
start-zstd = 12:05:55
start-sync_1 = 12:11:36
end-sync_1 = 12:11:57
end = 2022-10-03 12:11:57.312245848+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
go = 'go version go1.19.1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.1'

[other]
workdir = "/go"
```
