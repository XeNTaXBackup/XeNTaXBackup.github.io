## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-20T14:57:45+00:00
- Post Title: quickbms string xor then filexor

I read in two strings

```
getdstring str2 16

```


Then I want to xor them

```

```


Now I want to use the result as my filexor key

```
log NAME OFFSET SIZE
filexor ""

```


But the result isn't right.

When I print out str1, it's just two bytes for some reason.
Is this the right way to do it?

This is the logic I want to reproduce

```
   data[i] ^= str1[i % 16] ^ str2[i % 16]

```


So I should be able to xor the two strings first and then use the result for filexor'ing.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-30T19:47:20+00:00
- Post Title: quickbms string xor then filexor

use:
encryption xor str1

and if str1 contains some zeroes specify also its size
encryption xor str1 "" 0x10

filexor wants a hex string to work so it's not good in this case.
