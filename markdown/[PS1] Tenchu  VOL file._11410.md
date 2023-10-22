## Post #1
- Username: Stickman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 17, 2013 6:23 am
- Post datetime: 2014-04-12T08:11:49+00:00
- Post Title: [PS1] Tenchu  VOL file.

The japanese Version of Tenchu (SLPS 01272) contains a "TENCHU.VOL" file, with "AFS_VOL_200\0" as a magic number.

Since I couldn't find any information of this format on the Internet, I've decided to try figuring it out by myself, and share my results. 

Here is what I've figured out so far:

```

offset 	length 	value
---------------------
0	12	 Magic number - always "AFS_VOL_200\0" (0x4146535F564F4C5F32303000)
12	4	Number of files
16	4	Offset of file table
20	20	all zeroes


file entry

offset 	length	value
---------------------
0	2	 Always "IX" (0x4958)
2	2	 Index type  - is 0x0002 if the entry is a directory - is 0x0001 if the entry is a file
4	4	 File offset - is 0xcdcdcdcd if the entry is a directory
8	4	 File size   - is 0xcdcdcdcd if the entry is a directory
12	4	 Is also the file size? don't know why.
16	20	 File name in ASCII

If the file name starts with @ it points to the parent directory.
i.e. If you have three entries, one is named "files", the second is named "@0_images", and the third is named "@1_photo.jpg", the full structure of the third entry is "files\images\photo.jpg"

```


Based on these findings I wrote an unpacker in C# which can sucessfully unpack the TENCHU.VOL file from the disc. I've attached it here plus it's source code.
If you don't want to download files, I've pasted the source code here: [http://pastebin.com/uvttWqJc](http://pastebin.com/uvttWqJc)

Sorry, it's C# only - I have yet to learn QuickBMS.

What I'd like to know: Have I missed something - and are there other games using this archive format?
[unTenchu.7z](https://xentaxbackup.github.io/file/7196_unTenchu.7z)
## Post #2
- Username: leosilvas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 27, 2018 11:37 am
- Post datetime: 2018-05-27T03:53:20+00:00
- Post Title: [PS1] Tenchu  VOL file.

Great tool!!! How could I repack the extracted files into a DATA.VOL file?
