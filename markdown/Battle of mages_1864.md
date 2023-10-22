## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-04-25T10:23:05+00:00
- Post Title: Battle of mages

The game it's 2 big files, the 1st it's unpacked (900kb's):
[http://rapidshare.de/files/18890560/Gam ... p.zip.html](http://rapidshare.de/files/18890560/GamePack1_gdp.zip.html)

And the 2nd it's packed with zlib, i know how to unpack only 1 file of the big file, but not all files  (1.6 mb's).
[http://rapidshare.de/files/18890641/Gam ... p.zip.html](http://rapidshare.de/files/18890641/GamePack2.gdp.zip.html)

Tnxs
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-25T14:12:06+00:00
- Post Title: Battle of mages

I've made two bms-scripts, one to unpack the compressed data and one to unpack the not compressed data. I had no luck in combining both of them within one script though.. this script wouldn't work when loading the archives:

```
ComType ZLib1 ;
IDString 0 GDP ;
GoTo 12 0 ;
Get FILENUM Long 0 ;
GoTo 36 0 ;
For F = 1 To FILENUM ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos CFSIZEX 0 ;
Get CFSIZE Long 0 ;
If CFSIZE = 0 ;
Set DONTCLOG Byte 1 ;
Set DONTLOG Byte 1 ;
EndIf ;
SavePos DFSIZEX 0 ;
Get DFSIZE Long 0 ;
If DFSIZE = 0 ;
Set DONTCLOG Byte 1 ;
Set DONTLOG Byte 1 ;
EndIf ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
Get FNAME String 0 ;
If CFSIZE = DFSIZE ;
Set DONTCLOG Byte 1 ;
EndIf ;
If DONTCLOG = 0 ;
CLog FNAME FOFFSET CFSIZE FOFFSETX CFSIZEX DFSIZE DFSIZEX ;
EndIf ;
If DONTLOG = 0 ;
Log FNAME FOFFSET CFSIZE FOFFSETX CFSIZEX ;
EndIf ;
Set DONTCLOG Byte 0 ;
Set DONTLOG Byte 0 ;
Next F ;
```


Anyway, 1st script:

```
ComType ZLib1 ;
IDString 0 GDP ;
GoTo 12 0 ;
Get FILENUM Long 0 ;
GoTo 36 0 ;
For F = 1 To FILENUM ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos CFSIZEX 0 ;
Get CFSIZE Long 0 ;
If CFSIZE = 0 ;
Set DONTCLOG Byte 1 ;
EndIf ;
SavePos DFSIZEX 0 ;
Get DFSIZE Long 0 ;
If DFSIZE = 0 ;
Set DONTCLOG Byte 1 ;
EndIf ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
Get FNAME String 0 ;
If CFSIZE = DFSIZE ;
Set DONTCLOG Byte 1 ;
EndIf ;
If DONTCLOG = 0 ;
CLog FNAME FOFFSET CFSIZE FOFFSETX CFSIZEX DFSIZE DFSIZEX ;
EndIf ;
Set DONTCLOG Byte 0 ;
Next F ;
```

[GDP_zlib.zip](https://xentaxbackup.github.io/file/725_GDP_zlib.zip)
## Post #3
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-25T14:13:07+00:00
- Post Title: Battle of mages

And the second script:

```
IDString 0 GDP ;
GoTo 12 0 ;
Get FILENUM Long 0 ;
GoTo 36 0 ;
For F = 1 To FILENUM ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos CFSIZEX 0 ;
Get CFSIZE Long 0 ;
If CFSIZE = 0 ;
Set DONTLOG Byte 1 ;
EndIf ;
Get DFSIZE Long 0 ;
If DFSIZE = 0 ;
Set DONTLOG Byte 1 ;
EndIf ;
SavePos TEMP 0 ;
Math TEMP += 16 ;
GoTo TEMP 0 ;
Get FNAME String 0 ;
If CFSIZE <> DFSIZE ;
Set DONTLOG Byte 1 ;
EndIf ;
If DONTLOG = 0 ;
Log FNAME FOFFSET CFSIZE FOFFSETX CFSIZEX ;
EndIf ;
Set DONTLOG Byte 0 ;
Next F ;
```


If you get an error with "Empty file list" or something like that, just try loading the archive with the other script. Compiled scripts are attached.. 
[GDP.zip](https://xentaxbackup.github.io/file/726_GDP.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-26T06:54:51+00:00
- Post Title: Battle of mages

Awesome PXR!  

I will see why the first script doesn't work. I really need this BMS repository, so I can keep track of new BMSes...  

Meanwhile, I'll post it on the blog.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-04-26T18:36:29+00:00
- Post Title: Battle of mages

Tnx PXR
