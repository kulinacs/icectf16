---
value: 70
author: finalC
writeup: jtsperry
category: Web
---

# Kitty

They managed to secure their website this time and moved the hashing to the server :(. We managed to leak this hash of the admin's password though! c7e83c01ed3ef54812673569b2d79c4e1f6554ffeb27706e98c067de9ab12d1a. Can you get the flag? [kitty.vuln.icec.tf](kitty.vuln.icec.tf)

## Solution

We are given this hash c7e83c01ed3ef54812673569b2d79c4e1f6554ffeb27706e98c067de9ab12d1a that needs to be cracked.
Putting this hash in a hash checker will reveal it is a SHA256 hash.
From here check the login page source code and see we are required to follow a strict format for the password.

    [A-Z][a-z][0-9][0-9][\?%$@#\^\*\(\)\[\];:]

This means the password is 5 characters long and looks like this,

    [capital leter][lowercase letter][number 0-9][number 0-9][symbol]

With this information, create a wordlist following the format.
Using crunch I created a wordlist that was roughly 12 mb.

    ./crunch 5 5 -t ,@%%^ -o wordlist.txt
    
Then once you have your wordlist you can use hashcat to check your wordlist to your hash.

    hashcat -m 1400 hash.hash wordlist.txt -o flag.txt

## Flag

IceCTF{i_guess_hashing_isnt_everything_in_this_world}
