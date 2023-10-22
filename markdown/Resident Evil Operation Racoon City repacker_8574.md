## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-17T09:58:15+00:00
- Post Title: Resident Evil Operation Racoon City repacker

Hello,

Can anyone please help me with this? Does not look as complicated format...

```
http://dl.dropbox.com/u/38234344/Resident%20Evil%20Operation%20Raccoon%20City%20_Text_Fotns.rar
```


thank you
## Post #2
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-17T16:50:44+00:00
- Post Title: Resident Evil Operation Racoon City repacker

I couldn't find the dialogs subtitles in those files you uploaded. 
Can you search it? The files you sent seems to be the menus
and sytem/objective texts.

I'll wait!
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-17T18:46:29+00:00
- Post Title: Resident Evil Operation Racoon City repacker

I did that seems all text files in the game
## Post #4
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-17T20:13:05+00:00
- Post Title: Resident Evil Operation Racoon City repacker

> Reply from michalss
>
> I did that seems all text files in the game
Then, check it another time.
I saw some videos on youtube, got the subtitles and search in the
files you sent (hex editor). Nothing found.
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-18T00:57:15+00:00
- Post Title: Resident Evil Operation Racoon City repacker

FFS the subtitles are in

/TEXT/
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-18T11:47:35+00:00
- Post Title: Resident Evil Operation Racoon City repacker

yes i know all files are in my first post!
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-18T11:52:44+00:00
- Post Title: Resident Evil Operation Racoon City repacker

I tried to write a extractor yesterday but it didn't work out. I hope the PS3 version will be of more use.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-18T12:05:30+00:00
- Post Title: Resident Evil Operation Racoon City repacker

> Reply from C00L12345
>
> I tried to write a extractor yesterday but it didn't work out. I hope the PS3 version will be of more use.

All platforms seem to be the same.
## Post #9
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-18T13:30:03+00:00
- Post Title: Resident Evil Operation Racoon City repacker

> Reply from michalss
>
> C00L12345 wrote:I tried to write a extractor yesterday but it didn't work out. I hope the PS3 version will be of more use.

All platforms seem to be the same.They're not actually.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-18T20:39:36+00:00
- Post Title: Resident Evil Operation Racoon City repacker

SSG extraction with Noesis.

EDIT: This script wasn't accounting for frame resets in the LZX stream, use the new one here instead: [viewtopic.php?f=10&t=8574&start=15#p69940](http://forum.xentax.com/viewtopic.php?f=10&t=8574&start=15#p69940)

If you want to write a repacker from the spec outlined here it should be trivial. Just use a compressed size of 0 and you don't have to compress any of your repacked data.
## Post #11
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-18T21:51:56+00:00
- Post Title: Resident Evil Operation Racoon City repacker

Sorry for my n00bness, but WTF is noesis, and how to use this script?
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-18T22:07:45+00:00
- Post Title: Resident Evil Operation Racoon City repacker

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

Copy text from post, paste into notepad.exe, save it as a file called fmt_ssg_reorc.py in your Noesis\plugins\python directory. (after extracting Noesis of course) Load Noesis, browse to ssg file, double click it, say "Yes", hit "OK" to export with default settings/path, and there you go.
## Post #13
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-03-18T22:20:21+00:00
- Post Title: Resident Evil Operation Racoon City repacker

Thank you.
I worked here, but not like i've expected.
Only a new binary files were extracted, but not the texts (not the pure texts).
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-19T01:07:02+00:00
- Post Title: Resident Evil Operation Racoon City repacker

The PS3 files don't work with the Xbox script of course
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-19T01:08:23+00:00
- Post Title: Resident Evil Operation Racoon City repacker

the ps3 files are either 
a) encrypted after they were compressed
or
b) using a new unknown compression most likely found in the ps3 edge sdk
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-19T05:45:23+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

i gave up with this game. Its not worth to localizate this game at all  It is not Resident Evil anymore i would call it Gears of Evil
## Post #17
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-19T08:05:09+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from chrrox
>
> the ps3 files are either 
a) encrypted after they were compressed
or
b) using a new unknown compression most likely found in the ps3 edge sdk
Thanks i have one of the latest SDKs

It seems that the PS3 textures are GTF "swizzled" or whatever.

I've tried to use GTF2DDS in the SDK and it's not working on these files the header which comes out doesn't even have a DXT version. It did however work on one file but that file already looked like a standard DDS file through hex editor. I'm not sure what's wrong with the textures.

The .XTF for Xbox, doesn't look like those can be unpacked either.

Has anyone looked at the models yet?
## Post #18
- Username: kostasishere
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-19T09:34:16+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Some of the files with XPR extensions in the 360 version are really XPR2 files and others aren't XPR files at all, they're just raw DXT data and the actual image info seems to be in the material file(s) that reference them. On 360 most texture data is tiled as usual. You can view the headerless data with this script, just replace w/h/fmt with the right values. (or you could make it guess from the file size and be right most of the time)

```

def registerNoesisTypes():
	handle = noesis.register("Hackity Hack Hack", ".xpr")
	noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
	noesis.setHandlerLoadRGBA(handle, hackLoadRGBA)
	return 1

def hackLoadRGBA(data, texList):
	w = 256
	h = 256
	fmt = noesis.NOESISTEX_DXT5
	data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), w, h, 8 if fmt == noesis.NOESISTEX_DXT1 else 16)
	texList.append(NoeTexture("hacktex", w, h, data, fmt))
	return 1
```

I think chrrox has the model format pretty much figured out.
## Post #19
- Username: kostasishere
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Mar 20, 2012 10:00 am
- Post datetime: 2012-03-20T02:27:30+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Thanks a lot for the Noesis program!!!
Is it possible to repack the extracted files?
## Post #20
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-03-22T11:14:14+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Somebody works on RE ORC script?
Here's Nemesis model:
[http://www.sendspace.com/file/cedkqd](http://www.sendspace.com/file/cedkqd)
## Post #21
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2012-03-22T15:33:32+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from Kamillho
>
> Somebody works on RE ORC script?
Here's Nemesis model:
http://www.sendspace.com/file/cedkqd
 

[viewforum.php?f=16](http://forum.xentax.com/viewforum.php?f=16)
## Post #22
- Username: greywaste
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-25T02:37:32+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

It turns out that the lzx stream is set to reset every 2 frames, and the old script wasn't doing that, so even though it succeeded in putting out readable data a lot of it was corrupted.

Update to the latest Noesis and use this script instead or all of your data will be screwed and chrrox's model script will not work right or crash on most of the models.

```

def registerNoesisTypes():
	handle = noesis.register("RE:ORC archive", ".ssg")
	noesis.setHandlerExtractArc(handle, ssgExtractArc)
	return 1

def ssgExtractArc(fileName, fileLen, justChecking):
	if fileLen < 32:
		return 0
	with open(fileName, "rb") as f:
		endr = ">"
		idRaw = f.read(4);
		id = noeUnpack(endr+"i", idRaw)[0]
		if id != 6 and id != 5:
			endr = "<"
			id = noeUnpack(endr+"i", idRaw)[0]
			if id != 6 and id != 5:
				return 0

		unk = noeUnpack(endr+"i", f.read(4))[0]
		fofsSize = noeUnpack(endr+"i", f.read(4))[0]
		namesSize = noeUnpack(endr+"i", f.read(4))[0]
		dataSize = noeUnpack(endr+"i", f.read(4))[0]
		unk2 = noeUnpack(endr+"i", f.read(4))[0]
		fnInfoSize = noeUnpack(endr+"i", f.read(4))[0]
		decompDataSize = noeUnpack(endr+"i", f.read(4))[0] #just a guess
		if fofsSize <= 0 or fofsSize >= fileLen or namesSize <= 0 or namesSize >= fileLen or dataSize <= 0 or dataSize >= fileLen or fofsSize+namesSize+dataSize+unk2+fnInfoSize >= fileLen:
			return 0

		if justChecking:
			return 1

		if noesis.getAPIVersion() < 34:
			print("ERROR: This script is not compatible with your version of Noesis! UPGRADE!")
			return 0

		fofsOfs = f.tell()
		numFiles = fofsSize // 32
		fofsData = f.read(fofsSize)
		fnInfoOfs = f.tell()
		fnInfoData = f.read(fnInfoSize)
		namesOfs = f.tell()
		namesData = f.read(namesSize)
		dataOfs = f.tell()
		bsNames = NoeBitStream(namesData)

		fdataRead = 0 #hack
		f.seek(fofsOfs, 0)
		for i in range(0, numFiles):
			f.seek(4, 1)
			fnOfs = noeUnpack(endr+"i", f.read(4))[0]
			decmpSize = noeUnpack(endr+"i", f.read(4))[0]
			unkFl = noeUnpack(endr+"i", f.read(4))[0]
			fileOfs = noeUnpack(endr+"i", f.read(4))[0]
			fileExt = f.read(4)
			f.seek(4, 1)
			cmpSize = noeUnpack(endr+"i", f.read(4))[0]
			bsNames.seek(fnOfs, NOESEEK_ABS)
			fileName = bsNames.readString()
			if cmpSize < 0: #seems to indicate that the file is in a different archive
				#print("Skipping", fileName, "- file is in another archive.")
				continue
			#print(fileName, dataOfs+fdataRead, cmpSize, decmpSize)
			tmp = f.tell()
			f.seek(dataOfs+fdataRead, 0)
			if cmpSize == 0: #not compressed
				decompData = f.read(decmpSize)
				fdataRead += decmpSize
			else:
				fileData = f.read(cmpSize)
				decompData = rapi.decompXMemLZX(fileData, decmpSize, 16, -3)
				fdataRead += cmpSize
			f.seek(tmp, 0)
			print("Writing", fileName)
			rapi.exportArchiveFile(fileName, decompData)

	return 1

```
## Post #23
- Username: kostasishere
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Mar 20, 2012 10:00 am
- Post datetime: 2012-03-26T01:35:17+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

MrAdults is it possible to repack them again as ssg because than it's possible to swap the playable characters with another or for some skin mods.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-26T11:13:36+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

the game will read uncompressed models just re create the archive with uncompressed files. you can also try just putting the files in the correct spot the game may just read them.
## Post #25
- Username: kostasishere
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Mar 20, 2012 10:00 am
- Post datetime: 2012-03-26T12:48:35+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Thanks a lot for the help but unfortunally it doesn't work, i tried that and i created many subfolders with different names and in different locations but it doesn't find the model at all and i see only the weapon in game, not the character. I also tried to edit the .ssg file with notepad++ and a hex editor and rename the folder and model name with a different playable character (Hunk for Vector for ex) so i can swap the files but it corrupt the file and i cant even open open it with Noesis.
## Post #26
- Username: soroosh
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 11, 2011 12:48 pm
- Post datetime: 2012-03-30T12:40:22+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

MrAdults, let me thank you sooooooooooooo much for your ssg extraction and image viewing scripts.
I have some questions.

1- I think it would be alot better to write the ssg extraction script in bms because it can handle batch extraction and also I think the noesis is an image and model viewer not a programming tool for extracting archives - I know that it has the abilities to be used that way. So, my suggestion : if it's possible for u dear friend, write a bms script for batch ssg extraction.

2- Is it possible to change the extraction script to make it convert raw DXT images to readable dds on the fly?

thanks man  .
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-30T21:36:04+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

1) QuickBMS to my knowledge doesn't support the LZX features necessary for these files to extract correctly. Otherwise, feel free to write the BMS script, you already have the specs in the Python script. I personally don't give a shit. Also, Noesis has batch extraction and has a commandline mode. Read the documentation.

2) Sure, feel free. Or wait for chrrox to finish his script that draws in the correct headers. Unless he isn't doing that, then you're out of luck, cause again I don't give a shit. I doubt you indirectly insulting chrrox and calling him lazy makes him want to work any faster either. But maybe you're cognitively limited and you can't help it, in which case, I recommend not posting.
## Post #28
- Username: soroosh
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 11, 2011 12:48 pm
- Post datetime: 2012-03-31T04:44:55+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from MrAdults
>
> 1) QuickBMS to my knowledge doesn't support the LZX features necessary for these files to extract correctly. Otherwise, feel free to write the BMS script, you already have the specs in the Python script. I personally don't give a shit. Also, Noesis has batch extraction and has a commandline mode. Read the documentation.

2) Sure, feel free. Or wait for chrrox to finish his script that draws in the correct headers. Unless he isn't doing that, then you're out of luck, cause again I don't give a shit. I doubt you indirectly insulting chrrox and calling him lazy makes him want to work any faster either. But maybe you're cognitively limited and you can't help it, in which case, I recommend not posting.
Wow!!! I think that I started my questions by thanks didn't I?
So, what is this " I don't give a shit"!!!!! is it kind of speaking you use to call your family? Because of your kind of speaking it's obvious that who is cognitively limited to just shitttttt  . 
How dare you to speak like this in a common form? If I had enough time to spend on studing BMS documents OR noesis coding, Be sure I wouldn't even send a shit to guys like you   . So, don't try to make me mad by your shitty kind of talking baby. Instead better to learn how to apprecitae when the others thank you for your shitty stuff.
although I don't expect guys like you learn how to be polite and how to behave in a common society.
## Post #29
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T08:21:29+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Sorry, I'm just Dutch at heart.
## Post #30
- Username: soroosh
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 11, 2011 12:48 pm
- Post datetime: 2012-03-31T08:23:48+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from MrAdults
>
> Sorry, I'm just Dutch at heart.
Be my guest dear friend  .
## Post #31
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T08:31:34+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from soroosh
>
> MrAdults wrote:Sorry, I'm just Dutch at heart.
Be my guest dear friend  .
Thanks, I appreciate it! Then, with your permission... you strike me as a semi-manipulative tool who pesters others and throws fusses to get his own way when the tides turn against him, in lieu of the ability to contribute anything healthy or meaningful to any given community. Your posts will not expedite the arrival of the scripts and/or tools you desire, and having had decades to observe and predict people just like you, I find your very presence offensive.*

Again, thanks for that.

*Any information, statements or opinions contained in this post are those of the individual speaker. They do not represent the opinions of XeNTaX,  Moderation/Administration staff, or small flightless men.
## Post #32
- Username: soroosh
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 11, 2011 12:48 pm
- Post datetime: 2012-03-31T08:58:49+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from MrAdults
>
> soroosh wrote:MrAdults wrote:Sorry, I'm just Dutch at heart.
Be my guest dear friend  .
Thanks, I appreciate it! Then, with your permission... you strike me as a semi-manipulative tool who pesters others and throws fusses to get his own way when the tides turn against him, in lieu of the ability to contribute anything healthy or meaningful to any given community. Your posts will not expedite the arrival of the scripts and/or tools you desire, and having had decades to observe and predict people just like you, I find your very presence offensive.*

Again, thanks for that.

*Any information, statements or opinions contained in this post are those of the individual speaker. They do not represent the opinions of XeNTaX,  Moderation/Administration staff, or small flightless men.
Believe me man. I know how to behave in a virtual community like this and anything I have just done was to motivate the guys like chrrox to complete their favours and not just leaving it out like many others who have been dissapointed in the middles of the way. So again I want to tell u that my presence is not offensive and harmfull to anyone and this kind community. You must learn not to judge the others by just reading a few of their posts baby  . When the time passes and u know me more, you'll find out that u were wrong. Just lets not judge each other by reading a few posts    .
Thanks for your "having had decades to observe and predict people just like you, I find your very presence offensive"  BEHAVIOUR PREDICTOR    .
## Post #33
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T09:06:16+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

That's more like it, bro!    However, no one actually needs you to pester them for motivation, most especially chrrox and myself. Keep that in mind and I won't find the appeal of eating your face so overwhelming.
## Post #34
- Username: soroosh
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 11, 2011 12:48 pm
- Post datetime: 2012-03-31T09:20:09+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

> Reply from MrAdults
>
> That's more like it, bro!    However, no one actually needs you to pester them for motivation, most especially chrrox and myself. Keep that in mind and I won't find the appeal of eating your face so overwhelming.
Any way. Whether u like it or not I'll do what I like to do and cause I didn't know u and your beloved friend chroox  , I thought my joke will not just harm you OR make u sad. If it did, I ask u to forgive me to be motivative. Like u said, lets just not interfere with each others stuff and preserve the boundries of politeness and not to use the rude words like you used to bother me baby (specially in a common society like this one). And cause u liked it let me finish this pointless coversastion by just saying   . Just remember not to bother me OR the others again when you don't know their actual desires and please DO NOT use your behaviour prediction abilites for this.    .
## Post #35
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T09:24:22+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

You're the one that got your little panties in a bundle when I said I didn't give a shit. And I don't. I don't care about RE:ORC in the slightest, I find it to be a terrible game, and have absolutely no interest in its formats or resources. I just made a SSG script because chrrox asked me to, and made a hack to view the raw DXT data to verify that the decompression was functional. Also, you're showing your semi-manipulative properties again.

Edit: Congratulations to soroosh for being my very first ban, by going completely above and beyond my expectations.
## Post #36
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-04-08T12:10:48+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Mr Adults I used your script to extract level data but it just wouldn't extract the models. it seems that something is wrong with the stage models in your script because the script just extracts the first model of each stage and skips the rest of the models and sucessfully extracts the whole textures. would u please tell me what the problem is and how it can be fixed?
## Post #37
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-04-10T13:23:56+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Is this topic closed? why you guys don't respond? If it's closed please let me know.
## Post #38
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-04-16T19:52:21+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

hey guys i just wanted to know is there a repacker for ssg files ?
## Post #39
- Username: kostasishere
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Mar 20, 2012 10:00 am
- Post datetime: 2012-04-17T08:13:54+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

Unfortunately no, you can only unpack them.
## Post #40
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-28T21:43:09+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker

kk the only reason i ask is because someone made a iso mod with modded ssg's
## Post #41
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-08-14T19:53:37+00:00
- Post Title: Re: Resident Evil Operation Racoon City repacker


