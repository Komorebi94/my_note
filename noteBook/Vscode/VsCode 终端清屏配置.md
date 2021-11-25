### VsCode 终端清屏配置

+ 文件 => 首选项 => 键盘快捷方式 => keybindings.json

    ```json
    {
        "key": "ctrl+k", 
        "command": "workbench.action.terminal.clear", 
        "when": "terminalFocus" 
    }
    ```

    