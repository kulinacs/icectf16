---
value: 60
author: finalC
writeup: kulinacs
category: Web
---

# Exposed!

John is pretty happy with himself, he just made his first [website](http://exposed.vuln.icec.tf/)! He used all the hip and cool systems, like NginX, PHP and Git! Everyone is so happy for him, but can you get him to give you the flag? 

## Solution

The first important find is the `robots.txt` file left on the website:

	User-Agent: *
	Disallow: /.git
	Disallow: /flag.php

Of course, the first thing to check is `flag.php`, however, this is simply a blank page. Moving on to the git repo, we find a repo with anonymous access hosted at [exposed.vuln.icec.tf/.git](http://exposed.vuln.icec.tf/.git). We initially find the source for the website, including `flag.php`, which implies that at somepoint, the flag was located in the git repo. Stepping through the commits shown in `git log`, we find a dummy flag, the flag changed but added to the git ignore, and finally, hardcoded into the index page in one of the earliest commits.

## Flag

IceCTF{secure_y0ur_g1t_repos_pe0ple}
