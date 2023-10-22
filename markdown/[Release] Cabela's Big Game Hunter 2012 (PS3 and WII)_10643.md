## Post #1
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-07-29T23:34:47+00:00
- Post Title: [Release] Cabela's Big Game Hunter 2012 (PS3 and WII)

Fixed April 10 2014
First use this script to extract the CRS files (actor.crs contains the animal meshes):
[http://ps23dformat.wikispaces.com/file/ ... 012CRS.bms](http://ps23dformat.wikispaces.com/file/view/BGH2012CRS.bms)

```
# (c) CTPAX-X Team 2013
# http://www.ctpax-x.org/

ImpType Standard

IDString "!CPF"
# version?..
Get TMP Long
Get FileCount Long

For I = 1 To FileCount
  SavePos TOC
# skip some data
  Math TOC += 16
  GoTo TOC
# read file data
  Get FileSize Long
  Get FileOffs Long
# blocks in packed file
  Get BlockNum Long
  Get TMP Long
# read filename
  GetDString FileName 260
# get file packed size
  SavePos TOC

# create memory file - output buffer
  Log MEMORY_FILE 0 0
# append enabled
  Append
  For J = 1 To BlockNum
    GoTo FileOffs
    Get FilePack Long
    Math FileOffs += 4
# packed flag?..
If FilePack & 0x80000000
      Math FilePack -= 0x80000000
# LZO packed file
      ComType lzo1x
      CLog MEMORY_FILE FileOffs FilePack FileSize
      ComType copy
    Else
# unpacked?..
      Log MEMORY_FILE FileOffs FilePack
    EndIf
    Math FileOffs += FilePack
  Next J
# flush memory file to disk
  Get FileSize ASIZE MEMORY_FILE
# append disabled
  Append
  Log FileName 0 FileSize MEMORY_FILE

# back to TOC
  GoTo TOC

Next I
```

Source:
[http://www.extractor.ru/ipb/index.php?showtopic=8588](http://www.extractor.ru/ipb/index.php?showtopic=8588)


Then use the QuickBMS script I made here on the .msh files:
PS3 Version
[http://ps23dformat.wikispaces.com/file/ ... o3dsUV.bms](http://ps23dformat.wikispaces.com/file/view/BGH2012PS3mshTo3dsUV.bms)
Wii Version
[http://ps23dformat.wikispaces.com/file/ ... o3dsUV.bms](http://ps23dformat.wikispaces.com/file/view/BGH2012WIIwmhTo3dsUV.bms)


These scripts will convert the .msh files to .3ds files with UVs (The UV's need to divided by 512 (1024?) otherwise there will appear off the screen.




Some .msh files contain multiple meshes, and this script will convert each individual mesh. Some .msh files contain no meshes so no .3ds files will be produced by those meshes.

To save time you can use the Quickbms script on a folder that contains multiple .msh files instead of using the script on each .msh file one at a time.

Use the script as follows, (you need to use the Microsoft Windows Command Prompt and the w in -w must be lowercase):

```
C:\bgh2012\quickbms.exe -w C:\bgh2012\BGH2012PS3mshTo3dsUV.bms C:\bgh2012\canis_lupus.msh C:\bgh2012\output
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-04-10T07:49:09+00:00
- Post Title: [Release] Cabela's Big Game Hunter 2012 (PS3 and WII)

that script has an invalid command, replace:

```
If (FilePack & 0x80000000) != 0 Then
```
with
```
If FilePack & 0x80000000
```
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2014-04-10T11:36:03+00:00
- Post Title: [Release] Cabela's Big Game Hunter 2012 (PS3 and WII)

> Reply from aluigi
>
> that script has an invalid command, replace:
Code: Select allIf (FilePack & 0x80000000) != 0 ThenwithCode: Select allIf FilePack & 0x80000000
Thank you. I fixed it.
