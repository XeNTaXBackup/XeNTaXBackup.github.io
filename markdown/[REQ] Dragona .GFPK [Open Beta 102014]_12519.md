## Post #1
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-18T01:18:09+00:00
- Post Title: [REQ] Dragona .GFPK [Open Beta 10/20/14]

Hello again! I'm just wondering if anyone has a working quickbms script for the open beta version of Dragona? I tried using the script by chrrox, but it seems to fail.

Script by Chrrox:

```
get files short
get null short
filexor "0x78 0x6C 0x61 0x71 0x6A 0x23 0x65 0x6D 0x24 0x25 0x5E 0x66 0x6B 0x40 0x23 0x24 0x72 0x68 0x21 0x40 0x23 0x73 0x6B 0x40 0x23 0x24 0x21 0x00"
for i = 0 < files
get id long
putarray 0 i id
next i
for i = 0 < files
get id1 long
putarray 1 i id1
next i
for i = 0 < files
getarray OFFSET 1 i
if OFFSET == -1
getdstring null 0x310 #this is the recursive directory info but we can skip it in this game
endif
if OFFSET != -1
getdstring basename 0xF8
get SIZE long
get UNK01 long
get UNK02 long
getdstring NULL 0x27
getdstring NAME 0x1DD
getdstring basename 0x8
putarray 2 i SIZE
putarray 3 i NAME
endif
next i
filexor ""
savepos base
for i = 0 < files
getarray OFFSET 1 i
getarray SIZE 2 i
getarray NAME 3 i
math OFFSET + base
if NAME != 0
log NAME OFFSET SIZE
endif
next i
```


Sample Files:
[https://mega.co.nz/#!g1VkibBQ!FzplIcc91 ... zrU75oV9Eg](https://mega.co.nz/#!g1VkibBQ!FzplIcc91JxeFv_wtemRckyYiry10B4Z1zrU75oV9Eg)

I've attached a screenshot of what I'm getting as a result of trying.

Thanks in advance for reading and sorry for being annoying!
[wtf.jpg](https://xentaxbackup.github.io/file/8500_wtf.jpg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-18T11:54:28+00:00
- Post Title: [REQ] Dragona .GFPK [Open Beta 10/20/14]

if it's for the models, I could get one from Pet.gfpk using hex2obj:



Pet_gfpk_0xB09FD5.JPG (42.51 KiB) Viewed 130 times
## Post #3
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-18T17:09:42+00:00
- Post Title: [REQ] Dragona .GFPK [Open Beta 10/20/14]

@shakotay2, I was hoping for animations and textures too.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-18T17:50:12+00:00
- Post Title: [REQ] Dragona .GFPK [Open Beta 10/20/14]

textures can be easily extracted from gfpk. Just cut them from one DDS signature to the other ( 44 44 53 20 7C).

(I made a quick and dirty tool for it but it doesn't provide correct filenames, just numbered DDS files.
The models are not of that interest for me that I would care for anims, sry.)



Pet_cloth.JPG (93.44 KiB) Viewed 118 times
