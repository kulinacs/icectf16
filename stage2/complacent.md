---
value: 40
author: finalC
writeup: kulinacs
category: Reconnaissance
---

# Complacent

These silly bankers have gotten pretty complacent with their self signed SSL certificate. I wonder if there's anything in there. [complacent.vuln.icec.tf](https://complacent.vuln.icec.tf/)

## Solution

Connecting to the given url prompts the user to accept a self-signed certificate. Luckily, modern web browsers allow you to inspect the certificate before accepting. The certificate metadata contains the flag.

	Common Name (CN)         : complacent.icec.tf
	Organization (0)         : Secret IceCTF Buisness Corp
	Organizational Unit (OU) : Flag: IceCTF{this_1nformation_wasnt_h1dd3n_at_a11}

## Flag

IceCTF{this_1nformation_wasnt_h1dd3n_at_a11}
