# 全局配置

## 1. 检查 id_rsa.pub 文件在不在

一般路径
- Windows: `C:\Users\{UserName}\.ssh\id_ed25519.pub`
- Linux: `~/.ssh/id_rsa.pub`

## 2. 生成 key

```bash
ssh-keygen -t ed25519 -C "xxx@xxx.com"
```

生成后可以通过打印日志看到密钥文件所在位置。

## 3. 到 github 处的 settings 配置密钥。

https://github.com/settings/profile

SSH and GPG keys 选项，New SSH key。

将 .ssh/id_ed25519.pub 文本内容拷贝到 Authentication keys 。

# 单独一个仓库配置

第一和第二个步骤与全局配置完全一样。

第三步骤的设置地址为：

https://github.com/{用户名}/{仓库名}/settings/keys

选择 Add deploy key，添加密钥。

**注意：添加时要决定是否需要设置为可写，配置为是才有可写权限。**

# 多个仓库的多个配置

因为本地设备可能要单独设置多个 github 项目，因此需要这种更定制化的方案，方法如下。

## 步骤1：生成 key。

```bash
ssh-keygen -t ed25519 -C "your_email@example.com" -f {ssh主目录}/.ssh/id_ed25519_{project name}
```

## 步骤2：编写 config 配置文件。

在 `{ssh主目录}/.ssh/` 下，新建一个 config 文件（如果没有）。文件名为 `config` ，没有后缀。

这个文件是用来告诉 git，执行 git 仓库操作时应该读取哪个密钥文件。

`config` 示例如下：

```
# 默认的github配置，使用第一个密钥
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519

# 为特定仓库或另一个账户使用第二个密钥
# 这里我们创建一个别名 "newproject"
Host newproject
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_newproject
```

那么，git clone 命令应该为：

**注意 github.com被改为了 newproject**

```bash
git clone git@newproject:username/{仓库名}.git
```

## 步骤3：到 github 配置 key

地址： https://github.com/{用户名}/{仓库名}/settings/keys

选择 Add deploy key，添加密钥。