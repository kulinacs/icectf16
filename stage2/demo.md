---
value: 55
author: Glitch
writeup: kulinacs
category: Pwn
---

# Demo

I found this awesome premium shell, but my demo version just ran out... can you help me crack it? `/home/demo/` on the shell. 

## Challenge

Files given:

	-rwxr-sr-x 1 root demo 5692 Aug 12 09:08 demo
	-rw-r--r-- 1 root root  458 Aug 12 09:08 demo.c
	-r--r----- 1 root demo   33 Aug 12 09:08 flag.txt
	-rw-r--r-- 1 root root   83 Aug 12 09:08 Makefile

demo.c:

	#define _GNU_SOURCE
	#include <stdio.h>
	#include <stdlib.h>
	#include <unistd.h>
	#include <sys/types.h>
	#include <libgen.h>
	#include <string.h>

	void give_shell() {
		gid_t gid = getegid();
		setresgid(gid, gid, gid);
		system("/bin/sh");
	}
			
	int main(int argc, char *argv[]) {
		if(strncmp(basename(getenv("_")), "icesh", 6) == 0){
			give_shell();
		} else {
			printf("I'm sorry, your free trial has ended.\n");
		}
		return 0;
	}
	
## Solution

To read the flag, we'll need to be in the group demo. Fortunately, demo shell is in the demo group and assigns us its group permissions. The `_` environment variable initializes to the file name of the shell that is currently being run. Symlinking icesh in your home directory to bash or zsh and running the symlink allows you to then run /home/demo/demo and get a shell with the `demo` group's access.

## Flag

IceCTF{wH0_WoU1d_3vr_7Ru5t_4rgV}
