# 自媒体工作台（Media Desk Expert）

一句话记灵感，直接出能发的口播脚本、封面大字和分镜，排好发布时间，再把平台数据读成你自己的写作规则。

## 类型

Agent 型（单个 AI 专家）。技能 `media-desk` 随包自带，不依赖作者机器上的任何路径。

## 它能干什么

- **一句话成稿**：丢半句想法，出策划案 → 口播脚本 / 文章 → 分镜，中途不反问。
- **点名改稿**：「第 3 镜换俯拍」「封面字更有冲击力」只改那一处，不推翻重写。
- **风格卡**：15 个博主预设（AI 科技、美食探店、读书笔记…），也能从你自己的稿子里提炼一张。
- **排期 + 复盘**：日历排期，录播放/点赞/评论/转发/收藏，出互动率和日趋势。
- **规则自我强化**：数据里提炼出的规律，确认后变成规则，之后每次成稿自动生效。

## 使用示例

- 记个灵感：用 AI 做封面总像素材拼的
- 把这条灵感做成口播脚本，走 AI 科技博主那个风格
- 把这周的抖音数据录一下，看看有什么规律能沉淀成规则

## 安装（给别人用）

需要 Node.js 18+。

**方式一：放进专家目录**（最简单）

```bash
# macOS / Linux
mkdir -p ~/.workbuddy/plugins/marketplaces/my-experts/plugins
cp -R media-desk-expert ~/.workbuddy/plugins/marketplaces/my-experts/plugins/
```

Windows 放到 `%USERPROFILE%\.workbuddy\plugins\marketplaces\my-experts\plugins\`。

放好后重启 WorkBuddy，左侧「专家」里应该出现「自媒体工作台」。没出现就对着 WorkBuddy 说一句「注册 my-experts 下的 media-desk-expert」，它会跑注册脚本补上。

**方式二：命令行核验**

```bash
DESK="$HOME/.workbuddy/plugins/marketplaces/my-experts/plugins/media-desk-expert/skills/media-desk/scripts/desk.mjs"
node "$DESK" doctor
```

只要这条能打印出数据目录和风格数量，工作台就是通的。

## 数据在哪

`~/.workbuddy/media-desk/state.json`，纯本地文件，不上传、没有账号系统。

- 换电脑想带走历史：把整个 `~/.workbuddy/media-desk/` 目录拷过去。
- 想换个位置：设环境变量 `WORKBUDDY_MEDIA_DESK_HOME` 指向新目录。
- **别手改 `state.json`**，所有改动走 CLI，否则撤销链会断。

## 打开看板

```bash
node "$DESK" render     # 生成 ~/.workbuddy/media-desk/desk.html
```

用浏览器打开，五个页面：灵感 · 内容 · 排期 · 复盘 · 风格。

## 头像

写在 `avatars/expert.png`。要换就替换成 512×512、500KB 以内的 PNG/JPG。

## 卸载

删掉专家目录，可选再删 `~/.workbuddy/media-desk/`（数据会一起没，先备份）。

## 致谢

流程与提示词移植自 [woniuniuniu/dsh-media-desk](https://github.com/woniuniuniu/dsh-media-desk)（MIT）。WorkBuddy 版把它的宿主/客户端双半片换成了一个 CLI + 一个只读看板。
