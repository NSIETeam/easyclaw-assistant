# HEARTBEAT.md — 心跳任务模板

# 保持此文件为空（或仅有注释）以跳过心跳 API 调用。
# 需要 Agent 定期检查某些内容时，在此添加任务。

# 示例：
# - 每天早上 9 点检查邮件
# - 每隔 2 小时检查日历

# 心跳状态追踪文件: memory/heartbeat-state.json

# ```json
# {
#   "lastChecks": {
#     "email": null,
#     "calendar": null,
#     "weather": null
#   }
# }
# ```
