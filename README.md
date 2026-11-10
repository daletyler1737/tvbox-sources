# TVBox / 影视仓 订阅源（实测版）

国内可用，镜像统一走 `gh-proxy.com`（本机实测 200，`raw.githubusercontent.com` / `kkgithub` / `ghp.ci` 直连全死）。

## 1. 多仓（推荐先填这个）
```
https://cdn.jsdelivr.net/gh/daletyler1737/tvbox-sources@main/multi.json
```
备用：
```
https://gh-proxy.com/https://raw.githubusercontent.com/daletyler1737/tvbox-sources/main/multi.json
```
内容：17 个子仓，全部实测 JSON 可拉 + 每个仓的 spider jar 真身下载校验过（zip 头 + 大小 > 100KB）。

## 2. 单仓（oktv 修复版，41 站）
```
https://cdn.jsdelivr.net/gh/daletyler1737/tvbox-sources@main/oktv-fixed.json
```
修了原版三处：spider jar 的 `raw.kkgithub.com` 死链 → gh-proxy；jar md5 重算（原 md5 与文件不符，播放器会直接拒载）；4 条直播源里 2 条已死 + wallpaper 404 → 换活的。

## 说明
- 源会腐烂。失效后重跑探测脚本重新生成，不要手改 URL。
- 用户清单里 25 个热门源，本机实测只有「俊于」1 个能直连（其余域名已过期/需特定网络）。
