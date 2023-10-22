## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-02T10:46:46+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Phantasy Star Universe - Ambition of the Illuminus uses the ROFS Filesystem version 1.52.

I know you can turn a normal CMV to an ISO by removing the bytes before x1800, but doesn't seem to work with this one. SO, I'm wonder if anyone has found a way to get into ROFS 1.52. Thanks the rules, I cannot give you samples.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-03T10:51:26+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

if you can run the game in the emulator post a saved state and i can prolly find the file table.
## Post #3
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-03T14:48:38+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Oh, okay. SHould I PM it to you? And does it have to be in a specific place, or just make a savestate anywhere?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-03T21:14:43+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

just post the link to the saved state from anywhere.
## Post #5
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-03T21:21:10+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

[Here](https://dl.dropboxusercontent.com/u/32409323/Rips/SLUS-21631%20%285EA50CB0%29.00.p2s) it is.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-03T22:35:43+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

yeah the file table is in eeMemory.bin
probably with the first 20mb of the file i could make an extractor.
example file names.

pl_mua_la_000.snj
pl_wua_la_000.snj
pl_xxx_shadow000.snj
pl_xxx_shadow000.snt
body.sna
pl_mua_la_000.sna
pl_wua_la_000.sna
pl_xxx_shadow000.sna
pl_lod_wait.snm
pl_lod_walk.snm
MotTbl_00_COMMON_M.snr
MotTbl_00_COMMON_W.snr
MotTbl_01_DK_SWORD_M.snr
## Post #7
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-03T22:58:00+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Awesome, looks like some of them are sound files, which is what I was looking for.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-03T23:23:45+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

i need the start of the iso...
## Post #9
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-03T23:28:50+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Don't have the game? How much of it do you need?
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-03T23:51:19+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

the first 20 - 40 mb of it.
just cut that off and zip it.
## Post #11
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-04T00:46:51+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

I'll try, though, I'm not sure how to cut mega bytes with a Hex Editor, I guess I could use a file splitter.
## Post #12
- Username: shade
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-04T12:56:59+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Try this
[SLUS-21631.7z](https://xentaxbackup.github.io/file/6449_SLUS-21631.7z)
## Post #13
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-06-04T13:32:40+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

Awesome. Seems to be working. Would it be possible to have to dump the files in a folder according to the file's extension?
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-04T13:49:22+00:00
- Post Title: Phantasy Star Universe - AoTI (PS2) CVM

there are only a few types of files?
I would just create the folders then sort by extension and cut and paste.
