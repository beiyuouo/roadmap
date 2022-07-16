# VSCode

VSCode 是微软公司开发的一款开源的编程 IDE

## 快捷键

Keyboard Shortcuts for Windows: [PDF](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)

这里记几个常用的

| Key                             | Function            |
| ------------------------------- | ------------------- |
| `Ctrl + Shift + `<code>`</code> | 新建 Terminal       |
| `Ctrl + Shift + F`              | 搜索设置            |
| `Ctrl + Shift + [/]`            | 展开/折叠当前代码块 |
| `Ctrl + K Ctrl + 0/J`           | 展开/折叠所有代码块 |
| `F3/Shift + F3`                 | 查找下一个/上一个   |
| `Ctrl + X(empty selection)`     | 剪切当前行          |
| `Ctrl + C(empty selection)`     | 复制当前行          |
| `Ctrl + Shift + K`              | 删除当前行          |
| `Ctrl + P`                      | 打开文件搜索面板    |
| `Ctrl + (Shift) + Tab`          | 文件打开历史        |
| `Alt + ←/→`                     | 切换左右编辑器      |
| `Ctrl + Shift + Page Up/Down`   | 交换左右编辑器      |
| `Ctrl + K Ctrl + W`             | 关闭所有编辑器      |

## 环境变量

有时候你可能需要在项目中特定的添加环境变量

首先 VSCode 编辑器的配置是在 `settings.json` 中的，而每个项目可以有一个独立的配置文件，这个文件名是 `.vscode/settings.json`

创建这个文件，按如下的格式即可添加环境变量

```json
{
  "terminal.integrated.env.osx": {
    "PYTHONPATH": "${workspaceFolder}/"
  },
  "terminal.integrated.env.linux": {
    "PYTHONPATH": "${workspaceFolder}/"
  },
  "terminal.integrated.env.windows": {
    "PYTHONPATH": "${workspaceFolder}/:[Other Paths]"
  }
}
```

如果你是使用 Python，那么可以直接打开 Terminal，然后执行以下命令查看是否配置成功。

```bash
python -c "import sys; print(sys.path)"
```
