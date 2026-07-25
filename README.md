# Process-Sword
Process Sword 是一款专注于 Windows 系统底层安全分析的工具，集进程管理、窗口管理、文件粉碎、文件监控等操作于一体，适用于安全研究人员与系统管理员进行深度系统诊断。

## ✨ 核心功能（v1.2）

### 🔍 进程管理
- 枚举进程详细信息（路径、PID、PPL 级别、命令行等）
- 支持多种方式结束进程（普通结束、极端结束）
- 查询进程 PPL（Protected Process Light）级别

### 🧹 文件粉碎
- 支持文件/文件夹粉碎，递归枚举子目录

### ⚙️ 系统服务管理
- 枚举服务，查看状态与启动类型
- 启动/停止/重启服务，修改启动类型

### 🚀 启动项管理
- 枚举注册表启动项与启动文件夹
- 添加、删除、禁用/启用启动项

### 🖥️ 更多功能
- 窗口管理（激活/最小化/最大化/关闭）
- 系统监控（CPU/内存曲线、磁盘空间、开机时间）
- 电源控制（关机/重启/睡眠/锁定）
- 命令行模式支持（`/kill`、`/list`、`/help` 等）

---

## 🛠️ 技术特点（v1.2）

| 特点 | 说明 |
|------|------|
| **内核驱动支持** | 内置 `Process_Sword_Kernel.sys`，用于进程强杀等操作（自研） |
| **文件粉碎** | 提供强力删除功能 |
| **单文件发布** | 主程序为单文件，运行时释放驱动与依赖（大小较小） |
| **命令行 + GUI 双模式** | 支持图形界面与命令行操作，满足不同使用场景 |

---

### 命令行用法

```bash
Process Sword.exe /list              # 列出所有进程
Process Sword.exe /kill 1234         # 结束 PID 为 1234 的进程（ZwTerminateProcess）
Process Sword.exe /kill 1234 /f      # 极端模式结束进程（ZwTerminateProcess和PspTerminateProcess等多种方式）
Process Sword.exe /PID "notepad.exe" # 将进程名转为 PID
Process Sword.exe /im 1234           # 将 PID 转为进程名
Process Sword.exe /help              # 查看帮助
