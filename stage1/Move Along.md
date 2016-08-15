---
value: 30
author: Glitch
writeup: jtsperry
---

# Move Along

  [This site](http://move-along.vuln.icec.tf/) seems awfully suspicious, do you think you can figure out what they're hiding? 

## File

	<html>
    <head>
        <title>IceCTF 2016 - Move Along</title>
        <link rel="stylesheet" type="text/css" href="css/main.css">
    </head>
    <body>
        <img src="move_along/nothing-to-see-here.jpg"></img>
    </body>
  </html>

## Solution

Viewing the source code we can see an img tag containing "move_along/nothing-to-see-here.jpg"
if we check "http://move-along.vuln.icec.tf/move_along/"
we can see we have access to /move_along and find a jpg and another directory which contains secret.jpg

## Flag

IceCTF{tH3_c4t_15_Ou7oF_THe_b49}
