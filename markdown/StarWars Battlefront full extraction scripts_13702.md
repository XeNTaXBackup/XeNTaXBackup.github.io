## Post #1
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-18T20:25:23+00:00
- Post Title: StarWars Battlefront full extraction scripts

This script will extract all of the data/files from SWBF. Including the Patch and Update(xpack) data. There is still work to do on it. I eventually plan on it being able to get more data/files, like unpacking the initfs_Win32 and some other fun stuff.

Everything should be compatible with Daemon1's tools([https://forum.xentax.com/viewtopic.php?f=10&t=13584](https://forum.xentax.com/viewtopic.php?f=10&t=13584)). The FB3decoder is included in the rar file. 

I'm posting this here instead of an existing thread so you guys can let me know if anything isn't working and keep a change log as I update it. 

If you are looking to get just the EBX data you can comment out the marked section(line 207-251)

SWBF Extraction Scripts v1:
[https://mega.nz/#!ml53iTzS!Bt5j_dJ03IHk ... nKmdO9GVcM](https://mega.nz/#!ml53iTzS!Bt5j_dJ03IHk-GNt6ZE27cKySzGdWO4XFnKmdO9GVcM)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-19T10:40:17+00:00
- Post Title: StarWars Battlefront full extraction scripts

Again I recommend using my XAS decoder, because Frank's dll makes 32-bit WAV files, and you will get, say, 40GB of wavs instead of 20GB, and that's 20GB of useless data.
## Post #3
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-19T15:04:17+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from daemon1
>
> Again I recommend using my XAS decoder, because Frank's dll makes 32-bit WAV files, and you will get, say, 40GB of wavs instead of 20GB, and that's 20GB of useless data.

I saw some differences in the fb3decode.py and such but were not sure what they were. I know little about the difference between XAS output vs 32-bit wave output. If it can save that much room and not lose any quality, the multi channels and all that I can't recommend using your XAS decoder enough. It also looks your tool can target audio from specific ebx?  

I may just remove the fb3decoder from the rar. When writing this script res files, and chunks were all secondary to EBX files, patched versions of files, and making sure none of that slips through the cracks because at Symthic.com that is really what we are interested in.
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-20T03:10:44+00:00
- Post Title: StarWars Battlefront full extraction scripts

[out]
## Post #5
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-20T22:24:02+00:00
- Post Title: StarWars Battlefront full extraction scripts

You guys messed up the mesh format and switched it to meshset and now the chunk and mesh tool will not work with the files.

I'm in the process of trying to edit it, but why did you guys just not leave it to .mesh?

EDIT: Here is the updated mesh and chunk tool, i updated it to support the .meshset so if you use meshset this should work just fine with all other frostbite games that are listed on the program.

I also changed a few things on it,gave it a icon and a rename cause i never understood why it was named BF3 after it started getting more games added to the program so it's now named Frostbite mesh and chunk tool.

[http://www.mediafire.com/download/6orou ... Reader.rar](http://www.mediafire.com/download/6orou8dqq4uncdb/Frostbite_MeshFile_Type_Reader.rar)
## Post #6
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-21T04:28:30+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from JakeGreen
>
> You guys messed up the mesh format and switched it to meshset and now the chunk and mesh tool will not work with the files.

I'm in the process of trying to edit it, but why did you guys just not leave it to .mesh?

EDIT: Here is the updated mesh and chunk tool, i updated it to support the .meshset so if you this works just fine with all other frostbite games that are listed on the program.

I also changed a few things on it,gave it a icon and a rename cause i never understood why it was named BF3 after it started getting more games added to the program so it's now named Frostbite mesh and chunk tool.

http://www.mediafire.com/download/6orou ... Reader.rar

That was my bad, I don't really mess around with meshs or the mesh tool all that often and didn't even think about the mesh restype.  So yeah, its not like there was decision or something to change it to MeshSet . I just have my res list match what ever he is using because I use his tools too and figure most people do. However, I can't say I ever extracted and rigged up a mesh. 


That is awesome that you updated the mesh tool. I've had to do that in the past for textures while its not the hardest thing in the world, damn it can be tedious. I was just gonna fix the script real fast and upload it again but now that you've made this I think I'm just gonna make note of it in the op and remind people to check what tool they are using and the res list. 

Thank you for letting me know it was set wrong. If you notice anything else wrong with the script, let me know. That or have and suggestions or ideas on what else I can have the script do.
## Post #7
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-21T04:31:54+00:00
- Post Title: StarWars Battlefront full extraction scripts

Ah alright no problem.

I'm still having problems with some of the textures mainly the head and hair i can't figure out the hex value for their format does anyone know it?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-21T15:34:51+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from JakeGreen
>
> Ah alright no problem.

I'm still having problems with some of the textures mainly the head and hair i can't figure out the hex value for their format does anyone know it?

Can you send examples?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-21T15:37:30+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from elementofprgress
>
> I saw some differences in the fb3decode.py and such but were not sure what they were. I know little about the difference between XAS output vs 32-bit wave output. If it can save that much room and not lose any quality, the multi channels and all that I can't recommend using your XAS decoder enough. It also looks your tool can target audio from specific ebx?

My tool is a generic XAS decoder. And it supports multichannel too. I'm just running it from fb3decode.py with parameters, such as file name, offset, etc, just like it was with Frank's XAS.dll.

But in case of 4-bit ADPCM files (which XAS actually is) it is a waste of space making 32-bit WAVs of them.
## Post #10
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-22T01:32:24+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from daemon1
>
> JakeGreen wrote:Ah alright no problem.

I'm still having problems with some of the textures mainly the head and hair i can't figure out the hex value for their format does anyone know it?

Can you send examples?

Here you go [http://www.mediafire.com/download/uv77m ... exture.rar](http://www.mediafire.com/download/uv77m2t43mns12s/head_texture.rar)
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-22T15:43:46+00:00
- Post Title: StarWars Battlefront full extraction scripts

The format is right. The problem is in chunk extraction or maybe something else is wrong.

This is your t_heads_leia_cs texture:



It is 256x256, and the header says it is 2048x2048 (what i think its supposed to be). But in this case the file must be 2Mbytes, not 86k like you send me.

Same with teeth & eyes, they are 128x128 instead of 256x256

What did you use to dump these files? Can you send me the corresponding .texture files?
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-22T18:08:02+00:00
- Post Title: StarWars Battlefront full extraction scripts

I used the scripts on here to re-extract everything that I had extracted with your scripts but after I got everything extracted again I used your edited batch texture converter to get all the textures. When I get home from work later I'll get you the .texture files.
## Post #13
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-23T10:54:37+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from daemon1
>
> The format is right. The problem is in chunk extraction or maybe something else is wrong.

This is your t_heads_leia_cs texture:



It is 256x256, and the header says it is 2048x2048 (what i think its supposed to be). But in this case the file must be 2Mbytes, not 86k like you send me.

Same with teeth & eyes, they are 128x128 instead of 256x256

What did you use to dump these files? Can you send me the corresponding .texture files?

This is the issue I had when trying to get at textures during the beta.(with an eye texture IIRC) It makes me think that the chunk is a mipmap of the full sized texture, just as a texture itself. Instead of generated?? don't know, is that how they work or could work? and that the full size texture is in another chunk somewhere.

or chunks with certain res meta data might need to be combined in some way. IDK i'm taking total shots in the dark.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-23T16:56:06+00:00
- Post Title: StarWars Battlefront full extraction scripts

I just made a check with .res files extracted with my version of Franks's scripts

I took the mentioned t_eyes_black_c .texture file, and found that is points to only one chunk 75kb in size, that is the proper size. Not the 22k extracted with your script. I don't know what is wrong with your script, but something's definitely wrong. Maybe something's got messed after all the updates, I don't have them, but people still have teeth in the game, right?

So I'd recommend JakeGreen to re-extract everything back with my script and check if all textures are ok.

p.s. Also checked Leia's head, and its texture chunk is also 2,5MB as expected.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-23T20:36:42+00:00
- Post Title: StarWars Battlefront full extraction scripts

> Reply from elementofprgress
>
> It makes me think that the chunk is a mipmap of the full sized texture, just as a texture itself. Instead of generated?? don't know, is that how they work or could work? and that the full size texture is in another chunk somewhere.

That makes me think that maybe its time to give me all of the game files, or at least one full CAS folder. So I can finally see whats happening there.
## Post #16
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-23T21:27:48+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from daemon1
>
> I just made a check with .res files extracted with my version of Franks's scripts

I took the mentioned t_eyes_black_c .texture file, and found that is points to only one chunk 75kb in size, that is the proper size. Not the 22k extracted with your script. I don't know what is wrong with your script, but something's definitely wrong. Maybe something's got messed after all the updates, I don't have them, but people still have teeth in the game, right?

So I'd recommend JakeGreen to re-extract everything back with my script and check if all textures are ok.

p.s. Also checked Leia's head, and its texture chunk is also 2,5MB as expected.

Hm alright well i really only extracted everything from his script to get the jakku stuff and i got it so i'll re-extract everything with your scripts and use both tools on it again to get textures and mesh and chunks together.

Question though when i used his script it extracted 2 chunk folder 1 in the main extracted folder and the other in bundles, does that make a difference if your tool daemon1 doesn't do that?

Also here is the .texture files [http://www.mediafire.com/download/hnp34 ... exture.rar](http://www.mediafire.com/download/hnp34lku4tszbz1/SWBFtexture.rar) if you still want them.
## Post #17
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-24T01:08:31+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from JakeGreen
>
> daemon1 wrote:I just made a check with .res files extracted with my version of Franks's scripts

I took the mentioned t_eyes_black_c .texture file, and found that is points to only one chunk 75kb in size, that is the proper size. Not the 22k extracted with your script. I don't know what is wrong with your script, but something's definitely wrong. Maybe something's got messed after all the updates, I don't have them, but people still have teeth in the game, right?

So I'd recommend JakeGreen to re-extract everything back with my script and check if all textures are ok.

p.s. Also checked Leia's head, and its texture chunk is also 2,5MB as expected.

Hm alright well i really only extracted everything from his script to get the jakku stuff and i got it so i'll re-extract everything with your scripts and use both tools on it again to get textures and mesh and chunks together.

Question though when i used his script it extracted 2 chunk folder 1 in the main extracted folder and the other in bundles, does that make a difference if your tool daemon1 doesn't do that?

Also here is the .texture files http://www.mediafire.com/download/hnp34 ... exture.rar if you still want them.

Chunks in the dump/bundles/chunks come from bundles. Chunks in the  dump/chunk fold come from toc file. They have potentially different extraction methods/compression. His scripts do them separately but changed the output path to put it all in one IIRC. It makes it a little easier to use the texture tool. ie. you don't  have to run it twice, once for each chunk folder.

Wither it makes a difference or not....maybe? probably not.  The biggest difference is that the script might be a handling one better then the other. So, until it I can be sure it is definitely safer this way/easier to debug.
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-12-24T11:47:45+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

[out]
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-24T16:03:45+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from JakeGreen
>
> Question though when i used his script it extracted 2 chunk folder 1 in the main extracted folder and the other in bundles, does that make a difference if your tool daemon1 doesn't do that?

We'll know that soon.

The .texture files you sent are identical to the ones that I have. And they point to the same one chunk of a size about 2,5MB. So can you make one more check?

What is the size of chunk named 3262F9062141B23CE99A71E19FAA2771.chunk ?

Do you have one of these or two in different folders?
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-24T16:12:10+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from elementofprgress
>
> His scripts do them separately but changed the output path to put it all in one IIRC

I believe that chunk IDs must be unique. So there's no need to extract 2 folders, as it will only lead to lots of duplicates. At least that's how it was in games I extracted before. I actually compared the contents of chunks in both folders and they were always identical.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-26T13:04:04+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

The first check shows that after extraction with my script, Leia's face gives me proper 2048x2048 texture 2,5MB in size. Now time to find out why this script works wrong.
## Post #22
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-26T13:50:09+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from daemon1
>
> The first check shows that after extraction with my script, Leia's face gives me proper 2048x2048 texture 2,5MB in size. Now time to find out why this script works wrong.

it is the decompression failing. The 43 kb byte chunk. its entry.logicalsize is 43704...43kb -.-


okay, so its goes to writepayload. 
trys casPatchedPayload
fails no deltasha1
except to casPayload
...which once there it has all the required entries but fails...
hmmmm


damn this game. Okay, so SWBF is kinda....a modular install. We'll i doubt we will actually ever get that option however it is whats going on. Each file is part of 3 groups(4 now with Jakku) and only one is needed to load the game. You can actually remove most the files, unplug your internet and start SWBF. or just have the files for SP and I'm assuming co-op. This mean every file is assigned a cas/cat. I originally wrote the script in that manor but ditched it shortly before I started cleaning it up to share it.  It was just real messy and cluttered and a pain to go through the script because you couldn't tell what was going on with 6 cat dictionaries and a ton of different defined dumps and it really slowed down the performance of the script. So I tossed the idea in favor of one cat dict like the old script because it work, got the job done and was faster. However it looks like I'm going to have to go back to that build of my scripts because it is exactly what is causing this chunk issue and who knows what else that we just haven't run into yet.

What is going on is this. Both patch and unpatch Characters.toc want the entry with 87efb62023497402a4aa5e61e7422ee0c73254eb for a SHA1. Char is in the group of inital experience. So it needs to go to that cas/cat and get the entry. However, every map/gamemode/bundle however you break it all down including the texture of Leia's face and they want it from the cas/cat they are part of.  [http://pastebin.com/zJH7yVF9](http://pastebin.com/zJH7yVF9) They all want one with an entry of 39667 bytes. And that 39667 bytes decompresses into our 43kb wtf chunk file. 

It should be noted, it isn't like the file can't be extracted via any of the cas cats it tries to get it from. rangeEnd-RangeStart=the size of the other cas entry(39667) and plenty of other stuff like that but I just can't recall what values it would need or the compression method.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-27T12:59:15+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

Well, at least now I'm sure that texture tool works ok and all the formats are right. The eyes, teeth, Leia's head and hair, everything looks good.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-27T13:13:44+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from elementofprgress
>
> However, every map/gamemode/bundle however you break it all down including the texture of Leia's face and they want it from the cas/cat they are part of.  http://pastebin.com/zJH7yVF9 They all want one with an entry of 39667 bytes.

I think that's the same as in Unreal Engine. Every level (bundle) has a copy of a small MIP to load first. Like a draft. And only the main entry has the whole big texture that loads when we have time and space for that.
## Post #25
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2016-03-05T16:40:26+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

Can somebody be so kind to walk me through the script process. I'm stuck after extracting the .cas files to a bunch of none file extension names. What do I do after this? If I use the Frostbyte_chunk.exe it turns the file into a chunk file with no data size. Am I suppose to do this one by one to all the files after using swbf_cas.exe? I'm so lost - thanks.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T16:49:03+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from ebross67
>
> Can somebody be so kind to walk me through the script process. I'm stuck after extracting the .cas files to a bunch of none file extension names. What do I do after this? If I use the Frostbyte_chunk.exe it turns the file into a chunk file with no data size. Am I suppose to do this one by one to all the files after using swbf_cas.exe? I'm so lost - thanks.

First tell us what do you want to do. Do you need sounds? Names? Or everything?
## Post #27
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2016-03-05T19:02:13+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

I was looking for Mesh and texture data. I can use ninja ripper, but if there is an easier way to rip the models without being in game, that would be ideal. Thanks.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-06T11:17:32+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

> Reply from ebross67
>
> I was looking for Mesh and texture data. I can use ninja ripper, but if there is an easier way to rip the models without being in game, that would be ideal. Thanks.

swbf_cas.exe will not help you.

You need the python dumper script from that thread [viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584) and also mesh and texture tools. This may be even more complicated if you never used python before. You can find some "frostbite dumping" tutorials though.
## Post #29
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2016-03-06T15:59:58+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

Thanks daemon1,

I worked my way through many threads on this topic and figured out how to run python scripts. I was able to extract the game into bundles and chunks. I was able to convert the chunks to .meshset and .chunk files using frostbyte. I'm stock on the .meshset step. I can't find any tool to convert the Frostbyte output to an .obj file. There was one that would convert .mesh and .chunk, but it does not work on .meshset. Any ideas? 

Thanks.
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-06T16:26:45+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

You are using wrong scripts. I told you not use script from this thread. It's called "full extraction", but being such, it extracts some small texture mips over the big textures, so after that they can't be converted. Also it renames .mesh to .meshset, which may be correct for the engine, but it makes the old tool not working.

Maybe I'm wrong, and elementofprgress already corrected his scripts, I don't know.
## Post #31
- Username: ClubOn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 1:26 am
- Post datetime: 2016-08-04T20:59:25+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

Hi everyone I have a Little problema actualy when i use the Batch_Itexture_Converter the dds are all Black 

I have the deluxe version of the game.

My only request is the mesh and textures of the Tie Interceptor !!
## Post #32
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2016-12-23T23:10:59+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

well when i unpack i get this error 

Traceback (most recent call last):
  File "C:\Users\Mike\Desktop\SWBF\SWBFdumper.py", line 356, in <module>
    if "tocRoot" in locals():  dumpRoot(tocRoot)
  File "C:\Users\Mike\Desktop\SWBF\SWBFdumper.py", line 306, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\Mike\Desktop\SWBF\SWBFdumper.py", line 197, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\Mike\Desktop\SWBF\SWBFdumper.py", line 276, in casPatchedPayload
    casPayload(bundleEntry, targetPath, sourcePath)
  File "C:\Users\Mike\Desktop\SWBF\SWBFdumper.py", line 264, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: '\x01\x17T.(`\xfa\xc8\xd5\xc1Y9\xc7\xb4\x9cjs(\xc8\xea'

plus the stuff i do have i cant port the models to max and i cant get all chunk files help i have no idea what im doing and there is very little info on this
## Post #33
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-03T15:54:47+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

I'm hoping someone can help me with this, but I've just run daemon1's adjusted script and I can't find any of the ebx or chunk/mesh bundles for the DLC expansions. I'd love to get the files for Jabba's Palace and Scarif particularly, but also all those great new characters... Can anyone suggest why they aren't showing up after I run the dumper script and the bundle tools?
## Post #34
- Username: Crageo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 15, 2016 2:28 pm
- Post datetime: 2017-04-13T20:59:48+00:00
- Post Title: Re: StarWars Battlefront full extraction scripts

I'm getting the same problem too:

Traceback (most recent call last):
  File "E:\Misc\Modeling\Downloaded Models\Tools\SWBF_Extraction\SWBF\SWBFdumper.py", line 356, in <module>
    if "tocRoot" in locals():  dumpRoot(tocRoot)
  File "E:\Misc\Modeling\Downloaded Models\Tools\SWBF_Extraction\SWBF\SWBFdumper.py", line 306, in dumpRoot
    dump(fname,targetDirectory)
  File "E:\Misc\Modeling\Downloaded Models\Tools\SWBF_Extraction\SWBF\SWBFdumper.py", line 197, in dump
    writePayload(entry, targetPath, sourcePath)
  File "E:\Misc\Modeling\Downloaded Models\Tools\SWBF_Extraction\SWBF\SWBFdumper.py", line 276, in casPatchedPayload
    casPayload(bundleEntry, targetPath, sourcePath)
  File "E:\Misc\Modeling\Downloaded Models\Tools\SWBF_Extraction\SWBF\SWBFdumper.py", line 264, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: '\xa8\xd3\xe1F]\x94\x95DA4\x8c\xea\xb7\xf9]y\xba\xe5\xbd\xde'

Python version - 2.7 32bit

Very new to this sort of thing, any help?
