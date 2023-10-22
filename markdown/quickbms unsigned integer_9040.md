## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-05T22:39:57+00:00
- Post Title: quickbms unsigned integer

0xFFFF gives 65335
0xFFFFFFFF gives -1

I want it to give 4294967295 though.
How do I do that?

```

math temp = 4294967295

```


Both result in -1
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-05T23:03:21+00:00
- Post Title: quickbms unsigned integer

set it as a long long data type?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-05T23:05:58+00:00
- Post Title: quickbms unsigned integer

```

```


Still gives -1 though.

I'm only using 0xFFFFFFF as an example, but this applies to basically any situation where you want to work with large, unsigned values.

It messes up the XOR'ing.

I also want to read in unsigned integers, but longlong using get still returns signed integers.

The readme says everything is done using 32-bit signed integers, but there's no way to force it to use 32-bit unsigned? The encryption I'm working with uses 32-bit unsigned integers everywhere and the key itself is a huge 32-bit unsigned integer.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-06T14:32:07+00:00
- Post Title: quickbms unsigned integer

use the 'u' before any math operation to force unsigned numbers.

example:

signed operation:

```
math MYVAR /= 1234
```

unsigned operation:

```
math MYVAR u/= 1234
```
