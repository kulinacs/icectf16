---
value: 30
author: Glitch
writeup: kulinacs
category: Web
---

# Move Along

[This site](http://move-along.vuln.icec.tf/) seems awfully suspicious, do you think you can figure out what they're hiding? 

## Solution

Upon viewing the site source, only one thing seems remotely interesting, the url the page image is loading from:

	<img src="move_along/nothing-to-see-here.jpg"></img>

Appending `/move_along` to the url reveals that directory listing has been turned on on the web server, and that a second file, `/0f76da769d67e021518f05b552406ff6/secret.jpg` exists. This jpg contains the flag.

## Flag

IceCTF{tH3_c4t_15_Ou7_oF_THe_b49}

