# 🚀 Tieba Sign Assistant (百度贴吧自动签到助手)

[![GitHub stars](https://img.shields.io/github/stars/noahacgn/tieba-sign-assistant?style=social)](https://github.com/noahacgn/tieba-sign-assistant)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Script Manager](https://img.shields.io/badge/Script-Tampermonkey-green.svg)](https://www.tampermonkey.net/)
[![Version](https://img.shields.io/badge/Version-0.1.0-blue.svg)]()

> **如果觉得好用，请移步 [GitHub 仓库](https://github.com/noahacgn/tieba-sign-assistant) 点个 Star ⭐️ 支持一下！**

一个基于 Tampermonkey 的百度贴吧自动签到脚本。采用移动端接口模拟，提供现代化的可视化面板，支持一键签到与智能补签功能。

## ✨ 特性 (Features)

*   **📱 移动端伪装**: 模拟百度贴吧客户端 (v12.64.1.1) 协议，签到更稳定，经验更多。
*   **🧠 智能策略**: 
    *   优先尝试网页版“一键签到”接口。
    *   若遇限速或失败，自动降级为“逐个贴吧签到”模式。
    *   自动跳过已签到或被频控的贴吧。
*   **🎨 现代化 UI**: 
    *   注入式悬浮面板，无需打开控制台即可操作。
    *   深色模式 (Dark Mode) 设计，护眼美观。
    *   实时滚动日志，清晰展示签到进度与结果。
*   **🔒 安全隐私**: BDUSS 仅保存在本地 (GM_setValue)，不经过任何第三方服务器。
*   **📋 详细日志**: 区分成功、跳过、失败状态，错误原因一目了然。

## 🛠️ 安装 (Installation)

1.  **安装管理器**: 确保你的浏览器已安装 [Tampermonkey](https://www.tampermonkey.net/) 扩展。
2.  **安装脚本**: [点击此处安装](https://greasyfork.org/zh-CN/scripts/557370-tieba-auto-sign-aiotieba) 或将 `tieba-sign-assistant.user.js` 内容复制到 Tampermonkey 新建脚本中。
3.  **打开贴吧**: 访问 [tieba.baidu.com](https://tieba.baidu.com)。

## 📖 使用指南 (Usage)

1.  **启动面板**: 
    *   脚本加载后，页面右下角会出现一个蓝色悬浮球。
    *   点击悬浮球，或使用脚本菜单“打开/折叠签到面板”展开操作界面。
2.  **配置 BDUSS**:
    *   在面板的 `BDUSS` 输入框中填入你的百度账号 BDUSS。
    *   *注意：脚本不自动获取 BDUSS，需手动填写以确保安全。*
    *   点击 **“保存”** 按钮。
3.  **开始签到**:
    *   点击 **“开始”** 按钮。
    *   观察日志区域，脚本将自动执行获取 TBS、获取关注列表、执行签到等操作。

## ⚙️ 获取 BDUSS 方法

> BDUSS 是百度账号的身份凭证，请勿泄露给他人。

1.  在 PC 浏览器登录百度贴吧。
2.  按 `F12` 打开开发者工具，切换到 `Application` (应用) -> `Cookies`。
3.  找到 `tieba.baidu.com`，在右侧列表中找到名为 `BDUSS` 的项，复制其 Value 即可。

## ❓ 常见问题 (FAQ)

**Q: 为什么显示“获取 tbs 失败”？**  
A: 通常是因为 BDUSS 无效或已过期。请重新提取最新的 BDUSS 并保存。

**Q: 签到速度为什么变慢了？**  
A: 当触发百度服务端的“一键签到”限速（错误码 340011）时，脚本会自动切换为逐个签到模式，为了防止封禁，每个贴吧之间会有几百毫秒的延时。

**Q: 我的账号安全吗？**  
A: 脚本完全开源且本地运行。你的 BDUSS 仅存储在你的浏览器扩展存储中，代码中不包含任何上传数据的逻辑。

## 📜 许可证 (License)

本项目采用 [MIT License](LICENSE) 开源。

---
*Disclaimer: This script is for educational purposes only. Please use it responsibly.*
