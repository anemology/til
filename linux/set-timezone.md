# 設定時區

```bash
timedatectl # 顯示當前狀態
timedatectl list-timezones | grep Taipei # 列出所有時區
timedatectl set-timezone Asia/Taipei # 設定時區
timedatectl # 確認
```

已知 `timedatectl` 可以用在 CentOS 7 及 Ubuntu 18.04 以上，CentOS 6 不行、Ubuntu 18.04 以下沒有試過。

## 參考

* https://linuxize.com/post/how-to-set-or-change-timezone-on-ubuntu-18-04/
