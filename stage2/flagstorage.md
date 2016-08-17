---
value: 50
author: finalC
writeup: kulinacs
category: Web
---

# Flag Storage

What a cheat, I was promised a flag and I can't even log in. Can you get in for me? [flagstorage.vuln.icec.tf](http://flagstorage.vuln.icec.tf/). They seem to hash their passwords, but I think the problem is somehow related to [this](https://en.wikipedia.org/wiki/SQL_injection). 

## Solution

Viewing the data that gets posted with a tool like the Developer Console shows that three parameters are passed to the php script, username, password, and the hashed password. Seeing as they are hashing the password locally and a SQL Injection has been recommended, the hash parameter is our attack vector. Sending `' or '1'='1` as the hash (can be done with TamperData or curl) injects an SQL query into the existing query in the php, causing it to authenticate the user regardless of the information passed.

## Flag

IceCTF{why_would_you_even_do_anything_client_side}
