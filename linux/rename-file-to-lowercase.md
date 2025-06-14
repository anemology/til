# 重新命名檔案至小寫檔名

```bash
rename 'y/A-Z/a-z/' *
```

正常情況下可以成功，但是在 WSL 裡面，移動到 Windows system 上的資料夾底下，卻會出現

```bash
$ rename 'y/A-Z/a-z/' *
EXAMPLE.txt not renamed: example.txt already exists

# 用 mv 也有類似行為
$ mv EXAMPLE.txt example.txt
mv: 'EXAMPLE.txt' and 'example.txt' are the same file
```

是因為 Windows 不區分檔案大小寫，這時候可以多加 `--force` 來強制複寫

```bash
rename --force 'y/A-Z/a-z/' *
```

或是直接在 Windows 底下修改檔名

```bat
move EXAMPLE.txt example.txt
```

## 參考

* [How do I rename all folders and files to lowercase on Linux? - Stack Overflow](https://stackoverflow.com/questions/152514/how-do-i-rename-all-folders-and-files-to-lowercase-on-linux)
