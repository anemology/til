# last 和 logrotate

今天登入主機的時候，發現 `last` 和 `lastb` 都沒資料了！只顯示了一行字

```bash
wtmp begins Sat Aug  1 06:25:00 2020
```

排除被入侵的可能，查了一下是不是有排程在定期做清除的動作，原來還真的有

```bash
# /etc/crontab 內有一行
25 6    * * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
# 每天排程會執行 logrotate
vi /etc/cron.daily/logrotate
```

logrotate 的設定檔在 `/etc/logrotate.conf`

內容有一段如下，會定期 rotate `wtmp` 和 `btmp`

```bash
/var/log/wtmp {
    missingok # 略過如果 log 檔案不存在的問題
    monthly # 每個月做一次
    create 0664 root utmp # 建立一個空的 log 檔案, create 權限 使用者 群組
    rotate 1 # 保留多少個舊檔案
}
```

如果要看之前的紀錄，可以用以下指令，用 `-f` 帶入檔案名稱

```bash
sudo last -f /var/log/wtmp.1
```

## logrotate

`/etc/logrotate.conf` 內有一行

```bash
include /etc/logrotate.d
```

這資料夾是其他套件的 logrotate 設定檔，也有 `apache` 喔！就不會全部設定都寫在原本設定檔案，可以簡單分離。

之後如果有自己的程式要做 logrotate，可以在 `/etc/logrotate.d` 資料夾底下建立一個 link，連結到自己的設定檔，就可以很簡單做 logrotate 啦！

## 參考

* http://linux.vbird.org/linux_basic/0570syslog/0570syslog-fc4.php#rotate
* https://unix.stackexchange.com/questions/300169/does-last-command-in-linux-reset-after-a-specific-amount-of-time

---

* Ubuntu 18.04
