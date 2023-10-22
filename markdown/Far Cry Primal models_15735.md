## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T14:28:44+00:00
- Post Title: Far Cry Primal models

Far Cry Primal tools.

fcp_unpack.exe - unpack .fat/.dat pairs.

Drop .fat onto the tool. It will unpack all files. It will search all .XML files located in the same dir for names.
Names for all files in big primal_main package is here - [https://mega.nz/#!IZYlBSKJ!gjrLniO4goeC ... nH2QqOVcfs](https://mega.nz/#!IZYlBSKJ!gjrLniO4goeCFlSoQQk_PqhLEGcxW0dd7nH2QqOVcfs)

You can go to current dir, and run the tool from somewhere else and specify FAT file somewhere else. So you can place everything in 3 different dirs if you like:

1. dir with the tool
2. dir with fat/dat pair
3. current dir where unpacked files will go (also must have xml files for names)

fcp_pack.exe - repack .fat/.dat pairs.

Just run it in the dir where you have files to pack.

oasis_fcp - modified "dunia tools" strings converter for Far Cry Primal

1. Convert BIN to XML as usual
2. Find line with 0xAEE923DE code and delete it. (This new format somehow has 1 section without lines in it. This is causing the old tool to fail. Maybe it's needed or something, then I'll have to find a way to handle it.)
3. Make changes you need
4. Convert file back to BIN
5. Add "table_fcp" table to the end of the file (This can be done in any hex editor or commander tool, or with command line such as "copy /b oasis.bin + table_fcp oasiswithtable.bin")
6. Pack oasis file into FAT/DAT with my packer tool.

Important note. Patch.fat/dat is loaded before patch_sound.fat/dat so you have to find some other package to replace text, or remove old file from patch. I did this by finding the file hash in patch.fat and changing it. The hash is (F3 F8 E3 5D 29 FD BD F2) for english file. Changing any byte here will "mask" the file so game won't find it. Also if oasis file will be changed, you need to get the new table from the end of original file.

oasis_fc4 - strings converter for Far Cry 4

Same for FC4

Latest model tools: [viewtopic.php?p=126915#p126915](http://forum.xentax.com/viewtopic.php?p=126915#p126915)



I made a new tutorial on how to research model formats: [https://www.youtube.com/watch?v=-1b3bM7ih6Y](https://www.youtube.com/watch?v=-1b3bM7ih6Y)

And the thread for all my tutorials here: [viewtopic.php?f=29&t=15687](http://forum.xentax.com/viewtopic.php?f=29&t=15687)
[fcp_tools.rar](https://xentaxbackup.github.io/file/12420_fcp_tools.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T14:48:55+00:00
- Post Title: Far Cry Primal models

> Reply from bouvrie
>
> Far Cry *.dat/fat pairs unpack to smaller files.
So what if I just unpack *.dat/fat pairs into smaller files? Will you be able to use your dunia tools then? I can send you some unpacked examples.

> Reply from bouvrie
>
> One thing I noticed with Sir Kane's Watch Dogs 2 extractor, is that it manages to translate the filepath/name hashes from the dat/fat into the actual filenames. It would be very cool if that trick can be reproduced with Far Cry 4
There's NO TRICK. There's NO WAY to translate hashes to names, please remember that . Sir Kane's Watch Dogs 2 extractor is also using dictionary, and it works completely the same as all other "hashed" extractors. But there's a way to gather names automatically from running game, or from game files, which Ekey did for WD2, and which I did for Dead Space before.
## Post #3
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-14T16:20:55+00:00
- Post Title: Far Cry Primal models

// note: this conversation is a continuation of the post at viewtopic.php?p=126135#p126135

> Reply from daemon1
>
> bouvrie wrote:Far Cry *.dat/fat pairs unpack to smaller files. 
So what if I just unpack *.dat/fat pairs into smaller files? Will you be able to use your dunia tools then? I can send you some unpacked examples.That's the general idea, provided Ubi didn't change much with the filesystem. And for modding, it'd be great if you could do a reverse procedure too, packing a folder's contents into a dat/fat pair. I think this will work, UNLESS the binaryfile formats also uses different compression. But we'll see, sure, send me some examples! 

In Far Cry 4, we use different tools to 'convert' binary objects to XML, RML to XML, and .xbt to dds texture. Would it be thinkable that all those formats just share the same compression technique, and a generic unpacker/packer can be written for them?

> Reply from daemon1
>
> There's NO TRICK. There's NO WAY to translate hashes to names, please remember that . Sir Kane's Watch Dogs 2 extractor is also using dictionary, and it works completely the same as all other "hashed" extractors. But there's a way to gather names automatically from running game, or from game files, which Ekey did for WD2, and which I did for Dead Space before.
Yeah, I know hashes are one-way, I assumed Sir Kane uncovered a dictionary function within the game itself, returning the source string from a specified hash, but I misread [his post](http://forum.xentax.com/viewtopic.php?p=124885#p124885). Would've been cool though. 

For Far Cry 4, I compiled my own filelist based on the data I extracted from the various XML files, along with data from other sources. However, that only scratches the surface of all the files in there. Right now I'm batch processing about 188000 translated XML files to see if I can write their XML definitions. Dunia seems to load all definition files on startup, so performance is very bad at this point. But at least it's a step forward. 

Regarding the model: THIS IS AWESOME! For Far Cry 4, I always wondered if/whether sense can be made of both model files and audio files (the latter extract to *.SPK/*.SBAO files which seem to use different codec than Far Cry 3. There's a [topic on XeNTaX](http://forum.xentax.com/viewtopic.php?f=17&t=12495) about that). Perhaps some day, one can actually add new objects to the game, possibly even with customized *.HKX (Havok physics data?), materials and shaders.

In your Mammoth tutorial video I see you have a Far Cry Primal file-list already. How did you compile that, playing the game, analyzing subdats or something?

Looks like I'll be diving in your tutorials, thank you for those! This subject matter fascinates me.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T20:23:49+00:00
- Post Title: Far Cry Primal models

...
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T11:03:45+00:00
- Post Title: Far Cry Primal models

> Reply from bouvrie
>
> it'd be great if you could do a reverse procedure too, packing a folder's contents into a dat/fat pair.
I dont know how dunia2 tools did it, but putting back 200000+ files with total size of 6GIG+ is not a good idea. I can make a tool to replace only needed files though.

> Reply from bouvrie
>
> I assumed Sir Kane uncovered a dictionary function within the game itself, returning the source string from a specified hash, but I misread his post. Would've been cool though.
Such function is never present in games, because its obviously not needed by the game code. 

> Reply from bouvrie
>
> I always wondered if/whether sense can be made of both model files and audio files
Audio can be done too. Zench's DecUbiSnd is not perfect, its based on workarounds. I recently reversed Prince of Persia audiobanks format, which allows to properly extract all audio from UBI games, including those not extracted before with DecUbiSnd tool. Unfortunately I had no time to write a tool yet.

> Reply from bouvrie
>
> In your Mammoth tutorial video I see you have a Far Cry Primal file-list already. How did you compile that, playing the game, analyzing subdats or something?
The devs have left the full lists of filenames in game files. So no extra work needed here. For example, one of them is primal_main.dpv - its zip archive.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T12:16:35+00:00
- Post Title: Far Cry Primal models

couple of examples of data files
[fcb_bin.rar](https://xentaxbackup.github.io/file/12223_fcb_bin.rar)
## Post #7
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-15T14:33:39+00:00
- Post Title: Far Cry Primal models

> Reply from daemon1
>
> couple of examples of data filesYay, success! Dunia Tools converts the fcb just fine! As for the material bin file, I don't think I (or other FC modders) know what/how to edit that file further. But both filenames ring a bell in terms of Far Cry modding! Here's the fcb converted to XML, it defines a sector in the worldmap:

```
  <field name="Id" type="Int32">16842</field>
  <field hash="B7B2364B" type="BinHex">2A000000</field> // Float32:0, Int32:42, UInt32:42, Hash32:CRC32b(x)='0000002A'
  <field hash="C0B506DD" type="BinHex">69000000</field> // Int32:105, UInt32:105, Hash32:CRC32b(x)='00000069'
  <object name="MissionLayer">
    <field hash="B88F49FD" type="BinHex">6400000000000000</field>
    <object name="Entity">
      <field name="hidName" type="StringId">lightprobes_16842</field>
      <field name="disEntityId" type="UInt64">14484421259298931741</field>
      <field name="text_hidEntityClass" type="String">CEntity</field>
      <field name="hidEntityClass" type="Hash32">6750C950</field>	// 'CEntity'
      <field name="hidResourceCount" type="Int32">3</field>
      <field name="hidPos" type="Vector3">-2432,1600,0</field>
      <field name="hidAngles" type="Vector3">0,0,0</field>
      <field name="hidPos_precise" type="Vector3">-2432,1600,0</field>
      <field name="hidConstEntity" type="Boolean">False</field>
      <field name="hidIsLargeEntity" type="Boolean">False</field>
      <field hash="B435B769" type="String"></field>
      <field hash="2D90D933" type="UInt64">18446744073709551615</field>
      <object name="Components">
        <object hash="7C34E822">
          <field name="hidHasAliasName" type="Boolean">False</field>
          <field name="positions" type="Vector193">2,-2428,1604,455.984,-2420,1604,467.875,-2412,1604,0,-2404,1604,0,(...)</field>
          <field hash="EFE7E642" type="BinHex">00000000</field>
          <field hash="718373E1" type="BinHex">00000000</field>
          <field hash="06844377" type="Vector1665">(...)</field>
          <field hash="EAC5287A" type="Vector3">-2433.5,1598.5,392.906</field>
          <field hash="D6C81723" type="Vector3">-2366.5,1665.5,470.203</field>
          <field hash="6C1AAC52" type="BinHex">00001801000017000050726F626573456469746F7250726F70657274696573000000</field>
        </object>
        <object name="CEventComponent">
          <field name="hidHasAliasName" type="Boolean">False</field>
          <object name="hidLinks" />
        </object>
      </object>
    </object>
  </object>
</object>

```
 

> Reply from daemon1
>
> I dont know how dunia2 tools did it, but putting back 200000+ files with total size of 6GIG+ is not a good idea. I can make a tool to replace only needed files though.We do not edit the 6GB file, but Far Cry 3/4 looks for a patch_hd.dat/fat pair which is used to override files loaded into the game. FC:Primal doesn't load this file, but I believe we can exploit a currently nonexistent patch_sound.dat/fat file to accommodate the mods. However, for this type of modding to work, I'm afraid it would be a requirement to allow new files to be added to dat/fats, rather than replacing pre-existing ones...

If the compression used on the dat/fat is backward compatibele with earlier versions, perhaps the Dunia tools could still work. In that case, we'd only need your unpacker. 

If you could locate and share an .xbt texture used in something obvious (like Sayla, or a mammoth or something) and give me the filepath it's stored in, I could see if I can make the game load a modified one as part of a mod using the Dunia tools.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-17T15:59:54+00:00
- Post Title: Far Cry Primal models

> Reply from bouvrie
>
> If the compression used on the dat/fat is backward compatibele with earlier versions, perhaps the Dunia tools could still work. In that case, we'd only need your unpacker.

No, its not compatible. But I can always put them back uncompressed. This worked in Watch Dogs.

So now its time to decide. I have lots of other projects in queue. I can do something quick now, but that will not be much, just some simple solution if it works. If you want better tools, you have to wait until I finish other projects.

p.s. Don't update your messages, this way I won't probably notice it.
## Post #9
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-17T18:36:28+00:00
- Post Title: Far Cry Primal models

> Reply from daemon1
>
> So now its time to decide. I have lots of other projects in queue. I can do something quick now, but that will not be much, just some simple solution if it works. If you want better tools, you have to wait until I finish other projects.Seeing time is a factor, I'd already be very much interested in just a plain dat/fat unpacker. If you can do that quick, I can work on uncovering the file/object structure, start a Dunia2 project definition for Primal, and perhaps get some more insights to help me with Far Cry 4 modding in general as well.

Putting things back into existing dat/fats, or creating dat/fats from scratch would be of later concern to me. Don't let me distract you from your other projects, time is precious as it is!
## Post #10
- Username: FartingSquirrel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 06, 2016 8:36 am
- Post datetime: 2017-01-18T13:46:07+00:00
- Post Title: Far Cry Primal models

Hey guys!

Sorry for it's a bit off and that I'm kinda noob, but if you could unpack the patch.fat/.dat then it would be possible to get the oasisstrings.bin (for localization), right? At least I think there is an oasisstring.bin, based on FC3.

If you could look into that, it would be appreciated.
## Post #11
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-18T16:04:44+00:00
- Post Title: Far Cry Primal models

> Reply from FartingSquirrel
>
> if you could unpack the patch.fat/.dat then it would be possible to get the oasisstrings.bin (for localization), right?Yep, that's what I'm expecting, along with more insight in the NomadObjects file for future modding. I'm even hoping to find something that may counteract Far Cry 4's [LOD pixelation pop](https://www.youtube.com/watch?v=5FO2d-Vhf3w), if it can be ported over to FC4!
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-18T19:57:04+00:00
- Post Title: Far Cry Primal models

Ok i got first results. Loaded all the filenames and checked.

From the main 6gig file i have 173612 files with names, and 33601 still have no names.

They only provided names for main files, so "common.dat" has no names yet.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-18T20:53:54+00:00
- Post Title: Far Cry Primal models

Now I extracted  LANGUAGES\english\oasisstrings.oasis.bin  from common.dat and it really has lzo1x compressed text inside (as was said before). Here's an example of the very first string I'm getting from there:

```
<font color='#f46b00'>Rescued Wenja</font> will join your village and increase the population. 
```
## Post #14
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-19T00:26:48+00:00
- Post Title: Far Cry Primal models

Nice! it really does look much like the older Far Cry modding.  Speaking of the dpv compressed file, FC3 is again present:
> <Archetype ArchetypeId="7660420242520" hidArchetypeResId="entityarchetypeslibrary\7660420242520.ark.fcb" Name="WeaponProperties:FC3/MP5" />In case you want a filelist dictionary to 'unpack' more of the remaining dat/fat files: The majority can be found in the archive at [http://janne252.com/downloads/fc4/gibbed_fc4project.zip](http://janne252.com/downloads/fc4/gibbed_fc4project.zip) , in the "Far Cry 4\files\" dir. For Far Cry 4, nonetheless.
## Post #15
- Username: FartingSquirrel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 06, 2016 8:36 am
- Post datetime: 2017-01-19T17:06:02+00:00
- Post Title: Far Cry Primal models

> Reply from daemon1
>
> Now I extracted  LANGUAGES\english\oasisstrings.oasis.bin  from common.dat and it really has lzo1x compressed text inside (as was said before).

Wow, cool. So, that means the texts are editable now, and only a repacking method is needed for them?
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T17:16:45+00:00
- Post Title: Re: Far Cry Primal models

> Reply from FartingSquirrel
>
> Wow, cool. So, that means the texts are editable now, and only a repacking method is needed for them?

That means I unpacked the file and I can open it. I don't know if you have any tools to edit it.

Check it yourself: [http://www112.zippyshare.com/v/pYdElWqe/file.html](http://www112.zippyshare.com/v/pYdElWqe/file.html)
## Post #17
- Username: FartingSquirrel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 06, 2016 8:36 am
- Post datetime: 2017-01-19T17:40:12+00:00
- Post Title: Re: Far Cry Primal models

Oh, alright. But actually, I can't even unpack the .bin with GibbedDunia. Well, probably I'm doing something wrong, but Gibbed.Dunia2.ConvertBinaryObject.exe isn't supposed to unpack it?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T18:22:10+00:00
- Post Title: Re: Far Cry Primal models

> Reply from FartingSquirrel
>
> Oh, alright. But actually, I can't even unpack the .bin with GibbedDunia. Well, probably I'm doing something wrong, but Gibbed.Dunia2.ConvertBinaryObject.exe isn't supposed to unpack it?

I have no idea. Never used GibbedDunia. I could unpack it myself thats all I know.

Good news  I now have all 200k+ files unpacked from primal_main 6gig file with names. 
Thats quite a lot of files. What do you want me to do with the tool? Maybe add some filter? Do you really need them all unpacked?
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T20:04:00+00:00
- Post Title: Re: Far Cry Primal models

ok this is first test. This tool (with dictionary) will unpack all compressed files from fat/dat pairs. Dictionary includes all names for primal_main. Other files will be extracted names as hashes.

[https://mega.nz/#!YY5UgagB!waUFhD03EACg ... heZ6HN63ds](https://mega.nz/#!YY5UgagB!waUFhD03EACgNCrh2QEK6sqRZK5wR8A2QheZ6HN63ds)

That means uncompressed files (and there are many of them) will not be extracted for now. They are all tiny, no more than 1k in size.
## Post #20
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-19T20:42:48+00:00
- Post Title: Re: Far Cry Primal models

xbt textures seem to be identical to FarCry 2/3/4.  Model format is however changed. Probably not by much. I'll start working on an importer.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T20:44:40+00:00
- Post Title: Re: Far Cry Primal models

are you going to export with bones? because if not, i will do it
## Post #22
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2017-01-19T21:10:07+00:00
- Post Title: Re: Far Cry Primal models

I apologize if I interfere in your conversation, if you write a script, do, please, the ability to import and animation.


P.S. Sorry for my English, I use a translator.
## Post #23
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T00:15:13+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> are you going to export with bones? because if not, i will do it

yes, skeleton import is already done



As for animation import, I've never seen that animation importing has been done for any Far Cry game, so i'm doubtful on that. if someone else wants to figure out animations, be my guest.

Edit: mesh now imports too:



No UVs yet. but it's progressing rapidly. Format is like 90% similar to FarCry 4.
## Post #24
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T06:26:01+00:00
- Post Title: Re: Far Cry Primal models

nearly done. I have model, skeleton, UVs, and multiple materials all working. Bone weights still has a problem I need to work out, but I'll get it done.



As you see though, there's another problem. High rez textures are not being extracted. all of the texture are 128x128 or smaller. I'm wondering if this is because of the block on uncompressed files. High rez textures may not be compressed since the DDS format is already a compressed format.



I'm reading the UV offset and scale directly from the model file. nevertheless there seems to be some slight offset always present. I'll probably just end up hard coding in a correction, since it seems to be the same for every model. Strange though.
## Post #25
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-20T11:11:07+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> As you see though, there's another problem. High rez textures are not being extracted. all of the texture are 128x128 or smaller.Huh? I opened a texture for the Mammoth, and it was def larger than 128x128. Did you open the texture having 'LOD0' in its filename?
## Post #26
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2017-01-20T11:52:08+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> As for animation import, I've never seen that animation importing has been done for any Far Cry game, so i'm doubtful on that.
Sorry, what then is the use of 3D models of the skeleton, but without the animation?



P.S. Just me 3D model without animation unsuitable.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T16:01:27+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> High rez textures are not being extracted. all of the texture are 128x128 or smaller. I'm wondering if this is because of the block on uncompressed files. High rez textures may not be compressed since the DDS format is already a compressed format.

DDS has constant compression rate. So a big red square can still be 1MB in size, and compressing into about 100 bytes with zip or any other compressor. Thats why DDS textures are usually compressed in archives.

Highres textures must be in primal_main_hd_tex file, I didnt check for names for that archive yet.
## Post #28
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T18:04:54+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> volfin wrote:As you see though, there's another problem. High rez textures are not being extracted. all of the texture are 128x128 or smaller. Huh? I opened a texture for the Mammoth, and it was def larger than 128x128. Did you open the texture having 'LOD0' in its filename?

Ok yes, for the mammoth there are LOD0 files. but for some reason there are none for the tiger:


I guess I picked a bad test choice. But still strange it has none. 

> Reply from SoldierTODD
>
> Sorry, what then is the use of 3D models of the skeleton, but without the animation?
I'm guessing you're new around here, but out of thousands of games that models have been extracted for, I can only think of about 5 that ever had animations extracted as well. The *points* are many reasons, a few of being:
- Collection (XNALara fans)
- reuse (Source Film Maker, Gmod, insertion into other games)
- learning (my personal favorite, I have always been interested in the techniques used to keep poly count down and to achieve various visual effects)
and probably others.

Sure getting animations would be nice. But generally, the work involved in extracting them is far above their value. To me anyway. But as I said, maybe someone else wil tackle this. I saw someone worked out the Metal Gear Solid V animations recently (first time in years I've seen It done I might add.)
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T18:14:56+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I saw someone worked out the Metal Gear Solid V animations recently (first time in years I've seen It done I might add.)
Yeah it was me 

In 2016 I reversed animations for:

- Overwatch
- the whole Call of Duty series
- Bioshock Infinite Morpheme
- MGSV

I didn't think it was so rare. Difficult formats (such as MGSV) are hard to do, but simple ones must take not much time.
## Post #30
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T18:44:22+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> volfin wrote:I saw someone worked out the Metal Gear Solid V animations recently (first time in years I've seen It done I might add.)
Yeah it was me 

In 2016 I reversed animations for:

- Overwatch
- the whole Call of Duty series
- Bioshock Infinite Morpheme
- MGSV

I didn't think it was so rare. Difficult formats (such as MGSV) are hard to do, but simple ones must take not much time.

Nice, I didn't know about some of those.
It is pretty rare. For a long time games were using Havok for animation, so they were stored in HKX files, which were nearly impossible to figure out (nearly). I'm starting to notice publishers are moving away from Havok for animation more. So it may become simpler. And not all have the skills to isolate actual game code to reverse the format, I know I don't.  All I do is from direct examination of the data itself.  And when I examine animation, all I see is an ocean of floats.
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T19:39:05+00:00
- Post Title: Re: Far Cry Primal models

You don't have to look into code if animation is using normal floats. Its only required if some crazy non-standard types are used. Like variable bit integers or quaternions packed with special math.
## Post #32
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-20T22:02:52+00:00
- Post Title: Re: Far Cry Primal models

ok, Importer is complete.



Imports all mesh, with original scale, original skeleton, original weights, and UVs. Also option to import vertex colors if desired.
After trying quite a few models, as you see above, there doesn't seem to be textures for the 'hair'.  I suspect because it's generated on the GPU. those are just guide vertices. They do have UVs though, so perhaps there are 'hair' texture hiding somewhere. If someone finds them, please let me know. Oh yeah and Eye textures seem missing too.


Completely posable and animatable.   

There's some room for improvement, such as above the 'back hair' is a separate mesh, and when imported it brings in a second copy of the armature, instead of using the existing. I may try to make it a bit smarter. But otherwise seems working well.

The importer is for Blender 2.63 and above, and if you need to know how to install, see my previous tutorial here: 
[viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

Enjoy.
## Post #33
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-20T22:50:26+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> ok this is first test. This tool (with dictionary) will unpack all compressed files from fat/dat pairs. Dictionary includes all names for primal_main. Other files will be extracted names as hashes.

https://mega.nz/#!YY5UgagB!waUFhD03EACg ... heZ6HN63ds

That means uncompressed files (and there are many of them) will not be extracted for now. They are all tiny, no more than 1k in size.

are you planning to enhance support for you extractor in the future? so far it works pretty well for a lot of files, though most of them (as you mentioned) aren't working.
good work so far and thank you for the unpacker!
## Post #34
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-21T00:27:19+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I saw someone worked out the Metal Gear Solid V animations recently (first time in years I've seen It done I might add.)Haha, reminds me of [https://www.youtube.com/watch?v=Sl9H6iexJWI](https://www.youtube.com/watch?v=Sl9H6iexJWI) . Without ripping Norman Reedus' model from a reverse engineered demo sample, this wouldn't have been possible. It's almost an art form. 

> Reply from volfin
>
> For a long time games were using Havok for animation, so they were stored in HKX files, which were nearly impossible to figure out (nearly).AFAIK, Far Cry games use hkx along with xbg and xbt files. But now you're saying the game doesn't use them for the animation then? Or did you manage to reverse those?
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T02:05:39+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> volfin wrote:I saw someone worked out the Metal Gear Solid V animations recently (first time in years I've seen It done I might add.)Haha, reminds me of https://www.youtube.com/watch?v=Sl9H6iexJWI . Without ripping Norman Reedus' model from a reverse engineered demo sample, this wouldn't have been possible. It's almost an art form.

LOL, that's hilarious.

> Reply from bouvrie
>
> volfin wrote:For a long time games were using Havok for animation, so they were stored in HKX files, which were nearly impossible to figure out (nearly).AFAIK, Far Cry games use hkx along with xbg and xbt files. But now you're saying the game doesn't use them for the animation then? Or did you manage to reverse those?

I've noticed it does use HKX. There's other games that don't lately, was just speaking in general. I started a project to reverse the HKX format, years ago, but never finished it. It's my curse, always moving on to new projects, even if some don't get finished.
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T07:03:40+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I've noticed it does use HKX.

From the first look, HKX is only used for physics, but animation system is their own.
## Post #37
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T07:18:54+00:00
- Post Title: Re: Far Cry Primal models

> Reply from TheMask85
>
> 
are you planning to enhance support for you extractor in the future? so far it works pretty well for a lot of files, though most of them (as you mentioned) aren't working.
good work so far and thank you for the unpacker!

okay, that's strange. apparently you need to have each .dat + its belonging .fat file in seperate folders, otherwise the unpacker will crash after trying to extract more than 2 or 3 files.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T07:55:24+00:00
- Post Title: Re: Far Cry Primal models

yes i plan to support more files. And also repacker. What do you mean under "in seperate folders" ? What do you need to separate? It works on my side.
## Post #39
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T08:08:29+00:00
- Post Title: Re: Far Cry Primal models

what i did first was grabbing all .dat+.fat files and threw them into a "working folder" for extraction. (since i don't like messing in its original install path), than drag and dropped .fat files onto the fcp_unpack.exe. worked for "common.fat" and also for "installpkg.fat" but all the other files then refused to unpack (fcp_unpack.exe just crashed with all the other files).
but as soon as you have common.dat+.fat in its own single folder, primal_main.dat+fat in its own folder, etc., it will exract all the packages just fine. 
after export i threw them all in one single big folder and the game seems now to be fully extracted.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T08:29:45+00:00
- Post Title: Re: Far Cry Primal models

It can be that with all subfolders the name is too long, so tool crashes on some file. So if your "separate" folder name is shorter, it works and then, when you move them, windows automatically cuts the names at some point.
## Post #41
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T09:05:32+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> ok, Importer is complete.

may i post a little bug report here? it'd be cool, if you could fix these things.

- faces of the meshes are inverted
- vertex normals seem to be missing
- Uv's are "cut" onto the mesh. for example, where there's one single UV for the skin part of the body, there's more than one selection on the mesh, causing nasty vertex normals seams on the mesh (untill smoothed out in a 3d application manually)
- bone rotations and positions are off. for example (using the great "Urki" model as a reference), the bones are on positions of their parents. means: "RightShoulder" is on position of "Spine2", "RightArm" is on poition of "RightShoulder", "RightForeArm" is on position of "RightArm" and so on.
- material names/paths are missing

i know vertex normals can be hard to implement but it'd be amazing if you could tackle the bone rotations/positions and the flipped faces. otherwise it's one useful importer. thank you!!
## Post #42
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2017-01-21T12:36:07+00:00
- Post Title: Re: Far Cry Primal models

> ok, Importer is complete.
>
> Enjoy.
No animation importer has not been completed.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T16:44:24+00:00
- Post Title: Re: Far Cry Primal models

> Reply from SoldierTODD
>
> ok, Importer is complete.
Enjoy.
No animation importer has not been completed.

Sorry but as I said, I'm not going to do that. This isn't some Dictarorship. I donate my time freely, and you get what I decide to give.

> Reply from TheMask85
>
> 
may i post a little bug report here? it'd be cool, if you could fix these things 
  *LIST*
hehe, I knew when I used the term 'complete', I would regret it. I should have said 'functional'. It's still rough around the edges I know. I'll resolve what I can, Normals I can probably say won't happen. I'm still trying to find a way to reliably get Blender to accept those (it hates them).  And auto-materials is a big ask, don't expect that either.  I didn't notice any problems with the skeleton, at least on the Chicken/Tiger/Mammoth and other animals I tried. I'll have to find that specific model and see what you mean.  flipped faces should be an easy fix.  Seams is how the data is stored, can't do anything about that. you just need to join the parts, and remove duplicate vertices, it's simple mesh editing.
## Post #44
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T17:44:27+00:00
- Post Title: Re: Far Cry Primal models

it's cool. you pointed out already, it yet has some flaws. totally fine with me.

> Reply from volfin
>
> I didn't notice any problems with the skeleton, at least on the Chicken/Tiger/Mammoth and other animals I tried.

as it seems, this problem goes for all models. yes, the bone structure is there, however the position and bone rotations for all joints is unfortunately incorrect.
you can also check on the sabertooth for example. as a test, just rotate "LeftForeArm" for example, or better yet "LeftHand" and you will see what i mean.
## Post #45
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T17:54:15+00:00
- Post Title: Re: Far Cry Primal models

> Reply from TheMask85
>
> may i post a little bug report here? it'd be cool, if you could fix these things.

Ok here's the status:
- faces of the meshes are inverted  * Fixed *
- vertex normals seem to be missing * no fix at this time *
- Uv's are "cut" onto the mesh. * how models are stored, no fix *
- bone rotations and positions are off. * Checked, no issues *
- material names/paths are missing * no fix at this time *

About the skeleton. I see no issues with rotation or with naming.  To specifically point out what you mentioned:

You may not like Ubisoft's names for things, but they are what they should be. I only do it how Ubisoft defines it.

All bones are in rest position, and match up to rest pose of the mesh.  

If you're seeing something different than shown here, please give more info, such as model, what version of blender you use, and any other information that can help me figure it out. otherwise I have to assume all is well. 

as stated on the list, Normals, and material paths, i'll continue to look into. I may have something down the road. 

Edit: newer version below.
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T18:14:25+00:00
- Post Title: Re: Far Cry Primal models

After further review, I do see that on Urki, there's a vertex group problem:



I think this is what you meant. it's not a problem with the skeleton, Skeleton is fine. it's a problem with the vertex groups. My code assumes every bone has a vertex group. But it seems with human characters, they try to use a 'universal' skeleton, so some bones are unused. That's throwing off the naming. It may happen on some animals. but for examples of models that don't have spare bones, see "anml_chic.xbg" Chicken and "anml_sabertooth_body.xbg" Sabertooth. they load with no flaws, since no extra bones.  

I'll have to do some work to handle this situation. Stay tuned.
## Post #47
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T18:37:09+00:00
- Post Title: Re: Far Cry Primal models

thank you for looking into it. i can confirm, faces invertion has now been fixed. yay!

as for the bones, please let me explain a bit better.

see how i selected "Rightshoulder"?:
[https://pl.vc/bd120](https://pl.vc/bd120)

where it should actually be at this position:
[https://pl.vc/dekue](https://pl.vc/dekue)

and here's the weighting itself shown (which is correct - only position and rotation is wrong):
[https://pl.vc/1iknhq](https://pl.vc/1iknhq)

moving through the joint hierarchy, down to the next joint, the "RightArm":
[https://pl.vc/lulyg](https://pl.vc/lulyg)

the cross shows where the joint is ("Rightshoulder"), while the circle shows where it should be:
[https://pl.vc/1hjqfe](https://pl.vc/1hjqfe)

moving on to the "RightForeArm". when rotate it, that will happen (because its on position of "RightArm"):
[https://pl.vc/13w6hf](https://pl.vc/13w6hf)

i hope that helps a bit more.
using Blender 2.78 to im-/ and export to fbx, to continue work on the model itself in C4D. no fbx export options have been altered.

edit:
okay, i just saw you last post after i posted mine. however, that issue is also affecting the sabertooth aswell.
## Post #48
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T18:53:21+00:00
- Post Title: Re: Far Cry Primal models

Can you show me where on the Sabertooth? I checked it over and all looked fine. Granted, how they built the skeleton is odd but:


That is indeed Right Upper leg, and 


That is indeed RightLeg.

I know it looks counter intuitive, because the bone isn't right where the weight is. but this is intentional on Ubisoft's part. If you rotate the bones, you'll see the movement makes sense. Recall this isn't the Studio version with the fancy handles to move groups of bones together to make things easy for animators. This is the raw made from nothing version with no help to anyone version  it's not going to be easy to use at all.
## Post #49
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T19:03:06+00:00
- Post Title: Re: Far Cry Primal models

you just showed it. the selected joint should be, where the weighting is. not one step up the joint-hierarchy.

> Reply from volfin
>
> but this is intentional on Ubisoft's part.
i hate to say this but no, really, it's not.
## Post #50
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T19:05:02+00:00
- Post Title: Re: Far Cry Primal models

> Reply from TheMask85
>
> you just showed it. the selected joint should be, where the weighting is. not one step up the joint-hierarchy.
volfin wrote:but this is intentional on Ubisoft's part.
i hate to say this but no, really, it's not.

it is. I just played with the model and its fine. See my edit above also. This isn't a studio ready version. you have to grab groups of bones in some instances and move them together. there's no IK controllers etc, which seems to be what you expect.
## Post #51
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T19:14:39+00:00
- Post Title: Re: Far Cry Primal models

Alright. You convinced me. There must be a more fundamental problem I'm not seeing here. I'll have to review skeleton and vertex group creation from the ground up.  Will take a bit probably.  

Also just to say it clearly, I see you're not using Blender. I will never say the skeleton will work in any app but Blender. it's not made with any finesse at all.
## Post #52
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-21T19:16:06+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> 
it is. I just played with the model and its fine. See my edit above also. This isn't a studio ready version. you have to grab groups of bones in some instances and move them together. there's no IK controllers etc, which seems to be what you expect.

the bone reading/ranslating is not correct. i may be not a coder but i'm working with 3d models every day.
every single joint is simply shifted by one position and has a slightly wrong rotation. that's the whole thing here. 

> Reply from volfin
>
> Alright. You convinced me. There must be a more fundamental problem I'm not seeing here. I'll have to review skeleton and vertex group creation from the ground up. Will take a bit probably.

thank you so much!!

> Reply from volfin
>
> Also just to say it clearly, I see you're not using Blender. I will never say the skeleton will work in any app but Blender. it's not made with any finesse at all.

nah that's cool! the issue can be seen on your last example pic aswell with the sabertooth.
## Post #53
- Username: lukamas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 07, 2015 3:12 am
- Post datetime: 2017-01-21T22:21:11+00:00
- Post Title: Re: Far Cry Primal models

How do you extract the models from far cry primal?

gibbed dunia tools does not work, what do I do?

thanks in advance
## Post #54
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T23:38:34+00:00
- Post Title: Re: Far Cry Primal models

well I found one of the problems...
[https://developer.blender.org/T33172](https://developer.blender.org/T33172)
I actually knew about this 'feature' but completely forgot. You have to fudge zero length bones to not be zero. most other programs don't care and allow that, and the models have a few. Missing bones = big problems. I'm not sure this is the only problem, but it's a step in the right direction.
## Post #55
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-22T01:04:56+00:00
- Post Title: Re: Far Cry Primal models

Ok I think I have it solved now.

Looks better:







One difference is, I had to go to a 'tailless' system, since the game doesn't store tail data.  So each ball is a pivot bone. Valve uses this system for their Source Tools. But it works correctly. 


How it would appear with regular tails:


I'll test on the other models and if all is good, will post an updated version shortly.
## Post #56
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-22T03:52:33+00:00
- Post Title: Re: Far Cry Primal models

Ok, after a lot more pulling my hair out, it is working right for Urki too.

And i'm going to show you something before you say it's wrong, because even I thought it was wrong at first.   



When you select a shoulder, it looks like it's too far down the arm. but actually it's ok because it extends way, way down. and that bone also moves the child bone for shoulder tilt (and the other midway down), which as you see here:



takes care of the rest.  So all good!   

Now, also I did the huge, *huge* favor of putting small squares on all the invalid bones. Because otherwise it's crazy to figure out which bones actually do stuff.  So many unused bones.  (luckily they identified them).  So that's why the small squares. Ignore them, they do nothing.

Now maybe I can tomorrow see about Normals and materials.   

Enjoy.

Edit: newer version below.
## Post #57
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-22T12:03:20+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> When you select a shoulder, it looks like it's too far down the arm. but actually it's ok because it extends way, way down. and that bone also moves the child bone for shoulder tilt (and the other midway down), which as you see here:

exactly!
i can confirm, joint positions are now properly allocated and even the rotation is now correct. that's awesome!
materials and normals would be the icing on the cake. thank you!
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-22T17:19:19+00:00
- Post Title: Re: Far Cry Primal models

Making the packer. Your sound_patch trick worked, and now I'm hunting the rare blue goat ([watch the video](https://youtu.be/UAram-DkH3E)).
## Post #59
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-22T21:00:25+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Making the packer. Your sound_patch trick worked, and now I'm hunting the rare blue goatHaha, good to hear! I tried it myself with the mammoth & Dunia tools, but no luck; seems like the the game expect indeed isn't backward compatible/doesn't match the compression algorithm provided by the older Dunia2 tools.

So, this means you have only the modified texture in a BRAND NEW sound_patch file? Having a packer that can make archive from scratch will SURELY make mods viable, as it's easier to share that than a modified 6GB data file! 

Btw, in Far Cry 4 it looks like Dunia extracts (sub)dat/fat archives from a dat/fat archive in case of the fcc_main.dat. If you encounter a weird file format analyzing a Primal dat file, perhaps it's another dat/fat in there.
## Post #60
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2017-01-22T21:17:52+00:00
- Post Title: Re: Far Cry Primal models

We only expecting translation tool or editor-repacker for text string. as I have seen there isn't anything for it. if only, someone would hand it, too...
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-23T17:07:50+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> So, this means you have only the modified texture in a BRAND NEW sound_patch file?
Yes
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-23T20:15:59+00:00
- Post Title: Re: Far Cry Primal models

Packer. Place it where you have extracted files and run. Will only work with named files now. "Unknown" support later.
[fcp_pack.rar](https://xentaxbackup.github.io/file/12271_fcp_pack.rar)
## Post #63
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T05:20:53+00:00
- Post Title: Re: Far Cry Primal models

Ok, game normal and auto texture assignment are done. But a lot of caveats of course!

First Normals:


You remember my earlier pics, the tiger looked all cut up. well it still is. but since normal are now assigned, the cuts appear healed. This is the only proof I have that i'm importing normal correctly, since I have no way to know what they should be. But every other method appeared a mess, so I'll assume this is right. 

They look imperfect in places:

But I have no way to know if this is just a flaw from the devs, or what. So that's all I can say on that. 

Now, auto texture. It works, but with a lot of conditions.  Firstly, the model file must be opened from it's original folder it was extracted to.  And the contents of the _materials folder must also be in it's original location. And the xbt textures must also be in their original locations as well.  The importer will convert the xbt files to dds if not already converted. but if you already have the DDS there, it will use those instead.

when you load you'll get this automatically if those conditions are met:

As mentioned, you need to add lights to the scene to see the textures. You also have to switch it to "Material" display mode at the bottom. You can find the texture names and locations in the Texture pane on the right. 

Now, you see this really crazy glitch on the model. This is because, the normal maps as stored in the game are not normal (LOL a joke   )
They have their layers all mixed up. so you have to edit it in your favorite texture editor. (mine is photoshop)


First you'll notice the image has alpha, so if you're using Intel Textureworks, you have to use a handy Transparency to Alpha action to convert it to an alpha layer. Now you can see what is going on:

They put the R and G channels of the Normal map into Alpha and G.  

Channel B should be white, instead it's has what may be the actual specular map, I'm not sure really:


Channel R has a different map, PBR metalness maybe? (that splotch on the neck, that's why the normal seemed off)


Ok, so basically, you need to fill channel B with white (255), and move Alpha channel to R channel. Do your magic as you please.
Then you'll have a proper normal map:


Save it to disk as DDS (if using Intel Textureworks, save as Color/ BC1, Blender doesn't read DX10 formats), and reload the model in blender (it will use your custom DDS this time.)

no more odd splotch:

(yes it's a chrome chicken, you can adjust the specular of course, I just use defaults    )

I would probably recommend dumping the contents of the HD texture archive into the Main archive directory, so highest rez textures are used.  But there are still a number of missing textures and given the "*.material.bin" files are 1k to 2k in size, I can't say with certainty they were all extracted.
If anything is missing, it will simply skip the step for that item. I hope the unpacker is eventually updated to extract everything.

Enjoy.

Edit: new version Below.
## Post #64
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-24T09:24:33+00:00
- Post Title: Re: Far Cry Primal models

hmm, that's strange. the new plugin version is causing an error on import.   
with and without a light in the scene.

[https://picload.org/image/roagclrw/blender_error.jpg](https://picload.org/image/roagclrw/blender_error.jpg)
## Post #65
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T17:51:11+00:00
- Post Title: Re: Far Cry Primal models

> Reply from TheMask85
>
> hmm, that's strange. the new plugin version is causing an error on import.   
with and without a light in the scene.

https://picload.org/image/roagclrw/blender_error.jpg

it is strange, since that line changes the context to Object, which is a command that should work in any context.    So it saying 'wrong context' makes no sense at all. I'd recommend deleting the whole plugin folder and re-installing the plugin.

C:\Users\Mask\AppData\Roaming\Blender Foundation\Blender\2.78\scripts\addons\io_scene_FCP directory is the one to delete.

Barring that fixing it, i'd then have to say something is wrong with your copy of blender. I tested on 2.77 and 2.78, and works fine on both.
## Post #66
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-24T18:28:55+00:00
- Post Title: Re: Far Cry Primal models

man, i hate to be that guy ... but ...   

- if i change anything of the "new scene" (like deleting the cube for example), the importer will spit out an error and won't let me import a mesh
- the skeleton is off now
and the vertex normals are weirdly rotated. means - if you look at the mesh from the front, it will look fine but as soon as you change the camera you can see the lighting is off due to "weirdly rotated normals". see how the arms are rather dark while the front of the body is correct?



i re-installed blender (and deleted remaining folders), just to be sure - so it's a brand new installation with nothing changed in the app itself.
sorry for the trouble.
## Post #67
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T20:25:13+00:00
- Post Title: Re: Far Cry Primal models

Ok so you put in a cube then delete it. That's an important detail you didn't mention the first time. Now I can reproduce.

Also it seems the skeleton problem is only with that particular model. So i'll have to see why it's special. Stay tuned.

As for Normals, as I stated, I have no way to know what is 'right' or not. They appear smooth across edge breaks, which is the only indication I have they are 'right'. I can't say anything else beyond that. there is no original sample from the studio for me to compare against, nor a manual to tell me their encoding method.  All of this stuff is guess work. It's the best I can do. It may be correct (because many studios do bake in artificial normal directions to simulate lighting effects), or it may not. I simply have absolutely no way to know one way or the other. (and this is why generally I do not import game normal, it's a complete crapshoot). From my best knowledge and observations, it appears they are right.

This is what completely mis-interpreted normal looks like:


So you see the difference. The fact it's actually smooth is the one case of order out of chaos. And laws of entropy say, order never happens by chance.
## Post #68
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-24T20:39:01+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> Ok so you put in a cube then delete it. That's an important detail you didn't mention the first time. Now I can reproduce.

no i'm talking about the "startup scene". there's a light, a camera and a cube. and as soon as i change anything there (deleting this stuff before import - because it's not just unneeded but rather unwanted), i can't import.

about the vertex normals, don't sweat it. yeah, the edges are gone. these are just rotated. you're doing great work here!!
## Post #69
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T21:03:14+00:00
- Post Title: Re: Far Cry Primal models

the error will be fixed, I know why it's happening now. in fixing one issue I made another.   
P.S. delete the cube, save as "Startup Scene", then you don't have to delete it anymore.

And I see what is going on with the skeleton, that file is special:


All models up til now had this quaternion as 0,0,0,1 which means 'no rotation'. So I just ignored it. But Mr. nean seems to have 0,0,0.1401341,0.9901325, which is exactly 16.11 degrees of rotation on Z axis. which is exactly the error seen. So I just need to factor in this value and problem solved.  I see the vector also has a very tiny value. I may need to see if it's a translation. New version shortly.
## Post #70
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T21:43:15+00:00
- Post Title: Re: Far Cry Primal models

Ok, invalid context problem is fixed. Won't be any problems with deleting objects.

Skeleton rotation fixed:


And I fixed an unreported issue I noticed with alpha transparency settings for materials when no textures are found. Fixed.   

Enjoy.

Edit: New version below.
## Post #71
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-24T21:55:30+00:00
- Post Title: Re: Far Cry Primal models

thank you for your steady support! really appreciated.
well, you'll probably hate me now ...

[https://picload.org/image/roadacaw/blen ... _v1.04.jpg](https://picload.org/image/roadacaw/blender_error_v1.04.jpg)

that goes for almost all the european models :/
also mesh isn't bind to the skeleton anymore for the ones with the rotated bones.
## Post #72
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T22:44:27+00:00
- Post Title: Re: Far Cry Primal models

> Reply from TheMask85
>
> thank you for your steady support! really appreciated.
well, you'll probably hate me now ...

https://picload.org/image/roadacaw/blen ... _v1.04.jpg

that goes for almost all the european models :/
also mesh isn't bind to the skeleton anymore for the ones with the rotated bones.

Seems the *material.bin file format is more convoluted than it first seemed. Will take awhile.

As for not binding skeleton, I don't see that on "Nean" which was a rotated model. If you mean no binding on the ones that crash the script, that's normal, the script can't finish the job. If you mean something else, give me an example.
## Post #73
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2017-01-24T22:49:00+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> the script can't finish the job

nah, that's probably why. since the ones without error message and correct skeleton are bind just fine.
## Post #74
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-25T00:51:17+00:00
- Post Title: Re: Far Cry Primal models

Ok, crafter guy now loads and processes materials properly. I changed how it determines what texture is specular/diffuse/normal, it should do a better job of guessing.

Edit: new version below.
## Post #75
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-25T07:12:26+00:00
- Post Title: Re: Far Cry Primal models

Updated version. Fixed some problems with material.bin processing, a mesh validation issue, a skeleton offset issue, and added a new feature:



You can now check "Use Existing Skeleton" at the import pane, and instead of building a skeleton with the import, it will use the existing skeleton. If an existing skeleton doesn't exist, it will go ahead and build one (if the model has one).  Undestand it's not smart, so if you load in two meshes that don't use the same skeleton and use this feature, it will put them on the same skeleton anyway. So use wisely.  It's off by default.
[io_scene_FCP.zip](https://xentaxbackup.github.io/file/12286_io_scene_FCP.zip)
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-25T19:04:51+00:00
- Post Title: Re: Far Cry Primal models

I have good news and bad news.

Bad news is I found a mistake in my unpacker, so many files were unpacked a little wrong. It usually concerned a few bytes in the end, so it shouldn't affect models convertion. But to be safe, you have to unpack the whole game again.

Also I think you'll need not-compressed files anyway, so I'll update the tool soon. The low mip of blue goats were not compressed, and 40kbytes in size. Yet small models are all compressed. So the game decides whether compress the file or not based on its compression level, not size.

Good news is that I corrected oasis converter so now it converts both FC4 and FCP files.
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-25T21:01:29+00:00
- Post Title: Re: Far Cry Primal models

I'm not familiar with the Oasis converter. what is that?
## Post #78
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-25T23:19:55+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I'm not familiar with the Oasis converter. what is that?[oasisstrings.bin](http://forum.xentax.com/viewtopic.php?p=126332&hilit=oasisstrings#p126332), basically the dialog text in the game.

@daemon1 awesome work you're doing! The game contains a poo-load of files, it's quite something to make sense of, modding-wise. Luckily, there's a lot of overlap with Far Cry 4!
## Post #79
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-26T17:19:31+00:00
- Post Title: Re: Far Cry Primal models

Oasis converter for Far Cry Primal.

There are some tricks in making this work. The tool code had lots of unneeded complications. This is why I don't like messing with other people's code. So I'm trying to make it as easy as possible to me. You will need to do some manual work.

How to use it:

1. Convert BIN to XML as usual
2. Find line with 0xAEE923DE code and delete it. (This new format somehow has 1 section without lines in it. This is causing the old tool to fail. Maybe it's needed or something, then I'll have to find a way to handle it.)
3. Make changes you need
4. Convert file back to BIN
5. Add "table_fcp" table to the end of the file (This can be done in any hex editor or commander tool, or with command line such as "copy /b oasis.bin + table_fcp oasiswithtable.bin")
6. Pack oasis file into FAT/DAT with my packer tool.

Important note. Patch.fat/dat is loaded before patch_sound.fat/dat so you have to find some other package to replace text, or remove old file from patch. I did this by finding the file hash in patch.fat and changing it. The hash is (F3 F8 E3 5D 29 FD BD F2) for english file. Changing any byte here will "mask" the file so game won't find it.
[oasis_fcp.rar](https://xentaxbackup.github.io/file/12301_oasis_fcp.rar)
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-26T17:27:34+00:00
- Post Title: Re: Far Cry Primal models

The version for FC4. Same usage.
[oasis_fc4.rar](https://xentaxbackup.github.io/file/12302_oasis_fc4.rar)
## Post #81
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-26T18:33:41+00:00
- Post Title: Re: Far Cry Primal models

And latest packer/unpacker.

- No changes to packer. 
- Packer now correctly unpacks ALL files, including 1-byte sectors, and there are MANY of them, beware!

Included additional xml file with only 1 name for english oasis. Unpacker will use all xml files present in directory, so you can add your names if you find any.
[fcp_tools.rar](https://xentaxbackup.github.io/file/12303_fcp_tools.rar)
## Post #82
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T19:02:04+00:00
- Post Title: Re: Far Cry Primal models

i'll try this new unpacker and make sure it doesn't harm the model importer. If all is good I guess I will start breaking ground on a model exporter. I think I have a nearly complete understanding of this format, enough I can pull that off. I will do my best at any rate.
## Post #83
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T22:04:31+00:00
- Post Title: Re: Far Cry Primal models

the original unpacker came with a file named primal_main.xml, but this version doesn't have that file. And seems it outputs no filenames, only hash names?
## Post #84
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-27T04:23:39+00:00
- Post Title: Re: Far Cry Primal models

that file is big, there was no need to reupload it. Add old xml file to get names.
## Post #85
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-27T22:41:34+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> that file is big, there was no need to reupload it. Add old xml file to get names.For people wondering where that XML is at, see [here](http://forum.xentax.com/viewtopic.php?p=126394#p126394). But you already know, right Fino?
## Post #86
- Username: Fino
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 28, 2017 7:38 am
- Post datetime: 2017-01-27T23:55:45+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> daemon1 wrote:that file is big, there was no need to reupload it. Add old xml file to get names.For people wondering where that XML is at, see here. But you already know, right Fino?

Heya, I am new here in this forum 

To the quote, no I wasnt wondering where it is. I just saw the names.xml in this existent one and added all lines from primal_main.dvs 

But in another forum someone told me I should have a look here, since here is a tool for extracting the archives from FarCry Primal.
I was creating an own tool too until I saw yours now, daemon1. I dont even have an exe file, just my raw python script - but with a GUI

Now I was wondering, if I could maybe use your existent tools and create a GUI for it?
I am asking this, because my script for decrompressing the dat/fat files has a bug, which could create corrupted files... and tbh because you allready made a tool for this, there is no need anymore for me to fix or create a new one 

Cheers, Fino

EDIT:
btw, your tool works like a charm - good work!
## Post #87
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-01-28T18:04:58+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> 5. Add "table_fcp" table to the end of the file (This can be done in any hex editor or commander tool, or with command line such as "fc/b oasis.bin + table_fcp oasiswithtable.bin")
"fc/b oasis.bin + table_fcp oasiswithtable.bin" - it's for file comparing, not merging, and it thinks "+" symbol is file...

Upd: I googled it out, right command is: "copy/b oasis.bin +table_fcp oasiswithtable.bin"
## Post #88
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2017-01-28T18:06:20+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> And latest packer/unpacker.

- No changes to packer. 
- Packer now correctly unpacks ALL files, including 1-byte sectors, and there are MANY of them, beware!

Included additional xml file with only 1 name for english oasis. Unpacker will use all xml files present in directory, so you can add your names if you find any.

Hi, amazing work!

Thx
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-28T18:21:40+00:00
- Post Title: Re: Far Cry Primal models

> Reply from Andrakann
>
> 
Upd: I googled it out, right command is: "copy/b oasis.bin +table_fcp oasiswithtable.bin"
ok, corrected

> Reply from Fino
>
> Now I was wondering, if I could maybe use your existent tools and create a GUI for it?
yes you can.
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-28T18:27:21+00:00
- Post Title: Re: Far Cry Primal models

Alright, I think that's enough for now. Can be better to have dictionary as plain text, and add more names, so maybe later if I will have time. Enjoy the tools.

Also I didn't mention that oasis file will be probably changed again in next patch, and you need to get the new table from the end of original file...
## Post #91
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-29T04:17:19+00:00
- Post Title: Re: Far Cry Primal models

ok I've verified the new unpacker did change the model format slightly. Because the UV scale/offset is near the end of the file, it's location has changed. I'm surprised nobody noticed this. I'm concerned because at least one model appears corrupted, i'm worred the new unpacker is introducing errors. But i'll have to unpack with the old unpacker to do some comparisons and see.

Edit: it's not a corruption, just a change near the end of the file. New version to work with the new unpacker attached.
[io_scene_FCP.zip](https://xentaxbackup.github.io/file/12328_io_scene_FCP.zip)
## Post #92
- Username: FartingSquirrel
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 06, 2016 8:36 am
- Post datetime: 2017-01-30T11:53:08+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Fino wrote:Now I was wondering, if I could maybe use your existent tools and create a GUI for it?
yes you can.

That'd be awesome!
## Post #93
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-02T12:20:13+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Alright, I think that's enough for now. Can be better to have dictionary as plain text, and add more names, so maybe later if I will have time. Enjoy the tools.Great, finally found the time to extract the files with the new tools! They're working nicely! 

Some things I noticed though, that slightly differ from the Dunia toolset's workflow:
The unpacker seems to unpack to the current working dir? If you could add a parameter that defines the output dir for unpacking files to, It would be less cluttering.As unpacking occurs in the current working dir, I'm used to making a separate dir outside of the game location, with symlinks to the game's dat/fat files (to save diskspace). However, the tools don't support symlinks (windows' mklink): "Unhandled Exception: System.IO.IOException: The name of the file cannot be resolved by the system.".
The unpacker also loads the xml definitions from the current working dir, rather than the tool's dir. Same thing for the dat/fat specified. So currently, the tool *and* accompanying xmls *and* dat/fats must all be copied to a new dir in order to unpack it from there.Oh, and the unpacker loads definition XML's recursively. Meaning if unpacking a dat produces xml files, running the unpack again will try to load those XML files and error out I think.

But it's no biggie, I'm happy to be extracting already! But if you ever have a chance to work on them again...
## Post #94
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-02T12:46:52+00:00
- Post Title: Re: Far Cry Primal models

Another thing I noticed, is that unpacking file entries without a dirname will fail ("Unhandled Exception: System.ArgumentException: Path cannot be the empty string or all whitespace."). For example, try unpacking common.dat with this XML entry:
```

```
 Changing this entry to ".\soundregions.xml" in the XML would obviously be no fix, as the CRC64 value of the string will differ.
## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-02T16:07:32+00:00
- Post Title: Re: Far Cry Primal models

Yes having all in current dir was the fastest and simplest way to do.

But ok, here's a new version for you. Now you can go to current dir, run the tool from somewhere else and specify FAT file somewhere else. So you can place everything in 3 different dirs if you like:

1. dir with the tool
2. dir with fat/dat pair
3. current dir where unpacked files will go (also must have xml files for names)

Recursive xml search was one on purpose, because if more names will be found in files, this is only better.

As for "unpacking file entries without a dirname", do you think the game has some files without a dirname?

UPD. new versions below.
## Post #96
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-02T18:28:39+00:00
- Post Title: Re: Far Cry Primal models

Wow, thank you! really cool! 

> Reply from daemon1
>
> As for "unpacking file entries without a dirname", do you think the game has some files without a dirname?Yeah, I suspect that error only even occurred because of that. I assume your tool parses the name attribute and 'splits' it into a dir- and filename. In case of common.dat there's a soundregions.xml in the root. Possibly a credits.xml and version.xml too (as was the case in Far Cry 4, in the patch datfile as well).

Should be easily fixable by checking if the parsed dirname is empty, and if so, add a '.\' in its place?
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T10:25:14+00:00
- Post Title: Re: Far Cry Primal models

New versions. The unpacker will now work with "file entries without a dirname".
The packer will also pack "hashed" files with no names. Unfortunately the game doesn't work correctly with full repacked packages, for example, common.dat. No idea why is that.

Can anyone confirm oasis tools working? Its time to gather all tools and put them in title post. I need to know if it works.
[fcp_tools.rar](https://xentaxbackup.github.io/file/12396_fcp_tools.rar)
## Post #98
- Username: lukamas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 07, 2015 3:12 am
- Post datetime: 2017-02-07T01:31:37+00:00
- Post Title: Re: Far Cry Primal models

Hey guys, is anyone making an exporter for far cry 4, I really want to mod this game, and It would be my dream to make a new object or asset for the map editor for far cry 4,

If anyone makes an exporter for Far Cry 4, let me know, I would be more than excited!

thanks in advance.
## Post #99
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-07T05:45:43+00:00
- Post Title: Re: Far Cry Primal models

> Reply from lukamas
>
> Hey guys, is anyone making an exporter for far cry 4, I really want to mod this game, and It would be my dream to make a new object or asset for the map editor for far cry 4,

If anyone makes an exporter for Far Cry 4, let me know, I would be more than excited!

thanks in advance.

Far Cry 4 was done years ago. Just search the forums.
## Post #100
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-07T12:31:20+00:00
- Post Title: Re: Far Cry Primal models

> Reply from lukamas
>
> Hey guys, is anyone making an exporter for far cry 4, I really want to mod this game, and It would be my dream to make a new object or asset for the map editor for far cry 4You may want to head over to [http://farcrymods.freeforums.net/board/2/mod-far-cry-4](http://farcrymods.freeforums.net/board/2/mod-far-cry-4) and/or read [this post there](http://farcrymods.freeforums.net/thread/431/trying-documentation-where-start-modding?page=1&scrollTo=3050). 

I'm currently sifting through all the FCP files, uncovering filenames as I go. Will be releasing an XML file to use with daemon1's unpacker, which coincidentally also names some more Far Cry 4 files in the Dunia tools. Plus I'm working on updating Dunia's object definitions, first Far Cry 4, then Primal's.
## Post #101
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-07T17:30:22+00:00
- Post Title: Re: Far Cry Primal models

There's no need to 'go' anywhere. If people just search, you'd see what I said was true:
[viewtopic.php?f=16&t=12339](http://forum.xentax.com/viewtopic.php?f=16&t=12339)
Complete unpackers and model extraction, etc.  I mean Dunia Tools is fully supported for 4, which was what was talked about at the start of this thread.  All the filenames are already found. Redoing all the work is just wasteful.
## Post #102
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-07T18:50:47+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> There's no need to 'go' anywhere. If people just search, you'd see what I said was true:
viewtopic.php?f=16&t=12339
Complete unpackers and model extraction, etc.  I mean Dunia Tools is fully supported for 4, which was what was talked about at the start of this thread.  All the filenames are already found. Redoing all the work is just wasteful.Sorry, but the thread you referenced only deals with exporting models from FC4, not creating new game assets for use in the Far Cry 4 level editor and game as lukamas asked. Hence why I linked to the forum discussing modding Far Cry 4 as a game.

Also, as far as I know, Dunia currently has only 29% (146734/492208) filenames covered. If you could please point me to a full filelist for Far Cry 4's files, my work will finally be wasteful.
## Post #103
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-07T20:52:45+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Can anyone confirm oasis tools working? Its time to gather all tools and put them in title post. I need to know if it works.I tried the oasis tool for Far Cry Primal, and conversion seemed fine for English, German and Czech. Bins converted to XML, and back again. With the string replacement and table copy, as well as the patch.fat patch, it seems to work fine ingame! 

But, there may be something weird with the FC4 Oasis tool. On my end, it's working on the oasisstrings_compressed.bin for the english language, from the latest patch.dat. So far so good! However, trying to convert let's say Czech or Dutch back to bin seems problematic. For example:

1. Running "JGR.Dunia2.ConvertXml.fc4p.exe --osx oasisstrings_compressed.bin", creates oasisstrings_compressed_converted.xml
2. I open the XML, and remove the line "  <section name="0xAEE923DE" />", and the newline at the end of that line (that shouldn't matter, right?).
3. I run "JGR.Dunia2.ConvertXml.fc4p.exe --osb oasisstrings_compressed_converted.xml", it produced a "oasisstrings_compressed_converted_compressed_converted.bin" file, @ 30KB instead of 1.34MB. It throws an exception:
Unhandled Exception: System.ArgumentException: Source array was not long enough. Check srcIndex and length, and the array's lower bounds.
   at System.Array.Copy(Array sourceArray, Int32 sourceIndex, Array destinationArray, Int32 destinationIndex, Int32 length, Boolean reliable)
   at System.Array.Copy(Array sourceArray, Array destinationArray, Int32 length)
   at JGR.Dunia2.FileFormats.OasisstringsCompressedFile.OasisSection.Serialize(Stream output, Endian endian)
   at JGR.Dunia2.FileFormats.OasisstringsCompressedFile.Serialize(Stream output)
   at JGR.Dunia2.ConvertXml.Program.Main(String[] args)

For me personally, I'll probably only mod the english file to remove annoying prompts on the screen. perhaps that will work without issues. But if others want to make a translation mod, there may be problems down the road, I'm guessing it's due to some characters/encoding of the XML file or something? If you need more language files for testing, I upped them all [here](http://steve.farcry.eu/files/FarCry4_110_oasisstrings.zip).
## Post #104
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-08T00:50:35+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> volfin wrote:There's no need to 'go' anywhere. If people just search, you'd see what I said was true:
viewtopic.php?f=16&t=12339
Complete unpackers and model extraction, etc.  I mean Dunia Tools is fully supported for 4, which was what was talked about at the start of this thread.  All the filenames are already found. Redoing all the work is just wasteful.Sorry, but the thread you referenced only deals with exporting models from FC4, not creating new game assets for use in the Far Cry 4 level editor and game as lukamas asked. Hence why I linked to the forum discussing modding Far Cry 4 as a game.

Also, as far as I know, Dunia currently has only 29% (146734/492208) filenames covered. If you could please point me to a full filelist for Far Cry 4's files, my work will finally be wasteful.

he asked for an exporter. And that is what is in the thread. It's assumed he'd do any converting to assets for the editor himself. But if you want to do that work for him, have at it.

And it seems my copy has 33% of filenames, so you're correct, it's not all. It's been awhile since I messed with FC4.
## Post #105
- Username: lukamas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 07, 2015 3:12 am
- Post datetime: 2017-02-08T01:59:58+00:00
- Post Title: Re: Far Cry Primal models

guys, I was looking on this site [http://steve.farcry.eu/?log=fcmsig](http://steve.farcry.eu/?log=fcmsig), at the "FC4 Editor Selected Objects Export/Import" is that under development, or what is that all about, when modding Far Cry 4
## Post #106
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-08T13:59:31+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> he asked for an exporter. (...) It's assumed he'd do any converting to assets for the editor himself.
> Reply from lukamas
>
> Hey guys, is anyone making an exporter for far cry 4, I really want to mod this game, and It would be my dream to make a new object or asset for the map editor for far cry 4 

As for modifying Far Cry 4, this thread's topic is more about (unpacking) Far Cry Primal, and specifically its models. Far Cry 4 is only referenced because the games are so much alike, filesystem-wise.

If you're looking for modding the FC4 editor and game, the forum I linked previously is a good place to start. [Fino](http://farcry.eu), [Janne](https://fc4modding.janne252.com/index.php?area=mod) and [Predaator](http://www.nexusmods.com/farcry4/mods/33/?) have some nice mods, adding (Far Cry 3 based) objects to the Far Cry 4 editor. We're pushing the limits of custom maps even further. Perhaps one day we can add models and animations to the game, but for now we're reusing assets from the vanilla game to make sure everyone can play the maps that we're making.

The 'Selected Objects Export/Import' does not export models from the game to 3D software, but merely allows for saving object placement data in maps from one FC editor to another. For example, see [Fino's thread](http://farcrymods.freeforums.net/thread/403/self-build-objects-object-inventory) and understand that the 'models' used in those screenshots are not newly created/imported models, but instead constructed in the FC4 editor itself by placing many individual other objects together in the map to appear as new object.
## Post #107
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-08T15:36:49+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> daemon1 wrote:Can anyone confirm oasis tools working? Its time to gather all tools and put them in title post. I need to know if it works.I tried the oasis tool for Far Cry Primal, and conversion seemed fine for English, German and Czech. Bins converted to XML, and back again. With the string replacement and table copy, as well as the patch.fat patch, it seems to work fine ingame! 

But, there may be something weird with the FC4 Oasis tool.

I may check that later. But now its time to move all tools to title post. Let me know if I forgot anything. If you have more FCP filenames to add, I will add the link.
## Post #108
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-10T14:08:10+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Now you can go to current dir, run the tool from somewhere else and specify FAT file somewhere else. So you can place everything in 3 different dirs if you like:

1. dir with the tool
2. dir with fat/dat pair
3. current dir where unpacked files will go (also must have xml files for names)

Recursive xml search was one on purpose, because if more names will be found in files, this is only better.Just a note: it seems like you can't have 1 master tool dir with both the tool and all filename XMLs: the XML filelist definition files still must be placed in the current dir.

Also, I'm running the tool from C:, on files on my D:. Doing the following will however NOT work:
```
CD FarCryPrimal\data_win32
C:
CD FCtools
fcp_unpack.exe D:common.fat

```
The exe seems to look for D:\common.fat instead of the D:\FarCryPrimal\data_win32\common.dat as expected. So, you'd have to instead call it like:
```
CD FCtools
fcp_unpack.exe D:\FarCryPrimal\data_win32\common.fat
```
This has the added benefit of using the XML definitions from the FCTools dir, but the downside of unpacking the fat in the tools dir.
## Post #109
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-10T15:15:24+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> but the downside of unpacking the fat in the tools dir.

No, you don't have to unpack the fat in the tools dir. There's no such a thing as two current dirs (for each drive), current dir is only ONE dir. 

```
C:\fctools\fcp_unpack.exe D:\FarCryPrimal\data_win32\common.fat
```


This is what you need. Is it?
## Post #110
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-10T17:20:28+00:00
- Post Title: Re: Far Cry Primal models

> Reply from daemon1
>
> Code: Select allC:\fctools\fcp_unpack.exe D:\FarCryPrimal\data_win32\common.fat
This is what you need. Is it?Ideally, yes, the statement you suggest is the one I would want (and I bet the way you intended it). However, it does not seem to use C:\fctools\*.xml for the XML's detailing the file names, so you end up needing to copy those in the current dir for the actual filenames to be decoded. If it would check alongside the .exe for the XML files, the tool would be perfect!

Re: the working dir: the command prompt should remember a "current dir" per drive letter, and a single "current working dir". Your tool doesn't seem to be aware of the prior. I.e. see how this command prompt snippet works:
```
 Directory of D:\
10/02/2016  11:30    <DIR>          FarCry4
10/02/2017  14:54    <DIR>          FarCryPrimal
            2 Dir(s)

C:\Windows>CD D:\FarCryPrimal
C:\Windows>dir D:
 Directory of D:\FarCryPrimal

08/01/2017  22:34    <DIR>          .
08/01/2017  22:34    <DIR>          ..
08/01/2017  22:34    <DIR>          bin
07/02/2017  21:23    <DIR>          data_win32
08/01/2017  22:34    <DIR>          Output
08/01/2017  11:40    <DIR>          Support
08/01/2017  22:23            25,189 unins000.dat
08/01/2017  21:54           990,885 unins000.exe
               2 File(s)      1,016,074 bytes
               6 Dir(s)

```
See how the 2nd "Dir D:" picks the D:\FarCryPrimal dir instead of the D:\? that's what I was referring to. In that command prompt state, D:data_win32\common.fat does resolve to the fat, but somehow your tool doesn't. Perhaps the shell environment needs to be explicitly imported, or it requires an OS system call to expand the parameter to a full path. I haven't encountered this behavior with a console app before, so to me it's odd. But not unworkable.
## Post #111
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-10T18:00:29+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> Perhaps the shell environment needs to be explicitly imported, or it requires an OS system call

No, it was because I added an extra "\" inside a path. Try this one. Must work with your  "Dir D:" now and get XML from tool dir.
[fcp_unpack.rar](https://xentaxbackup.github.io/file/12430_fcp_unpack.rar)
## Post #112
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-10T18:52:07+00:00
- Post Title: Re: Far Cry Primal models

Sweet! Almost there, the unpack now seems to load the XMLs from the tools dir, but there's another backslash messing up this time:

```

Unhandled Exception: System.IO.FileNotFoundException: Could not find file 'c:\games\Far Cry Primal\data_win32common.dat'.
```
Backslashes can be annoying sometimes eh?
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-10T19:07:10+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> Sweet! Almost there, the unpack now seems to load the XMLs from the tools dir, but there's another backslash messing up this time

ok this means that "\" was needed. It seems impossible to make it work in both cases. I'm not going to start writing syntax analyzers here. So I should leave it either this, or like it was before.
## Post #114
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-10T23:41:37+00:00
- Post Title: Re: Far Cry Primal models

Haha, funny how that is rocket science compared to all the work you've done unpacking the game & handling the models! 

Published an XML with more FCP filenames to [http://steve.farcry.eu/](http://steve.farcry.eu/) ([direct link](http://steve.farcry.eu/files/fcp_steve64_generated_filenames_v1.0.zip)).
## Post #115
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-24T10:45:53+00:00
- Post Title: Re: Far Cry Primal models

Does anyone have a structure definition for Far Cry (4 / Primal) material.bin files?
## Post #116
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-24T21:22:36+00:00
- Post Title: Re: Far Cry Primal models

I have something you can start from:

```
//--- 010 Editor v7.0.2 Binary Template
//
//      File: UBisoft Primal Mat.bt
//   Authors: Volfin
//   Version: 0.1
//   Purpose: Template for FarCry Primal material.bin files
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------
struct MATHEADER {
    char head[4];
    unsigned int unk1;
    unsigned int unk2;
    unsigned int unk3;
    unsigned int unk4;
    unsigned int unk5;
    unsigned int unk6;
    unsigned int unk7;
    unsigned int unk8;
    unsigned int unk9;
    unsigned int unk10;
    unsigned short unk11;
    unsigned char name_len;
    char name[name_len];
    unsigned int hash;
    unsigned char name_len2;
    char name2[name_len2];
    byte j1;
    unsigned int f;
    byte j2;
    unsigned int g;
    byte wuh_len;
    char h[wuh_len];
    unsigned int i; // for normal
    //char i[28];
    unsigned char name_len3;
    char name_Specular[name_len3];
    byte o1;
    unsigned int k;
    byte o2;
    unsigned int l;
    byte o3;
    unsigned int m;
    unsigned int n;
    unsigned char name_len4;
    char name_Normal[name_len4];
    byte t1;
    unsigned int p;
    byte t2;
    unsigned int q;
    byte t3;
    unsigned int r;
    unsigned int s;
    unsigned char name_len5;
    char name_Diffuse[name_len5];
    byte y1;
    unsigned int u;
    byte y2;
    unsigned int v;
    byte y3;
    unsigned int w;
    unsigned int x;
    unsigned char name_len6;
    char name6[name_len6];
    byte aa1;
    unsigned int bb;
    byte aa2;
    unsigned int cc;
    byte aa3;
    unsigned int dd;
    unsigned int ee;
    unsigned char name_len7;
    char name7[name_len7];
    byte ff1;
    unsigned int gg;
    byte ff2;
    unsigned int hh;
    byte ff3;
    unsigned int ii;
    unsigned int jj;
    unsigned char name_len8;
    char name8[name_len8];
    byte kk1;
    unsigned int ll;
    byte kk2;
    unsigned int mm;
    byte kk3;
    unsigned int nn;
    unsigned int oo;
    unsigned char name_len9;
    char name9[name_len9];
    byte pp1;
    unsigned int qq;
    byte pp2;
    unsigned int rr;
    byte pp3;
    unsigned int ss;
    unsigned int tt;
    unsigned char name_len10;
    char name10[name_len10];
    byte uu1;
    unsigned int vv;
    byte uu2;
    unsigned int ww;
    byte uu3;
    unsigned int xx;
    unsigned int yy;
    unsigned char name_len11;
    char name11[name_len11];
} header;

```


I was only interested in getting texture paths out of it for my importer, so I only worked it out that far. It's by no means complete or meaningful in any other way. And Just because I used an Integer for the stuff in between, doesn't mean it is an Integer. I just used that to skip over bytes to get to the next texture. Also even though I stopped at 10 texture records, there's a lot more, usually unused, but not always. It goes on and on for quite a number of records. Since I only wanted Diffuse/Normal/Specular, Searching through the first 10 was usually sufficient to find them.
## Post #117
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-24T23:18:35+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I have something you can start from:
Thanks, that's what I was looking for. Saves me from doing some work again. 

Just wondering, does your importer/exporter do anything with the "wuh" string? I'm trying to determine its effects on the game, as it can be one of several options identified.
Would that name possibly impact the rendering, physics, or anything like that? As you're referring to Normal, Diffuse and Specular in a different part of the file, would the wuh influence how these values are interpreted or something?
## Post #118
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-25T00:19:13+00:00
- Post Title: Re: Far Cry Primal models

can you give an example? I'm unfamiliar with the 'wuh' string.
## Post #119
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-02-25T17:17:41+00:00
- Post Title: Re: Far Cry Primal models

Well, the 'wuh' string from that script seems to be any of the following values: Animal_Fur, Animal_Skin, BigLeaf, Blended, Cloth, Cloth_FC3, CloudDome, Decal, Detail, DynamicWater, EffectEmissive, EffectLit, Error, EyeAdvanced, FakeTerrain, Generic, Generic_FC3, Generic_FC3_LQ, Grass, GroundVegetation, Hair, Highlight, Ice, InkAndPaint, Leaf, Metal, Metal_Advanced, Ocean, RealtreeTrunk, Road, ShangrilaOcean, Simple, Skin, Skin_Advanced, Skin_Cinematic, Skin_FC3, SkyDome, StarSphere, Stream, Unlit, Vegetation, Vehicle, VertexColor, Vistas, Water, WaterRiver, or Weapon.

As we're trying to import Far Cry 3 assets into Far Cry 4, I was wondering what these strings related to a Material may affect in the game. I'm not too familiar with modeling/texturing, but I assume a material.bin would influence how light refracts on the object. Or would there be any other 'behavior' attached to a material, like physics-related information for example?
## Post #120
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-25T23:37:18+00:00
- Post Title: Re: Far Cry Primal models

I finally figured out you meant the name of one of the variables in my 010 Template. I was a bit lost there for a minute.   

Yeah I was a bit puzzled when I first found those non-ascii text entries. I just skip over them, I have no idea what they do. I recall I named it "wuh" for 'whut the hell" is this lol.
## Post #121
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-23T03:31:45+00:00
- Post Title: Re: Far Cry Primal models

I realise this thread's been inactive for a while, but with Last of Us and now Homefront Revolution gone through, I'm finally getting back to this and going through the files. Can someone help me out with something (I'm guessing either Volfin or Daemon will know this), but after I use the initial set of tools, I'm able to extract a lot of the files using the unpacker, but there are ones that don't appear -- I can't find a lot of the character models, or things like the sabretooth tiger. Is it something to do with the XML's? Do I need something more than just the "names.xml" that comes with the tools?

## EDIT ##

Never mind! Figured it out!
## Post #122
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2017-05-25T19:55:25+00:00
- Post Title: Re: Far Cry Primal models

Hi, how can we import animations from Far Cry 4 or Primal? their animations are amazing!
## Post #123
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2017-07-11T10:02:31+00:00
- Post Title: Re: Far Cry Primal models

Hi daemon1

I did everything as you described it, but the owl controls is missing. [http://i63.tinypic.com/mij3tj.png](http://i63.tinypic.com/mij3tj.png)

Original: [https://youtu.be/_ifOceaGNxI?t=12s](https://youtu.be/_ifOceaGNxI?t=12s)
## Post #124
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2017-11-26T21:18:29+00:00
- Post Title: Re: Far Cry Primal models

fcp_unpack crashes when i drop a fat. file onto it
Is the tool outdated or something?

C:\Users\Jakob>C:\Users\Jakob\Desktop\Primal\fcp_unpack.exe "D:\Steam\steamapps\common\Far Cry Primal\data_win32\common.fat"

Ikke-afviklet undtagelse: System.IO.FileNotFoundException: Filen 'D:\Steam\steamapps\common\Far Cry Primal\data_win32common.dat' blev ikke fundet.
Filnavn: 'D:\Steam\steamapps\common\Far Cry Primal\data_win32common.dat'
   ved System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   ved System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy)
   ved System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   ved System.IO.FileStream..ctor(String path, FileMode mode)
   ved LZ4Sharp.LZ4Sharp.Main(String[] args)
## Post #125
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-11-27T00:38:17+00:00
- Post Title: Re: Far Cry Primal models

Yeah, there are several versions, I think one had the bug with the missing backslash. Try another build.
## Post #126
- Username: lionfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 27, 2017 3:58 pm
- Post datetime: 2018-02-10T04:41:56+00:00
- Post Title: Re: Far Cry Primal models

Hey guys. I know this is an old thread but I've been trying to get some statics out of this game forever, and I'd appreciate any help.

I get this error when I try to open most of the files in Blender. When I get the error, the model is usually okay but the UVs are not right. [](https://ibb.co/hoqYT7)
Other folk seem to be getting decent results out of it. Perhaps I might be doing something wrong?

Thanks.
## Post #127
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-10T04:57:32+00:00
- Post Title: Re: Far Cry Primal models

> Reply from lionfx
>
> Hey guys. I know this is an old thread but I've been trying to get some statics out of this game forever, and I'd appreciate any help.

I get this error when I try to open most of the files in Blender. When I get the error, the model is usually okay but the UVs are not right. 
Other folk seem to be getting decent results out of it. Perhaps I might be doing something wrong?

Thanks.

It's possible the file type you're trying to import isn't supported yet. I'd need some example files to look at.
## Post #128
- Username: lionfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 27, 2017 3:58 pm
- Post datetime: 2018-02-10T05:18:54+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> 
It's possible the file type you're trying to import isn't supported yet. I'd need some example files to look at.

Hi, thanks a lot for getting back to me. I uploaded three examples here. [http://s000.tinyupload.com/?file_id=752 ... 9712668245](http://s000.tinyupload.com/?file_id=75262166919712668245)
## Post #129
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-10T20:50:27+00:00
- Post Title: Re: Far Cry Primal models

I tried your 3 examples, all loaded fine, without error. And have UVs included.







So I don't really know what to say, other than are you sure you have the latest version of the importer?
## Post #130
- Username: lionfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 27, 2017 3:58 pm
- Post datetime: 2018-02-10T21:27:46+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> I tried your 3 examples, all loaded fine, without error. And have UVs included.

So I don't really know what to say, other than are you sure you have the latest version of the importer?

Thanks for checking them out for me. 

Hm. I've tried I'd say every combination of unpack and importers but yeah I have the latest, as far as I know. 1.07 of the importer.
What I do is I just import them into Blender and export an FBX, bring them into Max where they look as if they've been pitch wrapped or something and the UVs are way out of whack. At least they're working for you, anyway, so it is solvable.

Is 1.07 the latest, can I ask? Just to be sure.

Thanks again.

Edited for clarity.
## Post #131
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-10T21:52:43+00:00
- Post Title: Re: Far Cry Primal models

yep, 1.07 is the latest. Also you understand the models are multi-material, so each material section has it's own part of the UV. They aren't all laid out for a single texture. I don't know if converting to FBX handles that right, but it's handled in Blender correctly. Also models can have multiple sets of UVs, but for FCP, they are usually identical.
## Post #132
- Username: lionfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 27, 2017 3:58 pm
- Post datetime: 2018-02-10T22:14:00+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin
>
> yep, 1.07 is the latest. Also you understand the models are multi-material, so each material section has it's own part of the UV. They aren't all laid out for a single texture. I don't know if converting to FBX handles that right, but it's handled in Blender correctly. Also models can have multiple sets of UVs, but for FCP, they are usually identical.

Okey doke, perhaps the error message is unrelated to the UV issue then. Might be clumsiness on my part with the exporting. At least I'm closing in on the problem anyway. I'll do a reinstall and try get them out a few different ways. Thanks. Appreciate the help.
## Post #133
- Username: HiryuX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 14, 2017 5:12 am
- Post datetime: 2018-02-16T16:05:15+00:00
- Post Title: Re: Far Cry Primal models

Hi -- thank you so much for this thread, especially Volfin -- the importer worked great!  I'm trying to port over some of the animals, but can't figure out how to get the correct texture for the fur for animals like the mammoth and wooly rhino.  

Also, when I export as fbx or obj, the models I've seen are usually one mesh, not separate meshes for the fur and body.  I assume the uv for the fur is separate.  I'm very new to blender, is there an export setting I'm missing?  I don't even know the way you make the actual textures show up in blender like some of the shots in this thread (I'm more used to 3ds max).  Any help and advice would be appreciated!

Finally, looking at the textures, they seem pretty low quality (512)?  Is that the best quality texture they have in the files, or should I be looking for higher quality textures elsewhere in the files (I only extracted primal_main.fat)

Thanks -- sorry for all the questions, all a bit new to me.
## Post #134
- Username: Delsiks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 11, 2019 1:24 pm
- Post datetime: 2019-02-11T06:49:28+00:00
- Post Title: Re: Far Cry Primal models

Total noob here, I'd seriously appreciate any help in the right direction with this. I'd love to get some of the hut/tent models and even Wenja dialog. But I have no clue what to do with the thousands of unpacked files with names such as '14C61C9CBE857C58". 

Looking at the xmls downloaded here that are said to have the file IDs in them I can see what I'm looking for such as "graphics\_singleplayer\_textures\missionspecific\mis_020\village_hut_shaman_02_d.xbt" and voices in "dialog\izila_warrior_01\izila_warrior_01.stimuli.dsc"

What I don't understand is how do you access these files? There is no "village_hut_shaman_02_d.xbt" file on my PC. There isn't even a graphics\_singleplayer\_textures\ directory

Unpacking the sound.fat and running the files through DecUbiSndGui gives me music, some of it definitely not from far cry primal, and some ambient sounds. No voices or sound effects.

If I could just get access to the actual textures/models I'd be able figure out how to work with them in 3ds/blender

Huge huge thanks for any help.
## Post #135
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2019-02-11T08:44:34+00:00
- Post Title: Re: Far Cry Primal models

Are you unpacking with [Fino's Dunia unpacker](https://www.nexusmods.com/farcryprimal/mods/5)? It should have a more complete filelist that'll name the unknown files correctly.
## Post #136
- Username: Delsiks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 11, 2019 1:24 pm
- Post datetime: 2019-02-11T15:02:19+00:00
- Post Title: Re: Far Cry Primal models

> Reply from bouvrie
>
> Are you unpacking with Fino's Dunia unpacker? It should have a more complete filelist that'll name the unknown files correctly.

Hi,
I was not, I was using the fcp_unpack.exe from this thread. What is this tool used for then?
Thank you though! I've used Fino's unpacker and have been checking out some models in blender.

On the dialog, it seems they are in .dsc and .ai.rml files which I've not found much info into opening/converting. Is anyone familiar with how one would get these sound/voice files?
## Post #137
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2019-02-15T10:29:37+00:00
- Post Title: Re: Far Cry Primal models

On one hand there's the tool to unpack. Both tools unpack fine, but they also need a list of filenames to make sense of the data inside the archive. Fino's tool release comes with a more complete filelist out of the box. 

I think voice/sound files should actually be in soundbinary/ , in *.spk and *.sbao files. 'm not into asset modding much, but that's the common place.
## Post #138
- Username: fn2505
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 24, 2018 9:26 pm
- Post datetime: 2019-04-21T13:58:51+00:00
- Post Title: Re: Far Cry Primal models

Hi everyone, I'm a noob. How to use the unpacker exactly?
## Post #139
- Username: glowattack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 05, 2019 8:40 pm
- Post datetime: 2019-06-09T01:06:22+00:00
- Post Title: Re: Far Cry Primal models

hello i want use some creatures, but i dont know how to fix the uv issue, anybody can help me with that??? is an obj file, i was try in blender and 3ds max to but i dont get the uv works right.........  sorry for my english
[Sin títulobo.png](https://xentaxbackup.github.io/file/16333_Sin títulobo.png)
## Post #140
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-06-13T03:35:32+00:00
- Post Title: Re: Far Cry Primal models

Which scenario is extracted using 3d model? Please give me the script
[123.png](https://xentaxbackup.github.io/file/16345_123.png)
## Post #141
- Username: BigTinz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 16, 2018 5:53 pm
- Post datetime: 2019-06-17T05:41:29+00:00
- Post Title: Re: Far Cry Primal models

Is there a functional .xbg viewer for Far Cry 2 models? I've looked all over the website and tried scripts and plugins for Blender, Noesis, etc. and none of them work.

Can anyone help?
## Post #142
- Username: Viatrix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 07, 2018 7:54 pm
- Post datetime: 2019-12-20T15:34:00+00:00
- Post Title: Re: Far Cry Primal models

So how to decode non-english oasisstring for Far Cry Primal
## Post #143
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2020-01-02T13:57:22+00:00
- Post Title: Re: Far Cry Primal models

Any news on the animations front?
## Post #144
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2020-01-06T08:23:41+00:00
- Post Title: Re: Far Cry Primal models

For Far Cry series modding, check [the Far Cry Modding Discord](https://discordapp.com/invite/XgBpEkS)
## Post #145
- Username: baoenzo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2020 11:17 am
- Post datetime: 2020-08-27T03:28:13+00:00
- Post Title: Re: Far Cry Primal models

Hello, how to repack common.fat ? after repack common.fat. Game wii crash
## Post #146
- Username: jlecoultre
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 20, 2020 4:39 am
- Post datetime: 2021-06-18T18:30:47+00:00
- Post Title: Re: Far Cry Primal models

> Reply from volfin ↑Sun Feb 11, 2018 4:50 am at Sun Feb 11, 2018 4:50 am
>
> 
I tried your 3 examples, all loaded fine, without error. And have UVs included.







So I don't really know what to say, other than are you sure you have the latest version of the importer?

I have the same problem, the buildings do not have UV's. Maybe it is because I extracted the files with Dunia Tools? I tried to unpack the primal_main.fat with @daemon1 tools but only extract 1.4gb and bunch of .xbg and .xbt files are missing.
