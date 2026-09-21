# 静态项目看板的 CI 报告接入

看板按 GitHub Actions run、提交 SHA 和重跑 attempt 关联测试证据。

现有 CI 的 `ut-results`、`st-results`、`e2e-results` 产物可直接采集。E2E 使用 Playwright `test-results/results.json`；重试后通过和跳过单独展示，不能算作稳定通过。

每日构建使用 `schedule` 触发或 daily/nightly 工作流名；版本验证使用 `release` 触发或 release/version 工作流名，并与版本标签对应的提交一致。尚未配置或没有报告时，看板显示未知。

本次变更只补充报告约定，供 PR 事件、门禁状态和静态看板联调。
