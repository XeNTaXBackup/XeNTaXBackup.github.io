## Post #1
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-12-04T04:22:36+00:00
- Post Title: Archive file Identification

an acquaintance of mine asked for my help identifying and extracting this file 
[https://mega.nz/#!sBQHkQwD!bFivjIfqvUn7 ... u7stVx5KpE](https://mega.nz/#!sBQHkQwD!bFivjIfqvUn7Z4ZJAXeDFlJfBjXU6rHeHu7stVx5KpE)
I've never encountered this before and I'm not sure how to go about extracting it.
I Think It's engine specific, but i'm not sure.
It comes from the PC port of Tales of Zestria, which I have been told uses It's own engine But I'm not 100%.
any INFO or Help would be greatly appreciated.
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-12-04T15:54:22+00:00
- Post Title: Archive file Identification

the link is incomplete (... in the middle)
## Post #3
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-12-04T17:28:54+00:00
- Post Title: Archive file Identification

> Reply from barti
>
> the link is incomplete (... in the middle)
it should work now provided you click on it instead of copying and pasting
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-04T19:46:29+00:00
- Post Title: Archive file Identification

This is very easy. This is just a cache of game files, with no names. Not compressed. You can extract them all.

First number is number of files, then for each file: id, size, offset.

If you need names, you should look for other files. Or in case they are hashed, you must guess them.
## Post #5
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-12-04T20:25:10+00:00
- Post Title: Archive file Identification

What should I use to extract it?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-04T20:36:30+00:00
- Post Title: Archive file Identification

You need to write a program or script for that. But are you sure you need 23536 files without names? What you would do with them?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-04T21:07:26+00:00
- Post Title: Archive file Identification

> Reply from SonofKalas
>
> What should I use to extract it?you could try out the below bms script.
But be warned! Use it on your own risk!
It also requires the following preparations:
Copy the first 0x44F44 bytes from FILE.CACHE into a new FILE.TAB.
Then rename FILE.CACHE to FILE.ARC.
Run quickbms, select the script then the tab file.
(Maybe kill quickbms after 2 or 3 seconds to check whether the extracted bin files are correct.)

```
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "tab" 0
open FDDE "arc" 1

set EXT string "bin"

get ARC_SIZE asize 1
get TAB_SIZE asize
goto 4

for i = 0
    savepos CURR_OFF
    if CURR_OFF >= TAB_SIZE
        cleanexit
    endif
    get NAME_CRC long
    get FSIZE long
    get OFFSET long

    math OFFSET += 282436
   
    string NAME p= "%08x.%s" NAME_CRC EXT
    log NAME OFFSET FSIZE 1
next i
```
## Post #8
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-12-04T21:09:45+00:00
- Post Title: Archive file Identification

> Reply from daemon1
>
> You need to write a program or script for that. But are you sure you need 23536 files without names? What you would do with them?

It's not for me but for someone who asked me to help them figure out how to extract it
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-04T22:16:23+00:00
- Post Title: Archive file Identification

adding 282440 to the offset might be the better choice:



bf9c740f.jpg (91.51 KiB) Viewed 63 times
