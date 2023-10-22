## Post #1
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2019-07-08T17:16:51+00:00
- Post Title: Shrek (Xbox) *.lmp Archive

Hi

I'm trying to write a script to dump the contents of the Shrek (Xbox) lmp files. The lmp files are extremely simple and appear to be a mutation of this lmp file that's already documented: [http://wiki.xentax.com/index.php/Baldur ... iance_XBox](http://wiki.xentax.com/index.php/Baldurs_Gate_-_Dark_Alliance_XBox)

The first int32 is File Count and the second int32 is FileSize

Then an array of blocks for each file in the archive 128 bytes long including:
char(x) File Name / Padding
int32 file offset
int32 file size
int32 unknown
int32 always 1
int32 unknown

This all seems very simple but when I go to and isolate/extract a dds file it's appears to be all random bytes with no header. I've never worked with file compression so is it possible that the unknowns are file data compression? Every dds file I've tried is the same random garbage data.

Here's some lmp files and an example of a dds I extracted "AM_ArrowSign.DDS"

Sample Files
[https://www.dropbox.com/s/abl9qdpst7hzd ... a.rar?dl=0](https://www.dropbox.com/s/abl9qdpst7hzdzn/media.rar?dl=0)

Any advice on what to do next would be appreciated Thank you.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-08T19:06:51+00:00
- Post Title: Shrek (Xbox) *.lmp Archive

Yes, you're right - the files are a slight modification of the BG: Dark Alliance format.

The DDS files are compressed.  In your list of the file table info, a couple of amendments:

The int32 "file size" you have listed is the uncompressed size.  The int32 following that is the compressed size in the .lmp archive - for example, the first DDS file in common.lmp is 0x2A4E bytes in the archive and 0xAB28 bytes when uncompressed.

If you're using QuickBMS, the compression algorithm used is DEFLATE64.

Hope that helps!
## Post #3
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2019-07-09T20:35:07+00:00
- Post Title: Shrek (Xbox) *.lmp Archive

Thanks DKDave that got me pretty far. I tried making my own program but I couldn't find any documentation on DEFLATE64 and none of the libraries seemed to want to work so I learned QuickBMS enough to get a few textures to decompress but i'm running into some issues:

Despite that the other textures are extracting and decompressing correctly so far, and it's because of that i'm kind of at a loss to why it only works with some.

Here's the script I have written so far:

```
get archiveSize long
goto 0x80

for i = 0 < (fileCount - 1)
	getdstring name[i] 108
	get recordOffset[i] long
	get recordSize[i] long
	get fileSize[i] long
	get compression[i] long
	get crc32[i] long
next i

ComType DEFLATE64

for i = 0 < (fileCount - 1)
	IF compression[i] == 0
		log name[i] recordOffset[i] recordSize[i]
	ELSE
		Clog name[i] recordOffset[i] fileSize[i] recordSize[i]
	ENDIF
next i
```


If anyone has any suggestions I'd love to hear them, thank you
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-09T23:12:44+00:00
- Post Title: Shrek (Xbox) *.lmp Archive

Having looked at it, I think you've got everything right.  I think I should have said the compression type is "DEFLATE" instead of "DEFLATE64".  If you change that, it should work.

I've tested it and my script is as follows, which is very similar to yours, and seems to extract and decompress everything ok:

# Shrek (XBox) - LMP Extract
# By Dave, 2019

ComType DEFLATE
Get ENTRIES Long

Goto 0x80

For A = 1 to ENTRIES

	GetDString FILENAME 0x6C
	Get OFFSET Long
	Get SIZE Long
	Get ZSIZE Long
	Get COMP_FLAG Long
	Get JUNK Long

	IF SIZE > ZSIZE
		CLog FILENAME OFFSET ZSIZE SIZE
	ELSE
		Log FILENAME OFFSET ZSIZE

	ENDIF

Next A
