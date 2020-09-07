# sudo 和 su

* `su`，切換使用者，若不指定帳號預設為 `root`，需要知道該使用者的密碼

* `sudo`，以 superuser 權限執行指令，使用者必須有 `sudoers` 權限

* `sudo -s`，run 一個新的 shell 環境，並有 superuser 權限

* `sudo -i`，run 一個新的 shell 環境，並有 superuser 權限 & 環境

* `sudo su`，以 superuser 權限執行 `su` 指令，跟 `su` 一樣會切換到 `root` 帳號，但輸入的是自己的密碼

## `sudo -s` 和 `sudo -i` 差別

兩者的差別主要是環境，可以用家目錄看出來

```bash
# sudo -s
# cd ~
# pwd
/home/user

# sudo -i
# cd ~
# pwd
/root
```

## 參考

* [sudo(8): execute command as another user - Linux man page](https://linux.die.net/man/8/sudo)
* [What are the differences between “su”, “sudo -s”, “sudo -i”, “sudo su”?](https://askubuntu.com/questions/70534/what-are-the-differences-between-su-sudo-s-sudo-i-sudo-su)

---

`#linux` `#sudo` `#su`
