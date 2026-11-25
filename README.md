# Cici · 豆包国际版风格 AI 助手（Android）

> Dola 界面的完整安卓复刻客户端：登录页 → 主工作台 → AI 问答 / 看图解读，全部可点击、可跳转。

## 下载 / Download

| 文件 | 说明 | 链接 |
| --- | --- | --- |
| **Cici-1.0.apk** | 已签名，可直接安装（minSdk 24 / Android 7.0+） | https://aka.doubaocdn.com/s/cO17A4InbZ |
| Cici-source-v1.0.zip | 完整工程源码（含构建脚本索引） | https://aka.doubaocdn.com/s/3cFfABKUFt |

> 安装时如提示“未知来源”，在系统设置里允许本应用安装未知应用即可。

## 界面预览

| 登录页 | 主界面 |
| --- | --- |
| ![login](https://aka.doubaocdn.com/s/e0QwXKwrqj) | ![main](https://aka.doubaocdn.com/s/KOla7ALFxP) |

## 功能

- **登录阻拦页**：Welcome back / Email or phone number / Continue / Google / Apple / QR code；右上角新增关闭 X，点击直接进入主界面。
- **手机号 / 邮箱登录**：Continue 后进入 6 位验证码页，输入完成即登录成功并回填头像。
- **Google / Apple**：点击提示“无法登录”（安卓环境无对应第三方登录能力）。
- **QR code**：打开二维码登录页，二维码直接使用提供的图4。
- **主工作台**：Dola 头像、New Chat、AI Writing、AI Reacing、Recent Chats、右上角 Log in。
- **侧边栏折叠**：左上角折叠按钮 → 侧边栏收起、主页面全屏；再次点击恢复图2 布局。
- **AI 问答**：输入框文本直接走大模型；回形针上传图片后由 AI 解读（视觉模型）。
- **可点击全覆盖**：AI 搜索 / 帮我写作 / View more / 四类写作模板 / 最近会话 / 头像 / 设置 / 登录 均有对应页面。
- **AI 服务**：默认调用 GitHub Models 推理接口；未填 Token 时自动走免密钥公共通道，保证开箱即用；设置页可填 GitHub Token 或任意 OpenAI 兼容接口。

## 技术实现

- 原生 Java + WebView 渲染（无第三方依赖，APK 约 350 KB）。
- 构建：aapt2 → javac → d8 → zipalign → apksigner（见 `docs/BUILD.md`）。
- 签名：自签名证书 `CN=Cici, O=Cici Mobile`，SHA-256 `f53a52f0d48689dece1520abc20b05be455b1e3adeda87089720dce95677ae11`。
- 应用包名：`com.cici.app`；应用名：`Cici`；图标使用提供的角色头像（图5）。
