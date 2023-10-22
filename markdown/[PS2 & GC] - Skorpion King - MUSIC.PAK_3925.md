## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-05T11:09:13+00:00
- Post Title: [PS2 & GC] - Skorpion King - MUSIC.PAK

Hi again!

Could someone maybe look at those two files from Skorpion King: Rise of the Akkadian? 
[http://www.sendspace.com/file/3geve8](http://www.sendspace.com/file/3geve8) (PS2)
[http://www.sendspace.com/file/yajqmj](http://www.sendspace.com/file/yajqmj) (GameCube)
Could the file table at the beginning be compressed? Because the filenames are missing. Nevertheless, the archives contain VAG files but they need to be exracted as FastElbJa's ADPCM Player doesn't recognize any of them.
I know I could have posted on alucard but I have the feeling that Gnie is quite busy.   

Thanks as always!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-05T12:19:54+00:00
- Post Title: [PS2 & GC] - Skorpion King - MUSIC.PAK

I have only tested the ps2 one quickly:

```
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    getdstring EXT 8
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    getdstring NAME 16
    getdstring NAME2 8
    if NAME == ""
        set NAME string NAME2
    endif
    string NAME += "_"
    string NAME += i    # avoids duplicates!
    string NAME += ".vag"
    log NAME OFFSET SIZE
next i
```
note that probably you want to build the VAG header to apply to each extracted file because they are saved headerless or maybe the header is just that one in the information of each file but I doubt because some of them don't have it (example US_MATH__8.vag with header at offset 0x244)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-05T14:35:52+00:00
- Post Title: [PS2 & GC] - Skorpion King - MUSIC.PAK

Works well, headers are not the main problem! 
If you don't mind, also take a look at the GC version - the script needs to be slightly different for this I think.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-05T19:19:27+00:00
- Post Title: [PS2 & GC] - Skorpion King - MUSIC.PAK

note that the coefficients for the gamecube adpcm are in the header of each file information but I don't know where this header starts and finishes exactly:

```
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    getdstring DUMMY 0x24
    getdstring COEFF 0x20
    getdstring DUMMY 0x24
    getdstring NAME 8
    string NAME += "_"
    string NAME += i    # avoids duplicates!
    log NAME OFFSET SIZE
next i
```
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-06T16:06:37+00:00
- Post Title: [PS2 & GC] - Skorpion King - MUSIC.PAK

Thanks a lot luigi! 
I'll find that out and maybe finally try to implement it into the script myself.
