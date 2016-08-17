---
value: Toke
author: Glitch
writeup: kulinacs
category: Web
---

# Toke

I have a feeling they were pretty high when they made [this website](http://toke.vuln.icec.tf/)...

## Solution

Upon analyzing the traffic, we can see that the website returns a cookie containing multiple pieces of information. One of these is a JSON Web Token, a standard for asserting information to the client. After base64 decoding the token, the flag is revealed. 

## Flag

IceCTF{jW7_t0K3ns_4Re_nO_p14CE_fOR_53CrE7S}
