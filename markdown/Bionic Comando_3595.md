## Post #1
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-19T19:54:42+00:00
- Post Title: Bionic Comando

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-19T20:28:48+00:00
- Post Title: Bionic Comando

it is just plain zlib let me know if it works on other files.

```
#Make sure you say yes when it asks to overwrite.
get CHUNKS long
get VERSION long
get NAME filename
set EXT string .ext
string NAME += EXT
append
for i = 0 < CHUNKS
get OFFSET long
get ZSIZE long
set SIZE 65536
clog NAME OFFSET ZSIZE SIZE
next i

```
## Post #3
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-19T20:55:47+00:00
- Post Title: Bionic Comando

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-19T21:38:18+00:00
- Post Title: Bionic Comando

those are the correct files you will get. what error do you get in the second file?
upload that one so i can see i want the original file.
## Post #5
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-20T09:59:10+00:00
- Post Title: Bionic Comando

well it's a 110mb file   

here's the error that i get 

> Error: the compressed zlib/deflate input is wrong or incomplete
## Post #6
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-07-20T16:52:50+00:00
- Post Title: Bionic Comando

How about to translate this game? How to determine which font file uses the game for non-English texts(language), for example there's also Russian, I couldn't determine which font file game uses for that.

p.s. languages and config files for game are in .bundle
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-20T19:08:25+00:00
- Post Title: Bionic Comando

I do not have this game and without the file there is no way i can determine what that error means
## Post #8
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2009-07-21T04:29:06+00:00
- Post Title: Bionic Comando

> Reply from Gocha
>
> How about to translate this game? How to determine which font file uses the game for non-English texts(language), for example there's also Russian, I couldn't determine which font file game uses for that.

p.s. languages and config files for game are in .bundle
That is a good idea.
I am searching those font files. If you know, tell me, please.
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-24T18:43:49+00:00
- Post Title: Bionic Comando

I tried the script with the file boot.fcl, but the game crashes
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-24T19:00:01+00:00
- Post Title: Bionic Comando

I do not have the game so I can not do more testing.
if I have that big archive I can update the script better.
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-25T01:38:58+00:00
- Post Title: Bionic Comando

How big can you download? I can upload 100mb's or more if you need
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-25T01:44:24+00:00
- Post Title: Bionic Comando

just give me a big archive that was giving errors I have unlimited download cap.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-25T07:11:48+00:00
- Post Title: Bionic Comando

Here is..3 big files:
[http://www.zshare.net/download/63127893c2d4cab1/](http://www.zshare.net/download/63127893c2d4cab1/)
and one small:
[http://www.zshare.net/download/631305585a0f0639/](http://www.zshare.net/download/631305585a0f0639/)
## Post #14
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-07-25T08:53:58+00:00
- Post Title: Bionic Comando

fcl files do not include any index information, the index data is stored in the game.LHD file
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-25T09:29:35+00:00
- Post Title: Bionic Comando

Look, the files are saved one after the other in these big files. Obviously, each last chunk of a resource is NOT 65536 in size. The BMS script assumes that this is just one big file, and incorrectly saves all chunks to one file. 

The archives start off with the number of resources, and then the chunksize for each zlib chunk (not 'version'). There is apparently a .LDH file that has the index (including filenames?). To get around it without an index, you should check whether the uncompressed piece returned by zlib.dll is 65536 in size, if not you have reached the end of the resource and should start another.
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-25T10:40:13+00:00
- Post Title: Re: Bionic Comando

Here is the lhd file:
[http://www.zshare.net/download/631350651ae9448b/](http://www.zshare.net/download/631350651ae9448b/) hope it helps
## Post #17
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-27T05:27:28+00:00
- Post Title: Re: Bionic Comando

[http://www.ghostrecon.net/files2/index. ... ror&id=323](http://www.ghostrecon.net/files2/index.php?act=mirror&id=323)

This utility will work with the .bundle files  (Also works for other titles with this engine, Terminator and Wanted for example.), quick.bundle holds most of the game data whereas the others are for sound and music files, have found quite a few interesting things in those archives (Developer remains, launch parameters like -s for the splash screen and -nointro plus remains of DX10 code to name some things.) but I'm pretty much a beginner at this sort of thing and the game doesn't really like to use the unpacked data (Can crash at times if you remove the .bundle file.), unsure what the fcl files use, seems to be for the game levels and some other things.
## Post #18
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-27T11:25:17+00:00
- Post Title: Re: Bionic Comando

The .bundle file is just a container, but the .fcl is compressed. The .fcl file contain (i think) only the data of levels.
But if you decompress the .fcl, and somehow unpack the files with own name and folder-tree, put this datas into the quick.bundle file, the game will use this files.
For example:
## Post #19
- Username: godinhochina
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 22, 2009 6:00 am
- Post datetime: 2009-08-09T21:18:17+00:00
- Post Title: Re: Bionic Comando

I managed to extract the file. Bundle of the game, but I am not getting replaced. 
So someone can help me replace the files that changed the game? 
I am wanting to translate this game for a site called GameVicio. 
Please help me. I hope you have understood my bad English
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-08-10T07:09:50+00:00
- Post Title: Re: Bionic Comando

I'm translating the game too. I have all source to translating. Just give me an e-mail address in PM, and I sent you all source.
But you have to work with DDS images! I hope this is not problem. And the texts is in XML format.
## Post #21
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-11T14:12:51+00:00
- Post Title: Re: Bionic Comando

Anyone managed to decompile the LUC files?
It appears to be a custom LUA 5.1.2 code, so the generic decompilers do not work.
## Post #22
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-08-12T15:11:05+00:00
- Post Title: Re: Bionic Comando

Just wanted to tell the news the GRIN that has made bionic commando and terminator salvation just filed for bankruptcy. It's a shame that game companies now have a hard time in the economic  crisis
## Post #23
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-12T19:10:15+00:00
- Post Title: Re: Bionic Comando

> Reply from pixellegolas
>
> Just wanted to tell the news the GRIN that has made bionic commando and terminator salvation just filed for bankruptcy. It's a shame that game companies now have a hard time in the economic  crisis
This is off-topic, but I have to say my piece.
Just take a look around. All games being still played one year after their release are moddable - to some extent.
The games Grin made are nice (I personally liked them), but they are not mod-friendly at all. You play them once, and leave them alone. They are not worth the money because the replay value is extremely low. This is the kind of game that you don't buy, you just borrow it from a friend of yours (or, borrow his account in case of Steam).
I guess they have learnt a lesson here - nowadays a game without modding capability won't survive; being pretty-looking (HD gaming) is just not enough on today's market. I only wish they'll remember this lesson well. I would go as far and say that HD is not even necessary as long as the game has a good, mod-friendly engine and a good storyline with good controls, camera and general gameplay. Modders will bring the added value later on - provided their job is relatively painless.
There, I said my piece.
## Post #24
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-08-12T20:29:18+00:00
- Post Title: Re: Bionic Comando

This engine is moddable or was. This (of course older) Diesel engine run under GRAW1-2.
Maybe the new GRAW will be much better, of course if then the GRIN is exist and they make the game.
## Post #25
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-12T22:44:39+00:00
- Post Title: Re: Bionic Comando

> Reply from evin
>
> This engine is moddable or was. This (of course older) Diesel engine run under GRAW1-2.
Maybe the new GRAW will be much better, of course if then the GRIN is exist and they make the game.
The GRAW modding tools do not work; they have changed the file formats slightly.
The ones that work are new, you can find them here:
[http://www.bioniccommando.com/app/webro ... hp?p=17038](http://www.bioniccommando.com/app/webroot/forum/showthread.php?p=17038)
I attached these for backup purposes.
[MODTOOLS.ZIP](https://xentaxbackup.github.io/file/2274_MODTOOLS.ZIP)
## Post #26
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-08-13T07:21:56+00:00
- Post Title: Re: Bionic Comando

I know, this is not so moddable as the GRAW (graw1-2 official modtool exist, but BC modtools not), but as you see in my earlier post the image, it' posible. I'm not touched to any bundle file, but still working. I know that the GRAW is more mod-friendlier as this. Also truth, that I don't care the 3D, XMB etc files, just the texts and textures. I make translation, not levels, weapons etc.
## Post #27
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-13T12:47:51+00:00
- Post Title: Re: Bionic Comando

> Reply from evin
>
> I know, this is not so moddable as the GRAW (graw1-2 official modtool exist, but BC modtools not), but as you see in my earlier post the image, it' posible. I'm not touched to any bundle file, but still working. I know that the GRAW is more mod-friendlier as this. Also truth, that I don't care the 3D, XMB etc files, just the texts and textures. I make translation, not levels, weapons etc.
I am interested in the internal mechanics - which usually means the scripts describing behaviour of objects, AI, etc. So, until a LUA decompiler has been created, I can't do pretty much anything...
## Post #28
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-08-13T13:23:27+00:00
- Post Title: Re: Bionic Comando

Earlier I tried to find LUA decompiler, to an other game (maybe lua 5.1.3), but only the 5.0 supported. 
And that was 1year ago! And still nothing new.
## Post #29
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-13T16:26:52+00:00
- Post Title: Re: Bionic Comando

> Reply from evin
>
> Earlier I tried to find LUA decompiler, to an other game (maybe lua 5.1.3), but only the 5.0 supported. 
And that was 1year ago! And still nothing new.
There is a LUA 5.1 decompiler available, but Grin's games deems to be using a custom 5.1.2 LUA, so the generic decompiler does not work.
## Post #30
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-13T22:09:47+00:00
- Post Title: Re: Bionic Comando

I tried the tool with W7 but don't works
## Post #31
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-08-31T07:23:45+00:00
- Post Title: Re: Bionic Comando

This is coordinats for characters on the font map


 bcfont_cyr_22.rar
(2.56 KiB) Downloaded 69 times



Question is how to explore
## Post #32
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2012-10-03T19:38:25+00:00
- Post Title: Re: Bionic Comando

the diesel engine can be modified using the content of the .fcl files 

we can change the type of the models (character by objects) , delete the AI from any stage



1.- decompress the quick.bundle file with the bundleReader.exe file and put the folders in the root folder of the game



2.- rename the executable to bc_win32_release.exe and delete the extension of the file quick.bundle (delete the "bundle" name to terminate the access of the game at the file)

the startup folder content some .bat files for execute some commands and deletes stages stages 

for example: Sandbox




Profiling:   ( for access to this stage edit the sandbox.bat or create a new bat file)



this is he bat file for the stages in the startup folder



Delete the Sandbox name for any unseen stage for the name folder (the names marked in red are the unseen stages)

- the stages are in the compiled\win32\data\levels folders



........... for access to a current mission without AI enter to the folder of the mision for example "city_a" or "vault" , copy the file world.xmb and paste in sandbox folder (back up the previous file)

........... some unseen stages not work.....simple , copy the world.xmb file and paste in the sandbox folder (character_previz)



for change the character models or objects in the Character_previz or other stage:

open the world.xmb with any text viewer... search "unit" and check the file names...



I edit the mag_cutscene_previz file .....the unit files can be found in db/unit folders



go to "m" folder



and open the file "mag_cutscene_previz.xml" this file content this:

```
    <model file="mag_cutscene"/>
    <extension name="unit_data" class="ScriptUnitData"/>
</unit>
```


in the <model file= ... /> line put any model with the .diesel extension, you can obtain the names from the game.lhd file in the bundles folder for example:



remember some missions don't work in direct form but but the world.xmb in the sandbox folder and execute the sandbox.bat (character_previz work with this method)

thanks to this method I obtain a unseen character.

the bioreign pilot.



Download model: [http://www.mediafire.com/?qoz3duxtw4ra88w](http://www.mediafire.com/?qoz3duxtw4ra88w)

this method work with any game with the diesel engine.

I hope I have been clear ,sorry if are there errors.
## Post #33
- Username: rayanm123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2022 10:35 am
- Post datetime: 2023-03-27T20:40:58+00:00
- Post Title: Re: Bionic Comando

Anything about the blb files for the font ?
