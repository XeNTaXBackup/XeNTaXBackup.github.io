## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-01T23:24:28+00:00
- Post Title: Da li shen online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-02T00:04:44+00:00
- Post Title: Da li shen online

offzip job, after all there are no filenames so the result is exactly the same of a script
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T07:36:38+00:00
- Post Title: Da li shen online

Here's the script to get the filenames, though I don't know the relationship between the filenames and the file data.
It runs into an issue while decompressing files though.
I might get through a couple files depending on the archive, before it tells me there's a decompression error.
Does offzip try many different types of compressions while it's scanning the file?

```

idstring "\x0A\x00\x00\x00"
get FILES long

goto 0x450
math count = 0
do
	savepos START
	get tag long
	get unk long
	#print "start: %START%, %tag% %unk%"
	if unk == 0
		getdstring useless 76
	elif count < FILES
		get unk1 long
		get unk2 long
		get one long
		get one long
		get NAME string
		savepos TEST
		print "%TEST% %NAME% %count% %FILES%"
		math count += 1
		savepos CURR
		math READ = CURR
		math READ -= START
		math REMAIN = 84
		math REMAIN -= READ
		goto REMAIN 0 SEEK_CUR
	endif
while unk != 2653586369

#went too far
savepos CURR
math CURR -= 4
print "get files! %CURR%"
goto CURR

for i = 0 < FILES do
	get crc long
	get unk long
	get ZSIZE long
	get SIZE long
	get ZSIZE long
	get SIZE long
	savepos OFFSET
	clog OFFSET OFFSET ZSIZE SIZE
	math OFFSET += ZSIZE
	goto OFFSET
next i

```




Notes:

Hmm actually the texture_mini.pak actually does have filenames.
It's just that there's a lot of unknown data (garbage) in between which makes it hard to tell.

The size and compressed sizes are located right before each file data, but the filenames are at the top.
Hopefully they appear the same order that the data is stored.

And hopefully there is a way to just jump to each filename.

There are a couple of sequences that continue to appear repeatedly.

"EC FE 2B 01" appears FILES times
"C0 FF C9 00" appears a bunch of times.

Some patterns I've found

1: C0 FF C9 00 appears at the start of each "chunk", where each chunk is 84 bytes including these 4 bytes.
2: EC FE 2B 01 appears in each chunk that contains a file entry.
3: if you ran a search and highlighted all instances of the above two sequences, you'll find that *Every* chunk is 84 bytes.

4: when you read the chunkID, you will read another integer. If the integer is zero, then there is nothing special. However, if you read a non-zero value, then it is a file entry. You should check whether the chunkID is one of those two sequences, and run a do-while loop, while files_seen < FILES.

5: the sequence "C1 83 2A 9E" indicates the start of the data. The file table always ends with one of the two sequences above, so if your unk value is this one, then you know you should start saving files.

This always begins at offset 0x450

With that said, this script parses all of the file paths.
Unfortunately, I don't know if the data is stored in the same order that the filepaths appear. It would be nice though.

Also, I ran into an issue while doing the unpacker.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-22T14:47:26+00:00
- Post Title: Da li shen online

offzip supports only zlib (windowbits 15, default) and deflate (-z -15).

if you have a problem with the decompression of some files it's highly probable that they are not compressed so you must check what are the parameters to recognize they are "plain" (like ZSIZE == SIZE) and using log instead of clog.
just as you have seen in the various other scripts, something like:

```
    log NAME OFFSET SIZE
else
    clog NAME OFFSET ZSIZE SIZE
endif
```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T17:42:28+00:00
- Post Title: Da li shen online

Oh yes, I looked more closely at it and it looks like it is actually a different struct! Which is weird...

Maybe after this I can start looking at the file names
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-22T19:03:04+00:00
- Post Title: Da li shen online

umm interesting guys, thanks a lot for it, but about what say aluigi, the script work like this?

```

idstring "\x0A\x00\x00\x00"
get FILES long

goto 0x450
math count = 0
do
   savepos START
   get tag long
   get unk long
   #print "start: %START%, %tag% %unk%"
   if ZSIZE == SIZE
    log NAME OFFSET SIZE
else
    clog NAME OFFSET ZSIZE SIZE
endif
while unk != 2653586369

#went too far
savepos CURR
math CURR -= 4
print "get files! %CURR%"
goto CURR

for i = 0 < FILES do
   get crc long
   get unk long
   get ZSIZE long
   get SIZE long
   get ZSIZE long
   get SIZE long
   savepos OFFSET
   clog OFFSET OFFSET ZSIZE SIZE
   math OFFSET += ZSIZE
   goto OFFSET
next i
```
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T19:19:12+00:00
- Post Title: Da li shen online

It doesn't work for two things 

1: some of the file entries have a different struct (not just unk, zsize, size, zsize, size)
2: I haven't connected the filenames and the data together so it's not useful.
