## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-18T23:40:59+00:00
- Post Title: Fushigi no Gensokyo

This looks like a simple archive but 

1: some parts are not encrypted, but the rest are
2: each character in the pathname takes up two bytes instead of one

The first 16 bytes are unencrypted but everything after is XOR'ed with 0x08
Can anyone write a bms script?
[d000.7z](https://xentaxbackup.github.io/file/4506_d000.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-18T23:52:16+00:00
- Post Title: Fushigi no Gensokyo

quickbms script

```
get one long
get files long
get one long
for i = 0 < files
filexor "0x08"
getdstring hash 0x8
get size long
get offset long
get one long
getdstring UNAME 0x80
set NAME unicode UNAME
log name offset size
next i
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T00:03:40+00:00
- Post Title: Fushigi no Gensokyo

Hmm I don't understand the "getdstring hash 0x8" part.

From the docs, it stores 8 bytes of data into the `hash` variable, but then it seems like you don't use it. Or is it just how you normally skip bytes? Or maybe just didn't find any use for it.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-19T00:46:35+00:00
- Post Title: Fushigi no Gensokyo

its probably a hash or crc check or something i don't use it.
