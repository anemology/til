# 設定允許遠端連線

PostgreSQL 預設不允許遠端連線，需要修改設定檔。

## 設定檔位置

使用 SQL 找到設定檔放在哪

```bash
sudo -u postgres psql -c 'SHOW config_file'
#                config_file
# -----------------------------------------
#  /etc/postgresql/10/main/postgresql.conf
# (1 row)
```

或是切到 `postgres` 帳號後再下 `psql` 也可以

```bash
su postgres
psql -c 'SHOW config_file'
```

## 主要設定檔

修改 `/etc/postgresql/10/main/postgresql.conf`

```text
#listen_addresses = 'localhost'         # what IP address(es) to listen on;
# 取消註解, 改為
listen_addresses = '*'
```

預設只能本機連線，改為 `*` 之後可以監聽本機所有網路介面

## 用戶驗證設定檔

在 `postgresql.conf` 同個資料夾底下的 `pg_hba.conf`

```conf
# TYPE  DATABASE        USER            ADDRESS                 METHOD
host    dbname          username        10.10.10.10/32          md5
```

上面註解底下加入那一行，將 `dbname`、`username` 改為自己要連線的資料庫名稱和使用者名稱

`10.10.10.10` 改為要連線的主機 IP，記得加上 __子網路遮罩__ !!! 這個很容易忘記

最後記得要重啟服務

```bash
sudo systemctl restart postgresql
```

## 參考

* https://stackoverflow.com/questions/3602450/where-are-my-postgres-conf-files
* https://ravenonhill.blogspot.com/2016/12/postgresqlconf-listenaddresses.html
* https://docs.postgresql.tw/server-administration/client-authentication/the-pg_hba.conf-file

---

* Ubuntu 18.04
