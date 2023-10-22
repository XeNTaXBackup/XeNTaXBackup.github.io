## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-01-30T23:27:46+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

I took a look at the files in ToD and while the format of the textures seem to be the same used in the later games the models seem to be in a different format.



I think the models could be in the vertices.dat and/or the main.dat located in each of the level folders.

Here are the those two files from the Fastoon level so that someone can take a look.
[https://www.dropbox.com/sh/z4fwpdnx7y36isa/a9hQ56QbN9](https://www.dropbox.com/sh/z4fwpdnx7y36isa/a9hQ56QbN9)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-06T21:23:57+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

Edited....
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-06T23:33:20+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

Neat, Thanks for the info.
I noticed the missing data when comparing the verticies.dat to the mobys.dat from the other games.
I'm able to get meshes with hex2obj after editing the verticies.dat slightly

It's a pretty painful processes though

I can't get files from ToD right now, but Quest for Booty uses the same format.
Here are some files from the prologue level. I included some files witch might have that missing data in them, though if it's not, then i'm not sure what would contain it?
the game.self, or eboot.bin maybe? There's also a debug.psarc and game.psarc in the main game folder.
[https://www.dropbox.com/s/qyqbhodsls12o ... ologue.zip](https://www.dropbox.com/s/qyqbhodsls12oc6/QuestforBootyPrologue.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-07T17:01:14+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from o0DemonBoy0o
>
> It's a pretty painful processes thoughyep.
The sequence 0000 0001 0002 is found 3945 times.
Don't know whether each sequence is indicating the start of a new object's/sub meshes face index list
but using a script on this as Gh0sBblade did seems to be the better choice.

btw: UV pos=12 seems to fit better for your example

For Quest for Booty (vertices.dat)I used these params:
[](http://www.pic-upload.de/view-22196034/Quest4Booty.jpg.html)
## Post #5
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-08T00:12:00+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

Wow, 3945 times?

I figured I would fix that once I got to a model I wanted, but it appears that won't happen anytime soon.
I've been through about 40 meshes so far in the ToD Fastoon verticies.dat, and everything seems to be its own object.
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-09T08:45:15+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from Gh0stBlade
>
> I'll get things started off. I decided to take a quick peek, I have managed to suss out the majority of the format however, there seems to be "missing info" for the mesh vert strides etc. I think another file must contain the info because I cannot see where it could be stored. Where i have the full size of the vertices it seems to be wrong since the data keeps changing, i think multiple FVFs must be referenced somewhere else.

I don't have the time to fix this nor the file samples so I'll just post this so that someone else can either fix it or just use it in the future.
Code: Select all#Ratchet and Clank Tools Of Destruction .DAT loader
#By Gh0stBlade
#v0.1a

from inc_noesis import *
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("Ratchet and Clank Tools Of Destruction [PS3]", ".dat")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
   noesis.logPopup()
   return 1

NOEPY_HEADER = ""

#check if it's this type based on the data
def noepyCheckType(data):
	bs = NoeBitStream(data)
	MAGIC = bs.readInt()
	if MAGIC != 0x57484749:
		print("Fatal Error: Unknown filetype!")
		return 0     
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	
	SIGN = bs.readInt() 								#Signature - "WHGI"
	UNK00 = bs.readShort()								#???
	UNK01 = bs.readShort()								#???
	NUMOBJECTS = bs.readInt()							#Number of Objects in the file?
	PTR_END_OTBL = bs.readInt()							#Points to end of object table OR start of "PAD" data o.o
	
	PTR_UNK00 = bs.readInt()							#Points to some unknown table with each value with length 0x4
	NUM_UNK00 = bs.readInt()							#Unknown, is the count of how many longs stored at the offset above.
	PADDING = bs.readShort()							#Padding just says "0xDE, 0xAD" or "DEAD" o.o;
	PADDING = bs.readShort()							#Padding just says "0xDE, 0xAD" or "DEAD" o.o;
	PADDING = bs.readShort()							#Padding just says "0xDE, 0xAD" or "DEAD" o.o;
	PADDING = bs.readShort()							#Padding just says "0xDE, 0xAD" or "DEAD" o.o;
	
	MESHINFO = []											#MESH[]
	for i in range(0, NUMOBJECTS):
		OBJECTTYPE = bs.readInt()
		OBJECTOFFSET = bs.readInt()
		OBJECTUNK00 = bs.readInt()
		OBJECTSIZE = bs.readInt()
		#					0			1			2				3
		MESHINFO.append([OBJECTTYPE, OBJECTOFFSET, OBJECTUNK00, OBJECTSIZE])
	
	
	for i in range(0, NUMOBJECTS):
		if MESHINFO[i][0] == 0x00009000: #Vertices?
			bs.seek(MESHINFO[i][1], NOESEEK_ABS)			#Skip to the vertices
			print(bs.tell())
			VBUFFER = bs.readBytes(MESHINFO[i][3])			#Read vertices
			NUMVERTS = int(MESHINFO[i][3] / 0x18)
			print(bs.tell())
		elif MESHINFO[i][0] == 0x00009100: #Faces?
			#bs.seek(MESHINFO[i][1], NOESEEK_ABS)			#Skip to the faces
			#FBUFFER = bs.readBytes(MESHINFO[i][3])			#Read faces
			#NUMFACES = 
			print(bs.tell())

	rapi.rpgBindPositionBufferOfs(VBUFFER, noesis.RPGEODATA_INT, 0x18, 0)
	rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, 0x1900, noesis.RPGEO_POINTS, 1)
	#rapi.rpgCommitTriangles(FBUFFER, noesis.RPGEODATA_USHORT, NUMFACES, noesis.RPGEO_TRIANGLE_STRIP, 1)
	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl) #important, don't forget to put your loaded model in the mdlList
	rapi.rpgClearBufferBinds()
	return 1


It's messy but it pretty much explains the full format.
Very useful yeah I'll look into it again
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-09T15:22:59+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

if you want to look at a full games files.
Ratchet & Clank: A Crack in Time Clank (Great Clock Demo):
[http://zeus.dl.playstation.net/cdn/UP90 ... 9JKPJF.pkg](http://zeus.dl.playstation.net/cdn/UP9000/NPUA70085_00/RwjY3BBr6LQxIcTx1MqSed0FYhFfPH2e2g3UDdc1infN4wdEkIr65QkDBg6vc68hoDe2creMOn5tj5ujaFLdCC1i6BAaVyg9JKPJF.pkg)

Ratchet & Clank: A Crack in Time Ratchet (Krell Canyon Demo):
[http://zeus.dl.playstation.net/cdn/UP90 ... jOPpBY.pkg](http://zeus.dl.playstation.net/cdn/UP9000/NPUA70083_00/0kXXrT5BU49KuDP20mXBhRjcuhrtCOE2fiXapd7ijH8hbxriVArbWQX2FIPbCmlwWXgDB8nj3cwwCDRPcPh0nv7FYlEcEVgjOPpBY.pkg)
## Post #8
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-09T18:10:39+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from chrrox
>
> if you want to look at a full games files.
Ratchet & Clank: A Crack in Time Clank (Great Clock Demo):
http://zeus.dl.playstation.net/cdn/UP90 ... 9JKPJF.pkg

Ratchet & Clank: A Crack in Time Ratchet (Krell Canyon Demo):
http://zeus.dl.playstation.net/cdn/UP90 ... jOPpBY.pkg

Thanks chrrox, but it's already possible to get models from A Crack in Time and the games after.
[viewtopic.php?f=16&t=10977](http://forum.xentax.com/viewtopic.php?f=16&t=10977)
The only thing left is the UVs which seem correct but stretch out for some reason

Tools of Destruction and Quest for Booty seem to use a different format than the later games which is what i'm interested in.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-10T05:28:26+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

Not sure what you mean the format looks identical.
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-10T15:01:17+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from chrrox
>
> Not sure what you mean the format looks identical.
Yeah I did a search and I think Resistance 2 (i think that's what the game was) used the same format. Only the flags had been changed which references the types of the objects.

-------------------------------------------------

I'm not sure what has been "done" but if there are already tools which can view the models as seen a few posts above, why does it need doing twice?

This thread needs a bit of clarification hmmm, I'm mis-informed.
## Post #11
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-10T22:30:30+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from Gh0stBlade
>
> chrrox wrote:Not sure what you mean the format looks identical.
Yeah I did a search and I think Resistance 2 (i think that's what the game was) used the same format. Only the flags had been changed which references the types of the objects.

-------------------------------------------------

I'm not sure what has been "done" but if there are already tools which can view the models as seen a few posts above, why does it need doing twice?

This thread needs a bit of clarification hmmm, I'm mis-informed.

Well while I can get the models, it's a very slow process. going through over 3000 different meshes one by one just to get a single model isn't very fun.
I guess what i'm looking for is some sort of automated process or something.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-11T02:23:38+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

you have to parse shaders.dat it contains all the information for loading the other files.
the list of files is in level_cached.toc and they need to be loaded in the order in that file.
## Post #13
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-11T04:06:06+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from chrrox
>
> you have to parse shaders.dat it contains all the information for loading the other files.
the list of files is in level_cached.toc and they need to be loaded in the order in that file.

Tools of Destruction and Quest for booty don't have a shaders.dat file.

All the level folders for both games look pretty much exactly like this

```
built/levels/fastoon/vertices.dat
built/levels/fastoon/textures.dat
built/levels/fastoon/collision.dat
built/levels/fastoon/gameplay.dat
built/levels/fastoon/resident_sound.dat
built/levels/fastoon/resident_sound.us.dat
built/levels/fastoon/resident_sound.gb.dat
built/levels/fastoon/resident_sound.fr.dat
built/levels/fastoon/resident_sound.it.dat
built/levels/fastoon/resident_sound.de.dat
built/levels/fastoon/resident_sound.es.dat
built/levels/fastoon/resident_sound.nl.dat
built/levels/fastoon/resident_sound.pt.dat
built/levels/fastoon/resident_sound.jp.dat
built/levels/fastoon/resident_sound.kr.dat
built/levels/fastoon/resident_sound.cn.dat
built/levels/fastoon/resident_sound.dk.dat
built/levels/fastoon/resident_sound.fi.dat
built/levels/fastoon/resident_sound.no.dat
built/levels/fastoon/resident_sound.se.dat
packed/levels/levelfastoon/ps3gameplay.us.pkg
packed/levels/levelfastoon/ps3gameplay.gb.pkg
packed/levels/levelfastoon/ps3gameplay.fr.pkg
packed/levels/levelfastoon/ps3gameplay.it.pkg
packed/levels/levelfastoon/ps3gameplay.de.pkg
packed/levels/levelfastoon/ps3gameplay.es.pkg
packed/levels/levelfastoon/ps3gameplay.nl.pkg
packed/levels/levelfastoon/ps3gameplay.pt.pkg
packed/levels/levelfastoon/ps3gameplay.jp.pkg
packed/levels/levelfastoon/ps3gameplay.kr.pkg
packed/levels/levelfastoon/ps3gameplay.cn.pkg
packed/levels/levelfastoon/ps3gameplay.dk.pkg
packed/levels/levelfastoon/ps3gameplay.fi.pkg
packed/levels/levelfastoon/ps3gameplay.no.pkg
packed/levels/levelfastoon/ps3gameplay.se.pkg
built/levels/fastoon/fxconduit_packed.dat
built/levels/fastoon/effect.dat
built/levels/fastoon/system.tp
built/levels/fastoon/system.tph
built/levels/fastoon/dialogue.us.pkg
built/levels/fastoon/dialogue.gb.pkg
built/levels/fastoon/dialogue.fr.pkg
built/levels/fastoon/dialogue.it.pkg
built/levels/fastoon/dialogue.de.pkg
built/levels/fastoon/dialogue.es.pkg
built/levels/fastoon/dialogue.nl.pkg
built/levels/fastoon/dialogue.pt.pkg
built/levels/fastoon/dialogue.jp.pkg
built/levels/fastoon/dialogue.kr.pkg
built/levels/fastoon/dialogue.cn.pkg
built/levels/fastoon/dialogue.dk.pkg
built/levels/fastoon/dialogue.fi.pkg
built/levels/fastoon/dialogue.no.pkg
built/levels/fastoon/dialogue.se.pkg
built/levels/fastoon/lipsync.us.dat
built/levels/fastoon/lipsync.gb.dat
built/levels/fastoon/lipsync.fr.dat
built/levels/fastoon/lipsync.it.dat
built/levels/fastoon/lipsync.de.dat
built/levels/fastoon/lipsync.es.dat
built/levels/fastoon/lipsync.nl.dat
built/levels/fastoon/lipsync.pt.dat
built/levels/fastoon/lipsync.jp.dat
built/levels/fastoon/lipsync.kr.dat
built/levels/fastoon/lipsync.cn.dat
built/levels/fastoon/lipsync.dk.dat
built/levels/fastoon/lipsync.fi.dat
built/levels/fastoon/lipsync.no.dat
built/levels/fastoon/lipsync.se.dat
built/levels/fastoon/resident_dialogue.us.dat
built/levels/fastoon/resident_dialogue.gb.dat
built/levels/fastoon/resident_dialogue.fr.dat
built/levels/fastoon/resident_dialogue.it.dat
built/levels/fastoon/resident_dialogue.de.dat
built/levels/fastoon/resident_dialogue.es.dat
built/levels/fastoon/resident_dialogue.nl.dat
built/levels/fastoon/resident_dialogue.pt.dat
built/levels/fastoon/resident_dialogue.jp.dat
built/levels/fastoon/resident_dialogue.kr.dat
built/levels/fastoon/resident_dialogue.cn.dat
built/levels/fastoon/resident_dialogue.dk.dat
built/levels/fastoon/resident_dialogue.fi.dat
built/levels/fastoon/resident_dialogue.no.dat
built/levels/fastoon/resident_dialogue.se.dat
```
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-11T13:32:16+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

> Reply from chrrox
>
> you have to parse shaders.dat it contains all the information for loading the other files.
the list of files is in level_cached.toc and they need to be loaded in the order in that file.

I had a quick look and there appears to be no shader.dat in one of the levels I extracted. I am just going to assume it's all contained in main.dat but I still don't know. You're right, it is indeed a pain.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-11T14:15:54+00:00
- Post Title: [Request]Ratchet & Clank: Tools of Destruction

you can tell if main.dat is the file just search for 00 02 AB 00 in hex
if it shows up everywhere that is your file.
## Post #16
- Username: o0DemonBoy0o
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-13T13:11:14+00:00
- Post Title: Re: [Request]Ratchet & Clank: Tools of Destruction

A little update, Chrrox managed to figure out which files contain the meshes. I'm writing up the script to view them which is currently W.I.P. Here are some pictures for you to enjoy!

Ratchet


Clank
## Post #17
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-13T14:43:38+00:00
- Post Title: Re: [Request]Ratchet & Clank: Tools of Destruction

Nice work. Any luck with ToD so far?

Also, textures are still an issue.

Messing around with PVRTexTool I found the textures may actually be compressed in some way

heres what I got 


and what it's supposed to look like


here is the file used
[https://www.dropbox.com/s/2hvtgsdrclhr5mu/tex1](https://www.dropbox.com/s/2hvtgsdrclhr5mu/tex1)
## Post #18
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-13T15:51:40+00:00
- Post Title: Re: [Request]Ratchet & Clank: Tools of Destruction

> Reply from o0DemonBoy0o
>
> Nice work. Any luck with ToD so far?

Also, textures are still an issue.

Messing around with PVRTexTool I found the textures may actually be compressed in some way

heres what I got 


and what it's supposed to look like


here is the file used
https://www.dropbox.com/s/2hvtgsdrclhr5mu/tex1

TOD is probably the exact same format although I've not extracted a mesh and checked yet. This is for Ratchet and Clank: Into the Nexus at the moment, I tried the script on Resistance 2 models which were posted a few months back on this forum and it also works on that game. There's a good chance the model format is the same between all the games as suggested by Chrrox. But even if it isn't then alterations can be made to support other versions   

I think Chrrox looked at the textures and they were standard DDS files with a custom header (if my memory is correct) or headerless which is probably why viewing it in that PVR tool is not working. I don't think there's compression since if it was compressed you wouldn't be able to see that shape which clearly ressembles the other texture.

I'll take a look if I can find the textures and get back to you.
## Post #19
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-13T16:19:47+00:00
- Post Title: Re: [Request]Ratchet & Clank: Tools of Destruction

Actually the PVR tool is the only thing that got me anything close to the image.
The textures and be found in the Level_Uncached.psarc in the Highmips.dat file.
Also, as far as I can tell the formats for A Crack in Time all the way to Into the Nexus are exactly the same. It's just ToD and QfB that seem different.

Anyway I'm happy to see progress on this and await the script to view the models.
## Post #20
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-04-17T11:50:53+00:00
- Post Title: Re: [Request]Ratchet & Clank: Tools of Destruction

Was there any more work done on this? Everything looked pretty promising.
