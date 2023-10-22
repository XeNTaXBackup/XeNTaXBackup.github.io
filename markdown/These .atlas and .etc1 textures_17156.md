## Post #1
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-10-18T23:32:20+00:00
- Post Title: These .atlas and .etc1 textures

Here's an example:
[https://mega.nz/#!3oVWiSwB!i5Qeix8F5tth ... rdVkXbzIpg](https://mega.nz/#!3oVWiSwB!i5Qeix8F5tthC7nr9Y2k69wLyQkdadQiVrdVkXbzIpg)

The atlas is quite obvious what it does, but the .etc1 files are apparently Ericsson Texture Compressed? Could not find any tool that knew how to decompress them, not even sure what the format is AFTER they are even decompressed. Probably a simple one but I couldn't figure it out.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-19T08:35:35+00:00
- Post Title: These .atlas and .etc1 textures

the *.etc1 files are gzip compressed, i just used 7-zip to extract the image file, then ran this bms script on those files

```

get SIZE asize
get NAME basename
string NAME + .pkm
math SIZE - 4
log NAME 0x4 SIZE

```

and finally open those *.pkm files with "Mali Texture Compression Tool".  

edit
if you want to extract and prep the pkm file in one step use this bms script on the *.etc1 files 

```

comtype gzip
get ZSIZE asize
get NAME basename
string NAME + .pkm
log memory_file 0 0
append
clog memory_file 0x0 ZSIZE ZSIZE
append
get SIZE asize memory_file
math SIZE - 4 
log NAME 0x4 SIZE memory_file

```
## Post #3
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-10-19T17:48:42+00:00
- Post Title: These .atlas and .etc1 textures

Thanks, I never even thought to try to open with 7zip! Couldn't figure out how to save the image with Mali (option was greyed out) but just used etc1tool from the android-sdk I had lying around.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-19T20:09:11+00:00
- Post Title: These .atlas and .etc1 textures

> Reply from Mikeee
>
> Couldn't figure out how to save the image with Mali (option was greyed out)
instruction for saving out in "Mali Texture Compression Tool" is here   
[viewtopic.php?p=92181#p92181](http://forum.xentax.com/viewtopic.php?p=92181#p92181)

> 1. Right-Click on the .pkm file and click "Compress selected images"
>
> 2. Set output format to "PKM"
>
> 3. Right-Click the .pkm file again and the "Save compressed image(s) as..." function should be unlocked
