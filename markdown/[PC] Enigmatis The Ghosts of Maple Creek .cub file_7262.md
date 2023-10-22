## Post #1
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-08-30T07:36:35+00:00
- Post Title: [PC] Enigmatis: The Ghosts of Maple Creek *.cub file

Please, help with unpacking *.cub file

[http://www.mediafire.com/?db2u0jn0jida95q](http://www.mediafire.com/?db2u0jn0jida95q)
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-09-01T15:22:21+00:00
- Post Title: [PC] Enigmatis: The Ghosts of Maple Creek *.cub file

Be more specific. What game? What platform?
## Post #3
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-09-01T16:52:29+00:00
- Post Title: [PC] Enigmatis: The Ghosts of Maple Creek *.cub file

> Reply from delutto
>
> Be more specific. What game? What platform?

Game - Enigmatis: The Ghosts of Maple Creek; platform - PC from bigfishgames
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-10-29T20:59:54+00:00
- Post Title: [PC] Enigmatis: The Ghosts of Maple Creek *.cub file

script for QuickBMS:

```
idstring "cub\0"
get VER string
get FILES long
getdstring DUMMY 0x100
for i = 0 < FILES
    getdstring NAME 0x100
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #5
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2011-10-31T18:54:43+00:00
- Post Title: [PC] Enigmatis: The Ghosts of Maple Creek *.cub file

aluigi, thank you! All works!
