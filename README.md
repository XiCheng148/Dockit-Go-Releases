# Dockit 发布产物

这个仓库**只放发布产物**（Dockit 的更新源），源码在私有的 `Dockit-Go` 仓库里。

Dockit 内置的自动更新就是从这里匿名下载的（公开仓库，不需要 token）：

    https://github.com/XiCheng148/Dockit-Go-Releases/releases/latest/download/update-windows-amd64.json

最新版下载页：<https://github.com/XiCheng148/Dockit-Go-Releases/releases/latest>

## 注意

- **不要改动 release 里的资产**（尤其 `update-*.json`、`*.tar.gz`、`install.ps1`）：
  文件名与 `update-*.json` 的内容是更新器的契约，改了已安装的应用就升不上去，
  签名也对不上。
- 发布由 CI 自动完成：源码仓库推 `vX.Y.Z` tag → 这里出现 draft release →
  人工确认后发布。流程写在源码仓库的 `RELEASING.md`。
- 更新包用内置公钥验签（`mygo.json` 的 `updates.publicKey`）；私钥只在 CI
  secret 与本机 `%APPDATA%/mygo/update-keys/` 里。
