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

## 发布到 GitHub

1. 在公司 GitHub 组织创建一个私有仓库，例如 `codex-plugins`。已登录 GitHub CLI 时，可在本目录执行：

```bash
git init -b main
git add .
git commit -m "feat: publish market entry team plugin"
gh repo create YOUR_ORG/codex-plugins --private --source=. --remote=origin --push
```

2. 团队成员运行：

```bash
codex plugin marketplace add YOUR_ORG/codex-plugins --ref main
```

3. 在 Codex Desktop 的 **Plugins** 页面选择“区域商业化专家团”并安装。安装后新开一个任务即可使用。

## 更新规则

1. 维护者在分支中修改插件文件并提交 Pull Request。
2. 审核通过后合并到 `main`，同步修改 `plugins/market-entry-team/.codex-plugin/plugin.json` 中的语义化版本号。
3. 团队成员运行：

```bash
codex plugin marketplace upgrade
```

4. 成员重新打开 Codex 或新开任务，以加载新版本的 Skill。

建议将稳定版本合并到 `main`；用 `beta` 分支供少数维护者提前验证。
