## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T22:11:43+00:00
- Post Title: TZ Online

[http://tzonline.zcdn.co.kr/tzonline/Cli ... 110121.exe](http://tzonline.zcdn.co.kr/tzonline/Client/TZSetup_Gameclub_110121.exe)

File table is at the end, each file entry is pretty long with a lot of different values but you can figure out where the OFFSET, SIZE, and ZSIZE are.

I believe there is encryption, cause looking at the DDS files we have a a 128 byte header that appears to be XOR'd with something. But the pixel data is not encrypted. Similarly, looking at the model files, the first 128 bytes are encrypted, but the rest is clear cut...

Audio files have no encryption, so you can just play them directly.

Seeking to a couple model offsets, you can see an index buffer clearly along with strings.

Here's a half-assed script to unpack it. The first 128 bytes of many files are encrypted, and that's pretty much the only thing that's in the way of getting models and textures. And probably animation.

```

getdstring magic 36
get len long
getdstring pack_type len
get unk long
get TABLE_OFS long
get unk2 long
get FILES long

goto TABLE_OFS

for i = 0 < FILES
	get len long
	getdstring NAME len
	get OFFSET long
	if OFFSET = 0
		get size long
		get unk long
	else
		get ZSIZE long #compressed size
		get SIZE long #original size
		get FLAG long
		get null long
		get null long
		get unk2 long
		get unk3 long
		get unk4 long
		get unk5 long	
	endif
	log NAME OFFSET SIZE
next i
```


There should be some directory structure...I really didn't bother.

The 4 unknowns at the bottom might be the  XOR key....or maybe one of them..

the FLAG I wrote down changes depending on the file type. Audio files have flag == 1, csv and lua files have flag == 5, models and textures have flag == 6.

That might indicate whether the first 128 bytes are encrypted or not.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-08T23:21:13+00:00
- Post Title: TZ Online

no luck with the 0x80 bytes encryption and the compression, the rest is ok:

```
#   incomplete script, no support for compressed files!
# script for QuickBMS http://quickbms.aluigi.org

get DUMMY string
get NAMESZ long
getdstring NAME NAMESZ
get DUMMY long
get OFFSET long
get SIZE long
get FILES long
goto OFFSET

get NAMESZ long
getdstring NAME NAMESZ
get DUMMY long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    get NAMESZ long
    getdstring NAME NAMESZ
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get FLAG long
    get DUMMY long
    get DUMMY long
    getdstring DUMMY 0x10

    # flag 1 are ok
    # flag 6 files have 0x80 bytes obfuscated (I guess a simple algorithm)
    # the others are usually compressed with an unknown algorithm

    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        set EXT extension NAME
        strlen TMP EXT
        string NAME -= TMP
        string NAME -= 1
        string NAME += "_compressed_"
        string NAME += SIZE
        string NAME += "."
        string NAME += EXT
        log NAME OFFSET ZSIZE
        # unknown compression algorithm
        #clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-08T23:37:12+00:00
- Post Title: TZ Online

very good job of 2 boys, they appreciated the effort.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:58:02+00:00
- Post Title: TZ Online

The contents of this post was deleted because of possible forum rules violation.
