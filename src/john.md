# john
## Introduction
John the Ripper(JTR)，在已知密文的情況下，用來反解出密碼。
## Example
新增一個user，帳號about，密碼iloveyou，用JTR進行破解，其中root的密碼沒有在字典當中，所以無法被破解。
```console
# useradd about
# passwd about
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully

# unshadow /etc/passwd /etc/shadow > test_passwd
# john --wordlist=/usr/share/john/password.lst test_passwd
Warning: detected hash type "sha512crypt", but the string is also recognized as "crypt"
Use the "--format=crypt" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 2 password hashes with 2 different salts (sha512crypt, crypt(3) $6$ [SHA512 128/128 SSE2 2x])
Press 'q' or Ctrl-C to abort, almost any other key for status
iloveyou         (about)
1g 0:00:00:09 DONE (2017-01-04 08:33) 0.1083g/s 384.1p/s 398.0c/s 398.0C/s paagal..sss
Use the "--show" option to display all of the cracked passwords reliably
Session completed

# john --show test_passwd
about:iloveyou:1000:1000::/home/about:/bin/sh

1 password hash cracked, 1 left
```
