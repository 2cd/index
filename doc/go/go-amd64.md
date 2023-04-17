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
tag = ["latest", "2023-04-17"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2023-04-17_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fcdf83a7779b3cc9a6782b628a635225b72114ad85db6dac11595e09a9a3c106"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "790M"
tar_bytes = 827609600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "184M"
zstd_bytes = 191971612

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230403"
previous_tag = "2023-04-03"
previous_file = "go_amd64_2023-04-03_12-09-rootfs.tar.zst"
previous_sha256 = "ae33fefcecb655b57f83bb4f711133bd46fd8915088d5af1c3d60da345814a06"

current_version = "latest01"
current_date = "20230417"
old_file = "go_amd64_2023-03-20_12-10-rootfs.tar.zst"
old_sha256 = "ee595446950d3eb53d5faab4171aa366ccbd8b703003a6cea0145cfefac3965f"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2023-04-17_12-09-rootfs.tar.zst
# SHA256SUM=fcdf83a7779b3cc9a6782b628a635225b72114ad85db6dac11595e09a9a3c106
# BUILD_DATE=20230417
# BUILD_TAG=2023-04-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-17
begin = 2023-04-17 12:02:33.349139904+00:00
start-sync_0 = 12:03:38
start-zstd = 12:03:51
start-sync_1 = 12:08:46
end-sync_1 = 12:09:00
end = 2023-04-17 12:09:00.792761057+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
go = 'go version go1.20.3 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.3'

[other]
workdir = "/go"
```
