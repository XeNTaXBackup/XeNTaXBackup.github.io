## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-09T12:55:29+00:00
- Post Title: AirMech (*.HPK)

```
#
# Written by Ekey (h4x0r)
#
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "HPK\x00"
get VERSION long
get FILES long
get FIRSTFILEPOS long
get VERSION long
get NTABLESIZE long
get NTABLEZSIZE long
savepos NTABLEOFFSET

clog MEMORY_FILE NTABLEOFFSET NTABLESIZE NTABLEZSIZE

math NTABLEOFFSET += NTABLEZSIZE

for i = 0 < FILES
	get NAME string MEMORY_FILE
	goto NTABLEOFFSET
	get ZSIZE long
	get OFFSET long
	get SIZE long
	get CRC long
	get NULL long
	math NTABLEOFFSET += 0x14
	clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #2
- Username: Player
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 15, 2011 5:38 pm
- Post datetime: 2013-04-09T15:56:28+00:00
- Post Title: AirMech (*.HPK)

Hi Ekey
Thanks for the script
well, I unpacked. HPK
examples of files [http://www.multiupload.nl/Z38MS2SY4Q](http://www.multiupload.nl/Z38MS2SY4Q)
model  .amf
animation .aaf
texture .DDS

how to import the model into 3DMAX?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-10T06:34:19+00:00
- Post Title: AirMech (*.HPK)

Ask in [3D/2D models](http://forum.xentax.com/viewforum.php?f=16) section about models, animation. DDS default DirectDraw Surface graphics ([here](https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop) plugin for Photoshop)
