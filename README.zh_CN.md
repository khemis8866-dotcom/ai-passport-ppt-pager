**简体中文** · [English](README.md)

# PPT 翻页笔 · 彩色版

> **本项目仅供个人学习研究，严禁商用。**
> 项目新增部分采用 PolyForm Noncommercial 1.0.0，适用范围见 [LICENSE](LICENSE)
> 和 [NOTICE](NOTICE)；上游 MIT、第三方许可及既有授权继续有效。

把演讲画面握在手里：设备上查看彩色实时预览，随手翻页、调节 Mac 音量。
在同一局域网覆盖范围内，可以离开电脑从容走动。实际连接范围取决于网络覆盖
及隔离设置，无需蓝牙配对。已实测 WPS，当前仅支持 macOS。这是画面预览，不是视频。

## v1.1 下载

- [彩色 Mac 伴侣](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/ppt-pager-mac.zip)：需要 Python 3.9 或更新版本，无额外 Python 包。
- [完整固件](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/FoloToy-AI-Passport-full.bin)：合并镜像写入 0x0；完整刷写可能重置保存的 Wi-Fi。
- [当前源码快照](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/ppt-pager-source.zip)：含玩法、伴侣、测试、字体材料和工程文档。

## 上手

1. 解压伴侣 ZIP。按 Command+空格打开“终端”，运行 `python3 --version`；需要时从 [Python 官网](https://www.python.org/downloads/macos/) 安装适合本机的 Python 3。
2. 设备提示配网时，iPhone 连接屏幕上的 `PPTPager-xxxx` 热点，密码看“热点密码”。Safari 打开 http://192.168.4.1，扫描选择现场 2.4 GHz Wi-Fi，输入密码后点 Connect PPT Pager；设备显示“等待电脑连接”才表示成功。Mac 连同一局域网，手机可回原 Wi-Fi。
3. 旧伴侣先按 Control+C 停止。在终端输入 `cd` 加一个空格，把解压后的 `PPT-Pager-Mac` 文件夹从访达拖入终端，再回车。运行 `python3 ppt_pager_companion.py --code 123456`，把 123456 换成设备当前六位“配对码”，保持终端运行。
4. 为“终端”开启屏幕录制、辅助功能及提示的 System Events 控制权限。若要求重开终端，重复第 3 步；否则授权后重启伴侣。等待设备显示“已连接电脑”。
5. WPS 保持前台放映：上键上一页，下键下一页；确定短按加音量、长按减音量。Control+C 停止伴侣。设备重启后先停旧伴侣，再用新配对码启动。配网失败重连设备热点、点网页 Choose Wi-Fi again 重选；仅换网时双击上键清除旧 Wi-Fi 后重新配网。

彩色画面必须使用新版伴侣；旧伴侣仍兼容，但只提供黑白预览。原生彩色画面为
240×135，使用保持比例的过滤缩放；电脑上的细小文字仍受设备屏幕大小限制。

## 验证与旧版

构建、主机检查及 14 项伴侣测试通过。用户已在这份烧录的 v1.1 镜像上确认
彩色预览、WPS 翻页和双向音量均正常。长时间运行、联网时堆余量测量仍待验证。
完整镜像 SHA-256：
`167ba37a191d376fc0a9da282998d8ddca9185bfb105fa59d665babf42450d3b`。

[冻结的 v1.0 Release](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/tag/v1.0)
继续保留。当前源码在上方 v1.1 源码快照中，仓库首页作为版本下载索引维护；
根目录的 `ppt-pager-source.zip` 是 v1.0 旧快照，当前源码请使用 v1.1 Release 链接。
发布包排除私有凭据、设备标识、本机路径、日志和调试文件。
