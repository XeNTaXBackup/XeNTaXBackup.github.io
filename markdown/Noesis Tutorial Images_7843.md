## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-11T13:38:26+00:00
- Post Title: Noesis Tutorial Images

Ok Here is a script i did for Virtual Fighter 5(PS3)/ Dreamy Theater 1/2 (PS3)
If you want the best examples for images MR adults has them in his bullet witch script and in the quake formats.
so here is the code

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Virtual Fighter 5 Textures", ".bin")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
   noesis.logPopup()
   #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if bs.readInt() != 0x3505854 :
      return 0
   return 1
texList = []
def noepyLoadRGBA(data, texList):
   bs = NoeBitStream(data)
   bs.seek(0, NOESEEK_ABS)
   Tex = bs.readInt()
   TexCount = bs.readInt()
   Unk01 = bs.readInt()
   TexOffList = bs.read("i"*TexCount)
   for i in range(0, TexCount):
      TexName = 'test'
      bs.seek(TexOffList[i], NOESEEK_ABS)
      print(bs.tell())
      TXP = bs.readInt()
      TXPMIPS = bs.readInt()
      TXPUNK = bs.readInt()
      TexOff = bs.readInt()
      bs.seek(TexOffList[i] + TexOff, NOESEEK_ABS)
      TxpHeader = bs.read("i"*6)
      print(bs.tell())
      Txpdata = bs.readBytes(TxpHeader[5])
      print(TxpHeader)
      print(TxpHeader[3])
      texFmt = 0
      #DXT1
      if TxpHeader[3] == 6:
         texFmt = noesis.NOESISTEX_DXT1
      #DXT3
      if TxpHeader[3] == 7:
         texFmt = noesis.NOESISTEX_DXT3
      #DXT5
      if TxpHeader[3] == 9:
         texFmt = noesis.NOESISTEX_DXT5
      #ATI2N
      if TxpHeader[3] == 11:
         Txpdata = rapi.imageDecodeDXT(Txpdata, int(TxpHeader[1]), int(TxpHeader[2]), noesis.FOURCC_ATI2)
         texFmt = noesis.NOESISTEX_RGBA32

      tex1 = NoeTexture(TexName, int(TxpHeader[1]), int(TxpHeader[2]), Txpdata, texFmt)
      texList.append(tex1)
   return 1
```

Its basically the same way you would work with models only your now working with textures.
So these are the important lines.

```
      if TxpHeader[3] == 6:
         texFmt = noesis.NOESISTEX_DXT1
      #DXT3
      if TxpHeader[3] == 7:
         texFmt = noesis.NOESISTEX_DXT3
      #DXT5
      if TxpHeader[3] == 9:
         texFmt = noesis.NOESISTEX_DXT5
      #ATI2N
      if TxpHeader[3] == 11:
         Txpdata = rapi.imageDecodeDXT(Txpdata, int(TxpHeader[1]), int(TxpHeader[2]), noesis.FOURCC_ATI2)
         texFmt = noesis.NOESISTEX_RGBA32

      tex1 = NoeTexture(TexName, int(TxpHeader[1]), int(TxpHeader[2]), Txpdata, texFmt)
      texList.append(tex1)
```

all you need to make dds based images work is the image height , width , type , and the raw data in a byte stream
This was the line at the end of bullet witch
NoeTexture(entry.name, imgWidth, imgHeight, data, texFmt)
Then once you have This up and running you can import this script into a model script to have the textures load right into the texture list of your main script.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-11T17:32:25+00:00
- Post Title: Noesis Tutorial Images

Ah, that's how you load textures and add them to the list.
Great, I can probably get something working.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-18T06:50:17+00:00
- Post Title: Noesis Tutorial Images

Can you also do a tutorial for this image format some time?
It has already been figured out and the source code is available (included in attachment)

I was using it to do some image parsing but I'm not sure what to do lol
[src.7z](https://xentaxbackup.github.io/file/4909_src.7z)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-18T12:20:28+00:00
- Post Title: Noesis Tutorial Images

its zlib compressed data/
you need to follow this function in python then just read the resulting byte stream as a raw image
	int AliceImageQntToRaw(PEImageRaw* a_Target, AliceImageQnt* a_Image)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-15T06:59:26+00:00
- Post Title: Noesis Tutorial Images

Pretty sure this tutorial had no links to downloads since it would be impractical.
