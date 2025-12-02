# 获取文件的 SHA256 校验值

```powershell
certutil -hashfile README.md SHA256
```

# winget 安装 ffmpeg

```powershell
winget install "FFmpeg (Essentials Build)"
```

# 安装 chocos

需要用管理员模式。

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
