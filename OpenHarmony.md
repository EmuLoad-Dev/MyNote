# 基础

助记，对应关系。

| 🔑 | 🚪 |
| --- | --- |
| DevEco Studio | Android Studio |
| HAP | APK |
| build-profile.json5 | build.gradle |

开发语言 ArkTS，TypeScript 的扩展。

# ArkUI

onClick

```typescript
.onClick(() => {
})
```

# Windows 11 开启鸿蒙模拟器失败的问题

在启动时不但检查 Hyper-V 主服务（hvhost、hvax64 等），还傻乎乎地去检查这几个只有 Guest 才需要的 vmic 服务，发现没运行就直接报 00801001。

正确且彻底的解决办法：

1. Win + R → regedit 打开注册表编辑器
2. 定位到路径：textHKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization（如果没有 Virtualization 文件夹，自己新建一个）。
3. 在右侧空白处右键 → 新建 → DWORD (32位)值，命名为：textGuestServicesEnabled双击把数值数据改为 1 。
4. 重启电脑（或者直接重启 DevEco Studio 也行）。

