## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-09-25T10:29:36+00:00
- Post Title: [REQ] Obscure II .hvp extractor

Hello. I know that this has been discussed before on the forum, but no actual solution was proposed. The "hvptool" extracts a lot of dat files, so no filenames and no extensions are known. A user has said that those are lzo1x compressed, but I couldn't extract them with any tool. So, could anyone, please, make an extractor for these files with correct extensions? Filenames are not a priority. Attached is an example of the hvp file and the hvptool itself (just in case). Thanks in advance.

```
https://cloud.mail.ru/public/GpsZ/1QbzShbtx
```
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-11-08T14:32:30+00:00
- Post Title: [REQ] Obscure II .hvp extractor

Hi
How to get models from this game:
1.make new folder - "DATAPACK"
2.copy file "DATAPACK.hvp" to new folder "DATAPACK"
3.unpack "DATAPACK.hvp" from folder "DATAPACK" with quickbms, use script

```
comtype lzo1x
get unk1 long
get unk2 long
get FILES long
get unk3 long
get unk4 long
for i = 0 < FILES
	get type long
	get unk long
	get size long
	get offset long
	get zsize long
	get unk long
    math C = i
	set NAME string C
	if type == 1
		clog NAME offset zsize size
	endif	
	if type == 0
		log NAME offset size
	endif	
next i
```

4.instal Blender 249 and Python 266
4.unpack blend importer and copy all files  to folder where is blender.exe
5.doubleclick Blender249.blend
6.in Blender Text Window press alt+p and select "DATAPACK.hvp" from folder "DATAPACK"
7.files are sorted in tree folder
8.one more time press alt+p and select file 102 from folder "0\1\10\100"
9.open "g2_body.image" from folder "0\1\10\100" in TextureFinder.exe and select pixel formats 565=16
10.save image as g2_body.bmp and move to folder "0\1\10\100\104"
11.repeat step 10 for all images .Some images have tga format, so don't need to convert (hair images)
12.one more time press alt+p and select file 105 from "0\1\10\100\104" and script import textured and skinned with bones model of girl

Importer works not for all files. Still in progress.
Some bones are scaled to 0 so please select armature and than select in 3d window "mode edit".
[Blender249[Obscure2][PC][hvp][2015-11-08].zip](https://xentaxbackup.github.io/file/9981_Blender249[Obscure2][PC][hvp][2015-11-08].zip)
## Post #3
- Username: panthalassa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 07, 2015 5:08 pm
- Post datetime: 2015-12-31T14:44:18+00:00
- Post Title: [REQ] Obscure II .hvp extractor

Hello, I hope someone can help me with this... When I press alt+p to run the script in blender, I get this error message:
File "C:\Users\1\Desktop\Blender249[Obscure2][PC][hvp][2015-11-08]\Blender249[Obscure2][PC][hvp][2015-11-08]\Blender249.blend\starter.py", line 10 print 'format',format

SyntaxError: invalid syntax

location: <unknown location>:-1


Can somebody PLEASE help me with this?? This game has been a huge part of my childhood and early teens, and I really want to browse through its files...  :/
## Post #4
- Username: panthalassa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 07, 2015 5:08 pm
- Post datetime: 2015-12-31T15:23:06+00:00
- Post Title: [REQ] Obscure II .hvp extractor

Never mind, I figured out what I did wrong.. My bad. Now my problem is, there are no files in any of the folders that are created after I run the script... Tried it twice. What now?
## Post #5
- Username: panthalassa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 07, 2015 5:08 pm
- Post datetime: 2015-12-31T16:37:30+00:00
- Post Title: [REQ] Obscure II .hvp extractor

Lol, fixed that too... omg I'm a noob at this. Now, my problem is, I don't know what to do with the hair files... Yes, they don't need conversion through blender, but when I rename them with a .tga extension in the end, photoshop can't read them. I'm confused ;_;
## Post #6
- Username: dx1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2016 4:55 pm
- Post datetime: 2016-08-16T09:59:31+00:00
- Post Title: [REQ] Obscure II .hvp extractor

it gives me an error :python script error check console--no module named shutil
## Post #7
- Username: hgdagon
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-19T15:27:47+00:00
- Post Title: [REQ] Obscure II .hvp extractor

My research on HVP archives from Obscure 2 --> [viewtopic.php?p=188831#p188831](https://forum.xentax.com/viewtopic.php?p=188831#p188831)
Links to extractor and file format are shared there. I hope that it will be helpful to someone.
