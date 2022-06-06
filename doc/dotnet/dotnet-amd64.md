# dotnet-amd64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-amd64 \
    cake233/dotnet-amd64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-amd64 /usr/local/powershell/pwsh
```


## dotnet-amd64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2022-06-06", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-06-06_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "65a1a05c13710fa3a9c6cd1fc2d11fabf77de1fff712f16a031cb51d74fea655"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1705738752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "397M"
zstd_bytes = 415930090

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220523"
previous_tag = "2022-05-23"
previous_file = "dotnet_amd64_2022-05-23_12-18-rootfs.tar.zst"
previous_sha256 = "abaed06ec625564f00a56803aed621954e90b8ca2d719a9a047bc8e3a23ae86b"

current_version = "latest02"
current_date = "20220606"
old_file = "dotnet_amd64_2022-05-09_12-18-rootfs.tar.zst"
old_sha256 = "a6c7fefa6832983f5aefb0033a6025ca2f393d9fb95e2154a5b3a9ff8cdb9062"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-06-06_12-16-rootfs.tar.zst
# SHA256SUM=65a1a05c13710fa3a9c6cd1fc2d11fabf77de1fff712f16a031cb51d74fea655
# BUILD_DATE=20220606
# BUILD_TAG=2022-06-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-06
begin = 2022-06-06 12:02:31.524727273+00:00
start-sync_0 = 12:05:01
start-zstd = 12:05:48
start-sync_1 = 12:15:50
end-sync_1 = 12:16:27
end = 2022-06-06 12:16:27.746354802+00:00

[server]
repo = "cake233/dotnet-amd64"

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
PATH = "/usr/local/powershell:/usr/local/dotnet/bin${PATH:+:${PATH}}"
DOTNET_ROOT = "/usr/local/dotnet"
DOTNET_RUNNING_IN_CONTAINER = true
ASPNETCORE_URLS = ""
DOTNET_GENERATE_ASPNET_CERTIFICATE = false
DOTNET_USE_POLLING_FILE_WATCHER = true
Logging__Console__FormatterName = ""
NUGET_XMLDOC_MODE = "skip"

[version]
ldd = 'ldd (GNU libc) 2.35'
git = 'git version 2.36.1'
dotnet = '6.0.300'
powershell = 'PowerShell 7.2.4'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.300
 Commit:    8473146e7d

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/6.0.300/

Host (useful for support):
  Version: 6.0.5
  Commit:  70ae3df4a6

.NET SDKs installed:
  6.0.300 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.5 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.5 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

To install additional .NET runtimes or SDKs:
  https://aka.ms/dotnet-download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
