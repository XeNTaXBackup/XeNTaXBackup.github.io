## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-07-21T21:29:49+00:00
- Post Title: Tron 2.0 DTX/LTB

I have 2 different file types and I have been trying to find a program to convert them with the only thing I have been able to find is something that is a paid addon for Unity. Here are a couple sample files. I would rather not use Hex2OBJ as I still have no knowledge or interest in trying to figure all of that out to convert every single model.
[TronSample.zip](https://xentaxbackup.github.io/file/11327_TronSample.zip)
## Post #2
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-07-22T01:51:17+00:00
- Post Title: Tron 2.0 DTX/LTB

Use noesis, same topic here  
[viewtopic.php?f=16&t=7230](http://forum.xentax.com/viewtopic.php?f=16&t=7230)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-22T04:51:21+00:00
- Post Title: Tron 2.0 DTX/LTB

does not support the uploaded ltb because it contains bones
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-22T19:44:16+00:00
- Post Title: Tron 2.0 DTX/LTB

i made a Noesis script that opens your dtx sample since finale00's script didn't work with it 


 tex_Tron2_dtx.zip
(596 Bytes) Downloaded 46 times


it only supports dxt5 right now because i only had one texture sample to work with
if you can upload more i will update the script
## Post #5
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-07-24T13:58:18+00:00
- Post Title: Tron 2.0 DTX/LTB

Here are a few more DTX files. Along with a few more LTB just in case. I've tried to download the scripts from that thread which was linked but none of the webpages seem to work. Also tried the LTB scripts for Noesis from the Himeworks webpage but had an error on trying.



Sorry would have uploaded this here but the max file size on the site is 256kb. 
[https://www.sendspace.com/file/h1gqfr](https://www.sendspace.com/file/h1gqfr)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-24T15:00:36+00:00
- Post Title: Tron 2.0 DTX/LTB

All of those new texture samples are dxt5 and work with the current script.
all of your model samples except for BASE_GENERAL.LTB work with finale00's ZuOnline_ltb script here 
[http://himeworks.com/redirect.php?type= ... Online_ltb](http://himeworks.com/redirect.php?type=noesis&name=ZuOnline_ltb)

i think BASE_GENERAL.LTB may be animation files or something
## Post #7
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-07-26T06:35:26+00:00
- Post Title: Tron 2.0 DTX/LTB

> Reply from Nintendude
>
> Here are a few more DTX files. Along with a few more LTB just in case. I've tried to download the scripts from that thread which was linked but none of the webpages seem to work. Also tried the LTB scripts for Noesis from the Himeworks webpage but had an error on trying.



Sorry would have uploaded this here but the max file size on the site is 256kb. 
https://www.sendspace.com/file/h1gqfr

Because your sample file just contain bones + anim, no mesh so that's why finale00's plugin didn't work
You must try the Tron_tools instead
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-06-19T18:53:05+00:00
- Post Title: Tron 2.0 DTX/LTB

> Reply from Acewell ↑Sat Jul 23, 2016 3:44 am at Sat Jul 23, 2016 3:44 am
>
> 
i made a Noesis script that opens your dtx sample since finale00's script didn't work with it 
tex_Tron2_dtx.zip
it only supports dxt5 right now because i only had one texture sample to work with
if you can upload more i will update the script

a few more samples landed my way, here is an adjustment to read types for DXT1 and ARGB32

```
#
#	Reads DDS Textures From .DTX files
#	
#	Author:	Acewell
#	Date:		July 22nd, 2016
#	Source:	https://forum.xentax.com/viewtopic.php?p=120609&sid=ca4f96392b14ec137869e208ab9a1719#p120609
#
#	Changelog:
#	June 19 2020
#		Added additional if statement to catch formats for DXT1 and ARGB32
#		- mariokart64n
#

from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("Tron 2.0", ".dtx")
	noesis.setHandlerTypeCheck(handle, Tron2CheckType)
	noesis.setHandlerLoadRGBA(handle, Tron2LoadRGBA)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def Tron2CheckType(data):
	bs = NoeBitStream(data)
	bs.seek(0x04, NOESEEK_ABS)
	Magic = bs.readBytes(4)
	print(Magic)
	if Magic != b'\xFB\xFF\xFF\xFF':
		return 0
	return 1
	
def Tron2LoadRGBA(data, texList):
	datasize = len(data) - 0xa4        
	bs = NoeBitStream(data)
	bs.seek(0x08, NOESEEK_ABS)
	imgWidth = bs.readShort()
	imgHeight = bs.readShort()
	bs.seek(0x1A, NOESEEK_ABS)
	texFmt = bs.readUByte()
	bs.seek(0xa4, NOESEEK_ABS)        
	data = bs.readBytes(datasize)     
	
	if texFmt == 3:	#ARGB32
		texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, noesis.NOESISTEX_RGBA32))
	elif texFmt == 4:	#DXT1
		texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, noesis.NOESISTEX_DXT1))
	elif texFmt == 5:	#DXT3
		texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, noesis.NOESISTEX_DXT3))
	elif texFmt == 6:	#DXT5
		texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, noesis.NOESISTEX_DXT5))
	
	return 1

```
