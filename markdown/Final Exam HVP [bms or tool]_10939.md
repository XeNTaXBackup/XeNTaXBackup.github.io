## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-11-09T03:27:34+00:00
- Post Title: Final Exam HVP [bms or tool]

Any bms os tool to unpack/pack the HPV files? 
Thanks

Download Demo [http://www.finalexam-thegame.com/?rub=demo](http://www.finalexam-thegame.com/?rub=demo) (You need steam).
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-09T09:48:47+00:00
- Post Title: Final Exam HVP [bms or tool]

Here is my try for quickbms. For me its hard to understand the folder structure, but i hope this is the right.

```
get ver long
get null long
get files long
get unk long
get nametablesz long
savepos offset
log MEMORY_FILE offset nametablesz
getdstring nametable nametablesz
for i = 0 < files
	putarray 0 i 0
next i
for i = 0 < files
	get unk1 long
	get type long
	get unk2 long
	get size long
	get nameoff long
	goto nameoff MEMORY_FILE
	get name string MEMORY_FILE
If type = 4
	get num1 long
	get num2 long
	If unk1 != 0	
		getarray fname 0 i
		If fname != 0
			string fname += \
			string fname += name
		else
			set fname name
		endif
	for n = 0 < num1
		putarray 0 num2 fname
		math num2 += 1
	next n
	endif
else
	get offset long
	get zsize long
	getarray fname 0 i
	If fname != 0
		string fname += \
		string fname += name
	else
		set fname name
	endif
	if zsize = size
		log fname offset size
	else
		clog fname offset zsize size
	endif
endif
next i
```
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-11-09T14:04:22+00:00
- Post Title: Final Exam HVP [bms or tool]

Works perfetc!! 
Thanks!!
## Post #4
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-20T14:46:15+00:00
- Post Title: Final Exam HVP [bms or tool]

After Extract the .hvp file how to see or edit the .hvt and string file?
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-21T20:20:47+00:00
- Post Title: Final Exam HVP [bms or tool]

Here is a tool for string file: [http://www.sendspace.com/file/x4zlrm](http://www.sendspace.com/file/x4zlrm)
Hvt files contains headerless images, and i dont know much about it.  You can see them with TextureFinder. The format is something like:

```
uint32 unknown
uint32 Header size
uint32 "DAEH"
uint32 null 
uint32 Image type(DXT1,DXT5,ARGB)
uint32 Width
uint32 Height
uint32 unknown
uint32 "/x0068X"
uint32 Number of image blocks
For each block{
uint32 Size of block
uint32 "ATAD"
uint64 null
uint32 Size of image data
byte() Image data
}
uint32 Eight
uint32 "/x00DNE"

```


Hvp file has some kind of crc check, so i think repimport will not work. You need to unpack the archive to gamedir, and rename the hvp file.
## Post #6
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2014-01-01T14:35:45+00:00
- Post Title: Final Exam HVP [bms or tool]

Thanks,swuforce.
## Post #7
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-01-01T18:40:47+00:00
- Post Title: Final Exam HVP [bms or tool]

Does anybody know if this could work with the HVP archives from Obscure 2?
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-02-27T00:30:51+00:00
- Post Title: Final Exam HVP [bms or tool]

> Reply from Modman69
>
> Does anybody know if this could work with the HVP archives from Obscure 2?
No, but you can unpack Obscure 2 files with the tool i attached  
[obscure.hvptool.zip](https://xentaxbackup.github.io/file/7044_obscure.hvptool.zip)
## Post #9
- Username: darkobscure
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 19, 2020 1:43 pm
- Post datetime: 2020-10-19T06:16:16+00:00
- Post Title: Final Exam HVP [bms or tool]

> Reply from Savage ↑Thu Feb 27, 2014 8:30 am at Thu Feb 27, 2014 8:30 am
>
> 
Modman69 wrote:Does anybody know if this could work with the HVP archives from Obscure 2?
No, but you can unpack Obscure 2 files with the tool i attached

Heyy you give the tool but how can I extract the files ?
## Post #10
- Username: TerrorMask
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 04, 2021 5:52 pm
- Post datetime: 2021-09-21T19:30:24+00:00
- Post Title: Final Exam HVP [bms or tool]

> Reply from Savage ↑Thu Feb 27, 2014 8:30 am at Thu Feb 27, 2014 8:30 am
>
> 
Modman69 wrote:Does anybody know if this could work with the HVP archives from Obscure 2?
No, but you can unpack Obscure 2 files with the tool i attached

doesn't work with obscure II  
All this tool does is repack the actual files present within into dat format extension. The Obscure 1 hvp extractor is more accurate and better and is a proper tool because it uses file handling and reverses the data into the original format. this tool isn't proper and only changes all default files into dat files.
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-10-05T17:26:45+00:00
- Post Title: Final Exam HVP [bms or tool]

> Reply from reznov ↑Fri Dec 20, 2013 10:46 pm at Fri Dec 20, 2013 10:46 pm
>
> 
After Extract the .hvp file how to see or edit the .hvt and string file?

I have finished my Final Exam .geo and .hvt loader modules and I have released the following programs as web updates:

- 3D Object Converter v8.016	(Windows)
- i3DConverter v4.106		(macOS)
- i3DConverter v2.106		(Linux)

How to get the 3D Object Converter v8.016:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.016.

How to get the i3DConverter macOS v4.104:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.104.

How to get the i3DConverter Linux v2.104:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.104.
