## 子代理派发约定

- 派发子代理时不指定 provider、model 与 reasoning_effort，交由已安装的「自动选择子代理供应商/模型」插件自动选择。
- 子代理提示词只带必需上下文：契约、任务清单、约束、验证标准。不塞调研全文——曾发生子代理读完 7 万字背景耗尽上下文零交付的事故。
- 本仓库文件是 CRLF、无 BOM 的 UTF-8 且含大量中文：绝不用 pwsh 的 `Set-Content`/`-replace` 重写，一律用 write/edit 工具或 Node 脚本（曾发生 GBK 重编码损坏 242 字符的事故）。
- 远端与部署：origin = fork（github.com/gurio-wine/dsh-email），upstream = 原仓库 STARDUSTLC666/dsh-email。**每次改动提交后必须 `git push origin main`**——本地 dsh 的插件从 fork 安装（`github:gurio-wine/dsh-email`），不推远端用户就拿不到。改完仓库后用 `dsh plugin --profile web update dsh-email` 从 fork 拉新生效（前端热替换，后端改动需重启 dsh）。
