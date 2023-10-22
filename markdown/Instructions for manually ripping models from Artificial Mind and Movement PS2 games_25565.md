## Post #1
- Username: LarryKoopaV2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 01, 2021 7:33 am
- Post datetime: 2022-06-30T16:42:37+00:00
- Post Title: Instructions for manually ripping models from Artificial Mind and Movement PS2 games

I recently learned how to rip models from the PS2 game Disney Move with the help of Model Researcher and a Noesis script created by DKDave. The process also appears to work with other PS2 games from the same developer, so I wanted to share it here for anyone who would have an interest in extracting models from these games. At the moment it is very manual, and Dave has emphasized that his script was thrown together quickly using a made up file extension and with information that requires the script to be edited for each individual model. One of the purposes of sharing this is if anyone would want to use the script and instructions to create a much more automatic process. Another major issue I've found with ripping the models is that they can often have erroneous faces as well as the intended ones which right now will need removing individually with a model editor. Instructions and Noesis script are attached.

Links:
Model Researcher: [http://mr.game-viewer.org/](http://mr.game-viewer.org/)
QuickBMS archive extraction script: [https://web.archive.org/web/20180724224 ... o+Unmasked](https://web.archive.org/web/20180724224411/https://ps23dformat.wikispaces.com/Scooby+Doo+Unmasked)

I have found that the process works on the following games. For multiconsole games, it was only tested on the PS2 version:
Scaler: identical process
Get On Da Mic: identical process
Scooby-Doo! Unmasked: identical process
Ed, Edd n Eddy: The Mis-Edventures: files stored in .PS2 archive, extraction method doesn't work but individual models can still be found with a hex editor. Textures also stored in .PS2 archive. Model ripping process is otherwise identical
Flow: Urban Dance Uprising: process is identical except the model files have the extension .dob, therefore the python script will need to have mentions of .move changed to .dob, or the extension of the model file changed to .move
Teen Titans: files stored in .PS2 archive, extraction method doesn't work but individual models can still be found with a hex editor. Textures also stored in .PS2 archive. Model ripping process is otherwise identical
Monster House: files stored in .PS2 archive, extraction method doesn't work but individual models can still be found with a hex editor. Textures also stored in .PS2 archive. Model ripping process is otherwise identical
The Ant Bully: all files including models and textures are stored in a single .A2M archive which the extraction method doesn't work on but individual models can still be found with a hex editor. Model ripping process is otherwise identical
Disney's Kim Possible: What's the Switch?: all files including models and textures are stored in a single .A2M archive which the extraction method doesn't work on but individual models can still be found with a hex editor. Model ripping process is otherwise identical
Happy Feet: all files including models and textures are stored in a single .A2M archive which the extraction method doesn't work on but individual models can still be found with a hex editor. Model ripping process is otherwise identical
Power Rangers: Super Legends: files stored in .PS2 archive, extraction method doesn't work but individual models can still be found with a hex editor. Textures also stored in .PS2 archive. Model ripping process is otherwise identical
High School Musical: Sing It!: files stored in .PS2 archive, extraction method doesn't work but individual models can still be found with a hex editor. Textures also stored in .PS2 archive. Model ripping process is otherwise identical
Iron Man: all files including models and textures are stored in a single .A2M archive which the extraction method doesn't work on but individual models can still be found with a hex editor. Model ripping process is otherwise identical
Indiana Jones and the Staff of Kings: all files including models and textures are stored in a single .A2M archive which the extraction method doesn't work on but individual models can still be found with a hex editor. Model ripping process is otherwise identical
[instructions & script.zip](https://xentaxbackup.github.io/file/22438_instructions & script.zip)
## Post #2
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2022-07-17T11:50:01+00:00
- Post Title: Instructions for manually ripping models from Artificial Mind and Movement PS2 games

Hey
I made a Texture Noesis script for Ed, Edd n Eddy: The Mis-Edventures (PC).
You have to give it the extension .tex, cause it has none.
So far I identify textures by looking into a hex editor, at the beginning there is a texturename and then 0xCC padding.
All textures so far are DTX5, if anyone finds other textureformats please tell me.
Have a nice day.  

```

def registerNoesisTypes():
    handle = noesis.register("Texture File A2M (PC)", ".tex")
    noesis.setHandlerTypeCheck(handle, A2MCheckType)
    noesis.setHandlerLoadRGBA(handle, A2MLoadRGBA)
    noesis.logPopup()
    return 1

def A2MCheckType(data):
    return 1   

def A2MLoadRGBA(data, texList):
    bs = NoeBitStream(data)
    textureName = bs.readString()
    bs.seek(0x64, NOESEEK_ABS)
    mipmapCount = bs.readUInt()
    bs.seek(0x24, NOESEEK_ABS)
    imageOffset = bs.readUInt() - 64 # cause offsets always with -64
    bs.seek(4 * (mipmapCount - 1), NOESEEK_REL)
    imageEnd = bs.readUInt() - 64
    bs.seek(0x68, NOESEEK_ABS)
    width = bs.readUInt()
    height = bs.readUInt()
    textureFormat = bs.readUInt()
    if (textureFormat != 4):
        print("Unknown Textureformat: ", textureFormat)
        return 0
    bs.seek(imageOffset, NOESEEK_ABS)
    textureSize = imageEnd - imageOffset
    textureData = bs.readBytes(textureSize)
    rawTextureData = rapi.imageDecodeDXT(textureData, width, height, noesis.FOURCC_DXT5)
    texList.append(NoeTexture(textureName, width, height, rawTextureData, noesis.NOESISTEX_RGBA32))
    return 1


```
