# 区域商业化专家团

这是一个可安装到 Codex 的团队插件。它包含市场进入、法规、渠道、消费者、产品与品牌、增长、铺货和商业测算的协作工作流。

## 仓库结构

```text
.agents/plugins/marketplace.json   Codex Marketplace 目录
plugins/market-entry-team/         可安装插件
```

插件主体位于 `plugins/market-entry-team/skills/market-entry-team/`。修改专家团规则、专家合同或参考资料时，只修改该目录中的文件。

## 本地验证

```bash
python3 /Users/jiangyang/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py \
  plugins/market-entry-team
```

## 安装到 Codex

本仓库发布在 GitHub：<https://github.com/orgcomcn/codex-plugins>。

插件名为 `market-entry-team`，Marketplace 名为 `market-entry-team-marketplace`。团队成员可任选以下一种方式安装。

### 方式一：在 Terminal 中执行

```bash
codex plugin marketplace add orgcomcn/codex-plugins --ref main
codex plugin add market-entry-team@market-entry-team-marketplace
```

完成后，在 Codex 的 Plugins 页面确认 `market-entry-team` 显示为 `installed`、`enabled`。随后新开一个任务即可使用。

### 方式二：将以下提示词发给 Codex

```text
请帮我在这台电脑安装公司内部的“区域商业化专家团”Codex 插件。

GitHub 仓库是：https://github.com/orgcomcn/codex-plugins
插件名：market-entry-team
Marketplace 名：market-entry-team-marketplace

请在 Terminal 依次执行：
codex plugin marketplace add orgcomcn/codex-plugins --ref main
codex plugin add market-entry-team@market-entry-team-marketplace

执行后检查插件是否显示为 installed、enabled。不要修改或删除任何现有 Skill、插件和 Codex 配置；请告诉我实际安装的版本号。
```

## 更新到最新版

维护者将新版本合并到 `main` 后，已安装插件的同事可任选以下一种方式更新。

### 方式一：在 Terminal 中执行

```bash
codex plugin marketplace upgrade market-entry-team-marketplace
codex plugin add market-entry-team@market-entry-team-marketplace
```

完成后，在 Codex 的 Plugins 页面确认 `market-entry-team` 显示为 `installed`、`enabled`，并新开一个任务以加载新版 Skill。

### 方式二：将以下提示词发给 Codex

```text
请帮我把公司内部“区域商业化专家团”Codex 插件更新到 GitHub 上的最新版本。

Marketplace 名：market-entry-team-marketplace
插件名：market-entry-team

请在 Terminal 依次执行：
codex plugin marketplace upgrade market-entry-team-marketplace
codex plugin add market-entry-team@market-entry-team-marketplace

执行后检查 market-entry-team 是否为 installed、enabled，并告诉我实际安装的版本号。不要修改或删除任何现有 Skill、插件和 Codex 配置。
```

## 发布到 GitHub

1. 在公司 GitHub 组织创建一个私有仓库，例如 `codex-plugins`。已登录 GitHub CLI 时，可在本目录执行：

```bash
git init -b main
git add .
git commit -m "feat: publish market entry team plugin"
gh repo create YOUR_ORG/codex-plugins --private --source=. --remote=origin --push
```

2. 将 README 中的仓库地址和安装命令中的 `orgcomcn/codex-plugins` 替换为实际仓库地址（本仓库已配置完成）。

3. 团队成员按上方“安装到 Codex”的任一方式安装。

## 更新规则

1. 维护者在分支中修改插件文件并提交 Pull Request。
2. 审核通过后合并到 `main`，同步修改 `plugins/market-entry-team/.codex-plugin/plugin.json` 中的语义化版本号。
3. 团队成员按上方“更新到最新版”的任一方式更新。

建议将稳定版本合并到 `main`；用 `beta` 分支供少数维护者提前验证。
