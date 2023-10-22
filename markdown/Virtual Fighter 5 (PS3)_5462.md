## Post #1
- Username: darkangelalhena
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-26T00:14:01+00:00
- Post Title: Virtual Fighter 5 (PS3)

Here is a quickbms script to extract vf5 ps3 farc archives.

```
get arcsize asize
get idstring long
get headersize long
get one long
for i = 0 < 0xFFFF
get name string
get offset long
get zsize long
get size long
string name + ".gz"
if offset > 0
log name offset zsize
else
cleanexit
endif
next i

```
## Post #2
- Username: SackGirl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 07, 2011 10:35 am
- Post datetime: 2011-02-07T02:50:37+00:00
- Post Title: Virtual Fighter 5 (PS3)

> Reply from chrrox
>
> Here is a quickbms script to extract vf5 ps3 farc archives.
Code: Select allendian big
get arcsize asize
get idstring long
get headersize long
get one long
for i = 0 < 0xFFFF
get name string
get offset long
get zsize long
get size long
string name + ".gz"
if offset > 0
log name offset zsize
else
cleanexit
endif
next i
yeah might be a bump but this seems like the best place to post, LittleBigPlanet and LittleBigPlanet 2 both include a data.farc I tried this to extract them but all i got was a error saying it's not possible to make the file, and I have to change the name, as soon as I do the script crashes, is this .farc script universal or is it a unique script to Virtual Fighter 5?
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-02-07T03:09:14+00:00
- Post Title: Virtual Fighter 5 (PS3)

> Reply from SackGirl
>
> unique script to Virtual Fighter 5
## Post #4
- Username: Vladanor
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 25, 2011 12:04 am
- Post datetime: 2011-04-26T15:10:12+00:00
- Post Title: Virtual Fighter 5 (PS3)

When i run the script,it shows me error: "-- Type error: Call needs function or class, got: undefined"
