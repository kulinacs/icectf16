---
value: 40
author: finalC
writeup: kulinacs
category: Misc
---

# Search

There's something about this domain... search.icec.tf, I don't see anything, but maybe its all about the conTEXT. 

## Solution

The hint points to a TEXT record of some sort, which, in the scope of domain names, leads to a DNS TXT record. Checking the text record with host reveals the key.

	host -t txt search.icec.tf

## Flag

IceCTF{flag5_all_0v3r_the_Plac3}
