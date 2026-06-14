# 音流车机版播放解析源

这个仓库保存音流车机版使用的 LX 兼容 JS 播放解析源。

## 清单导入

App 支持导入清单文件。清单是一行一个 JS 地址，空行和 `#` 开头的注释会被忽略。

默认清单：

```text
https://raw.giteeusercontent.com/hailongg/something/raw/main/sources.txt
```

在音流车机版的播放解析源页面里，通过 URL 导入这个清单地址，App 会后台逐行读取并依次导入每个 JS 源。

## 来源范围

本仓库同步自 `pdone/lx-music-source` 当前 README 中列出的 7 个在线导入源，每个源只保留 `latest.js`，不保留历史版本文件，避免 App 清单导入时出现过期或重复解析源。

| 源 | 本仓库文件 | 上游原始文件 |
| --- | --- | --- |
| SixYin | `sources/sixyin-latest.js` | `sixyin/latest.js` |
| Huibq | `sources/huibq-latest.js` | `huibq/latest.js` |
| Flower | `sources/flower-latest.js` | `flower/latest.js` |
| LX | `sources/lx-latest.js` | `lx/latest.js` |
| ikun | `sources/ikun-latest.js` | `ikun/latest.js` |
| Grass | `sources/grass-latest.js` | `grass/latest.js` |
| JuheApi | `sources/juhe-latest.js` | `juhe/latest.js` |

上游仓库：

```text
https://github.com/pdone/lx-music-source
```

## 文件说明

- `sources.txt`：默认解析源清单。
- `sources/*.js`：从上游同步的 JS 解析源快照。

## 更新方式

1. 更新 `sources/*.js`。
2. 确认 `sources.txt` 仍指向需要导入的 JS raw 地址。
3. 提交并推送本仓库。
4. 在 App 里重新导入 `sources.txt` 清单。

清单使用 raw URL，避免 App 需要理解 GitHub 页面地址或仓库结构。
