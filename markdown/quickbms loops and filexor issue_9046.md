## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-07T04:15:47+00:00
- Post Title: quickbms loops and filexor issue

I was doing some loops and xor'ing and it seems to be unintuitive.

The following snippets apparently don't result in the same things:

```
for i = 0 < 2
   get one long
   get two long
   getdstring name two
next i

```


```
get one long
get two long
getdstring name two

filexor my_key
get one long
get two long
getdstring name two

```


With the loop, the filexor seems to be xor'ing with something else after the first iteration, which results in a bad "two" value, resulting in the wrong filename.

The second snippet works correctly and gets the names as expected.

I'm using 0.5.13

EDIT: hmm I found the issue.
Turns out my idea of filexor is not what quickbms is actually doing lol

If I say

```
   savepos curpos
   filexor my_key curpos
   get one long
   get two long
   getdstring name two
next i

```


Then it works.

Though, that doesn't explain why this worked.

```
get one long
get two long
getdstring name two

filexor my_key
get one long
get two long
getdstring name two

```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-08T07:23:48+00:00
- Post Title: quickbms loops and filexor issue

filexor uses the key from the offset 0, so the first byte of the key is at offset 0x0 of the file.
if the key is used for each entry then you must tell quickbms to use it in that way, so first byte of the key is at the offset you get with savepos.
