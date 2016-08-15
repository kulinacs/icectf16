---
value: 10
author: Glitch
writeup: kulinacs
---

# Spotlight

Someone turned out the lights and now we can't find anything. Send halp! [spotlight](http://spotlight.vuln.icec.tf/)

## Solution

The flag can be found viewing the JavaScript console as a debug statement. 

	DEBUG: Loading canvas context... spotlight.js:6:1
	DEBUG: Adjusting canvas size... spotlight.js:11:1
	DEBUG: Adding mouse listener... spotlight.js:16:1
	DEBUG: Initializing spotlight sequence... spotlight.js:21:1
	DEBUG: IceCTF{5tup1d_d3v5_w1th_th31r_l095} spotlight.js:53:1
	DEBUG: Loading up helper functions... spotlight.js:55:1
	DEBUG:     * getMousePos(canvas, evt) spotlight.js:56:1
	DEBUG:     * height(perc) spotlight.js:66:1
	DEBUG:     * width(perc) spotlight.js:74:1
	DEBUG: Done. spotlight.js:80:1
	DEBUG: Ready for blast off!←

## Flag

IceCTF{5tup1d_d3v5_w1th_th31r_l095}
