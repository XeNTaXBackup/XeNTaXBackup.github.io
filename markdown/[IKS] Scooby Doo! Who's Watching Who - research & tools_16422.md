## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-18T19:56:57+00:00
- Post Title: [IKS] Scooby Doo! Who's Watching Who? - research & tools

Hello. I did a little research on MST archives from "Scooby Doo! Who's Watching Who?" on PSP platform. (ULES00572)


* MST file format *

```
8 bytes - magic
4 bytes - archive size
4 bytes - number of files in archive
120 bytes - ???



//file entries  (28 bytes per entry)
number of files *
{
	16 bytes - filename + padding
	4 bytes - file offset
	4 bytes - file size
	4 bytes - ??
}



//file data
number of files *
{
	x bytes - file data
	x bytes - padding
}
```


* Tool for extraction the mst archive *

And here is a simple Python 2.7 script for getting files from archives:


 Scooby_Doo_MST_Tool_1.zip
(1000 Bytes) Downloaded 39 times



Instruction:
1. Download UMDGen v4.00
2. Create folder "C:\Scooby_archives"
3. Extract all MST archives from Scooby Doo iso image to above folder using UMDGen
4. Edit folder path on the end of my script
5. Run script
6. Enjoy your unpacked files.
