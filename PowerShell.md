> 获取文件的 SHA256 校验值

获取单个文件。

```powershell
Get-FileHash -Path "README.md" -Algorithm SHA256
```

获取指定文件夹内所有 SHA256

```powershell
Get-ChildItem "{文件夹地址}" | Get-FileHash -Algorithm SHA256
```
