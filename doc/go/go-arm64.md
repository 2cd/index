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
tag = ["latest", "2022-05-30"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2022-05-30_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "40ef08fb75fee5b3cbb8e4b6b029e9ff967d447acc484a9996a76b93f81e985b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "831M"
tar_bytes = 870653440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198715718

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220516"
previous_tag = "2022-05-16"
previous_file = "go_arm64_2022-05-16_12-12-rootfs.tar.zst"
previous_sha256 = "00f7bb3766157a8aa179b07577472b1464adab651cbf3bfe01e255cd86cd8b8b"

current_version = "latest01"
current_date = "20220530"
old_file = "go_arm64_2022-05-02_12-21-rootfs.tar.zst"
old_sha256 = "c853bf911319da2f7a4ad4c18bdefd418faea2c8a4a63b16429c62235ae8ee49"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-05-30_12-11-rootfs.tar.zst
# SHA256SUM=40ef08fb75fee5b3cbb8e4b6b029e9ff967d447acc484a9996a76b93f81e985b
# BUILD_DATE=20220530
# BUILD_TAG=2022-05-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-30
begin = 2022-05-30 12:02:42.377495958+00:00
start-sync_0 = 12:05:46
start-zstd = 12:06:02
start-sync_1 = 12:11:19
end-sync_1 = 12:11:37
end = 2022-05-30 12:11:37.110082785+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.18.2 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.2'

[other]
workdir = "/go"
```
