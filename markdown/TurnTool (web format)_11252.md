## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-25T20:18:57+00:00
- Post Title: TurnTool (web format)

About TurnTool: [http://turntool.com/](http://turntool.com/)
Example: [http://configurator.atlant-m.kiev.ua/](http://configurator.atlant-m.kiev.ua/)
Sample: [http://configurator.atlant-m.kiev.ua/fi ... rtline.tnt](http://configurator.atlant-m.kiev.ua/files/multivan/vw_multivan_comfortline.tnt)
Script:

```
idstring "TRAW\x00"
get headSize long		#or maybe data offset in case of multiple TRAW sections?

get numFiles long
for i = 0 < numFiles
	get strLen short	#strings are null delimited anyway
	get fileName STRING
	get fileOffset long
	get fileSize long
	savepos nextFile

	goto fileOffset
	idstring "PAC\x00"
	get SIZE long
	savepos OFFSET
	math fileSize -= 0x08
	clog fileName OFFSET fileSize SIZE
	goto nextFile
next i
```

This is my first and only quickbms script, so if anyone has any suggestions I'm all ears.

After extraction, 2 types of files stand out:
- T3D: mesh data with vertices and face indices "in plain view"
- T2D: one or more JPEG textures
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-26T09:21:32+00:00
- Post Title: TurnTool (web format)

Regarding the script syntax it's ok, the only suggestion I can give is to use DUMMY variables for unknown fields instead of goto.
For example "goto 0x1 0 SEEK_CUR" -> "get DUMMY byte"
And if there are more bytes but they can't be idenfied as a field, for example a sequence of 5 bytes, you can use "getdstring DUMMY 5".
In idstring you can use also C strings so if the signature is "PAC" followed by a 0x00 byte, you can use idstring "PAC\0" or "PAC\x00"
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-26T10:41:26+00:00
- Post Title: TurnTool (web format)

Thanks, that helped a lot.
I edited the script with your suggestions.
