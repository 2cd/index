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
tag = ["latest", "2022-09-05"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2022-09-05_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e6daab33760097a9e679f466f6b41aa63cf32da2a68f64783727a0f5de6f0d36"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "994M"
tar_bytes = 1041777152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220610521

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220822"
previous_tag = "2022-08-22"
previous_file = "go_amd64_2022-08-22_12-09-rootfs.tar.zst"
previous_sha256 = "d3f4d7433221f958d897ab14006414b33836638077bd8324a5d35d205ca8fd8f"

current_version = "latest01"
current_date = "20220905"
old_file = "go_amd64_2022-08-08_12-10-rootfs.tar.zst"
old_sha256 = "8f3a110a955fd78b0b2321e4daeb5d2c06bea221cfac57d5a4c297728fd3c077"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2022-09-05_12-10-rootfs.tar.zst
# SHA256SUM=e6daab33760097a9e679f466f6b41aa63cf32da2a68f64783727a0f5de6f0d36
# BUILD_DATE=20220905
# BUILD_TAG=2022-09-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-05
begin = 2022-09-05 12:02:26.630882600+00:00
start-sync_0 = 12:03:47
start-zstd = 12:04:38
start-sync_1 = 12:09:56
end-sync_1 = 12:10:15
end = 2022-09-05 12:10:15.744782883+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.19 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.19'

[other]
workdir = "/go"
```
