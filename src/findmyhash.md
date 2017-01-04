# findmyhash
## Introduction
利用破解hash value的網站，來查詢hash value
```console
# findmyhash
/usr/bin/findmyhash 1.1.2 ( http://code.google.com/p/findmyhash/ )

Usage:
------

  python /usr/bin/findmyhash <algorithm> OPTIONS


Accepted algorithms are:
------------------------

  MD4       - RFC 1320
  MD5       - RFC 1321
  SHA1      - RFC 3174 (FIPS 180-3)
  SHA224    - RFC 3874 (FIPS 180-3)
  SHA256    - FIPS 180-3
  SHA384    - FIPS 180-3
  SHA512    - FIPS 180-3
  RMD160    - RFC 2857
  GOST      - RFC 5831
  WHIRLPOOL - ISO/IEC 10118-3:2004
  LM        - Microsoft Windows hash
  NTLM      - Microsoft Windows hash
  MYSQL     - MySQL 3, 4, 5 hash
  CISCO7    - Cisco IOS type 7 encrypted passwords
  JUNIPER   - Juniper Networks $9$ encrypted passwords
  LDAP_MD5  - MD5 Base64 encoded
  LDAP_SHA1 - SHA1 Base64 encoded
```

## example
```console
# echo -n test | md5sum
098f6bcd4621d373cade4e832627b4f6  -

# findmyhash MD5 -h 098f6bcd4621d373cade4e832627b4f6

Cracking hash: 098f6bcd4621d373cade4e832627b4f6

Analyzing with my-addr (http://md5.my-addr.com)...

***** HASH CRACKED!! *****
The original string is: test


The following hashes were cracked:
----------------------------------

098f6bcd4621d373cade4e832627b4f6 -> test
```
