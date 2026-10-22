# AI响铃 · 公众号内容仓库

用于统一管理公众号的选题、正文、配图、排版稿、资料来源和实际发布记录。

远程主源为 **[code5m/ai-ring-wechat](https://github.com/code5m/ai-ring-wechat)**，主分支为 `main`。仓库由用户创建，当前可见性为 **Public（公开）**；提交的正文、配图及记录均公开可见。仅保存可公开的公众号资料。

## 先打开哪里

下载整个仓库并解压后，双击根目录的 **[index.html](index.html)**，从中文内容目录打开文章。第一篇已经包含正文复制、标题与摘要复制、封面和卡片保存入口。

**首篇：** [Codex 重置消息总是看到太晚？先看懂这 3 件事](articles/2026-10-22-codex-reset-basics/article.md)

- [打开首篇排版与复制页](articles/2026-10-22-codex-reset-basics/layout.html)
- [封面](articles/2026-10-22-codex-reset-basics/assets/cover.png)
- [双语资料卡](articles/2026-10-22-codex-reset-basics/assets/source-card.png)
- [公众号头像](brand/avatar.png)

首篇当前为 **排版就绪，待公众号手机预览和实际发布**。正式发布链接与发布时间保持为空。GitHub 的 HTML 文件页显示源代码；使用复制按钮时，请下载并在浏览器打开排版页，保留整个目录中的配图。

## 平时怎么用

1. 在 [内容计划](docs/content-plan.md) 里确定选题。
2. 为文章建立独立目录，保存正文、来源、时间与配图。
3. 打开该篇 `layout.html`，复制标题、摘要与正文排版。
4. 到公众号后台粘贴，按插图标记上传图片，设置封面并做手机预览。
5. 实际发布后，把正式文章链接与发布时间填回 `article.json`。
6. 记录真实分享渠道和读者反馈，继续补充下一篇选题。

详细步骤见 [公众号发布流程](docs/publishing-workflow.md)。当前没有连接微信公众号账号或自动发布 API，仓库提交不会自动发布公众号文章。

## 内容放在哪里

| 目录或文件 | 用途 |
| --- | --- |
| `articles/<文章编号>/article.md` | 可编辑正文，保留来源链接 |
| `articles/<文章编号>/article.json` | 标题、摘要、状态、素材路径、来源与真实发布信息 |
| `articles/<文章编号>/layout.html` | 可打开的排版与复制页 |
| `articles/<文章编号>/assets/` | 该篇封面与正文卡片 |
| `brand/` | 统一头像与素材清单 |
| `templates/` | 新文章正文和资料模板 |
| `docs/` | 品牌、选题、发布流程与已确认决策 |
| `scripts/manage.py` | 校验、新建草稿、更新目录与记录发布结果 |
| `index.html` | 根据文章资料生成的中文内容目录 |

文章资料以各篇 `article.json` 为准；`index.html` 由脚本生成。调整正文时，同步更新该篇排版稿，避免两份文字不一致。

## 内容状态

| 状态 | 含义 |
| --- | --- |
| `draft` | 正在撰写或资料尚未齐全 |
| `ready` | 正文、排版稿、封面和卡片齐备，仍需公众号预览与发布 |
| `published` | 已取得正式公众号 URL，并记录实际发布时间 |
| `archived` | 已归档，不继续更新 |

公告本身的“预告、发放中、确认完成”与稿件状态分别记录。不能因为预计时间过去，就把公告记成已经完成。

## 可选的管理命令

需要 Python 3.9 或以上版本，不需要安装第三方包。在仓库目录运行：

```bash
python3 scripts/manage.py check
python3 scripts/manage.py catalog
python3 scripts/manage.py new reset-types --title "直接重置和备用重置有什么区别？" --summary "按原帖、账号状态和有效期判断。"
```

已经在微信完成发布后，才使用 `record-published` 记录真实 URL 和带时区的实际发布时间。这个命令只更新仓库记录，不向微信发送内容。具体参数可运行：

```bash
python3 scripts/manage.py record-published --help
```

## 统一风格与事实记录

遵循 [品牌规范](docs/brand-guide.md)：深色背景、青色重点、黑色玻璃卡片、原创虚拟人物与铃铛识别元素。正文优先保证阅读，来源卡片标清原文、中文理解和核对日期。

首篇关于备用重置的资料来自 [OpenAI 帮助中心](https://help.openai.com/en/articles/20001498-how-banked-codex-resets-work)，核对日期为 2026-10-22。后续涉及最新额度或重置消息时，应重新核对对应公告。

网站和 App 仍按实际进度表述。未提供真实群二维码前，文末使用“给公众号发：交流”的意向入口，不承诺自动回复或自动进群。

仓库建立与首次提交说明见 [仓库初始化](docs/repository-setup.md)。
