## Post #1
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-07T18:42:49+00:00
- Post Title: Extracting DDS textures in container with names?

Hello guys, please help me to extract DDS textures with names in this container.

Names and DDS Header:
Start DDS in file

End DDS in file

But I do not know how to find the end of DDS and wrote file names with script 
This container files can contain up to 100 textures

Sample files:
It contains one texture: [https://www.dropbox.com/s/1b6yhnt3oqp6c ... G.img?dl=0](https://www.dropbox.com/s/1b6yhnt3oqp6cat/TUNE_BG.img?dl=0)
It contains three texture: [https://www.dropbox.com/s/weaazytqmijne ... R.img?dl=0](https://www.dropbox.com/s/weaazytqmijnefx/AIR_CLEANER.img?dl=0)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-11T01:25:57+00:00
- Post Title: Extracting DDS textures in container with names?

here is bms script to split dds from your samples with names  

```
findloc OFFSET binary "\x44\x44\x53\x20"
do
    math OFFSET - 4
    goto OFFSET
    get SIZE long
    savepos OFFSET
    xmath nameloc "SIZE + OFFSET + 7"
    goto nameloc
    get NAME string
    log NAME OFFSET SIZE
    findloc OFFSET binary "\x44\x44\x53\x20" 0 ""
while OFFSET != ""
```
## Post #3
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-13T22:31:46+00:00
- Post Title: Extracting DDS textures in container with names?

Many thanks AceWell
