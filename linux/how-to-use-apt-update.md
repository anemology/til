# 如何使用 apt update

一直以來，只知道 Ubuntu 更新時要下 `apt update` 和 `apt upgrade`，但不知道實際作用，查了之後才明白這兩個指令為什麼總是會一起出現了。

```bash
# 更新套件的清單資訊
sudo apt update
# 實際執行更新
sudo apt upgrade
```

而網路上有發現有人使用 `apt`，而有些是 `apt-get`，順便查了一下這兩者的分別

`apt` 集合了一些 `apt-get`、`apt-cache`、`apt-config` 的常用指令，但我也用只過 `apt-get` 而已。

而對比 `apt-get`，`apt` 多出了進度條、上色等功能，所以一般使用 `apt` 就可以了，除非 `apt` 沒有對應的指令，再回去用 `apt-get`。

## 參考

* https://manpages.ubuntu.com/manpages/focal/man8/apt.8.html
* https://askubuntu.com/questions/196768/how-to-install-updates-via-command-line
* https://askubuntu.com/questions/445384/what-is-the-difference-between-apt-and-apt-get
* https://www.sysgeek.cn/apt-vs-apt-get/
