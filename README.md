# 7z

## 压缩文件并设置密码，同时指定压缩格式为zip：

```bash
7z a -tzip -p<你的密码> <输出压缩包名称.zip> <要压缩的文件或文件夹路径>
```

## 指定压缩等级 -mx{N}，例如最高等级如下

```bash
-mx9
```

## 解压缩文件并同时把解压缩密码设置好

```bash
7z x -p<密码> <压缩文件路径> -o<解压目标目录>
```

# MyBase

## 修改时间戳持续延长试用期：

Windows 下一般在

```
C:\Users\{用户名}\Mybase8.ini
```

Mac 下一般在

```
~\Mybase8.ini
```

删除关键词为 FirstUseOn.UserLic.App 的这一行。

# GitHub

## 下载 GitHub CLI 客户端：

```bash
# macOS
brew install gh

# Linux (Ubuntu/Debian)
sudo apt install gh

# Windows
winget install GitHub.cli
```

## 下载 release 资源

gh release download {资源tag名}

# MarkDown

## 用 html 标签指定图片尺寸

否则用默认的图片展示会特别容易尺寸失控。

```html
<img src="https://bafkreicqzgxkfohyzgclz2mkbywlted25opyphj5yflz6n5zqjbxgg5k2y.pinme.dev/" alt="https://bxgg5k2y.pinit.eth.limo" width="320" />
```



