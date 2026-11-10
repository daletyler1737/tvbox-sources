# TVBox / 影视仓 订阅源（实测版）

国内可用，全部经本机 curl 实测。`raw.githubusercontent.com` / `raw.kkgithub.com` / `ghp.ci` / `gitdl.cn` / `raw.githubusercontents.com` 在本机**全部不可达**，所以统一走 `gh-proxy.com` 与 `jsdelivr`。

## 1. 多仓（推荐，先填这个）

```
https://cdn.jsdelivr.net/gh/daletyler1737/tvbox-sources@main/multi.json
```

备用（镜像轮换，任选其一）：

```
https://gh-proxy.com/https://raw.githubusercontent.com/daletyler1737/tvbox-sources/main/multi.json
https://ghproxy.cfd/https://raw.githubusercontent.com/daletyler1737/tvbox-sources/main/multi.json
https://gh-proxy.net/https://raw.githubusercontent.com/daletyler1737/tvbox-sources/main/multi.json
```

**17 个子仓，实测 17/17 可拉**，且每个仓的 spider jar 都下到真身校验过（zip 头 + >100KB）：

| 子仓 | 站点数 |
|---|---|
| 高天流云 js | 298 |
| 聚合 juhe | 223 |
| 牛虎 | 135 |
| 王二小 / 牛二 | 100 / 100 |
| 神仙 | 94 |
| 高天流云 0821 | 86（+16 条直播） |
| Qist 0821 | 86 |
| 挺好 | 46 |
| 2hacc oktv（修复版） | 41 |
| 肥猫 | 40 |
| 短剧 | 35 |
| 高天流云 0827 | 33 |
| 茄子库 | 31 |
| 动漫 | 27 |
| Sylvan 精选 | 20 |
| 讴歌 | 12 |

## 2. 单仓（oktv 修复版，41 站）

```
https://cdn.jsdelivr.net/gh/daletyler1737/tvbox-sources@main/oktv-fixed.json
```

原版 oktv.json 有三处硬伤，已修：

1. `spider` 指向 `raw.kkgithub.com` —— 该域名国内已死，jar 下不来，整仓全站不可用 → 换 gh-proxy
2. `spider` 里的 md5 与 jar 文件实际 md5 不符（265301f4… vs f98827d8…），播放器校验不过会直接拒载 → 重算
3. 4 条直播源死 2 条、wallpaper 404 → 换成实测 200 的

另外把 `notabug.org` 上的 drpy2.min.js（404）换成了 dr_py 官方镜像。

## 说明

- 源会腐烂。失效后重跑探测脚本重新生成，别手改 URL。
- 你给的 25 个热门源里，本机实测只有「俊于」(http://home.jundie.top:81/top98.json) 直连能通，其余域名基本已过期。
- 唐三 `gh.t4tv.hz.cz`、`饭太硬.top`、`肥猫.love:63`、`yydsys.top/duo`（404）、`kstore.space`（域名失效）这些也都不可达。
