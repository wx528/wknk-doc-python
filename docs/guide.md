# 脚本教程指南 (Shell 示例)

## 快速清理日志文件

您可以使用以下简单的 Shell 脚本来自动清除大于 100MB 且超过 30 天的日志文件：

```bash
#!/bin/bash
find /var/log/ -type f -name "*.log" -size +100M -mtime +30 -exec rm {} \;
echo "Log cleanup finished."