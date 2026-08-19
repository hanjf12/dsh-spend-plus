# dsh-spend-plus

DeepSeek Harness 插件：**dsh-spend 用量/费用看板 + DeepSeek 账户余额**，合并为一个插件。

- 右下角悬浮窗：token 用量、多维度统计、预计费用（USD，自动识别峰谷价）
- 输入框下方余额 chip：DeepSeek 官方账户余额（人民币）+ 本场会话费用，自动套峰谷（北京时间 09:00–12:00 / 14:00–18:00）

## 来源

基于两个 MIT 项目合并：

- [nonewind/dsh-spend](https://github.com/nonewind/dsh-spend)（ziheng，MIT）—— 用量/费用看板
- [Ghost011118/dsh-balance-meter](https://github.com/Ghost011118/dsh-balance-meter)（MIT）—— 余额查询

## 安装

```sh
dsh plugin --profile web add git+https://github.com/hanjf12/dsh-spend-plus.git
# 或本地：
# dsh plugin --profile web add link:$(pwd)/dsh-spend-plus
```

装完重启 `dsh web` 并刷新页面。

## 依赖

余额查询通过 DSH 凭据 seam 读取 `DEEPSEEK_API_KEY`（Web 设置页的模型页已写入该凭据）。未配置 key 时余额 chip 会显示「不可用」，但用量看板不受影响。
