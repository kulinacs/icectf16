---
value: 55
author: Glitch
writeup: kulinacs
category: Misc
---

# Thor's a hacker now

Thor has been staring at this for hours and he can't make any sense out of it, can you help him figure out what it is? [thor.txt](https://play.icec.tf/problem-static/thor_7101f3b9690d5dc6c3afefa49d82e0526b278ec1c564139369ad22c28721d4cf.txt)

## File Except

	00000000: 4c5a 4950 01b3 007f b61b edf0 8440 58e3  LZIP.........@X.
	00000010: 91de 1027 5861 8a67 4282 46a4 92f9 4cad  ...'Xa.gB.F...L.
	00000020: 2d5d 14eb 3099 2c31 01c2 d13a 74d2 c620  -]..0.,1...:t.. 
	00000030: de27 3a8f fa92 0644 5468 2d02 01fa 24bb  .':....DTh-...$.
	00000040: 719f a0fd a191 1678 8bff a2c4 2627 9871  q......x....&'.q
	00000050: 83bf cff2 f8af 99fa c465 2b7c 6bdf ee3c  .........e+|k..<

## Solution

The file given is the hexdump of an LZIP archive, we just need to get it back to binary form. Luckily, xxd can also do reverse hexdumps, so running `xxd -r` will spit out the lzip binary. Decompressing the archive with `lzip -d` will reveal an image containing the flag.

![Hackerman Thor](/images/stage2/thor.jpg)

## Flag
IceCTF{h3XduMp1N9_l1k3_A_r341_B14Ckh47}
