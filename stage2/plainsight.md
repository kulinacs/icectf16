---
value: 45
author: hkr
writeup: kulinacs
category: ReverseEngineering
---

# Hidden in Plain Sight
Make sure you take a real close look at it, it should be right there! `/home/plain_sight/` or download it [here](https://play.icec.tf/problem-static/828644c3ad8ccfa14b86a69dccd36f2b-plain_sight_df5d2c1da50110458fa00d0db6586b23cd67317c7f7b95f4a092d645a4570296)

## Solution

The binary given leaks no information when analyzed with strings or readelf. Disassembling the file, however, leads to an interesting sequence of move instructions that look suspicious.

	804851b:       b0 49                   mov    $0x49,%al
	804851d:       b0 63                   mov    $0x63,%al
	804851f:       b0 65                   mov    $0x65,%al
	8048521:       b0 43                   mov    $0x43,%al
	8048523:       b0 54                   mov    $0x54,%al
	8048525:       b0 46                   mov    $0x46,%al
	8048527:       b0 7b                   mov    $0x7b,%al
	8048529:       b0 6c                   mov    $0x6c,%al
	804852b:       b0 6f                   mov    $0x6f,%al
	804852d:       b0 6f                   mov    $0x6f,%al
	804852f:       b0 6b                   mov    $0x6b,%al
	8048531:       b0 5f                   mov    $0x5f,%al
	8048533:       b0 6d                   mov    $0x6d,%al
	8048535:       b0 6f                   mov    $0x6f,%al
	8048537:       b0 6d                   mov    $0x6d,%al
	8048539:       b0 5f                   mov    $0x5f,%al
	804853b:       b0 49                   mov    $0x49,%al
	804853d:       b0 5f                   mov    $0x5f,%al
	804853f:       b0 66                   mov    $0x66,%al
	8048541:       b0 6f                   mov    $0x6f,%al
	8048543:       b0 75                   mov    $0x75,%al
	8048545:       b0 6e                   mov    $0x6e,%al
	8048547:       b0 64                   mov    $0x64,%al
	8048549:       b0 5f                   mov    $0x5f,%al
	804854b:       b0 69                   mov    $0x69,%al
	804854d:       b0 74                   mov    $0x74,%al
	804854f:       b0 7d                   mov    $0x7d,%al

Decoding the hex values to their ASCII equivalents reveals the flag.

## Flag

IceCTF{look_mom_I_found_it}
