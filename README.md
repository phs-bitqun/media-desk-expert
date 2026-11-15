# ⚠️ 本仓库已合并，请勿再从这里安装

内容已迁入 **[phs-bitqun/workbuddy-media-desk](https://github.com/phs-bitqun/workbuddy-media-desk)**。

那个仓库现在是**一个包两种形态**：既是专家包（左侧「专家」里出卡片），也内置技能（说「记个灵感」直接命中）。本仓库的专家卡、技能、落地页、issue 模板已全部并入，且修了路径与 Node 版本口径。

## 现在这样装

```bash
git clone --depth 1 https://github.com/phs-bitqun/workbuddy-media-desk.git ~/workbuddy-media-desk
mkdir -p ~/.workbuddy/plugins/marketplaces/my-experts/plugins
cp -R ~/workbuddy-media-desk ~/.workbuddy/plugins/marketplaces/my-experts/plugins/
```

只想装技能、不要专家卡：

```bash
git clone --depth 1 https://github.com/phs-bitqun/workbuddy-media-desk ~/.workbuddy/media-desk-src \
  && bash ~/.workbuddy/media-desk-src/install.sh
```

- 介绍页：<https://phs-bitqun.github.io/workbuddy-media-desk/>
- 安装说明：[INSTALL.md](https://github.com/phs-bitqun/workbuddy-media-desk/blob/main/INSTALL.md)
- 提 issue：<https://github.com/phs-bitqun/workbuddy-media-desk/issues>

## 从本仓库迁移

如果你已经按旧说明装过（`plugins/media-desk-expert/`），先删掉旧包再按上面重装：

```bash
rm -rf ~/.workbuddy/plugins/marketplaces/my-experts/plugins/media-desk-expert
```

**你的数据不受影响**——内容一直在 `~/.workbuddy/media-desk/`，两个包读的是同一份。

---

本仓库保留作历史存档，不再更新。原始上游：[woniuniuniu/dsh-media-desk](https://github.com/woniuniuniu/dsh-media-desk)（MIT）。
