## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-29T03:46:15+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

*script updated December 1, 2016*

made my first model import script for Noesis to open these models  


 fmt_SWCWA_dme.zip
(1.29 KiB) Downloaded 133 times




supports mesh and UVs only
textures will load if they are in the same folder with the model   

some models might display transparent if the texture has an alpha channel,
but i don't know how to turn off displayed transparency   

3d object converter can open these models too
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-29T05:31:52+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

great to see your progress! (though I find this python crxp is harder to deal with than 'C' or maxscript in many cases  )
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-29T10:04:20+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

thanks! i have no clue how to do this in C or maxscript and i'm still not sure of many things in python, i mostly just used what i learned from texture scripts. 
i used your Hex2obj program to confirm vertex and face counts, vertex strides and UV positions for each model type, this would not have been possible for me otherwise so thank you for wonderful program.    
now is time for some of these
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-05-30T17:19:26+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
>  3d object converter can open these models too but it mirrors and rotates them for some reason

Thank you for your information.

It loads the 3d points as X,Z,Y, but I did not realized it mirrors the loaded objects.
I fixed it (X,Y,Z vertex order + transformation matrix to get the correct view in my program).

I released the v6.408 as a web update now, so just use the Help/Check for updates... function to get it.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-04T10:25:34+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

i have updated the script in the top post so it prints the texture names in a more readable vertical list under the model name in the logPopup so it looks like this

```
texturename.dds
texturename.dds
```


and i added mesh IDs to each submesh so Noesis won't merge them all into a single megamesh!   
this was a problem when models had more than one submesh that used different textures and
the UVs were layered making it difficult to apply textures to the right parts.
## Post #6
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-06-06T00:54:45+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

That's the older version of the format used by Planetside 2/H1Z1.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-01T23:32:14+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

i have updated the script in the first post so it auto loads the textures as long as they are in the same folder as the model.  
if a texture has an alpha channel the model or just parts will display transparent, i don't know how to turn off this transparency.  
also, if someone knows how to read normals properly for the dme format i will gladly fix the script.   
i am not 100% certain i am doing it right as of now.
## Post #8
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-12-02T12:00:07+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
> i have updated the script in the first post so it auto loads the textures as long as they are in the same folder as the model.  
if a texture has an alpha channel the model or just parts will display transparent, i don't know how to turn off this transparency.  
also, if someone knows how to read normals properly for the dme format i will gladly fix the script.   
i am not 100% certain i am doing it right as of now.

AceWell, how can I contact you? I can provide you some help
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-02T22:38:21+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

you can contact me right in this very thread about this format, that is why this thread exist   
i don't own the format so i don't discuss the research in private any more, i think everyone has a right
to see the research and add on to it if they know something so they don't have to start from nothing.  

Karpati seems to have this dme format figured out and i'm hoping he will share some specs
## Post #10
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-12-02T23:22:06+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
> you can contact me right in this very thread about this format, that is why this thread exist   
i don't own the format so i don't discuss the research in private any more, i think everyone has a right
to see the research and add on to it if they know something so they don't have to start from nothing.  

Karpati seems to have this dme format figured out and i'm hoping he will share some specs

I would like to speak with you privately fist, but if you insist. You have only DME files, or you have CWA game on your computer with all the files?
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-02T23:45:28+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

i have all game files, but i only research dme files because i am only interested in the models and textures
## Post #12
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-12-05T14:49:31+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
> i have all game files, but i only research dme files because i am only interested in the models and textures

I also have this game and I wanted to share all the necessary files,but looks like you have everything you need. 

Do you add bones  support in the future? As far as I know the skeleton is stored in dsk files.
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-05T21:02:47+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

i have no plans to add bones, skinning or animations unless you can show
me the python code that is needed to add these things to the script.
## Post #14
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-12-07T15:28:26+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
> i have no plans to add bones, skinning or animations unless you can show
me the python code that is needed to add these things to the script.

What is the point in the models without bones?
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-12-07T15:35:48+00:00
- Post Title: Star Wars: Clone Wars Adventures (*.dme)

> Reply from lyutor1945
>
> AceWell wrote:i have no plans to add bones, skinning or animations unless you can show
me the python code that is needed to add these things to the script.  What is the point in the models without bones?not the point of discussion this in here for sure.
## Post #16
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-12-21T00:14:30+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from AceWell
>
> i have all game files, but i only research dme files because i am only interested in the models and textures

One more question. In the game files, I found only Ventress in the mask.  In the game has only this model or   unmasked version too? And where if it so?
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-21T01:27:22+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

i only see a partial face for the Dathomir outfit like the one seen in the first picture
[http://cwa.wikia.com/wiki/Asajj_Ventress](http://cwa.wikia.com/wiki/Asajj_Ventress)

Char_AsajjHead_LOD0.dme extracted from AssetsW_001 and
goes with Char_AsajjBody_LOD0.dme from AssetsW_002
## Post #18
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2017-05-25T22:31:08+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Guys, maybe someone knows, is it possible to download somewhere the game or pack archives?
## Post #19
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2017-10-23T01:40:28+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Excuse me, but I am looking for the sound effects to this game. Does anybody have access to the original sound archives, and if so, how can I access them?
## Post #20
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-21T10:08:56+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

So I've recently been attempting to add bone support to this (I hope this is okay with you AceWell) and have gotten somewhere but still haven't managed to get proper positions on bones, any chance someone could look? This is the part of the script I added in:

```
		sk = rapi.loadIntoByteArray(skelFile)
		sk = NoeBitStream(sk)
		nameList = []
		parentList = []
		boneList = []
		mtxList = []
		sk.seek(0x08, NOESEEK_ABS)
		skipCount = sk.readUInt()
		currentPos = sk.tell()
		skip = sk.readBytes(skipCount)
		boneCount = sk.readUInt()
		print(boneCount)
		sk.seek(currentPos)
		for i in range(boneCount):
			boneName = sk.readString()
			#print(boneName)
			nameList.append(boneName)
		skip = sk.readBytes(4)
		for i in range(boneCount):
			skip = sk.readBytes(4)
			parent = sk.readUByte()
			skip = sk.readBytes(3)
			parentList.append(parent)
		for i in range(boneCount):
			unk = sk.readFloat()
			rot = NoeQuat(sk.read("4f"))
			scale = sk.read("3f")
			unk2 = sk.readFloat()
			posX, posY, posZ = sk.read("3f")
			#print(pos)
			boneMtx = rot.toMat43().inverse()
			boneMtx[0] *= scale[0]
			boneMtx[1] *= scale[1]
			boneMtx[2] *= scale[2]
			boneMtx[3] = NoeVec3((posX, posY, posZ))
			#print(posY)
			print(sk.tell())
			mtxList.append(boneMtx)
			newBone = NoeBone(i, nameList[i], mtxList[i], None, parentList[i])
			boneList.append(newBone)
```


It overall looks like it gets good positioning on heads although not at the position of the mesh, but it is very wrong on bodies. I could just be reading the data for bones completely wrong because I'm not familiar with how to read them properly, but any help is appreciated on how to do that. I've attached both bone files for the characters shown in the images.

 
[CWABones.7z](https://xentaxbackup.github.io/file/14889_CWABones.7z)
## Post #21
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-21T12:31:06+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

ugh. ehh... how do i get noesis to see the skelly file? i tried the local and absolute path, but it doesn't work, damnit.

```
        print("skelly found")
        sk = rapi.loadIntoByteArray(str("D:\starwars\models\cwa_xtr_wip\ahsokaV2\Char_HumanFemaleBody.dsk"))

```

btw. tab indents pls. your space code differs from ace's spaces.  and tabs are easier to track and manage/count for the parser to interpret. plus the current script doesn't read the boneweights and indices anymore. i have another (the older) version of the script tho.
## Post #22
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-21T13:02:14+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

```
	ctx = rapi.rpgCreateContext()
	#skelloading
	baseName = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getLastCheckedName()))
	print(baseName)
	skelFile = rapi.getDirForFilePath(rapi.getInputName()) + baseName + ".dsk"
```


That is before the other code I posted, obviously will need the .dme file to make this work, and I had to remove the LOD0 from the name of the .dme file to make it work too.

It also needs this at the end instead of just mdlList.append(mdl)

```
	mdlList.append(mdl); mdl.setBones(boneList)
```


They are tabbed, pasting the code makes it have spaces and not tabs, and I only have skeleton loading right now, still no weights.
## Post #23
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-21T14:25:22+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

got it. manual debug right now. the whole thing should be done using the adr files and all files dumped in a single folder to be able to load all files directly. i only got the bone relationships sorta figured. there're possibly a bone_id -1 (FFFF) and a parent_id -1 (FFFF) too, potentially unparented bones. the other offset is directly into the bonename table. i still got no clue howto assemble the matrices. i'm a noob when it comes to this. i could math that there are 12 floats per bone tho. could be a 4x3 or 3x4 matrix, depending how you get the translation vector in there. using a quaternion you have 7, 3 for translation and maybe 1 for the scale, so... this doesn't make alot of sense to me.  anyway... the bonetable code

```
    ctx = rapi.rpgCreateContext()
    if (rapi.checkFileExists(skellyfile)):
        print("skelly found")
        sk = rapi.loadIntoByteArray(skellyfile)
        sk = NoeBitStream(sk)
        nameList = []
        parentList = []
        boneList = []
        mtxList = []
        sk.seek(0x08, NOESEEK_ABS)
        ofsrel_bonestruct = sk.readUInt()
        BNametable = sk.tell()
        sk.seek(ofsrel_bonestruct, NOESEEK_REL)
        boneCount = sk.readUInt()
        print(boneCount)
        currentbone = sk.tell()
        for i in range(boneCount):
            sk.seek(currentbone, NOESEEK_ABS)
            ofsrel_BName = sk.readUInt()
            boneId = sk.readUShort()
            parent = sk.readUShort()
            parentList.append(parent)
            currentbone = sk.tell()
            sk.seek(BNametable)
            sk.seek(ofsrel_BName, NOESEEK_REL)
            boneName = sk.readString()
            print(boneName)
            nameList.append(boneName)
        for i in range(boneCount):
            unk = sk.readFloat()
...

```
## Post #24
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-21T15:02:20+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Yeah my issue is the bone reading, I knew there were 12 floats per bone but I don't know which would be the rotation, position etc. I've tried various options aswell as just reading the matrix with Mat43 but it still results in the same thing I have right now.
## Post #25
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-21T16:42:29+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

yo. same here. but i got somewhere removing all the matrix stuff. using an identity mat to pin the locations. your script did output weird stuff. and i forgot to save the offset after the bone array.  the head bones were sorta pinned by the L and R X values. for sure the array location without all the matrix crap. still gotta figure where the delta or 'local translation' is. some parent child relations seem wrong too. i pretty much don't care about the rotation.



i'm not sure if this dislocation may be intentional even. i'm not sure about the math invloved but if the original pose is not stored and just uses the animation files this may still work without the tpose skelly. kinda protection. i'll try to figure it out anyway tho.
## Post #26
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-21T16:49:32+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Yeah that result is what I got with mine, the root and neck bones seem to be accurate in positioning, the X axis on the other bones seem accurate but everything else for those doesn't, which makes me confused.

Looks like the face positions are stored in the .dme file actually, but doesn't work for body. This is manual seeking in the file atm, gotta code in getting to it properly.
## Post #27
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-21T20:15:11+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

i got the head looking good. and a nice start at the body. parent recursion. i guess the rotation matters.



wip script if you wanna mess with it. 
[fmt_SWCWA_dme_vx.rar](https://xentaxbackup.github.io/file/14892_fmt_SWCWA_dme_vx.rar)
## Post #28
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-21T21:06:48+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

I'm not entirely sure how the parent recursion stuff works but nice work so far
## Post #29
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-21T22:37:35+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

yo. it was a weird thing to find anyway. i figured it out when i messed with the boneids. i added those and the head added to the neck was at the right place. but it didn't work any further. i had to try to recurse it. basicly what it does is adding what seems local bone transforms based on their parent bones.

recursion itself explained

```
    parent = parentList[i]
    if parent >= 0:
        recursion(parent)
```


1) i = toe -> search parent -> finds foot -> function calls itself with i paremeter foot
2) i = foot -> search parent -> finds calf -> function calls itself with i parameter calf
3) i = calf -> searhc parent -> finds thigh -> function calls itself with i parameter thigh
...

until there's no parent in the chain, which is the root bone. it's maybe just stupid code. now that i think about it could potentially be done with a while loop too. i just didn't think about that i guess.
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-22T11:38:06+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

9 floats for 3x3 local rotation matrix, 3 floats for local position vector.



sw_skel.png (59.17 KiB) Viewed 110 times



@episoder Your approach is correct, as you need to reach the world space coordinates, but it can be achieved more easily using matrices. Load 12 floats as NoeMat43. Multiply bone matrix with the parent in recursion until, you reach the top. You need the rotation to load the skeleton properly anyway.
## Post #31
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-22T17:23:33+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from akderebur
>
> 9 floats for 3x3 local rotation matrix, 3 floats for local position vector.

snip

@episoder Your approach is correct, as you need to reach the world space coordinates, but it can be achieved more easily using matrices. Load 12 floats as NoeMat43. Multiply bone matrix with the parent in recursion until, you reach the top. You need the rotation to load the skeleton properly anyway.

alright. i didn't see the 3x3 in the hex like that. i'm used to 4 column matrix data. will have to use an identity matrix then and fill the rows. i thought about testing the matrix adding yesternight already, since the rotation is broken. will have to see how that works in noesis.
## Post #32
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-25T19:07:40+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

well. i felt like it. easy progress. the weight data seems easy, but it sure doesn't wanna work easy. i need a break now.
## Post #33
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-25T20:27:31+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

I've been trying to get it to work for the past few days but didn't manage to, nice to see that you have.
Is there any chance you can explain how you did it? Just want to learn for the future so I don't have to rely on others.
## Post #34
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-09-25T22:32:30+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

explain? take the file then. it's still incomplete. as posted i just read all the 3x3 and transform in the matrix prelist (so it's not messing up the matrices doing the recursion at the same time). then recursed (and multiplied) all into the seperate postlist. done that trick.

still got no clue howto fix the weights. the bone indices seem to be not so correct when using this all straight.
[fmt_SWCWA_dme_dazbones_wip.rar](https://xentaxbackup.github.io/file/14919_fmt_SWCWA_dme_dazbones_wip.rar)
## Post #35
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-09-26T08:59:35+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Thanks, that helped me understand how you did it.
## Post #36
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-10-25T03:08:40+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Sorry for the bump.... If anyone knows which archives the sound files would be stored in for this game, please PM me. Thanks!
## Post #37
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-25T04:05:21+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from Anexenaumoon
>
> Sorry for the bump.... If anyone knows which archives the sound files would be stored in for this game, please PM me. Thanks!

( why PM? it's partially open source. i dunno anymore where i got the adpcm code tho. i can't credit it. defsb bat to de-fsbext and decode bat to de-code the adpcm codec files. 
[https://www.mediafire.com/file/36mrm78c9gpx2u0/dev.rar](https://www.mediafire.com/file/36mrm78c9gpx2u0/dev.rar) may leave that here anyway. )

wait a sec... wrong game... adventures not republic heroes...

doesn't the cwa bms script extract just mp3 and ogg files in the dearchived folders? you could use the windows search to get all of those.
## Post #38
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2018-10-25T15:21:31+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

episoder, in regards to that link you posted, does it have the assets to Star Wars: The Clone Wars - Republic Heroes or Star Wars: Clone Wars Adventures? I found a link to what somebody described as “all the assets” to the later here: [https://forum.facepunch.com/dev/bszzx/S ... postcwbwbk](https://forum.facepunch.com/dev/bszzx/Star-Wars-Model-Links-Thread-V4-Stay-on-Target/28/#postcwbwbk) However, Anexenaumoon said he couldn’t find the sound archives in there. They are .pack files, but I don’t know if they contain any sound archives.

What is your evaluation on this?
## Post #39
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-25T20:14:46+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

well. what i linked was a lil mistake in my thought process. the sound extractor is for republic heroes. 

about that pack. that is correct those are all the assets. the script or the modification to extract those can be found [there](https://zenhax.com/viewtopic.php?t=3621). it should extract everything sound related as mp3 or ogg files.
## Post #40
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2018-10-26T16:51:47+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

So, episoder, can you help me and Anexenaumoon which of the .pack archives to rip? That is to narrow down where the sound files are?
## Post #41
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-26T18:35:46+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from ARAJediMaster
>
> So, episoder, can you help me and Anexenaumoon which of the .pack archives to rip? That is to narrow down where the sound files are?

you gotta extract all of them. the files are all across the archives. see? ... get it? the modification from acewell apparently extracts all into one folder, which i haven't tested tho.
## Post #42
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-02-04T20:33:47+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

update... cause why not?!? a working head.



the remapping seems to be a lil harder on bodies tho. differences in bone count and all that.
## Post #43
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-02-05T03:21:11+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

almost there. now, it's just noesis fucking up the data. smd (right) has missing weights and fbx (left) is missing some bones. wth softwarez. damnit. for some reason i need 2 bone mappings for the 'normal' heads and 'uberloaded' bodies anyway. not a coherent data structure. mmh.
## Post #44
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-07T02:42:31+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

update: revamped the loader to use the adr files and loading the repective skeleton itself. rest is in the readme.

[https://www.mediafire.com/file/39v5gg5t ... ed_wip.rar](https://www.mediafire.com/file/39v5gg5t9touilb/cwa_rigged_wip.rar)
## Post #45
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-26T08:36:53+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

I loaded these scripts using noesis to extract the. DME file of PlanetSide 2, but the error was reported. Could you help me? I want to use these models to make interstellar MODs.

Here are some related samples.Thank you.
[Indar_Props_Rocks_OceanRock06_Lod0_LODAuto.zip](https://xentaxbackup.github.io/file/15964_Indar_Props_Rocks_OceanRock06_Lod0_LODAuto.zip)
## Post #46
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-26T09:22:26+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Extraction of DME file error screenshot of PlanetSide 2
[190326171952.png](https://xentaxbackup.github.io/file/15965_190326171952.png)
## Post #47
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-26T16:07:51+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

well it's a lil bit of a different container structure.

multiple streams. vertices and attributes. byte packed normals and probably tangents and 3 uv sets in half float format, it seems.

try it. all i can guesstimate what this rock gotta look like. if you wanna you can shuffle the uv offsets to get the 2nd and/or 3rd set until you get something usable. noesis only supports 2 sets. i'm certain on this sample the lot is unused. i won't try to figure out howto decode and recast the packed normal into a float array either. this sort of noesis syntax is cancer. maybe somebody wanna...
[fmt_Planetside2_dme.rar](https://xentaxbackup.github.io/file/15969_fmt_Planetside2_dme.rar)
## Post #48
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-27T03:35:23+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Sorry to use this script but still unable to export the model
[20190327104417.png](https://xentaxbackup.github.io/file/15972_20190327104417.png)
## Post #49
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-27T10:55:57+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

then upload more samples and/or the model that shows the error. i can't guess what's wrong with that one or how many model variations there are. you wanna mod this? dunno code or data? how you gonna reimport it anyway? guessing you just wanna extract, huh.
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-27T19:20:41+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

might want to create a new thread for Planetside 2, kind of off topic in my Star Wars thread.   
besides i'm pretty sure tools exist already for that game. 
[https://github.com/psemu](https://github.com/psemu)
[https://github.com/psemu/forgelight-dme](https://github.com/psemu/forgelight-dme)
[https://forums.daybreakgames.com/ps2/in ... ols.54360/](https://forums.daybreakgames.com/ps2/index.php?threads/tool-release-ps2ls-planetside-tools.54360/)
## Post #51
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-29T15:27:53+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

I want to use UE4 engine and blueprint to make such a single PC game, but I can not extract the relevant model.
So I have a hard time. I need help. Thank you.
## Post #52
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-29T15:31:52+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

My reference game is this game and Warframe.
Unfortunately, I cannot find the relevant extraction tool or script of Warframe game.
Because nobody seems to be able to extract the latest version of Warframe's models and textures, and ninjaripper is a tool that has no effect on warframes.
## Post #53
- Username: mummmm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 26, 2017 7:04 pm
- Post datetime: 2022-08-07T03:24:07+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from episoder ↑Thu Mar 07, 2019 10:42 am at Thu Mar 07, 2019 10:42 am
>
> 
update: revamped the loader to use the adr files and loading the repective skeleton itself. rest is in the readme.

https://www.mediafire.com/file/39v5gg5t ... ed_wip.rar

I think the file is missing now  
Can you please upload the file again?
## Post #54
- Username: rikstar44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 07, 2021 5:38 am
- Post datetime: 2023-06-17T12:02:19+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

Assets Download

Hello,
Since the ZenHax website is down, I can't find aynwhere to download the CWA Assets, which is unfortunate...
I decided to upload the full archive on my google drive an share the link with you, since I still got it on my PC:

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1P-K-WjtEdCvCV2X2YvZ6nFtL8npkeJfI?usp=sharing) 

To extract the .pack files I recommend a programm like ps2ls. You can download it also from my google drive:

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1P-K-WjtEdCvCV2X2YvZ6nFtL8npkeJfI?usp=sharing)

(optional) If you want an Asset Browser to quick-view the 3d-models and export them as .fbx (since they are .dme files) I recommend Noesis:

[https://richwhitehouse.com/index.php?co ... ojects.php](https://richwhitehouse.com/index.php?content=inc_projects.php)

If you want to share this post or the links attatched to it, I would appreciate it!
## Post #55
- Username: rikstar44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 07, 2021 5:38 am
- Post datetime: 2023-06-17T12:04:03+00:00
- Post Title: Re: Star Wars: Clone Wars Adventures (*.dme)

> Reply from lyutor1945 ↑Fri May 26, 2017 6:31 am at Fri May 26, 2017 6:31 am
>
> 
Guys, maybe someone knows, is it possible to download somewhere the game or pack archives?

Yeah, you might wanna look at my post to this topic
