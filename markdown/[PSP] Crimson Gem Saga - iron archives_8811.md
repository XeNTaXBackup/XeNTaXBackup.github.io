## Post #1
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-04-22T10:06:49+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives

I wanted to take a look at the wonderful sprites the game has but I got stuck.
The main archive, asto2.dat, has a very simple format and can be unpacked with this script:

```

endian little
get NOF long
for i = 1 to NOF
	getdstring FILENAME 0x100
	set FILENAME unicode FILENAME
	get FILEOFFSET long
	get FILESIZE long
	log FILENAME FILEOFFSET FILESIZE
next i

```

So far so good. Now the sprites are stored in the sprite directory in files with the extension *.nr2. The images are compressed with zlib and several are stored in one nr2 file. Thats what I know about the nr2 archives:

```
endian little
get FSNOHEADER long //filesize without the header (idstring, this value and filename)
getdstring FILENAME 0x40 //same as the filename of the nr2 file itself but with the extension *.nri
set FILENAME unicode FILENAME
goto 0x354 //everything before this is an unknown chunk of data, its always 0x30c big
get SIZE long //from here on all compressed files are aligned one after another with real size and compressed size before the zlibed data till the arhive ends
get ZSIZE long

```

I don't know were the number of files of the archive is stored or the name of the images in it. Maybe the unknown data stores information of how the sprites are assembled but the number of files is not in it.

Please tell me, how can I extract the files in the nr2 archive when I don't know the number of files with quickbms?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-22T16:46:10+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives

Just infinite loop if you see a pattern.
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-04-22T21:16:12+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives

> Reply from finale00
>
> Just infinite loop if you see a pattern.
Ahh, ok.

I tried it this way but it wont work. I must have an error in reasoning.

```
endian little
get FSNOHEADER long
getdstring FILENAME 0x40
set FILENAME unicode FILENAME
//here begins the fun
goto 0x354
for i = 1 to 9999
	get SIZE long
	get ZSIZE long
	SavePos OFFSET
	clog i OFFSET ZSIZE SIZE
	math ZSIZE - 4
	math OFFSET + ZSIZE
	goto OFFSET
next i
```


"The requested amount of bytes to allocate is negative" on the second file. Looks like the size is not getting read right. But the start offset for the file to extract is right.

EDIT:
I ran the script with the verbose option and it seems like every variable got read in successively and the offsets are fine too.
Why is quickbms giving this error? Could it be that there are different compression types in the archive?
These are the first 4 bytes of the files I try to extract:

```
0x78DA5D8C error about negative amount of bytes

```

EDIT2:
My bad I just guessed the the value before the ZSIZE was the size of the decompressed file... Here is a working script:

```

idstring "iron"
endian little
get FSNOHEADER long
getdstring FILENAME 0x40
set FILENAME unicode FILENAME
goto 0x358
for i = 1 to 9999
	get ZSIZE long
	SavePos OFFSET
	clog i OFFSET ZSIZE 999999
	math OFFSET + ZSIZE
	goto OFFSET
next i
```

I just set a huge value for the unknown filesize of the extracted files, seems to work.
