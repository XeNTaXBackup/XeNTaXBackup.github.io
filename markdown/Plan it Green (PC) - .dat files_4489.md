## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-05-23T00:19:25+00:00
- Post Title: Plan it Green (PC) - .dat files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-05-25T22:46:47+00:00
- Post Title: Plan it Green (PC) - .dat files

I tried to write a script, but all what can I do is extract the first file of interface.dat

My try:

```
getdstring DUMMY 0x1C

getdstring UNAME 0x4A 
set NAME unicode UNAME

getdstring DUMMY 0x1B6
get OFFSET long
get SIZE long

log NAME OFFSET SIZE
```


I don't know how to extract the other files
## Post #3
- Username: merlinsvk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-25T23:03:22+00:00
- Post Title: Plan it Green (PC) - .dat files

here is a working quickbms script.

```
goto 0x20
for i = 0 < files
getdstring name 0x200
set NAME unicode NAME
get offset long
get size long
log name offset size
next i
```
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-05-26T13:28:21+00:00
- Post Title: Plan it Green (PC) - .dat files

Hmm, I was close.
Thank you, chrrox  

And it is possible to reverse that process to create packer? I ask only out of curiosity.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-26T19:29:54+00:00
- Post Title: Plan it Green (PC) - .dat files

i am not good with repacking bms wise.
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-05-26T21:24:49+00:00
- Post Title: Plan it Green (PC) - .dat files

It's a pity, because that game doesn't run with unpacked archives.

Never mind, I have to use hex editor
