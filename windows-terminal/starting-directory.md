# Starting Directory

因開新的 `WSL` tab 時不想每次都是在 Windows 的使用者目錄 (`/mnt/c/Users/username`)，所以找了一下，在 Windows Terminal 的 settings.json 內新增 `startingDirectory` 設定。

```json
    {
        "guid": "{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}",
        "hidden": false,
        "name": "Ubuntu-20.04",
        "source": "Windows.Terminal.Wsl",
        "startingDirectory" : "//wsl$/Ubuntu-20.04/home/linux_username"
    }
```

路徑可以是 Windwos 路徑或 WSL 內的路徑，例如：

* "D:\\\\my\\\\windows\\\\path"
* "//wsl$/Ubuntu-20.04/home/username"

但如果直接使用 /mnt 的路徑好像不行呢，這樣會直接跑回預設 Windows 使用者目錄

* "//wsl$/Ubuntu-20.04/mnt/c"
