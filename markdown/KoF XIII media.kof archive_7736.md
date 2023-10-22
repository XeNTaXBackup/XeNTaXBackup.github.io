## Post #1
- Username: Layer
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Feb 19, 2011 5:53 am
- Post datetime: 2011-11-23T14:58:20+00:00
- Post Title: KoF XIII media.kof archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-11-26T19:24:45+00:00
- Post Title: KoF XIII media.kof archive

I'd actually like some help with this too. I've been trying to find patterns in the Hex to write a script, but this archive is giving me all kinds of trouble.
## Post #3
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-11-26T21:10:52+00:00
- Post Title: KoF XIII media.kof archive

here the script, very easy format, just the numFiles is missing

```
set numFiles 7222

for x = 0 < numFiles

GetDString Name 232
get unk1_0 long
get unk1_1 long
get Offset_0 long
get Offset_1 long
get Size_0 long
get Size_1 long

log Name Offset_1 Size_1

next x
```
## Post #4
- Username: JohnGrimm
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Nov 20, 2011 4:22 pm
- Post datetime: 2011-11-27T00:02:12+00:00
- Post Title: KoF XIII media.kof archive

Than you for the help Falo. I'm still new to BMS scripts and that archive was rough.
