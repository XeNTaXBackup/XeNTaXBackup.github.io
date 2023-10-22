## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T06:56:54+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Here is a 3ds max script for importing the models with bones and weights.
I still want to add auto material support.
Use this to extract the models 
[viewtopic.php?f=10&t=6868](http://forum.xentax.com/viewtopic.php?f=10&t=6868)
[mal.png](https://xentaxbackup.github.io/file/4395_mal.png)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T13:24:11+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Here is a texture converter and i made my max script faster and it only adds the used bones to the mesh now.


```
goto 0x8
get files long
for i = 0 < files
get id long
set name id
string name + .dds
get offset long
get size long
get type byte
getdstring null 0x7
get width short
get height short
getdstring null 0xC
callfunction addDDSheader
math size + 0x80
log NAME 0 size MEMORY_FILE
next i


startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x10 width long
putVarChr MEMORY_FILE 0xC height long
if type == 0x86
putVarChr MEMORY_FILE 0x57 0x31
endif
if type == 0x87
putVarChr MEMORY_FILE 0x57 0x33
endif
if type == 0x88
putVarChr MEMORY_FILE 0x57 0x35
endif
endian big
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

```
## Post #3
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-29T20:13:24+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Never heard about this game before. The models looks nice.
Thank you chrrox.

Edit nvm failed at reading.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T21:42:02+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Updated script to correct a problem with some bones and added material support (textures are not auto applied just materials.)
## Post #5
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-29T22:17:33+00:00
- Post Title: MALICIOUS マリシアス (PS3)

All models and textures are like that to me.
What I'm doing is use psarc tool to extract the psarc>bms script on .dat generated>bms texture script on .gtf> import model .mdl to Max.
Every texture looks like that and the character import like that too.
Am I missing doing anything?
Thanks.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T22:28:01+00:00
- Post Title: MALICIOUS マリシアス (PS3)

updated to v4 should fix some problems with stages and static models.
to see the players try player pl0102
also be patient with the script some models even tho small can take a while to load due to bones.
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-06-29T22:30:32+00:00
- Post Title: MALICIOUS マリシアス (PS3)

nice one!
## Post #8
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-29T22:37:55+00:00
- Post Title: MALICIOUS マリシアス (PS3)

> Reply from chrrox
>
> updated to v4 should fix some problems with stages and static models.
to see the players try player pl0102
also be patient with the script some models even tho small can take a while to load due to bones.

That one worked wonderfully. The problem was in that thing that is between the chair and the monitor.
Thank you.

Edit: Looks like the V4 script don't load the model "--No ""get"" function for undefined" V3 is working fine.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T23:05:57+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Sorry type-O try it now v5
[MALICIOUS v5.rar](https://xentaxbackup.github.io/file/4400_MALICIOUS v5.rar)
## Post #10
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-29T23:10:21+00:00
- Post Title: MALICIOUS マリシアス (PS3)

> Reply from chrrox
>
> Sorry type-O try it now v5
Working great.
Thank you.
## Post #11
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-06-30T11:40:45+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Wow, great work chrrox. thank you;)
## Post #12
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-07-01T01:31:11+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Ok guys i need a little help here i download the script for
get the file models from the big file , but its a pkg file 
and chrrox said that i need to extract the psarc files
first , but when i use the script for the big file didnt
work its said "invalid argument " so can any one 
can helpme ?

Thanks in advance
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-01T02:10:54+00:00
- Post Title: MALICIOUS マリシアス (PS3)

all psn files need to be decrypted and extracted with a ps3 pkg tool just Google it.
