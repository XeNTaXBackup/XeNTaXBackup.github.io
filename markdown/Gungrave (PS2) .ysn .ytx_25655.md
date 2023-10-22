## Post #1
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-07-28T21:58:59+00:00
- Post Title: Gungrave (PS2) .ysn .ytx

no information on these formats, any help? some samples: [https://www.mediafire.com/file/lvkob7jh ... a.zip/file](https://www.mediafire.com/file/lvkob7jh2gtoe4k/chara.zip/file)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-07-29T00:08:04+00:00
- Post Title: Gungrave (PS2) .ysn .ytx

Well, i did not get the .ysn seems to be a hash file.
however.
use this script to extract all textures from YTX

The pallet of color is the offset 0X10

```
math i = 0

get file basename
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET LONGLONG 0X0000000200000030 0 ""

     if NEXT_OFFSET == ""

        get SIZE asize
    else
        math SIZE = NEXT_OFFSET

    endif
    math SIZE -= OFFSET
  String FILENAME P "%file%_%i%.dat"
    log filename OFFSET SIZE
    math i += 1
    math OFFSET = NEXT_OFFSET

while NEXT_OFFSET != ""
```




chara_1_9@0000000059.png (65.89 KiB) Viewed 83 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-29T03:55:48+00:00
- Post Title: Gungrave (PS2) .ysn .ytx

char_1-ysn.jpg (82.55 KiB) Viewed 67 times


(I have no idea how auto creation of face indices should work here.)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-29T10:09:35+00:00
- Post Title: Gungrave (PS2) .ysn .ytx

Using a point cloud skinner plugin for blender:
.



chara_1_pt_cloud_skinner.jpg (124.82 KiB) Viewed 52 times

Sometimes results heavily depend on the choice of parameters (see rectangle).
