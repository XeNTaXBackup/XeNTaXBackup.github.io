## Post #1
- Username: hexg0d18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 30, 2016 12:22 am
- Post datetime: 2016-09-03T13:45:45+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

here is my file : [https://drive.google.com/open?id=0BwPrT ... kZrXzRpam8](https://drive.google.com/open?id=0BwPrTHrbxMOeRVFWMkZrXzRpam8). please create bms script for it, Aluigi. please help. Any other thread not worked!!!
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-09-04T00:26:54+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

Try this

Unpack:
ffxiiicrypt.exe -d filelist2a.win32.bin 3
ffxiiicrypt.exe -d white_img2a.win32.bin 3
ff13tool -x -ff133 filelist2a.win32.bin white_img2a.win32.bin

Pack:
ff13tool -c -ff133 filelist2a.win32.bin white_img2a
ffxiiicrypt.exe -e filelist2a.win32.bin 3
ffxiiicrypt.exe -e white_img2a.win32.bin 3
[Tools.rar](https://xentaxbackup.github.io/file/11656_Tools.rar)
## Post #3
- Username: hexg0d18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 30, 2016 12:22 am
- Post datetime: 2016-09-04T05:25:16+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

where is output file?? I do like you said, but it happen so fast, may be 1 second. Is it really extract this file with this tool??Here my picture show off: [http://imgur.com/a/2Gmx9](http://imgur.com/a/2Gmx9).
## Post #4
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-09-04T07:27:48+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

Usage .bat

[](http://radikal.ru/fp/66bb4ee708c54f66b2d4d8beaeef67ee)
## Post #5
- Username: hexg0d18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 30, 2016 12:22 am
- Post datetime: 2016-09-04T09:14:16+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

Thanks you. It worked. Love you, buddy. what about file .wdb and .xgr , imgb , xfv? how to open those file? can you extract white_z0100a_img2.win32.bin file in "/weiss_data/zone" folder?
## Post #6
- Username: Fshy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 02, 2017 5:50 am
- Post datetime: 2017-02-05T06:51:24+00:00
- Post Title: Final Fantasy 13 Lightning Returns (.bin) ??

I'll zombie this thread to give a gift for wdb files in QuickBMS - I couldn't find anything related to these files which begin with WPD, so I made this for my own uses. Its rough, and I'm lazy, but it should work - its a very simple archive format.

```
idstring "WPD\x00"
get fileCount long
get null long
get null long
for i = 0 < fileCount
	getdstring name 0x10
	get pointer long
	get length long
	getdstring fileType 0x04
	get null long
	string FNAME p= "%s.%s" name fileType
	log FNAME pointer length
next i

```
