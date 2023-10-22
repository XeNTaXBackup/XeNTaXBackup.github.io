## Post #1
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2020-06-24T02:05:00+00:00
- Post Title: Zula Online *.mdl models

Hi guys  

The game .gen has been unpacked and the .mdl file is obtained
Tools:
```
# script for QuickBMS http://quickbms.aluigi.org

set KEY binary "\xaa"
comtype lzss0   # lzss or lzss0? same results with samples
endian big
idstring "WRS4"
get INFO_OFF long
savepos OFFSET
goto INFO_OFF
get ZSIZE long
get SIZE long
savepos INFO_OFF
clog MEMORY_FILE INFO_OFF ZSIZE SIZE
xmath FILES "SIZE / (0x20 + 4 + 4)"
for i = 0 < FILES
    getdstring NAME 0x20 MEMORY_FILE
    string NAME ^ KEY
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    clog NAME OFFSET ZSIZE SIZE
    math OFFSET + ZSIZE
next i
```


I found that the format of many games is .mdl. I tried many scripts and tools of the game, but I couldn’t open it.

Please help me write a Noesis script, it is best to support export animation.  
I will upload some sample files:
[https://drive.google.com/file/d/115VAAu ... sp=sharing](https://drive.google.com/file/d/115VAAucd-kJpI0GKnvYxhuY_PuSCO5p_/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-26T17:48:28+00:00
- Post Title: Zula Online *.mdl models

> Reply from LiangZong ↑Wed Jun 24, 2020 10:05 am at Wed Jun 24, 2020 10:05 am
>
> Please help me write a Noesis script, it is best to support export animation."help"? What does that mean exactly? What's your progress with the script so far?

Using hex2obj (view link in my sig) on sil_PS_MAC10_n_fps.mdl ,
(uvs might be half floats, dunno):
.



sil_PS_MAC10_n_fps-mdl-.png (83.77 KiB) Viewed 89 times
