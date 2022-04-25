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
tag = ["latest", "2022-04-25", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "dotnet_arm64_2022-04-25_12-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0676774661520a583f786c9449a3596264d5fd4a459e13a6e7880d4b11716617"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1702780928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "380M"
zstd_bytes = 397455921

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "dotnet_arm64_2022-04-11_11-26-rootfs.tar.zst"
previous_sha256 = "4adc1505a9e6b330767d72d38082c56e2461b8e8bc87bfab687165a0dd3ef8d8"

current_version = "latest01"
current_date = "20220425"
old_file = "dotnet_arm64_2022-03-28_11-26-rootfs.tar.zst"
old_sha256 = "1d558e6dc57c28219bfebd259f3d9a4c5b985a01a464751ac025fa65bd2588ab"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2022-04-25_12-26-rootfs.tar.zst
# SHA256SUM=0676774661520a583f786c9449a3596264d5fd4a459e13a6e7880d4b11716617
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 12:02:30.573974839+00:00
start-sync_0 = 12:15:52
start-zstd = 12:16:35
start-sync_1 = 12:25:39
end-sync_1 = 12:26:08
end = 2022-04-25 12:26:08.610384763+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
git = 'git version 2.36.0'
dotnet = '6.0.202'
powershell = 'PowerShell 7.2.2'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.202
 Commit:    f8a55617d2

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/6.0.202/

Host (useful for support):
  Version: 6.0.4
  Commit:  be98e88c76

.NET SDKs installed:
  6.0.202 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.4 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.4 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

To install additional .NET runtimes or SDKs:
  https://aka.ms/dotnet-download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
