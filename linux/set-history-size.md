# 設定 history 大小

```bash
# 修改檔案
vi ~/.bashrc
# 加入以下參數或是修改原本數值
# history 指令顯示的數量
HISTSIZE=1000
# ~/.bash_history 檔案行數
HISTFILESIZE=2000
# 顯示日期與時間, 1999-02-29 23:59:59
HISTTIMEFORMAT="%F %T "
# 使設定生效
source ~/.bashrc
```

---

參考
* https://www.gnu.org/software/bash/manual/bash.html#index-HISTFILESIZE
* https://askubuntu.com/questions/391082/how-to-see-time-stamps-in-bash-history
* https://askubuntu.com/questions/307541/how-to-change-history-size-for-ever
