# dotnet-arm64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-arm64 \
    cake233/dotnet-arm64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-arm64 /usr/local/powershell/pwsh
```


## dotnet-arm64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2023-01-02", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2023-01-02_12-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bbd01b49648d0954945c3e9f3665d3960a71b7149155da972333d7861174a425"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1810969088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "400M"
zstd_bytes = 419154304

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221219"
previous_tag = "2022-12-19"
previous_file = "dotnet_arm64_2022-12-19_12-30-rootfs.tar.zst"
previous_sha256 = "a13f997afdd693b9d7e0b0bfb37c30e7f8d67759ab94a9de8dcc57e769cc8619"

current_version = "latest02"
current_date = "20230102"
old_file = "dotnet_arm64_2022-12-05_12-27-rootfs.tar.zst"
old_sha256 = "fbf05e781476a9c16b07b3af539891bd6e616140a434fba72cbb48e7b42e5a82"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2023-01-02_12-27-rootfs.tar.zst
# SHA256SUM=bbd01b49648d0954945c3e9f3665d3960a71b7149155da972333d7861174a425
# BUILD_DATE=20230102
# BUILD_TAG=2023-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-02
begin = 2023-01-02 12:02:35.449085316+00:00
start-sync_0 = 12:17:41
start-zstd = 12:18:34
start-sync_1 = 12:27:24
end-sync_1 = 12:27:54
end = 2023-01-02 12:27:54.071136830+00:00

[server]
repo = "cake233/dotnet-arm64"

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
git = 'git version 2.39.0'
dotnet = '7.0.101'
powershell = 'PowerShell 7.3.1'
dotnet_info = '''
.NET SDK:
 Version:   7.0.101
 Commit:    bb24aafa11

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/7.0.101/

Host:
  Version:      7.0.1
  Architecture: arm64
  Commit:       97203d38ba

.NET SDKs installed:
  7.0.101 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.1 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.1 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Other architectures found:
  None

Environment variables:
  DOTNET_ROOT       [/usr/local/dotnet]

global.json file:
  Not found

Learn more:
  https://aka.ms/dotnet/info

Download .NET:
  https://aka.ms/dotnet/download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
