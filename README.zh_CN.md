**简体中文** · [English](README.md)

# PPT 翻页笔

把 AI Passport 变成 Mac 演讲遥控器，支持上下翻页、电脑音量控制和实时黑白画面缩略预览，已实测 WPS 放映。

## 下载

- [Mac 伴侣程序 ZIP](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/raw/refs/heads/main/ppt-pager-mac.zip)：必须使用；先在 macOS 安装 Python 3，再解压此文件。
- [当前固件源码 ZIP](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/raw/refs/heads/main/ppt-pager-source.zip)：包含本玩法源码、依赖配置、测试和开发文档，不是可烧录固件。

## 上手

1. 设备显示 IPHONE WI-FI SETUP 后，用 iPhone 连接 JOIN 后的 PPTPager-xxxx 热点，密码看 AP 后的内容。Safari 打开 http://192.168.4.1，选择现场 2.4 GHz Wi-Fi，输入密码并点 Connect PPT Pager。设备显示 LOOKING FOR MAC 即配网成功。Mac 接入同一局域网，手机回连原 Wi-Fi。
2. Mac 终端进入解压后的伴侣文件夹，运行 `python3 ppt_pager_companion.py --code 123456`，将 123456 换成设备 PAIR 后的六位码。为终端授予屏幕录制、辅助功能权限；如有 System Events 自动化请求，也请允许。等设备显示 CONNECTED。
3. 开始放映并保持窗口为前台。上键上一页，下键下一页；OK 短按加音量，长按减音量。设备显示电脑画面的黑白缩略预览。
4. 配网失败用 Choose Wi-Fi again 重选；双击上键可换网。设备重启后配对码会改变，请用新码重启伴侣。用完在终端按 Ctrl+C 停止。

## 验证与源码

用户于 2026-11-09 确认预览、WPS 上下翻页及双向音量控制均生效。重启重连、Wi-Fi 重置和长时间运行尚未验收。

源码 ZIP 包含本玩法基于 [FoloToy 原始工程](https://gitee.com/FoloToy/ai-passport) 的实际修改，并非未修改的模板。社区完整镜像 SHA-256 为 `825a14d514b7dc94b1d2c94449a3364b60669b507302e5b8b5d8317e5f7fb0fb`。上游 MIT 许可证已保留在 LICENSE 和源码包内。没有包含私有凭据或运行日志。

Mac 伴侣仅使用 Python 标准库和 macOS 自带工具，请在可信局域网使用。当前不支持 Windows。
