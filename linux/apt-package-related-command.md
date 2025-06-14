# apt 套件管理相關指令

## remove

```bash
sudo apt remove package # 移除套件
sudo apt purge package # 移除套件, 不保留設定
sudo apt remove --purge package # 同上
# 刪除完之後可執行
sudo apt autoremove # 會刪除當初安裝套件所依賴的套件, 但現在已經使用不到的
sudo apt autoremove --purge # 或加上 --purge 同時移除設定
```

參考下方移除結果，會提示你再用 `sudo apt autoremove` 移除不需要的套件

```bash
anemology@ubuntu2004:~$ sudo apt purge bashtop
[sudo] password for anemology:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following package was automatically installed and is no longer required:
  sysstat
Use 'sudo apt autoremove' to remove it.
The following packages will be REMOVED:
  bashtop*
0 upgraded, 0 newly installed, 1 to remove and 4 not upgraded.
After this operation, 241 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 31999 files and directories currently installed.)
Removing bashtop (0.9.25+git275-9f8a133~ubuntu20.04.1) ...
[  removing packet from the system ]
[ successfully removed ]
Processing triggers for mime-support (3.64ubuntu1) ...
(Reading database ... 31992 files and directories currently installed.)
Purging configuration files for bashtop (0.9.25+git275-9f8a133~ubuntu20.04.1) ...
[ successfully removed ]
```

`apt purge` 移除後，發現在 `$HOME/.config/` 還有套件的設定檔

原因是 `apt purge` 移除時，只會移除 `/etc` 底下的檔案，通常設定檔也在這邊

`$HOME/.config/` 的設定可能是套件執行中產生的，所以沒有移除，需要手動刪除

## clean

```bash
# 清除已下載的套件暫存檔案, 不是解除安裝, 只是清理硬碟空間
sudo apt autoclean # 清除過時的套件
sudo apt clean # 清除所有套件
```

## policy

```bash
# 列出所有套件來源
apt policy
cat /etc/apt/sources.list
```

至於 `PPA (Personal Package Archive)` 會在 `/etc/apt/sources.list.d`

`PPA` 是非官方的套件來源，`Ubuntu` 上的 PPA 套件通常會由 [Launchpad](https://launchpad.net/ubuntu) 這個網站來管理

```bash
sudo add-apt-repository ppa:user/repository # 加入 PPA
sudo add-apt-repository --remove ppa:user/repository # 移除 PPA
```

## 參考

* https://askubuntu.com/questions/3167/what-is-difference-between-the-options-autoclean-autoremove-and-clean
* https://unix.stackexchange.com/questions/38549/does-apt-get-purge-remove-config-files-stored-in-user-home-dir
* https://how-to.fandom.com/wiki/Guide_to_linux_configuration_files
* https://help.launchpad.net/Packaging/PPA
* https://askubuntu.com/questions/307/how-can-ppas-be-removed

---

`#linux` `#ubuntu` `#ubuntu2004` `#apt` `#ppa`
