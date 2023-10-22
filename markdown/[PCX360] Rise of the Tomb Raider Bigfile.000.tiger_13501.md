## Post #1
- Username: T0M099
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-05T20:21:28+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Rise of the Tomb Raider - [TR2] - [PC/XENON]/b]




 Requires Noesis version >= 4.177 
fmt_TR2_mesh_1_5.py - Version 1.5 - 07/02/15

Works with EKey's Bigfile/Drm Dumper.

Xbox 360 DRM/Bigfile Tool:
EKey - RTBTIGGERUnpacker_0.0.2b_r4.rar
EKey - RTBDRMDumper_0.0.1_r1.rar

PC DRM/Bigfile Tool:
EKey - ROTTR_TIGGERUnpacker_0.0.3c_r7.rar
Ekey - ROTTR_DRMDumper_0.0.3a_r7.rar
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-06T12:55:28+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Dev's did some changes in archives. Anyway here my unpacker. As a previous games unpacker save only CDRM index files.

Download: See below.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-06T18:53:31+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Dev's did some changes in archives. Anyway here my unpacker. As a previous games unpacker save only CDRM index files.

Nice,

Can you please post struct of the archive ?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-06T19:31:14+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

```
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; // Previous is 3 , Current is 4
   uint32_t   dwUnknown1;
   uint32_t   dwTotalFiles;
   uint32_t   dwUnknown2;
   uint8_t    iPlatform[32]; //Platform (xenon-w) or (ps3-w) or (pc-w)
};

//Entry stucture for version 3
struct iEntryV3
{
   uint32_t   dwHash; //Hash of filename
   uint32_t   dwLanguage;
   uint32_t   dwSize;
   uint32_t   dwZSize; //Posible
   uint32_t   dwFlags; //or two uint16_t
   uint32_t   dwOffset;
};

//Entry stucture for version 4
struct iEntryV4
{
   uint32_t   dwHash; //Hash of filename
   uint32_t   dwLanguage;
   uint32_t   dwSize;
   uint32_t   dwZSize; //Posible
   uint32_t   dwOffset;
   uint32_t   dwFlags; //or two uint16_t
};
```
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-06T19:38:31+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

thank you , but files are compressed zlibbed. When i used yr tool, getting extracted correct zlib files. But on start of each files is something strange it does not start with zlib header actually but this:
WTF is that pls ?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-06T21:32:32+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

MUL files not compressed, only chunks data provided by DRM index
## Post #7
- Username: GRINSPANKER13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 30, 2012 3:26 pm
- Post datetime: 2015-11-06T23:09:47+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> .drm index files not compressed, only chunks data provided by DRM index

Ekey,
I'm looking for all the resource names and ids, like Cloth, Herbs...etc, and I'm not sure if they are in these tiger files.
I understand the file names are all saved as hashes in the entry table, but is there a way to decode them?

For example, in the gamesave Cloth's hash is 0x4D826A39, but I'm looking for all the others.
I'm not sure if they are hashes for the resource name, or just a unique id they were assigned.

I have coded up a little program to read the tiger file for the xbox 360.
I just don't know what to do with the DRM files after unpacking them.

Any help would be appreciated, thanks!
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-07T00:26:32+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from GRINSPANKER13
>
> Ekey wrote:.drm index files not compressed, only chunks data provided by DRM index

Ekey,
I'm looking for all the resource names and ids, like Cloth, Herbs...etc, and I'm not sure if they are in these tiger files.
I understand the file names are all saved as hashes in the entry table, but is there a way to decode them?

For example, in the gamesave Cloth's hash is 0x4D826A39, but I'm looking for all the others.
I'm not sure if they are hashes for the resource name, or just a unique id they were assigned.

I have coded up a little program to read the tiger file for the xbox 360.
I just don't know what to do with the DRM files after unpacking them.

Any help would be appreciated, thanks!

Thanks for the unpacker EKey!   

Everything apart from in-game voice overs are stored in Bigfile.000.tiger, Bigfile.001.tiger. You can't exactly decode the hash, the only way to obtain the filenames is to create a dumper that dumps filenames before the hash is generated within the engine. This is much easier to do on PC. Once the filenames are known it's a case of generating the hash then comparing it.

To clarify, the save-game hashes for weapons/collectibles etc have nothing to do with bigfile entry hashes, they're two completely different things.

Bigfile (Contains .MUL files, DRM Section info)
.MUL -> Audio files (in-game music)
.DRM->(Contains pointers to various files within the Bigfile a specific DRM uses. This could be textures, models, sound effects, scripts etc..)

So you have to read the DRM section table and decompress anything that's compressed (It will be ZLIB compressed for some sections).

We just need a tool that dumps the DRM sections.

I'm working on the model importer, I just need Lara's model correctly extracted since there are some problems at the moment, it would help me confirm a few things.

Regards.
## Post #9
- Username: GRINSPANKER13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 30, 2012 3:26 pm
- Post datetime: 2015-11-07T00:39:01+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thanks Gh0stBlade. I know they have nothing to do with one another.
I was hoping that one of the files in the tiger archive had the strings that the games uses to generate the hash for the weapons and resources.
I'm just playing the game collecting them all but that takes time to do.
Maybe they are just ids assigned and not even hashes.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-07T08:35:13+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> MUL files not compressed, only chunks data provided by DRM index

OK, but every file starts with that. Is there a way how to identify the DRM index files ? My achievement will be repack the archive, but for that i need to understand this DRM files..
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T09:03:34+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> OK, but every file starts with that. Is there a way how to identify the DRM index files ?
If you swap it you can see value like > 44100. What this could be for music files? 

> Reply from michalss
>
> My achievement will be repack the archive
Packer will not be possible until the DRM stuff is understood. (c) Rick

> Reply from michalss
>
> but for that i need to understand this DRM files..
Seems from Lara Croft and the Temple of Osiris DRM files little bit changed.

1) Duplicated id's for sections.
2) Two unknown types with id 1031 and 1034. 
3) Some CDRM's not compressed.
4) Strange texture data. Header is X360 and seems compressed by XMem.

I will share all extracted types of files for confirmation.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-07T12:22:44+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from GRINSPANKER13
>
> Thanks Gh0stBlade. I know they have nothing to do with one another.
I was hoping that one of the files in the tiger archive had the strings that the games uses to generate the hash for the weapons and resources.
I'm just playing the game collecting them all but that takes time to do.
Maybe they are just ids assigned and not even hashes.

Just to make this easier for you, the game does not use strings to compute a hash that is used for weapons etc in the save file. It's already pre-defined as a hash in the DRM file   

> Reply from michalss
>
> Ekey wrote:MUL files not compressed, only chunks data provided by DRM index

OK, but every file starts with that. Is there a way how to identify the DRM index files ? My achievement will be repack the archive, but for that i need to understand this DRM files..

I think the best thing to do is, undo what Crystal Dynamics did. For example, in TR8 all the DRM files included the section info PLUS the file data at the end. The way I'd do this is, extract each DRM header file, locate the section info and write it at the end of the file updating the offsets in the DRM header file. That would make sure all DRM files include all the data they need, some sections are referenced in multiple DRM files (point to the same file, like sharing). Then someone could make any alterations to that, then it's repacked where only the DRM header file is pointed at by the Bigfile file table with the file data stored else where plus the DRM section info re-updated to point to the new file offsets within the bigfile (it MUST be aligned) and the hashes MUST be indexed (lowest to highest if i remember correctly) or it will not work. I wrote a test repacker for MUL files (TR 2013) Didn't take it as far as that unfortunately.

Regards.
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T12:24:25+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Small update.

```
* Base with names updated (added ~2k).
```


Download: See next page.
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T12:55:41+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Base updated (added ~10k)
[RTB_Base_[r4].rar](https://xentaxbackup.github.io/file/9976_RTB_Base_[r4].rar)
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-07T14:46:14+00:00
- Post Title: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Base updated (added ~10k)

Thx. How do you compare what filename belongs to what file pls ? I can see you have only filenames, but not hash asign to it each filename. Also i can see there is so many audiofiles but not any DRM ? Can you also pls update your struct once you digg more information  please?
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T15:08:00+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Thx. How do you compare what filename belongs to what file pls ? I can see you have only filenames, but not hash asign to it each filename. Also i can see there is so many audiofiles but not any DRM ? Can you also pls update your struct once you digg more information  please?
Base loaded in memory (StringList) and parallel creating second StringList with generated hashes from base. Read entry from archive to get hash. Search him in second StringList. If found - remember index position. And finally this position used for get real name (from base) by this index. If hash not found otherwise it just return formated name like __Unknown\0A0C30A1. Easy. If you want - look source's from Rick (C#).
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-07T18:13:06+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> michalss wrote:Thx. How do you compare what filename belongs to what file pls ? I can see you have only filenames, but not hash asign to it each filename. Also i can see there is so many audiofiles but not any DRM ? Can you also pls update your struct once you digg more information  please?
Base loaded in memory (StringList) and parallel creating second StringList with generated hashes from base. Read entry from archive to get hash. Search him in second StringList. If found - remember index position. And finally this position used for get real name (from base) by this index. If hash not found otherwise it just return formated name like __Unknown\0A0C30A1. Easy. If you want - look source's from Rick (C#).

Hmm interesting method, what exactly is mean by base ? Also can you please post Rick source ?
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T19:05:10+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Hmm interesting method
Anyway it works fast 

> Reply from michalss
>
> what exactly is mean by base ?
I mean base with file names -> FileNames.list

> Reply from michalss
>
> Also can you please post Rick source ?
[http://svn.gib.me/public/crystaldynamics/trunk/](http://svn.gib.me/public/crystaldynamics/trunk/)
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-07T20:14:14+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

thx Ekey, it is very simple  Now just need to understand this DRM files. To be hones im looking for fonts and texts/subs only..
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T20:51:28+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> im looking for fonts

```
xenon-w\fontchinese.drm
xenon-w\fontjapanese.drm
xenon-w\fontkorean.drm
xenon-w\fontrussian.drm
xenon-w\fontsimplechinese.drm
xenon-w\fontuniversal.drm
```


> Reply from michalss
>
> texts

```
xenon-w\local\locals.bin
```


> Reply from michalss
>
> subs only..
Subs in MUL files
## Post #21
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-07T21:09:40+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> michalss wrote:im looking for fonts
Code: Select allxenon-w\fontarabic.drm
xenon-w\fontchinese.drm
xenon-w\fontjapanese.drm
xenon-w\fontkorean.drm
xenon-w\fontrussian.drm
xenon-w\fontsimplechinese.drm
xenon-w\fontuniversal.drm
michalss wrote:texts
Code: Select allxenon-w\local\locals.bin
michalss wrote:subs only..
Subs in MUL files

Yeah thx, i know this, but to make full support of my lang, still need to understand DRM and MUL..  Also if you look at this font files, they are only 164 bytes of size.. strange
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-07T21:36:57+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Because all DRM's

> Reply from Gh0stBlade
>
> Contains pointers to various data blocks within the Bigfile a specific DRM uses. This could be textures, models, sound effects, scripts etc.
[here](https://www.sendspace.com/file/1kd8z4) unpacked some sections from jonah_cine.drm for research (included Texture, Material, Mesh, Shader, Sound and two unknown types).
1034 - seems also Material.
1031 - no idea.
## Post #23
- Username: GRINSPANKER13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 30, 2012 3:26 pm
- Post datetime: 2015-11-07T23:04:27+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
Just to make this easier for you, the game does not use strings to compute a hash that is used for weapons etc in the save file. It's already pre-defined as a hash in the DRM file

I think I understand. I would need to find the DRM files for each weapon / resource to find the hashes?
How would one know what DRM file is for what weapon / resource?
Let me know if I'm not following correctly, thanks.
## Post #24
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-07T23:56:24+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Because all DRM's
Gh0stBlade wrote:Contains pointers to various data blocks within the Bigfile a specific DRM uses. This could be textures, models, sound effects, scripts etc.
here unpacked some sections from jonah_cine.drm for research (included Texture, Material, Mesh, Shader, Sound and two unknown types).
1034 - seems also Material.
1031 - no idea.

Thanks for the file! Just tried to load Jonah using my current mesh importer. It does not work, it looks like the file is incorrectly extracted or corrupted?

I suggest this because, one of the pointers in the file to specific data is larger than the filesize so we get an error reading beyond the file. If you check the mesh file, the unsigned integer at 0x8 is always equal to the whole mesh file size, it seems the extracted file is smaller than that.

> Reply from GRINSPANKER13
>
> Gh0stBlade wrote:
Just to make this easier for you, the game does not use strings to compute a hash that is used for weapons etc in the save file. It's already pre-defined as a hash in the DRM file

Why exactly do you need the hashes?, can't you just obtain them through trial and error/changing weapons then saving, checking the new hash?

Cheers.
## Post #25
- Username: GRINSPANKER13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 30, 2012 3:26 pm
- Post datetime: 2015-11-08T00:20:42+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
Why exactly do you need the hashes?, can't you just obtain them through trial and error/changing weapons then saving, checking the new hash?

In the gamesave, there are weapons and ammo that you have to collect or craft.
Once you collect them they are added to an inventory block with uint32 hash/id, uint16 value, uint16 null.
I'm making a editor for the game, and I'm looking for all of the hashs/ids for that.
I have all but 3 of the resources, but barley any of the weapons and ammo.
Sure I can keep playing until I acquire everything, but that takes time.
I was hoping the tiger files would be a faster way to get them all.

Bear Hide = 0x104D7CDF
Compound Bow = 0xD37B01CC

There are many more though.
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-11-08T00:33:58+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

material files also reference textures by hashes. could do some texture modding... thus you need hashes for auto texture.

goooooo ekey! i still don't understand why you don't come to the US to work here rather than waste your life mapping strings to 22,000+ different hash IDs  .
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T10:00:08+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
Thanks for the file! Just tried to load Jonah using my current mesh importer. It does not work, it looks like the file is incorrectly extracted or corrupted?
Ops. One block missed. [here](https://www.sendspace.com/file/0s69eo) correct one.

> Reply from howfie
>
> i still don't understand why you don't come to the US to work here rather than waste your life mapping strings to 22,000+ different hash IDs  .
WTF?
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T11:05:38+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Small update with small fixes 

P.S: Can't attach it lol. -> [here](https://www.sendspace.com/file/t5hw3p)
## Post #29
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-08T13:36:56+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Thanks EKey   

Works perfectly, just got to sort out the rest of the vertex components and we're good to go I think.
## Post #30
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T13:48:01+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Good job. I will share DRM dumper later after some tests
## Post #31
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-08T13:51:48+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Good job. I will share DRM dumper later after some tests

Perhaps one of those other new files which are unknown, may contain the skeleton? Looks like we have the same problem as Lara Croft and the Temple of Osiris, Skeleton is moved out of the mesh file
## Post #32
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T14:14:22+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Perhaps one of those other new files which are unknown, may contain the skeleton? Looks like we have the same problem as Lara Croft and the Temple of Osiris, Skeleton is moved out of the mesh file
1034 - same format of Material.
1031 - dunno what this - seems like script :

```
BloodyTorso
BloodyTorso!
CineMaterialIsActive
CineMaterial_IsActive
ExposedWound
ExposedWound!
FX_cine_jonah_coldbreath_lrg_quick
FX_cine_jonah_coldbreath_sml_quick
StabWound
StabWound!
WoundHealed
WoundHealed!
fx_rain_off
fx_rain_on jonah_cine
```
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T14:25:08+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Look [this](https://www.sendspace.com/file/bw2aig) model. Dumped from laracroft_armor_demonseed.drm. Maybe there is a skeleton?
## Post #34
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-08T15:03:27+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Look this model. Dumped from laracroft_armor_demonseed.drm. Maybe there is a skeleton?

No skeleton in this mesh file either. Could be located in another DRM section or perhaps a single DRM file where all skeletons in the game are stored? Lots of possibilities, could be anywhere
## Post #35
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T16:15:09+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Anyway, 5107 files is unknown. I guess among them can be drm with of skeleton data.
## Post #36
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-08T17:35:20+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Good job. I will share DRM dumper later after some tests

Also please share struct as well.. Thank you Ekey gr8 job as always
## Post #37
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T22:41:32+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Let's go for testing.



Download: [here](https://www.sendspace.com/file/86btkw)
## Post #38
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-08T23:08:29+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Can Anyone help me with mul files please ? I need to get subtitles from it...
## Post #39
- Username: RedJohn
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-09T08:39:20+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Thanks for releasing the DRM Dumper EKey   

Ok so, todo on the mesh importer.

1. Finish up support for remaining texture formats.
2. Fix a small bug regarding some meshes being displayed incorrectly (probably another data type is being used for vertex on those meshes)
3. Look at potential skeleton data, managed to find a file which contains data that resembles skeleton data from Tomb Raider 2013. I'm 99% sure this could be it. If it's confirmed we know where to find skeletons which is GOOD.
## Post #40
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-09T21:13:16+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

I was able to make repacker for local.bin and also partialy for SUBS in MUL files  Still looking for real fonts, anyone got any idea where to find them please ? Also Ekey, please can you share complete structure of DRM you found ?
## Post #41
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-09T21:16:09+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> I was able to make repacker for local.bin and also partialy for SUBS in MUL files  Still looking for real fonts, anyone got any idea where to find them please ? Also Ekey, please can you share complete structure of DRM you found ?

Try check font*.drm. There should be textures if I'm right, try open them with the Noesis importer.

Noesis mesh importer plugins now available!
## Post #42
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-09T21:17:28+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> michalss wrote:I was able to make repacker for local.bin and also partialy for SUBS in MUL files  Still looking for real fonts, anyone got any idea where to find them please ? Also Ekey, please can you share complete structure of DRM you found ?

Try check font*.drm. There should be textures if I'm right, try open them with the Noesis importer.

Noesis mesh importer plugins now available!

this files has only 1kb of size
## Post #43
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-09T21:30:33+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Gh0stBlade wrote:michalss wrote:I was able to make repacker for local.bin and also partialy for SUBS in MUL files  Still looking for real fonts, anyone got any idea where to find them please ? Also Ekey, please can you share complete structure of DRM you found ?

Try check font*.drm. There should be textures if I'm right, try open them with the Noesis importer.

Noesis mesh importer plugins now available!

this files has only 1kb of size
That's tricky, I have no idea where it could be then. It could be one of the several DRMs in the unknown folder :/ That's the biggest problem with this engine, it's absolutely rubbish for easily finding what files you need and altering them.
## Post #44
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-09T21:48:50+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Also Ekey, please can you share complete structure of DRM you found ?
Structure is incomplete. There more unknown values, than previous games.
## Post #45
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-10T05:48:58+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> michalss wrote:Also Ekey, please can you share complete structure of DRM you found ?
Structure is incomplete. There more unknown values, than previous games.

Hmm ok, but still can you please post it, i would like to make texture scanner and found out fonts...  Or if you can please make something like this it would be even better . My goals is to found all textures even in unknow files and put them into 1 single folder and check for fonts..
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-10T09:52:00+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

```
{
   uint32_t   dwVersion; //16
   uint32_t   dwStrLength1;
   uint32_t   dwStrLength2;
   uint32_t   dwNull1;
   uint32_t   dwNull2;
   uint32_t   dwNull3;
   uint32_t   dwTotalSections;
   uint32_t   dwLocaleID;
};

struct iDRMEntry
{
   uint32_t   dwUnknown1;
   uint32_t   dwType;
   uint32_t   dwResourceID; //??
   uint32_t   dwSectionID; //??
   uint32_t   dwLanguageID;
};

struct iDRMSubEntry
{
   uint32_t   dwUnknown1;
   uint32_t   dwNull;
   uint32_t   dwOffset;
   uint32_t   dwFlags; // or two uint16_t
   uint32_t   dwLanguageID;
   uint32_t   dwSize;
   uint32_t   dwUnknown2;
};

struct iCDRMHeader
{
   uint32_t   dwID; //CDRM
   uint32_t   dwNull1;
   uint32_t   dwTotalBlocks;
   uint32_t   dwNull2;
};

struct iCDRMEntry
{
   uint32_t   dwUnknown;
   uint32_t   dwBlockZSize;
};
```
## Post #47
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-10T10:15:55+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

nice, how do you recognize types pls ? ALso is there any existing type list?
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-10T10:25:30+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

```
dwType & 0xFF
```


```
1 - Empty Data
2 - Animation
5 - Texture
6 - Sound
7 - DTP Data
8 - Script
9 - Shader
10 - Material
11 - Object
12 - Render Mesh
13 - Collision Mesh
14 - Stream Group List
15 - Trigger Data
```


Some meshes from mainmenu_larasflat_01.drm can't be loaded.

Section 1138 - [mesh](https://www.sendspace.com/file/3c3wnl)


Section Pack - [meshes](https://www.sendspace.com/file/o6pf5b) - All look like this:
## Post #49
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2015-11-15T14:45:46+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Hello   

I have minimal experience with ripping models and other stuff from games,

but it is possible to extract game models and textures from Xbox One version ?
## Post #50
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-15T15:03:56+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from T0M099
>
> Hello   

I have minimal experience with ripping models and other stuff from games,

but it is possible to extract game models and textures from Xbox One version ?

No it is not..
## Post #51
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-17T13:42:50+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Code: Select allstruct iHeader
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; // Previous is 3 , Current is 4
   uint32_t   dwUnknown1;
   uint32_t   dwTotalFiles;
   uint32_t   dwUnknown2;
   uint8_t    iPlatform[32]; //Platform (xenon-w) or (ps3-w) or (pc-w)
};

//Entry stucture for version 3
struct iEntryV3
{
   uint32_t   dwHash; //Hash of filename
   uint32_t   dwLanguage;
   uint32_t   dwSize;
   uint32_t   dwZSize; //Posible
   uint32_t   dwFlags; //or two uint16_t
   uint32_t   dwOffset;
};

//Entry stucture for version 4
struct iEntryV4
{
   uint32_t   dwHash; //Hash of filename
   uint32_t   dwLanguage;
   uint32_t   dwSize;
   uint32_t   dwZSize; //Posible
   uint32_t   dwOffset;
   uint32_t   dwFlags; //or two uint16_t
};

HI Ekey,

Found out something very disturbing. IF you extract archive then all files size does not match the size of archive, not even close. Something very strange happening in there. Can you please double check i cannot figure it out  For example big file with size 298 MB after extraction all files togerther is not even 131 MB of size
## Post #52
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-17T14:03:26+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

i guess i found it, each tiger file has 2 sets of headers... this is very interesting crap also depending on the size of archive

Any help would be nice
## Post #53
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-18T19:31:03+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> i guess i found it, each tiger file has 2 sets of headers... this is very interesting crap also depending on the size of archive

Any help would be nice

It shouldn't be a problem to extract those files with the information EKey provided. Are you sure you are extracting all of the sections correctly? Also, each file is aligned so there's tons of unused space in those archives which is not extracted or needed to be.


New script update in OP.
## Post #54
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-18T19:36:19+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> New script update in OP.
File Blocked for Violation.
## Post #55
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-18T20:36:32+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> michalss wrote:i guess i found it, each tiger file has 2 sets of headers... this is very interesting crap also depending on the size of archive

Any help would be nice 

It shouldn't be a problem to extract those files with the information EKey provided. Are you sure you are extracting all of the sections correctly? Also, each file is aligned so there's tons of unused space in those archives which is not extracted or needed to be.


New script update in OP.

Yes im sure, but as i said and also ekey, only base files are getting extracted, rest is data from DRM put in random places in TIGER format, repack is impossible in this case..
## Post #56
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-18T20:59:04+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Gh0stBlade wrote:michalss wrote:i guess i found it, each tiger file has 2 sets of headers... this is very interesting crap also depending on the size of archive

Any help would be nice 

It shouldn't be a problem to extract those files with the information EKey provided. Are you sure you are extracting all of the sections correctly? Also, each file is aligned so there's tons of unused space in those archives which is not extracted or needed to be.


New script update in OP.

Yes im sure, but as i said and also ekey, only base files are getting extracted, rest is data from DRM put in random places in TIGER format, repack is impossible in this case..
Repacking is not impossible, it's just a lot of work to do. The best way to do this is to modify the PATCH tiger files and inject modified DRM files into those. The game will automatically load anything with higher priority in the PATCH tiger files so that way, you can still modify the game without altering the larger bigfiles.
## Post #57
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-18T21:33:31+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 

Yes im sure, but as i said and also ekey, only base files are getting extracted, rest is data from DRM put in random places in TIGER format, repack is impossible in this case.. 
Repacking is not impossible, it's just a lot of work to do. The best way to do this is to modify the PATCH tiger files and inject modified DRM files into those. The game will automatically load anything with higher priority in the PATCH tiger files so that way, you can still modify the game without altering the larger bigfiles.

I sort it already, im specializing on repacking things, this one is bad for this purpose, but on X360 found the way how to make a localization tools and it working just fine... Just glad i did not need to edit fonts, coz it is impossibl, for me, to even found it. I will post it in Tools Forum soon...
## Post #58
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-11-24T13:59:12+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Anyone success on parsing the MUL files?
## Post #59
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-24T18:34:51+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from OrangeC
>
> Anyone success on parsing the MUL files?

Nope, very hard, hard format, not even 1 was able to parse it, even aluigi ... I would also need that, but not success at all
## Post #60
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2015-11-26T06:59:50+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> fmt_TR2_mesh_1_0.py - Version 1.1 - 18/11/15Deleted?
## Post #61
- Username: SILENTpavel
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-26T12:15:44+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from SILENTpavel
>
> Gh0stBlade wrote:fmt_TR2_mesh_1_0.py - Version 1.1 - 18/11/15Deleted?
Hmm try now.
## Post #62
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2015-11-27T08:34:23+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Hmm try now.Now working perfect, thanks! But how about textures, is it compressed .DDS? I saw them in the first post. That possibly means that you know how to convert them? I don't need 3d models, i need some textures of the soviet military base as normal 2D pictures.

example: soviet_poster_bendie_v01.drm - Section 17.texture - 85,8 KB
```
00000000  58 33 36 30 1A 20 7F 75 00 01 57 28 00 00 00 01  X360. .u..W(....
00000010  01 00 01 00 00 01 00 08 10 07 01 00 00 01 40 80  ..............@Ђ
00000020  00 00 00 00 04 01 11 B6 F4 DB D8 3C 10 82 00 00  .......¶фЫШ<.‚..
00000030  57 8B 56 0B 08 02 0C 73 82 DB B8 63 6A C9 00 00  W‹V....s‚ЫёcjЙ..
00000040  0D AD 87 05 05 01 1D B0 60 D8 DB 27 18 A2 00 00  ..‡....°`ШЫ'.ў..
00000050  55 AA 55 08 EE 06 63 36 E6 FC FE 63 83 8C 29 03  UЄU.о.c6жьюcѓЊ).
00000060  0A BF DD 0B 41 02 0D B6 B0 0C DA 14 20 C3 00 00  .їЭ.A..¶°.Ъ. Г..
00000070  55 BB 55 20 FF 08 95 9F 09 9A 7A 14 8B AC 18 E3  U»U я.•џ.љz.‹¬.г
00000080  80 EA 55 A2 83 07 6D B6 B6 00 26 ED 18 A2 00 00  ЂкUўѓ.m¶¶.&н.ў..
00000090  55 EA 55 20 FB 68 FF F8 FF 24 FC FF 7B 0A 18 C2  UкU ыhяшя$ья{..В
```




soviet_truck.JPG (38.18 KiB) Viewed 272 times
## Post #63
- Username: SILENTpavel
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-27T12:11:21+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from SILENTpavel
>
> Gh0stBlade wrote:Hmm try now.Now working perfect, thanks! But how about textures, is it compressed .DDS? I saw them in the first post. That possibly means that you know how to convert them? I don't need 3d models, i need some textures of the soviet military base as normal 2D pictures.

example: soviet_poster_bendie_v01.drm - Section 17.texture - 85,8 KBCode: Select allOffset(h) 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
00000000  58 33 36 30 1A 20 7F 75 00 01 57 28 00 00 00 01  X360. .u..W(....
00000010  01 00 01 00 00 01 00 08 10 07 01 00 00 01 40 80  ..............@Ђ
00000020  00 00 00 00 04 01 11 B6 F4 DB D8 3C 10 82 00 00  .......¶фЫШ<.‚..
00000030  57 8B 56 0B 08 02 0C 73 82 DB B8 63 6A C9 00 00  W‹V....s‚ЫёcjЙ..
00000040  0D AD 87 05 05 01 1D B0 60 D8 DB 27 18 A2 00 00  ..‡....°`ШЫ'.ў..
00000050  55 AA 55 08 EE 06 63 36 E6 FC FE 63 83 8C 29 03  UЄU.о.c6жьюcѓЊ).
00000060  0A BF DD 0B 41 02 0D B6 B0 0C DA 14 20 C3 00 00  .їЭ.A..¶°.Ъ. Г..
00000070  55 BB 55 20 FF 08 95 9F 09 9A 7A 14 8B AC 18 E3  U»U я.•џ.љz.‹¬.г
00000080  80 EA 55 A2 83 07 6D B6 B6 00 26 ED 18 A2 00 00  ЂкUўѓ.m¶¶.&н.ў..
00000090  55 EA 55 20 FB 68 FF F8 FF 24 FC FF 7B 0A 18 C2  UкU ыhяшя$ья{..В
soviet_truck.JPG

The script supports some texture types, not all but most of the main ones. Extension for the texture files needs to be renamed to ".tr2x360"
## Post #64
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-01-17T07:20:19+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Can we dump level maps and cordinates yet?
## Post #65
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-01-17T13:51:59+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from d875j
>
> Can we dump level maps and cordinates yet?
Nope, I actually forgot to look at the scene mesh. Never mind, PC version will be releasing soon. Also, what co-ordinates more specifically?
## Post #66
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-01-28T21:07:34+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

PC version is out, need an unpacker. Probably the same format, just needs endian swapping.

Noesis model script for ROTTR PC is W.I.P  

Edit: I spent a while searching through model files extracted by OffZip. Noesis mesh importer is pretty much done, fortunately the vertices are not packed like the Xbox 360 version. Everything should go smoothly, needs further testing but I don't have much samples to work with until an unpacker is avail. I haven't looked at the textures yet..
## Post #67
- Username: Sajjad Rahim
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-29T07:09:10+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Here is unpacker, repacker, reimporter,

I never tested repacker or reimporter, just change endian. However, its working only with base files, NOT DRMs!!

THIS TOOL WONT HELP YOU WITH LOCALIZATION!!

```
https://mega.nz/#!39wxESxb!GrqBf4sakesQrCpK9Qmpp4tVVIqYPlUt-EYGMv0VoN8
```
## Post #68
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-29T07:57:28+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

Uff finally i found local.bin  for all current languages...
## Post #69
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-29T08:50:36+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

if anyone is interested, here is local.bin

```
https://mega.nz/#!Xw4mnATC!DKHkOkjPCHKQqseI7vjs8EVrDxK6Uej4L0GkgyPyVb8
```
## Post #70
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-01-29T10:17:33+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

how to repack files ?
## Post #71
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-29T10:30:16+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

well can you read ?
## Post #72
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-01-29T15:29:17+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Here is unpacker, repacker, reimporter,

I never tested repacker or reimporter, just change endian. However, its working only with base files, NOT DRMs!!

THIS TOOL WONT HELP YOU WITH LOCALIZATION!!
Code: Select allhttps://mega.nz/#!39wxESxb!GrqBf4sakesQrCpK9Qmpp4tVVIqYPlUt-EYGMv0VoN8

You mean, both local.bin and font file are DRMs file?
## Post #73
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-29T16:06:52+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from shadowlonely1989
>
> michalss wrote:Here is unpacker, repacker, reimporter,

I never tested repacker or reimporter, just change endian. However, its working only with base files, NOT DRMs!!

THIS TOOL WONT HELP YOU WITH LOCALIZATION!!
Code: Select allhttps://mega.nz/#!39wxESxb!GrqBf4sakesQrCpK9Qmpp4tVVIqYPlUt-EYGMv0VoN8

You mean, both local.bin and font file are DRMs file?

Fonts are in DRM, texts are ok kind of, split into 3 different archives.. It is a mess..
## Post #74
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-01-29T18:11:09+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

How to extract audio from this game? Audio extract from the FSB, has a bad sound. Example - [https://yadi.sk/d/5xUqMRctnwxb8](https://yadi.sk/d/5xUqMRctnwxb8)
## Post #75
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-30T01:29:21+00:00
- Post Title: Re: Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Here is unpacker, repacker, reimporter,

I never tested repacker or reimporter, just change endian. However, its working only with base files, NOT DRMs!!

THIS TOOL WONT HELP YOU WITH LOCALIZATION!!
Code: Select allhttps://mega.nz/#!39wxESxb!GrqBf4sakesQrCpK9Qmpp4tVVIqYPlUt-EYGMv0VoN8

I want to localize this game. This moment is not possible?
Thousands of Turks have wanted to play this game in our language
And I want to provide it.
## Post #76
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-01-30T04:45:09+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> shadowlonely1989 wrote:michalss wrote:Here is unpacker, repacker, reimporter,

I never tested repacker or reimporter, just change endian. However, its working only with base files, NOT DRMs!!

THIS TOOL WONT HELP YOU WITH LOCALIZATION!!
Code: Select allhttps://mega.nz/#!39wxESxb!GrqBf4sakesQrCpK9Qmpp4tVVIqYPlUt-EYGMv0VoN8

You mean, both local.bin and font file are DRMs file? 

Fonts are in DRM, texts are ok kind of, split into 3 different archives.. It is a mess..

Thanks for your hard work!
## Post #77
- Username: Sajjad Rahim
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-30T07:08:58+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

i will rls some tools in time, right now im focusing on to do localization into our language..
## Post #78
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-01-30T07:12:51+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> i will rls some tools in time, right now im focusing on to do localization into our language..

I am waiting you to write tools to localize the game.
Thank you in advance for your help
## Post #79
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-01-31T07:04:04+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> i will rls some tools in time, right now im focusing on to do localization into our language..

I've seen your post on tomb raider forums 
I'm so excited & waiting your tools
## Post #80
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-01-31T11:13:37+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> i will rls some tools in time, right now im focusing on to do localization into our language..

We are waiting
## Post #81
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-01T17:24:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

TIGER Unpacker v0.0.3 r5 - See below.
DRM Dumper v0.0.2 r4 - See below.

About textures format:

```
{
   uint32_t   dwID; // PCD9
   uint32_t   dwType; // ??? 49, 71, 72, 78, 91 and etc.
   uint32_t   dwDataSize;
   uint32_t   dwVersion; // 1
   uint16_t   sWidth;
   uint16_t   sHeight;
   uint16_t   sBPP; // Bits Per Pixel ?
   uint8_t    bUnknown1;
   uint8_t    bMipMapCount;
   uint16_t   sFlags;
   uint8_t    bUnknown2;
   uint8_t    bFilePath[256];
};

```

Note: It's for PC only because format different from console version.
## Post #82
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-01T20:11:40+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thanks a bunch EKey!   

Any chance you can strip out the header/relocation info on mesh files? That's Everything before "Mesh" file signature like your previous X360 DRM unpacker did. Also, would be great if your DRM unpacker could extract textures with the extension ".tr2pcd" that way people don't have to rename all the textures.

Cheers! 



Noesis script for Rise of the Tomb Raider (PC) is now available on the first post. There might be some unsupported texture formats, I just used all the code from Lara Croft and the Temple of Osiris to speed the release up.

Edit: It won't work unless all data before "Mesh" is deleted.
## Post #83
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-01T20:34:23+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

TIGER Unpacker v0.0.3b r6 - [Download](https://www.sendspace.com/file/xaz6ks)

> * Individual unpack folder for each archive
>
> * Small updated base with names
DRM Dumper v0.0.2b r5 - [Download](https://www.sendspace.com/file/8dia4j)

> * Textures extension changed to *.tr2pcd

> Reply from Gh0stBlade
>
> Thanks a bunch EKey!   

Any chance you can strip out the header/relocation info on mesh files?
In PC version all data files different from console version. In the console version does not have a grid - always begins with a header Mesh. Anyway you can skip it like this:

```
Seek > 0x18 - Read 4 (dwBlockSize)

dwMeshOffset = dwEntryCount * 4 + 0x34 + dwBlockSize;

Seek > dwMeshOffset (from beginning)

```


Profit 

> Reply from Gh0stBlade
>
> 
Also, would be great if your DRM unpacker could extract textures with the extension ".tr2pcd" that way people don't have to rename all the textures.
Implemented.
## Post #84
- Username: TheMask85
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-01T21:55:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> TIGER Unpacker v0.0.3b r6 - Download
* Individual unpack folder for each archive
* Small updated base with names
DRM Dumper v0.0.2b r5 - Download
* Textures extension changed to *.tr2pcd
Gh0stBlade wrote:Thanks a bunch EKey!   

Any chance you can strip out the header/relocation info on mesh files? 
In PC version all data files different from console version. In the console version does not have a grid - always begins with a header Mesh. Anyway you can skip it like this:
Code: Select allSeek > 0x10 - Read 4 (dwEntryCount)
Seek > 0x18 - Read 4 (dwBlockSize)

dwMeshOffset = dwEntryCount * 4 + 0x34 + dwBlockSize;

Seek > dwMeshOffset (from beginning)


Profit 
Gh0stBlade wrote:
Also, would be great if your DRM unpacker could extract textures with the extension ".tr2pcd" that way people don't have to rename all the textures.
Implemented.

Thanks a bunch!

Script updated, should work fine with the latest unpacker
## Post #85
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-02-01T22:18:38+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

i would like to know if there's a way to load models up along with their bones/original riggin in noesis.
for me it'll only load up the mesh itself without any rigging. or isn't this supported anyways?

edit:
also the vertex normals are coming out twisted. for every model. at least for me.
## Post #86
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-01T23:19:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from TheMask85
>
> i would like to know if there's a way to load models up along with their bones/original riggin in noesis.
for me it'll only load up the mesh itself without any rigging. or isn't this supported anyways?

edit:
also the vertex normals are coming out twisted. for every model. at least for me.

The engine changed since Lara Croft and the Temple of Osiris. The Skeleton has since been moved completely out of the mesh file and it's location is unknown. So that's not supported.

For the normals, I'll check this later, thanks for reporting it!
## Post #87
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-02-01T23:37:52+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

прикольно... bigfile.096.tiger
//fedia? fedia- gde ti? gde ti?
## Post #88
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-02-01T23:43:13+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
The engine changed since Lara Croft and the Temple of Osiris. The Skeleton has since been moved completely out of the mesh file and it's location is unknown. So that's not supported.

Supported...yet? Assuming the skeletons can be found, support for those can be added I hope.
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-02T00:17:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> The engine changed since Lara Croft and the Temple of Osiris. The Skeleton has since been moved completely out of the mesh file and it's location is unknown. So that's not supported.

For the normals, I'll check this later, thanks for reporting it!
Maybe in animation files? btw you have simple block with skeleton from older version?

> Reply from Paliha
>
> прикольно... bigfile.096.tiger
//fedia? fedia- gde ti? gde ti?
What? More details.
## Post #90
- Username: TheMask85
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-02T14:40:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> 
Maybe in animation files? btw you have simple block with skeleton from older version?
Here is Lara's model from Tomb Raider: Underworld. [Download](http://www.mediafire.com/download/yd4gtpn7yqmomod/lara.tr8mesh)

Bones start at 0x19EFC0 Each bone sized 0x40 till the end of the file.

I originally thought the same about the Skeleton being stored in animation files. Recent findings make me suspect otherwise. I extracted Lara's hair (xenon-hair.drm) From Rise of the Tomb Raider (PC). The model should have a skeleton yet there are no animation files. I have seen some data ressembling a skeleton in DTP files but loading them results in nothing usable. I'll take another look at that.

Edit:

Breaking news:

Bones have been located!



Now we just need a way of identifying them since they are stored in DTP files. @EKey see "Section 16.dtp" Perhaps first uint "0x6" is a type meaning skeleton. If there is a hash name referencing the skeleton in the mesh file that would be useful. I can't check unless original hash names for sections are known.

Edit:

Confirming that DTP files with the first integer as "0x6" are skeleton files.



@Ekey could you have your unpacker rename those file's extension to ".skl" it would make it easier to identify them. Cheers!
## Post #91
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-02T16:44:45+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> Ekey wrote:
Maybe in animation files? btw you have simple block with skeleton from older version?
Paliha wrote:прикольно... bigfile.096.tiger
//fedia? fedia- gde ti? gde ti?
What? More details.
Да всё нормально, у меня не все архивы игры в одном месте лежали.
Ну а так конечно куча впросов.Нах столькоо хлама вытаскивать?
У харда есть же предел.
Замутил бы  вьюверы для разных данных. Кому что надо то и вытащит.
Ща заканчиваю кодить DRMEdit для 4 игр, на базе сорцов Gibbed.
Если заинтересуют сорцы, стучи в личку.
// насколько понял, по русски ты понимаешь хорошо.

English pls! this is English speaking forum..
## Post #92
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-02T17:56:43+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> Замутил бы  вьюверы для разных данных. Кому что надо то и вытащит.
Ща заканчиваю кодить DRMEdit для 4 игр, на базе сорцов Gibbed.
DRMEdit не забудь только переименовать в DRMViewer  

> Reply from Paliha
>
> Если заинтересуют сорцы, стучи в личку.
На гит залей да и все. Сверх секретного вроде ничего нету. Еще бы логгер хеш-функи замутить и было бы ок.

DRM Dumper v0.0.2c r6 - (Executable size is: 686 080 bytes) - [Download](https://www.sendspace.com/file/b16o53)

> * [Test] Added some DTP detection types for skeleton and scaleform gfx
## Post #93
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-02T20:01:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thanks EKey!

Ok so should be possible to pull out models with original bones etc. New script is in the first post.

How to load a mesh with bones:
1. Extract the .DRM using the latest DRM dumper.
2. In the extracted folder for the DRM. There should be a folder called "DTPData". Open it and locate a file with the extension ".skl" which is the skeleton.
3. Copy this file to the same directory as the ".tr2mesh" you are loading into Noesis. Rename it to "skeleton.skl".

If done correctly, the bones should load fine into Noesis.

Xbox 360 version should be supported but it's untested.

I'm guessing this will work for Lara Croft and the Temple of Osiris too!
## Post #94
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2016-02-02T20:08:53+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Omg amazing work all of you! I can't wait to try this out later!
## Post #95
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-02-02T20:46:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

just tried the new script. i can't say much about the bones yet but unfortunately the vertex normals are still funky.
i simply exported as an fbx and loaded it up in my 3d program. same goes for obj and psk.
## Post #96
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-02T21:11:38+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from TheMask85
>
> just tried the new script. i can't say much about the bones yet but unfortunately the vertex normals are still funky.
i simply exported as an fbx and loaded it up in my 3d program. same goes for obj and psk.

I checked the normals for several models and they're fine. What model file is this?
## Post #97
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-02-02T21:21:04+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

it's every mesh model file. unfortunately there's no exception. export as fbx, obj, psk, smd ... nothing works. funny thing is, i have no such problems with -let's say- Fallout 4 files exported through Noesis to similar common 3d file formats.
that specific model is that one though.
[https://onedrive.live.com/redir?resid=C ... =file%2c7z](https://onedrive.live.com/redir?resid=CE6D08FB61EC450C!228&authkey=!AHaPbitdIcc2Qgw&ithint=file%2C7z)
## Post #98
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-02-02T22:46:39+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> 
DRMEdit не забудь только переименовать в DRMViewer

Agree. But it's the idea of the author. Save DRM is present and the header is not difficult. But I haven't done.

> Reply from Ekey
>
> 
Еще бы логгер хеш-функи замутить и было бы ок.
Что сейчас юзают, не знаю, но то что раньше юзали, хешем назвать трудно, так, самопальная контрольная сумма. Логер при парсинге bigfile.000.tiger? Или мы либы для игры хукаем?
===============
On scrennshots:
Judging by the rendering problem with polygons.Possible indices of negative polygons. With the first negative index, we need to intercept the array with points.
count_points + (-index_poligon)+1
## Post #99
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-02T22:57:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I am waiting for localization.

Any progress mates?
## Post #100
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-03T01:20:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> 
Что сейчас юзают, не знаю, но то что раньше юзали, хешем назвать трудно, так, самопальная контрольная сумма.
CRC32 не самопальная контрольная сумма. Он всегда был на всех движках начиная с игр серии Legacy of Kain 

> Reply from Paliha
>
> 
Логер при парсинге bigfile.000.tiger? Или мы либы для игры хукаем?
I mean hook hash algo for filenames. Today spent ~3h to resolve [this error](http://i.imgur.com/ePqAxS6.png) for my logger
## Post #101
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-03T17:41:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Was anyone able to extract the mul files? Or am I way behind and you can already get sound out of it?
## Post #102
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-03T19:19:31+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Blechpappen
>
> Was anyone able to extract the mul files? Or am I way behind and you can already get sound out of it?

I can extract them just fine.
## Post #103
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-03T19:46:56+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Blechpappen wrote:Was anyone able to extract the mul files? Or am I way behind and you can already get sound out of it?

I can extract them just fine.

What tool do you use to do that? I tried several and my result always ended with 2 seconds cut off at the end, i used fsbii
## Post #104
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-02-03T22:24:46+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I think he meant demultilex them into their original FSB4 containers. Im trying to find a Demuxer tool, but haven't yet.
## Post #105
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-04T11:02:22+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Up mates. I'm waiting for localization tools.
## Post #106
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2016-02-04T18:55:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> Up mates. I'm waiting for localization tools.
I have textools.
Xbox360, Ps3 and PC.
## Post #107
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-04T19:49:51+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I have serious issues with extracting .mul files, can someone help me with this please?
## Post #108
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-04T22:44:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from gula
>
> Taner038 wrote:Up mates. I'm waiting for localization tools.
I have textools.
Xbox360, Ps3 and PC.

You can share with me pc tools, mate?
And does it work?
## Post #109
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-05T00:42:17+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Anyone please  I cannot seem to find a way how to get mul files to fsb without the file being cut in half, please I need help D:
## Post #110
- Username: MARK2580
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 13, 2014 2:29 pm
- Post datetime: 2016-02-05T05:01:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Вижу тут проскакивают рашен комменты. Расскажите народ как вообще достать модели + текстуры ларки ?
Хотяб пошаговую инструкцию. Это распакуй, это переименуй хоть что-то, а то в заголовке тупо 2 проги и скрипт который хз куда девать, с блендером я не дружу... работаю только в 3ds max.
UPD: про Noesis и скрипт понял. Остались вопросы как добыть скелет / развес и текстуры к модели.
## Post #111
- Username: moxxy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 01, 2015 8:43 am
- Post datetime: 2016-02-05T06:57:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

With the current version of the importer (fmt_TR2_mesh_1_4.py) Noesis throws an exception if it encounters a triangle index with the value 65535 (0xffff): "RuntimeError: Index buffer was not valid for drawing."

I modified the script so that it skips those triangles. It is slower but is able to import larger meshes.
However, Noesis crashes when I try to load very large meshes (like 46MB).

The modified script: [https://www.sendspace.com/file/60ocwn](https://www.sendspace.com/file/60ocwn)
## Post #112
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-05T07:29:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from moxxy
>
> With the current version of the importer (fmt_TR2_mesh_1_4.py) Noesis throws an exception if it encounters a triangle index with the value 65535 (0xffff): "RuntimeError: Index buffer was not valid for drawing."

I modified the script so that it skips those triangles. It is slower but is able to import larger meshes.
However, Noesis crashes when I try to load very large meshes (like 46MB).

The modified script: https://www.sendspace.com/file/60ocwn
Thanks, can you upload the mesh file which gave you this error as well?

Cheers.
## Post #113
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-05T17:35:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

TIGER Unpacker v0.0.3c r7 - [Download](https://www.sendspace.com/file/4rjey7)

> * Base with names updated. Added 6890 filenames.
>
> * Fixed unpack files with too long path more then 260 bytes
DRM Dumper v0.0.3a r7 - [Download](https://www.sendspace.com/file/tthw9q)

> * Updated for 1.0.610.1 game version (bigfile.update2.000.000)
## Post #114
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-05T21:04:45+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> TIGER Unpacker v0.0.3c r7 - Download
* Base with names updated. Added 6890 filenames.
* Fixed unpack files with too long path more then 260 bytes
DRM Dumper v0.0.3a r7 - Download
* Updated for 1.0.610.1 game version (bigfile.update2.000.000)

Ekey, how can I repack ?

And, you're any working the localization tools?
## Post #115
- Username: moxxy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 01, 2015 8:43 am
- Post datetime: 2016-02-05T21:18:38+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
Thanks, can you upload the mesh file which gave you this error as well?

Here you are: [https://www.sendspace.com/file/x0vvq6](https://www.sendspace.com/file/x0vvq6)

Section 70.tr2mesh: Can be imported using my patched script.
Section 68.tr2mesh: Crashes Noesis

I checked the amount of the memory that Noesis uses while importing those meshes and it gets very high
(more than 3400MB in case of Section 68). So the crash seems to be caused by low memory. Python is not my primary programming language
and my patch is just a dirty hack. Maybe you can make the script more efficient.
## Post #116
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-05T21:35:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from moxxy
>
> Gh0stBlade wrote:
Thanks, can you upload the mesh file which gave you this error as well?


Here you are: https://www.sendspace.com/file/x0vvq6

Section 70.tr2mesh: Can be imported using my patched script.
Section 68.tr2mesh: Crashes Noesis

I checked the amount of the memory that Noesis uses while importing those meshes and it gets very high
(more than 3400MB in case of Section 68). So the crash seems to be caused by low memory. Python is not my primary programming language
and my patch is just a dirty hack. Maybe you can make the script more efficient.

Thanks, just checked both of those which seem to crash Noesis. On the bright side, when I load them into my engine I don't get a crash at all. The file should load fine, it looks like there's a bug in Noesis so there's not much we can do.
## Post #117
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-05T22:12:06+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

That's not the case, Noesis allows 0xFFFF for 16-bit indices by default. If you're feeding 32-bit indices, you will need to set 0xFFFF as an explicit strip ender using rpgSetStripEnder. However, the error "Index buffer was not valid for drawing" is not caused by out of range indices (this is a different error and informs you of which vertex buffer would be accessed out of range by the index), it's caused by one of the following:

1) Number of indices < 3 for triange list, strip, fan, or polygon.
2) Number of indices not divisible by 3 for triangle list.
3) Same as above 2 but 4 instead for quad lists.

Sounds to me like you're not correctly recognizing triangle strips and are trying to draw them as lists.
## Post #118
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-05T23:11:27+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hi there!   

> Reply from MrAdults
>
> That's not the case, Noesis allows 0xFFFF for 16-bit indices by default. If you're feeding 32-bit indices, you will need to set 0xFFFF as an explicit strip ender using rpgSetStripEnder.
The face indices are unsigned 16 bits. Triangle strips are usually reset/ended by 0xFFFF index. But this doesn't seem to be the case, 0xFFFF only occurs at the end of the face index buffer which suggests it's most likely triangle list like all previous games.

> Reply from MrAdults
>
> 
However, the error "Index buffer was not valid for drawing" is not caused by out of range indices (this is a different error and informs you of which vertex buffer would be accessed out of range by the index), it's caused by one of the following:

1) Number of indices < 3 for triange list, strip, fan, or polygon.
2) Number of indices not divisible by 3 for triangle list.
3) Same as above 2 but 4 instead for quad lists.

Sounds to me like you're not correctly recognizing triangle strips and are trying to draw them as lists.

After debugging this I found the mesh has 65536 vertices:
Section 70.tr2mesh
Vertex Start: 2028
Vertex Count: 65536
Vertex End: 1574892

If the highest face index is ‭65535.‬ Somehow it exceeds vertex[65536] which is what I don't understand. 

####

This should work fine, I'm puzzled so there's not much that can be done.
## Post #119
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-05T23:45:46+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

If you have a legitimate list that happens to use index 0xFFFF, it's probably just hitting the default 16-bit path which rejects 0xFFFF, thus truncating the list by one and making it not divisible by 3. You could feed the indices as 32-bit (just expand them with one line of Python prior to commit), partition the commit calls, or get the next build I put out, whenever that is, and I can give you a hook to disable the ushort rejection.
## Post #120
- Username: aobw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 29, 2014 12:22 pm
- Post datetime: 2016-02-06T14:53:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> TIGER Unpacker v0.0.3c r7 - Download
* Base with names updated. Added 6890 filenames.
* Fixed unpack files with too long path more then 260 bytes
DRM Dumper v0.0.3a r7 - Download
* Updated for 1.0.610.1 game version (bigfile.update2.000.000)
@Ekey Hi 
The scene model appears to be a bit of a problem.
Could you fix it
THANKS!



 Section_1159.zip
cineset_larasflat_01\RenderMesh\Section 1159.tr2mesh (151.19 KiB) Downloaded 47 times
## Post #121
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-06T15:45:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

shakotay, why'd you delete that post? I was just coming here to reply to it.

I assume that 0xFFFF is a valid triangle index based on what Gh0stBlade is saying. If as shakotay said those are not actually indices, then obviously, the solution is to not feed them in as indices.

I haven't looked at any script or data here, I'm only here because Gh0stBlade PM'd me.
## Post #122
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-06T16:11:45+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

By the way, with all these people running out of memory, you ought to be using rpgConstructModelSlim instead of rpgConstructModel if you aren't already (didn't look), Python object overhead is gross and the Slim version will reduce the amount of data that gets back-translated to Python after the model's constructed. If that's not enough, well, that's what native plugins are for.
## Post #123
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-06T16:13:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from MrAdults
>
> shakotay, why'd you delete that post? I was just coming here to reply to it.After I reread Gh0stBlade's post and your reply I found that:

> I assume that 0xFFFF is a valid triangle index based on what Gh0stBlade is saying.this is true.

> If as shakotay said those are not actually indices, then obviously, the solution is to not feed them in as indices.and I was not.
So there was nothing in my post that would help to clear up things.
(It ony would have shown that I always need more time to understand things in their depth, especially at times where I'd better sleep.  )
## Post #124
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-06T17:44:20+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from aobw
>
> 
@Ekey Hi 
The scene model appears to be a bit of a problem.
Could you fix it
THANKS!

Section_1159.zip
That file is from the Xbox 360 version. It is already known that some meshes have vertices packed into a single 32-bit integer. The method in question is presumably the same as what they used to encode/decode the normals. I'm guessing there are other flags/parameter differences for specific types of meshes as it doesn't work on them all. 

To save yourself the trouble I would recommend you use assets from the PC version. All art assets from the PC version are higher quality. An example of this is the chair mesh you uploaded X360 has 6012 vertices. PC: 21121. That's more than 3x the X360 vertex count there.

Unfortunately the Xbox 360 script is dis-continued as the PC version is released, though any features such as bones which were implemented recently should still work for Xbox 360.
## Post #125
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-06T22:07:18+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

still waiting for translation tools. (PC)
## Post #126
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-06T22:10:11+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Pleez guys I just want to know how I can extract those goddang mul files
## Post #127
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2016-02-07T07:51:16+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger


## Post #128
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-07T08:33:16+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I almost finnish localization. I will publish tools once im done completely with localization, not early then that. Please accept this..... All i can do for all of you is to extract all text and put it in here  Also if game does not support your accent i cannot help, coz i dont know how to replace fonts. Fonts are in GFX format...  Also have complete access to MUL files.....

This is from POLISH fonts....
## Post #129
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-07T09:11:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> I almost finnish localization. I will publish tools once im done completely with localization, not early then that. Please accept this..... All i can do for all of you is to extract all text and put it in here  Also if game does not support your accent i cannot help, coz i dont know how to replace fonts. Fonts are in GFX format...  Also have complete access to MUL files.....

This is from POLISH fonts....

You're sharing font supports my language.
I'm waiting for you finish localization. 
Thanks the helping us
## Post #130
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-07T10:42:33+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

But how can I get AUDIO out of the mul files??
## Post #131
- Username: lacek33
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 12, 2014 3:39 am
- Post datetime: 2016-02-07T10:46:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Bet wins as the gfx files?
## Post #132
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-07T16:08:03+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

All text from Game include DLC..

```
https://dl.dropboxusercontent.com/u/38234344/Revers%20Engineering/Rise%20Of%20Tomb%20Raider_PC.rar
```
## Post #133
- Username: aobw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 29, 2014 12:22 pm
- Post datetime: 2016-02-07T16:33:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
That file is from the Xbox 360 version. It is already known that some meshes have vertices packed into a single 32-bit integer. The method in question is presumably the same as what they used to encode/decode the normals. I'm guessing there are other flags/parameter differences for specific types of meshes as it doesn't work on them all. 

To save yourself the trouble I would recommend you use assets from the PC version. All art assets from the PC version are higher quality. An example of this is the chair mesh you uploaded X360 has 6012 vertices. PC: 21121. That's more than 3x the X360 vertex count there.

Unfortunately the Xbox 360 script is dis-continued as the PC version is released, though any features such as bones which were implemented recently should still work for Xbox 360.
THANKS @Gh0stBlade
## Post #134
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-07T18:03:41+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

New fmt_TR2_mesh_1_5.py is available in first post. Special thanks to MrAdults Issue with triangle lists should be fixed on models containing meshes with face indices equivalent to 65535.

A new texture type is also supported.
## Post #135
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-07T19:46:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hellooooou, please someone! How can I extract audio of these mul files? Is there a special tool for that that I don't know about but you all do? Please just help me, at least tell me IF there's a tool for that.
## Post #136
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-02-07T19:50:00+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> New fmt_TR2_mesh_1_5.py is available in first post. Special thanks to MrAdults Issue with triangle lists should be fixed on models containing meshes with face indices equivalent to 65535.

A new texture type is also supported.

First post's link redirects to the fmt_TR2_mesh_1_4.py
## Post #137
- Username: lacek33
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 12, 2014 3:39 am
- Post datetime: 2016-02-07T20:04:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

100% text file.
unpack and repack Kingmakers Team 
[00.jpg](https://xentaxbackup.github.io/file/10441_00.jpg)
## Post #138
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-07T20:52:23+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Keezie
>
> Gh0stBlade wrote:New fmt_TR2_mesh_1_5.py is available in first post. Special thanks to MrAdults Issue with triangle lists should be fixed on models containing meshes with face indices equivalent to 65535.

A new texture type is also supported.

First post's link redirects to the fmt_TR2_mesh_1_4.py
Small mistake, should be fixed, thanks!
## Post #139
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-02-07T21:24:09+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from lacek33
>
> 100% text file.
unpack and repack Kingmakers Team

can you share it ?
## Post #140
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-02-07T22:21:16+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from lacek33
>
> 100% text file.
unpack and repack Kingmakers Team

It would be SuperMega awesome of you if u can share it with us.
We want to translate it to Persian.
## Post #141
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-07T23:50:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from lacek33
>
> 100% text file.
unpack and repack Kingmakers Team

To get local.bin is super easy task(menu,UI,items). To repack cines is a different story.But text is packed into 4 different files with 3 different formats. Just a hint...
## Post #142
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-08T05:26:09+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> All text from Game include DLC..
Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/Revers%20Engineering/Rise%20Of%20Tomb%20Raider_PC.rar

Ok thanks. But how can I repack this file. ?
## Post #143
- Username: lacek33
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 12, 2014 3:39 am
- Post datetime: 2016-02-08T05:29:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> lacek33 wrote:100% text file.
unpack and repack Kingmakers Team 

To get local.bin is super easy task(menu,UI,items). To repack cines is a different story.But text is packed into 4 different files with 3 different formats. Just a hint...

All text retrieval is successful. The real difficulty update.tiger claims is different from the other tiger species ... But it is also solved.
[0000000.jpg](https://xentaxbackup.github.io/file/10443_0000000.jpg)
## Post #144
- Username: lacek33
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 12, 2014 3:39 am
- Post datetime: 2016-02-08T05:32:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> michalss wrote:All text from Game include DLC..
Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/Revers%20Engineering/Rise%20Of%20Tomb%20Raider_PC.rar

Ok thanks. But how can I repack this file. ?

We do not use this tool your own text files
## Post #145
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-08T05:45:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from lacek33
>
> 
We do not use this tool your own text files

mate, your purpose is flaunt, nothing else.
## Post #146
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-08T06:13:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Could someone please not ignore me? I want to know how to extract audio from mul files ...
## Post #147
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-08T07:00:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> michalss wrote:All text from Game include DLC..
Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/Revers%20Engineering/Rise%20Of%20Tomb%20Raider_PC.rar

Ok thanks. But how can I repack this file. ?

I allready told you a few posts back..
## Post #148
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-08T07:41:40+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> 
I allready told you a few posts back..

Ok. I'm start localization. 
and I understand it correctly
you give it the tools when your translation is finish, right?
## Post #149
- Username: Melkor
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-08T07:51:58+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> michalss wrote:
I allready told you a few posts back..

Ok. I'm start localization. 
and I understand it correctly
you give it the tools when your translation is finish, right?

Yes i will.. Might someone make some other loc tools sooner, you never know  But you have all text allready. I can guarante this is all text in game + DLC include MUL file Cines..
## Post #150
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-08T08:06:22+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Taner038 wrote:michalss wrote:
I allready told you a few posts back..

Ok. I'm start localization. 
and I understand it correctly
you give it the tools when your translation is finish, right?

Yes i will.. Might someone make some other loc tools sooner, you never know  But you have all text allready. I can guarante this is all text in game + DLC include MUL file Cines..

Very Very thanks man. I'm starting now and I'm forward waiting you're finish localization and share the tools  
Thanks again
## Post #151
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-02-08T08:15:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Taner038 wrote:michalss wrote:
I allready told you a few posts back..

Ok. I'm start localization. 
and I understand it correctly
you give it the tools when your translation is finish, right?

Yes i will.. Might someone make some other loc tools sooner, you never know  But you have all text allready. I can guarante this is all text in game + DLC include MUL file Cines..

Greatest news ever! Thank you! Then we will began translation and I am looking forward for you tools!
To what language you are translating the game? My language is so different from English so i definitely need to completely edit/change the game fonts, do you have a solution for that too?
## Post #152
- Username: Melkor
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-08T08:21:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Melkor
>
> 

Ok. I'm start localization. 
and I understand it correctly
you give it the tools when your translation is finish, right?

Yes i will.. Might someone make some other loc tools sooner, you never know  But you have all text allready. I can guarante this is all text in game + DLC include MUL file Cines..

Greatest news ever! Thank you! Then we will began translation and I am looking forward for you tools!
To what language you are translating the game? My language is so different from English so i definitely need to completely edit/change the game fonts, do you have a solution for that too?

Im replacing Polish Lang. I suggest do the same think.
## Post #153
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-08T08:34:57+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> 
Im replacing Polish Lang. I suggest do the same think.

I'm a one questions mate,

MUL_Cine_EN.txt and Cine_EN.txt
There are the same lines
which translations?
## Post #154
- Username: Melkor
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-08T08:55:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> michalss wrote:
Im replacing Polish Lang. I suggest do the same think.

I'm a one questions mate,

MUL_Cine_EN.txt and Cine_EN.txt
There are the same lines
which translations?

Same text different formating!
## Post #155
- Username: Blechpappen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 3:50 am
- Post datetime: 2016-02-09T16:39:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hey! I made a video showcasing the problem I have. Is that because of the DRM extractor? Is it because of the method I use to extract the mul files? Is it because of the tigger unpacker I don't know.

[https://www.youtube.com/watch?v=gz8s9ZiWIl4](https://www.youtube.com/watch?v=gz8s9ZiWIl4)
## Post #156
- Username: moxxy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 01, 2015 8:43 am
- Post datetime: 2016-02-11T00:47:23+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Does anybody know how textures are referenced in material files and materials in mesh files respectively?

I extracted the asset names from the .tr2pcd files, hashed them and brute forced the material files for values containing the hashed
name. Unfortunately it didn't yield any match.

For example:

```
hash = HashName("assets\textures\environment\manmade\rh_hub_uniq_wood_pile_v01")
ScanFiles(hash)

```

I also tried various asset name combinations like prepending "pcx64-w\" or appending ".tr2pcd", ".pcd", ".dds", ...
Does anybody have an idea?

By the way, I use the hash algorithm from [http://svn.gib.me/public/crystaldynamics/trunk/](http://svn.gib.me/public/crystaldynamics/trunk/) is it still valid?
## Post #157
- Username: T0M099
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-11T13:57:32+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from moxxy
>
> Does anybody know how textures are referenced in material files and materials in mesh files respectively?

I extracted the asset names from the .tr2pcd files, hashed them and brute forced the material files for values containing the hashed
name. Unfortunately it didn't yield any match.

For example:
Code: Select all// Repeat for every texture asset name.
hash = HashName("assets\textures\environment\manmade\rh_hub_uniq_wood_pile_v01")
ScanFiles(hash)

I also tried various asset name combinations like prepending "pcx64-w\" or appending ".tr2pcd", ".pcd", ".dds", ...
Does anybody have an idea?

By the way, I use the hash algorithm from http://svn.gib.me/public/crystaldynamics/trunk/ is it still valid?

This is pointless, I'll save you the trouble and explain why.

1. Each DRM section has it's own unique hash name which is a unsigned 16-bit integer. Ekey's unpacker does not extract the sections with their hash names.
2. Each meshInfo[] contains a 32-bit integer which is an index into the material list (stored else where in the mesh file). The material list is just an array of 16-bit hash names which match the material hash section it uses.
3. At the end of the material files you should see a struct array sized 0x10. These are the texture definitions, each array starts with a 16-bit hash identical to the corresponding texture section it is referring to.
4. It is almost impossible to implement auto-texturing. The materials specify all textures it utilises. Within the material file there is no flag which determines whether a texture definition is diffuse, normal, mask or specular textures. This is controlled directly by the shaders which are compiled so it's pretty much impossible. I have confirmed this information for Tomb Raider Underworld by modifying the material file itself. Modifying the other data stored in the texture definition struct does nothing in regards to what texture is diffuse etc. Replacing the shader proved that my initial concerns are correct. This may have changed since Tomb Raider: Underworld but it's highly unlikely.

You can take a look at my Tomb Raider: Underworld Noesis script which does load material files and partially auto texture the meshes but it's not accurate all the time.

Regards.
## Post #158
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-02-11T15:00:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

A profound mistake...For example - Underworld.
I can say with certainty for models.
This mesh:

```
00 00 00 00   10 00 00 00   E2 1F 00 00   E3 1F 00 00 
E4 1F 00 00   E5 1F 00 00   E6 1F 00 00   E7 1F 00 00 
E8 1F 00 00   E9 1F 00 00   EA 1F 00 00   EB 1F 00 00 
EC 1F 00 00   ED 1F 00 00   EE 1F 00 00   EF 1F 00 00 
F0 1F 00 00   F1 1F 00 00    00 00 00 00   00 00 00 00

```
 
10 00 00 00 < - This count Material (*.matd), next Material_ID.
Next Material (matd) In the beginning header, taking count graphic files.
Then reverse the array, and pick the graphics identifiers.

```
 Name         Type    Flag    №
00000A82|00000003|0002 0100
00000A83|00000003|0002 0200
00000A84|00000005|0002 0300
00000A85|00000005|0002 0400
00000079|00000002|0002 0500
0000011E|00000003|0002 0600
00000079|00000002|0002 0700
00000A81|00000005|0002 0000
00000A86|00000007|0002 0800
000000FF|00000002|0002 0900
00000A87|00000001|0002 0A00
2. 00001FE3 count : 11
 Name     Type    Flag  №
00000A89|00000003|00020100
00000A8A|00000003|00020200
000008DE|00000005|00020300
00000A8B|00000005|00020400
00000A8C|00000002|00020500
000008DD|00000003|00020600
00000A8D|00000002|00020700
00000A88|00000005|00020000
00000A8E|00000007|00020800
000000FF|00000002|00020900
00000A8F|00000001|00020A00

```

We need at index 1.With this index is greater than one, and there are duds. Their skip. Of the remaining, is not critical. Usually the first. The second is for other situation in the game.

```
    { if ((name != 0x00000128) && (name != 0x00000138) && (name != 0x000000FF))
            { data += string.Format("{0:X4}", name);
              var Search = string.Format("{0:X8}", name);
               find = SearchNode(Search + " : RenderResource", entryTreeView.Nodes[0]);
                find.ForeColor = Color.DarkRed;
                sector = true; } }


```
## Post #159
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-11T15:50:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> A profound mistake...For example - Underworld.
I can say with certainty for models.
This mesh:
Code: Select allFF FF FF FF   FF FF FF FF   FF FF FF FF   00 00 00 00  
00 00 00 00   10 00 00 00   E2 1F 00 00   E3 1F 00 00 
E4 1F 00 00   E5 1F 00 00   E6 1F 00 00   E7 1F 00 00 
E8 1F 00 00   E9 1F 00 00   EA 1F 00 00   EB 1F 00 00 
EC 1F 00 00   ED 1F 00 00   EE 1F 00 00   EF 1F 00 00 
F0 1F 00 00   F1 1F 00 00    00 00 00 00   00 00 00 00
 
10 00 00 00 < - This count Material (*.matd), next Material_ID.
Next Material (matd) In the beginning header, taking count graphic files.
Then reverse the array, and pick the graphics identifiers.
Code: Select all1. 00001FE2 count : 11
 Name         Type    Flag    №
00000A82|00000003|0002 0100
00000A83|00000003|0002 0200
00000A84|00000005|0002 0300
00000A85|00000005|0002 0400
00000079|00000002|0002 0500
0000011E|00000003|0002 0600
00000079|00000002|0002 0700
00000A81|00000005|0002 0000
00000A86|00000007|0002 0800
000000FF|00000002|0002 0900
00000A87|00000001|0002 0A00
2. 00001FE3 count : 11
 Name     Type    Flag  №
00000A89|00000003|00020100
00000A8A|00000003|00020200
000008DE|00000005|00020300
00000A8B|00000005|00020400
00000A8C|00000002|00020500
000008DD|00000003|00020600
00000A8D|00000002|00020700
00000A88|00000005|00020000
00000A8E|00000007|00020800
000000FF|00000002|00020900
00000A8F|00000001|00020A00

We need at index 1.With this index is greater than one, and there are duds. Their skip. Of the remaining, is not critical. Usually the first. The second is for other situation in the game.
Code: Select all if ((type == 0x00000001)&(sector == false))
    { if ((name != 0x00000128) && (name != 0x00000138) && (name != 0x000000FF))
            { data += string.Format("{0:X4}", name);
              var Search = string.Format("{0:X8}", name);
               find = SearchNode(Search + " : RenderResource", entryTreeView.Nodes[0]);
                find.ForeColor = Color.DarkRed;
                sector = true; } }

I don't understand what you mean. All that material info has been known for some time now.

If you are suggesting that type 0x1 is the correct texture for diffuse maps then you are wrong. There are several material files with multiple texture definitions with type 0x1. Either way, this is all controlled by the shaders, any other work around is nothing more than a hack and will never be stable/accurate enough. Looking into the materials is a waste of time.

Regards.
## Post #160
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-02-11T16:50:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

to Gh0stBlade
Lara for example is in the mud, and sometimes came out of the water. Both of these files have one type = 1. File selection goes according to the game script . These files also has type 1,(128,138,ff) but their purpose I don't know yet. For the model they are not needed.
I tried your plugins, they just use the indexes of the graphics. Therefore concluded that before the end of you in this matter is not sorted out.
## Post #161
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2016-02-15T09:00:40+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Does someone know how Lara's new hair - Pure Hair are stored ?

I know that they aren't made by polygons, probably they are curves/splines. 

Also, would be possible to extract them ? Thanks for help.
## Post #162
- Username: T0M099
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-15T13:57:37+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from T0M099
>
> Does someone know how Lara's new hair - Pure Hair are stored ?

I know that they aren't made by polygons, probably they are curves/splines. 

Also, would be possible to extract them ? Thanks for help.

I have no idea, if you do find them let me know!  

Edit: lara_hair_all.drm It's most likely stored in Section 1.dtp custom mesh format it seems.
## Post #163
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2016-02-17T13:27:12+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thank you Gh0stBlade, maybe another silly question, but I'm curious if whole level/scene could be exported (e.g. main menu scene) ?
## Post #164
- Username: T0M099
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-17T14:37:18+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from T0M099
>
> Thank you Gh0stBlade, maybe another silly question, but I'm curious if whole level/scene could be exported (e.g. main menu scene) ?
Depends, scenes are just composed of terrain meshes and tons of statics. The only way to do that would be to load the data which states what parts of the scene/statics are needed and where they go. I have no idea where that's stored, I'm betting it's part of the DTPData and the format for that section type is completely unknown/inconsistent.
## Post #165
- Username: nudifyher
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 10, 2015 11:50 pm
- Post datetime: 2016-02-18T00:02:03+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Maybe this tool will aid you, texture replacer for Directx11 games, it will be updated this week so keep an eye on it.
[https://www.undertow.club/threads/tool- ... acer.8402/](https://www.undertow.club/threads/tool-resorep-directx-11-texture-replacer.8402/)
and here [https://www.undertow.club/threads/looki ... tive.3088/](https://www.undertow.club/threads/looking-for-programmer-texmod-and-umod-alternative.3088/)
## Post #166
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-02-23T14:50:07+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> TIGER Unpacker v0.0.3c r7 - Download
Hello. How to extract files from the rest of the Tiger? The program will extract only the file bigfile.000.tiger. It seems that it is not full, bigfile.000.tiger file size 1,99 GB, and the size Unpacked folder 1.54 GB.
## Post #167
- Username: VladlenCry
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-23T15:00:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from VladlenCry
>
> Ekey wrote:TIGER Unpacker v0.0.3c r7 - Download
Hello. How to extract files from the rest of the Tiger? The program will extract only the file bigfile.000.tiger. It seems that it is not full, bigfile.000.tiger file size 1,99 GB, and the size Unpacked folder 1.54 GB.

Please read the tool usage instructions.

1. The TIGER unpacker only extracts the DRM headers.
2. The DRM files are then dumped using DRM DUMPER.
3. The tool works 100% perfectly. Bigfile.000.tiger includes tons of unused null data due to file alignments. This means the extracted output will be significantly smaller than the original tiger file itself.
## Post #168
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-02-23T15:12:52+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Please read the tool usage instructions.
Thanks!!!
## Post #169
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-02-23T18:04:57+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

any news about Localization tool ?
## Post #170
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2016-02-23T21:15:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> About textures format:
struct PCD9Header...
Does anyone have a tool to view/convert PCD9 texture? Should I be hex editing these .tr2pcd files in some way? Unlike DDS plugin for example, I'm not finding out how to get PCD9 into Photoshop.

> MUL_Cine_EN.txt
Somehow extracted from MUL files?

> Cine_EN.txt
>
> locals5430.bin.txt
Tiger/CDRM source?
## Post #171
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-23T21:38:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from relight
>
> Ekey wrote:About textures format:
struct PCD9Header...
Does anyone have a tool to view/convert PCD9 texture? Should I be hex editing these .tr2pcd files in some way? Unlike DDS plugin for example, I'm not finding out how to get PCD9 into Photoshop.

Use the Noesis importer. It also supports textures.
## Post #172
- Username: galaxymax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 24, 2014 1:18 pm
- Post datetime: 2016-02-27T15:26:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

@Gh0stBlade
Thanks !!!
## Post #173
- Username: Sajjad Rahim
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-29T08:30:52+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Our localization is done so next week i will share my tools...
## Post #174
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-03-02T15:15:27+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Pardon my ignorance... Does fmt_TR2_mesh_1_5.py export static or fully rigged models?
## Post #175
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-03T23:24:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from artworkplay
>
> Pardon my ignorance... Does fmt_TR2_mesh_1_5.py export static or fully rigged models?
Supports original bones and weights. Skeleton must be manually renamed.
## Post #176
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-04T04:16:22+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Our localization is done so next week i will share my tools...
Nice! Thanks!
## Post #177
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-03-07T05:36:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Looking through the thread, still confused on extracting the content... could someone guide me?
## Post #178
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-03-07T15:44:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Our localization is done so next week i will share my tools...

It was 1 week, my friend.
## Post #179
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-03-07T19:42:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Taner038
>
> michalss wrote:Our localization is done so next week i will share my tools...

It was 1 week, my friend.

Dont worry it will be here this week.. Im still preparing tut document. Repack will be very very hard for you PPL, it is nothing what everyone can do it, so i want to make sure that doc, at least make sense..
## Post #180
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-03-07T20:57:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> Taner038 wrote:michalss wrote:Our localization is done so next week i will share my tools...

It was 1 week, my friend.

Dont worry it will be here this week.. Im still preparing tut document. Repack will be very very hard for you PPL, it is nothing what everyone can do it, so i want to make sure that doc, at least make sense..

thanks my friend. I look forward
## Post #181
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-03-08T07:50:06+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Here it is my localization tools : [viewtopic.php?f=32&t=14064](http://forum.xentax.com/viewtopic.php?f=32&t=14064)
## Post #182
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-10T06:42:19+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> I almost finnish localization. I will publish tools once im done completely with localization, not early then that. Please accept this..... All i can do for all of you is to extract all text and put it in here  Also if game does not support your accent i cannot help, coz i dont know how to replace fonts. Fonts are in GFX format...  Also have complete access to MUL files.....

This is from POLISH fonts....

Hi! Could you tell me where is POLISH font store, please! Thanks!
## Post #183
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-03-10T07:04:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from shadowlonely1989
>
> michalss wrote:I almost finnish localization. I will publish tools once im done completely with localization, not early then that. Please accept this..... All i can do for all of you is to extract all text and put it in here  Also if game does not support your accent i cannot help, coz i dont know how to replace fonts. Fonts are in GFX format...  Also have complete access to MUL files.....

This is from POLISH fonts....


Hi! Could you tell me where is POLISH font store, please! Thanks!

I cannot it is in dmr files, wont be able to do anything with that anyway. I allready told you, i cannot replace font files...! If you want to use this font you have to use POLISH language.
## Post #184
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-10T07:15:49+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from michalss
>
> shadowlonely1989 wrote:michalss wrote:I almost finnish localization. I will publish tools once im done completely with localization, not early then that. Please accept this..... All i can do for all of you is to extract all text and put it in here  Also if game does not support your accent i cannot help, coz i dont know how to replace fonts. Fonts are in GFX format...  Also have complete access to MUL files.....

This is from POLISH fonts....


Hi! Could you tell me where is POLISH font store, please! Thanks!

I cannot it is in drm files, wont be able to do anything with that anyway. I allready told you, i cannot replace font files...! If you want to use this font you have to use POLISH language.

Oh, I understand, we can not edit drm file, right? We only can dump drm file. Thanks! Hope we can reinsert drm file in the future.
## Post #185
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-03-11T07:00:06+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

made update for my loc tools....
## Post #186
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-17T08:28:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

@Gh0stBlade
When writing a parser of a scene from Tomb Raider - Underworld, 
faced with the indices of faces which point beyond the data block.

```

```

For example the binary code of the mesh for the block edges:

```
8A 93 14 A0 13 A0 89 93 14 A0 15 A0 13 A0 16 A0

```

After conversion we get:

```
f 40977/40977/40977 40978/40978/40978 40972/40972/40972
f 37769/37769/37769 40979/40979/40979 37770/37770/37770
f 40980/40980/40980 40979/40979/40979 37769/37769/37769
f 40980/40980/40980 40981/40981/40981 40979/40979/40979

```

The first decision was removal, but in some cases the number of such indexes are not always a multiple of three. So I had to delete the duplicates:

```
while ( FaceIndex.Min() < FaceIndex.First())
      { int pos = FaceIndex.IndexOf (FaceIndex.Min());
        if (( pos !=FaceIndex.Count-1) && ( pos !=FaceIndex.Count))
           index_ = FaceIndex.ElementAt (pos+1);
        else 
           index_ = FaceIndex.ElementAt (pos-1);
           FaceIndex [pos] = index_+1; }
FaceIndex = RemoveDoubles(FaceIndex);

```

There is a solution to recalculate the indices of the faces?
=============
ADD:
The problem is solved. There is no problem of indexes. Remove duplicate bad decision. It is necessary to collect the indices of the faces, respectively with the blocks of vertices.

```
C0 12 06 00 00 00 00 00 7A FD 00 00 00 00 00 00 
20 CC 21 00 00 00 00 00 8B 09 00 00 01 00 00 00  
80 FD 22 00 00 00 00 00 91 3C 00 00 02 00 00 00 
60 9D 29 00 00 00 00 00 06 00 00 00 03 00 00 00 

```
## Post #187
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-18T14:02:44+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> @Gh0stBlade
When writing a parser of a scene from Tomb Raider - Underworld, 
faced with the indices of faces which point beyond the data block.
Code: Select allFaceIndex.Min() < FaceIndex.First()

For example the binary code of the mesh for the block edges:
Code: Select all12 A0 10 A0 0C A0 11 A0 12 A0 0C A0 89 93 13 A0
8A 93 14 A0 13 A0 89 93 14 A0 15 A0 13 A0 16 A0

After conversion we get:
Code: Select allf 40978/40978/40978 40976/40976/40976 40972/40972/40972
f 40977/40977/40977 40978/40978/40978 40972/40972/40972
f 37769/37769/37769 40979/40979/40979 37770/37770/37770
f 40980/40980/40980 40979/40979/40979 37769/37769/37769
f 40980/40980/40980 40981/40981/40981 40979/40979/40979

The first decision was removal, but in some cases the number of such indexes are not always a multiple of three. So I had to delete the duplicates:
Code: Select allint index_= 0;               
while ( FaceIndex.Min() < FaceIndex.First())
      { int pos = FaceIndex.IndexOf (FaceIndex.Min());
        if (( pos !=FaceIndex.Count-1) && ( pos !=FaceIndex.Count))
           index_ = FaceIndex.ElementAt (pos+1);
        else 
           index_ = FaceIndex.ElementAt (pos-1);
           FaceIndex [pos] = index_+1; }
FaceIndex = RemoveDoubles(FaceIndex);

There is a solution to recalculate the indices of the faces?
=============
ADD:
The problem is solved. There is no problem of indexes. Remove duplicate bad decision. It is necessary to collect the indices of the faces, respectively with the blocks of vertices.
Code: Select allOffset                  Count            Group
C0 12 06 00 00 00 00 00 7A FD 00 00 00 00 00 00 
20 CC 21 00 00 00 00 00 8B 09 00 00 01 00 00 00  
80 FD 22 00 00 00 00 00 91 3C 00 00 02 00 00 00 
60 9D 29 00 00 00 00 00 06 00 00 00 03 00 00 00

Sorry, I don't understand your post. It's strange you're having to write such code to remove face indices from Tomb Raider: Underworld scene meshes. You shouldn't have to do this at all, I managed to pull out the scene models with no issues.

Also, please use this thread only for Rise of the Tomb Raider related discussions.

Cheers.
## Post #188
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-19T04:07:45+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Paliha wrote:@Gh0stBlade
=============
ADD:
The problem is solved. There is no problem of indexes. Remove duplicate bad decision. It is necessary to collect the indices of the faces, respectively with the blocks of vertices.
Code: Select allOffset                  Count            Group
C0 12 06 00 00 00 00 00 7A FD 00 00 00 00 00 00 
20 CC 21 00 00 00 00 00 8B 09 00 00 01 00 00 00  
80 FD 22 00 00 00 00 00 91 3C 00 00 02 00 00 00 
60 9D 29 00 00 00 00 00 06 00 00 00 03 00 00 00 


Sorry, I don't understand your post. It's strange you're having to write such code to remove face indices from Tomb Raider: Underworld scene meshes. You shouldn't have to do this at all, I managed to pull out the scene models with no issues.

Also, please use this thread only for Rise of the Tomb Raider related discussions.

Cheers.

With you it is very difficult to consult
===============

```
                  { int count = FaceIndexData[k].Count();
                        { for ( int h = 0; h < count; h++) 
                              { TempIndex.Add(string.Format("f {0}/{0}/{0} {1}/{1}/{1} {2}/{2}/{2}", 
                                             (FaceIndexData[k][h].IndexX) + CurrentСountVertex + 1 , 
                                             (FaceIndexData[k][h].IndexY) + CurrentСountVertex + 1 , 
                                             (FaceIndexData[k][h].IndexZ) + CurrentСountVertex + 1  ));
                                Сounter++; 
                                if ( Сounter == MaterialData[k][md].FaceCount/3) 
                                    { FaceGroup.Add(string.Format ("usemtl Texture{0}", MaterialData[k][md].FaceGroupNum + 1));
                                      FaceGroup.AddRange(TempIndex);
                                      TempIndex.Clear();
                                      Сounter = 0; 
                                      md++; } } }
                    md = 0;  
                    CurrentСountVertex += Point3DData[k].Count();}<<<<<<<<<<<<<<<!!!!!!!!!!!!!!!!!!



```
## Post #189
- Username: doppel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 20, 2013 1:09 am
- Post datetime: 2016-03-31T14:10:06+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hi! i have a problem when i try to rip the drm files from bigfile.update2.000.000, 
ripping one of those drm files, this message apears.
[](http://s1383.photobucket.com/user/David_Paracuellos_Gil/media/problem_ripper_zpsuc5ufyhk.jpg.html)
It's possible fix this?
Thanks in advance
## Post #190
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-04-07T08:18:20+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Is xenon_hair.drm the only file for Lara's hair?
## Post #191
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-07T12:45:19+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from meganmi
>
> Is xenon_hair.drm the only file for Lara's hair?
That's the hair file used when TressFX is disabled. The actual TressFX mesh uses a different format so it's not possible to extract that.
## Post #192
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-04-08T18:26:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> meganmi wrote:Is xenon_hair.drm the only file for Lara's hair?
That's the hair file used when TressFX is disabled. The actual TressFX mesh uses a different format so it's not possible to extract that.

I see, that's why it's so stiff when I move the bones around (barely anything moves anyway.)
## Post #193
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2016-05-01T23:48:42+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> TIGER Unpacker v0.0.3c r7 - Download
* Base with names updated. Added 6890 filenames.
* Fixed unpack files with too long path more then 260 bytes
DRM Dumper v0.0.3a r7 - Download
* Updated for 1.0.610.1 game version (bigfile.update2.000.000)
Ekey, is there any chance you can do a final update for the Cold Darkness Awakened DLC? It would be much appreciated!
## Post #194
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-05-02T20:02:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from relight
>
> Ekey, is there any chance you can do a final update for the Cold Darkness Awakened DLC? It would be much appreciated!
Whats wrong? DRM Dumper supported this DLC.
## Post #195
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2016-05-02T20:25:47+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> relight wrote:Ekey, is there any chance you can do a final update for the Cold Darkness Awakened DLC? It would be much appreciated!
Whats wrong? DRM Dumper supported this DLC.
For one example, looking for Cold Darkness map.

For structure example, bigfile.update1 contains pcx64-w/Design/image resources/map/_dlc_wickedvale and _dlc_witchfight, those are the maps for Baba Yaga DLC.

But bigfile.update2 and bigfile.dlc.mode.colddarkness does not contain any pcx64-w/Design

Also I believed DLC was released March 29 and the last update I saw for Unpacker / DRM Dumper in this thread was February 5.

That's what led me to think the DLC was not fully supported.
## Post #196
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-05-04T18:31:03+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> relight wrote:Ekey, is there any chance you can do a final update for the Cold Darkness Awakened DLC? It would be much appreciated!
Whats wrong? DRM Dumper supported this DLC.
+1
for the unpacker, you need to specify the path to bigfile.dlc.mode.colddarkness.000.000.tiger
But there is nothing interesting there...))))
## Post #197
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2016-05-15T22:09:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Not sure if you subscribe to this thread Ekey, so I just wanted to give this a small bump in case my explanation post was missed on the previous page.

I know that looking at this again would be low priority compared to newer stuff, but if there's any possibility of an update it would be much appreciated.

> Reply from relight
>
> Ekey wrote:Whats wrong? DRM Dumper supported this DLC.
For one example, looking for Cold Darkness map.

For structure example, bigfile.update1 contains pcx64-w/Design/image resources/map/_dlc_wickedvale and _dlc_witchfight, those are the maps for Baba Yaga DLC.

But bigfile.update2 and bigfile.dlc.mode.colddarkness does not contain any pcx64-w/Design

Also I believed DLC was released March 29 and the last update I saw for Unpacker / DRM Dumper in this thread was February 5.

That's what led me to think the DLC was not fully supported.
## Post #198
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2016-06-28T00:48:37+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hello, ekey!

Is there any way to run DRM Dumper in command line? I want to extract all DRMs, and opening each one, then waiting, then closing the window will require just too much time.
## Post #199
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-08-19T09:58:42+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Is this how her head is suppose to be rigged?

Did i extract the wrong model?
## Post #200
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2016-08-19T11:56:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from pewposterous
>
> Is this how her head is suppose to be rigged?
[img]http://i.imgur.com/TPMYnic.png[/im]
Did i extract the wrong model?
That is the correct model you ripped. The face bones do not have weights because the developers used blend shapes for animations ([http://tombraider.tumblr.com/post/13159 ... lendshapes](http://tombraider.tumblr.com/post/131592399635/dev-blog-bringing-lara-to-life-with-blendshapes))
## Post #201
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-08-19T15:16:39+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thanks for the info
## Post #202
- Username: hexg0d18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 30, 2016 12:22 am
- Post datetime: 2016-09-07T13:30:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

WHAT ABOUT CDRM , SFX FILE??? HOW TO OPEN IT?
## Post #203
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-09-29T00:10:19+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

the noesis script seams to be having issues with some dlc textures.



Section 739.jpg (122.57 KiB) Viewed 190 times



here's the file in question, if anyone can take a look.
[https://www.dropbox.com/s/dele6mtsxrphc ... r2pcd?dl=0](https://www.dropbox.com/s/dele6mtsxrphczz/Section%20739.tr2pcd?dl=0)
## Post #204
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-09-29T00:16:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from OriginOfWaves
>
> the noesis script seams to be having issues with some dlc textures.
Section 739.jpg

here's the file in question, if anyone can take a look.
https://www.dropbox.com/s/dele6mtsxrphc ... r2pcd?dl=0

opens fine in Noesis for me.
## Post #205
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-09-29T01:33:11+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

which version are you using? 4177? and are you using the script from the OP? also which python version do you have installed? i'm not getting the PCD type in the debug window.
## Post #206
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-09-29T04:51:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from OriginOfWaves
>
> which version are you using? 4177? and are you using the script from the OP? also which python version do you have installed? i'm not getting the PCD type in the debug window.

Oh yeah, now that I look, I see I modified the script to add more support for textures and stuff. Since I don't recall al the stuff I modded, i'll just attach my tweaked version here.
[fmt_TR2_mesh_1_5.rar](https://xentaxbackup.github.io/file/11740_fmt_TR2_mesh_1_5.rar)
## Post #207
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-09-29T11:43:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from volfin
>
> OriginOfWaves wrote:which version are you using? 4177? and are you using the script from the OP? also which python version do you have installed? i'm not getting the PCD type in the debug window.

Oh yeah, now that I look, I see I modified the script to add more support for textures and stuff. Since I don't recall al the stuff I modded, i'll just attach my tweaked version here.
thanks a bunch man for sharing. works perfectly now. maybe should look into adding your version to the OP.
## Post #208
- Username: urao
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 29, 2016 9:14 pm
- Post datetime: 2016-10-29T14:12:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hi
I can look the model any the skeleton into the Noesis program, but How I can see the textures in the model, please?
Thanks in advance
## Post #209
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-10-29T14:51:09+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from urao
>
> Hi
I can look the model any the skeleton into the Noesis program, but How I can see the textures in the model, please?
Thanks in advance

Auto texturing is impossible without customised shaders.
## Post #210
- Username: LostField
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 29, 2015 1:04 am
- Post datetime: 2016-12-15T21:35:55+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Gh0stBlade, сan you reupload PC DRM/Bigfile Tool please?
## Post #211
- Username: LostField
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-16T00:27:41+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from LostField
>
> Gh0stBlade, сan you reupload PC DRM/Bigfile Tool please?
Why? The links work.
## Post #212
- Username: LostField
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 29, 2015 1:04 am
- Post datetime: 2016-12-17T13:26:30+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> LostField wrote:Gh0stBlade, сan you reupload PC DRM/Bigfile Tool please?
Why? The links work.

Sorry, then isn't working for my internet service provider or for my country (Russia). Thanks a lot
## Post #213
- Username: nico3522
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 26, 2016 7:38 am
- Post datetime: 2016-12-25T23:45:24+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hello everybody,
I have downloaded the game and want to burn it using abgx 360. The thing is I need ISO files to do that, but in the file I downloaded there's only .tiger files... what can I do with that? Is there a way to use that or convert it or I have to downloaded everything again?

Thanks a lot !
## Post #214
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-26T11:55:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from nico3522
>
> Hello everybody,
I have downloaded the game and want to burn it using abgx 360. The thing is I need ISO files to do that, but in the file I downloaded there's only .tiger files... what can I do with that? Is there a way to use that or convert it or I have to downloaded everything again?

Thanks a lot !

We do not support piracy here. Please discontinue this discussion or sanctions may be incurred.

Cheers.
## Post #215
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-28T04:50:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

hello!
I need help with this toolset.
I can't find many textures - as example - normal for this map (wolf body).

[](http://hostingkartinok.com/show-image.php?id=1c6be98591f6cbdd6b20ecb3fba0a5ac)

And when I convert animal models for fbx I have  warnrng- "WARNING: Mesh contains bone weights, but the model has no skeleton"

pc vrersion.
## Post #216
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-28T20:59:55+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> hello!
I need help with this toolset.
I can't find many textures - as example - normal for this map (wolf body).



And when I convert animal models for fbx I have  warnrng- "WARNING: Mesh contains bone weights, but the model has no skeleton"

pc vrersion.

The skeleton data is stored in .DTPDATA files, you must locate it and rename it to "skeleton.skl" so it's loaded in Noesis.
You should check the wolf's material file to see if it has other maps.

Cheers.
## Post #217
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-29T07:18:19+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thank you!
With skeleton understood.
As for the texture - I can not find a part of the texture and do not know drm in which they are described. I tried all drm with the word "wolf". Are there any opportunities globally to extract all the textures of bigfile in one folder?
## Post #218
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-01-01T21:30:44+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hey,
would it eventually be possible to update the Tiger unpacker and DRM Dumper to support the last update of the game? (bigfile.dlc.mode.bloodties.000.000.tiger)
## Post #219
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-02T00:21:30+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Unpacker doesn't works? I think that I can update tools if you can upload this files.
## Post #220
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2017-01-02T19:41:04+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Unpacker doesn't works?
Hi !

```
    bigfilenum = GameFilePath + @"\bigfile.dlc.mode.bloodties.000.000.tiger";

```

no names, extract the archives DRM, do not look very...(((
And with scenes not quite clear where they are. a lot of individual objects, but no scenes, as for example in TR 2013.
## Post #221
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-02T20:49:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Ekey  Is there a way to globally extract all texture from bigfile without using drm?
## Post #222
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-02T20:52:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> Ekey  Is there a way to globally extract all texture from bigfile without using drm?
With this too much problems.

> Reply from Paliha
>
> no names
In this case, you must update the filelist base in Projects folder.
## Post #223
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-02T21:06:18+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I can't find some textures (wolf normal, bear without damage - normal and spc, e.t.c.)
What can you advise?
## Post #224
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-02T21:09:37+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> I can't find some textures (wolf normal, bear without damage - normal and spc, e.t.c)
What can you advise?
I do not remember exactly, but it seems not all the textures are converted to DDS. Supported only A8R8G8B8, DXT1 and DXT5.
## Post #225
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-02T21:18:17+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I do not see there tr2pcd with suitable size.
## Post #226
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2017-01-02T21:32:46+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

>>In this case, you must update the filelist base in Projects folder.
ну да, только логер у тебя, если ты не забыл...)))
могу помочь унпакнуть *.exe, чтоб комфортней имена дёргать...))
## Post #227
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-02T22:14:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Paliha
>
> ну да, только логер у тебя, если ты не забыл...)))
Логгер я потер случайно, новый писать надо, но лениво.

> Reply from Paliha
>
> могу помочь унпакнуть *.exe, чтоб комфортней имена дёргать...))
Зачем? Detours от мелкософта прекрасно работает, надо только знать RVA адрес хеш функции.
## Post #228
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-02T22:17:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Хех, сколько русских собралось
## Post #229
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-01-02T23:17:04+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Unpacker doesn't works? I think that I can update tools if you can upload this files.

I'd like to send them to you but i can't write you a PM. I think posting public on Forum is not allowed or is it?
## Post #230
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-02T23:22:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from o0Crofty0o
>
> I'd like to send them to you but i can't write you a PM. I think posting public on Forum is not allowed or is it?
Just upload on mega. You can also send me PM in ZenHAX forums > [http://zenhax.com](http://zenhax.com)
## Post #231
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-03T18:53:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Updated tools and project base for DLC's. > See below
## Post #232
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-03T19:43:08+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Sorry, this link translate me to my account.
This is error?
## Post #233
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-03T20:19:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> Sorry, this link translate me to my account.
This is error?

Apparently the file can only be downloaded by account holders at Mega.
## Post #234
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2017-01-03T20:52:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

[http://dropmefiles.com/8axiM](http://dropmefiles.com/8axiM)
## Post #235
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-03T21:05:43+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thank you!
## Post #236
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2017-01-04T07:34:33+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Updated project base for DLC's. > See below
Super...
## Post #237
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-04T21:11:55+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Can you add options to DRMdumer for extract all drm from a folder?
To avoid selecting them one by one.
Thank you.
## Post #238
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2017-01-05T09:37:31+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> Can you add options to DRMdumer for extract all drm from a folder?
To avoid selecting them one by one.
Thank you.
In drm, no resources. There is only a header specifying the type, and in which the container he is in a Packed form. So it will take a lot of time, and will require disk space, 2-3 times more than the distribution of the game.
## Post #239
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-05T17:15:00+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Yes I know that.
For example, I need a weapons.
I choose all drm with mask "wp_*", copy them to a separate folder, and treat this whole folder.
## Post #240
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-05T18:41:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

if you want to run a program on every file in a folder, just use a batch file like:

```
for %%a in (*.EXT) do YOUR_PROGRAM "%%a" "OUTFOLDER\%%a"
```


obviously change EXT to the extension of the file you want to work on, YOUR_PROGRAM to the program you want to run, and OUTFOLDER to the output folder it should save to (if the program supports that of course).  can put your options on there too.
## Post #241
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-05T18:51:11+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

As far as I know, this program does not support the launch with parameters. Also I need to somehow kill the old copies of the program.
## Post #242
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2017-01-07T09:04:03+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from erik945
>
> Yes I know that.
For example, I need a weapons.
I choose all drm with mask "wp_*", copy them to a separate folder, and treat this whole folder.
Each DRM where there is mesh, a lot of "garbage"...)) Only 16 data types, but for each type in the container from 10 to 200 resources. Of them 60% of have duplicates in any container DRM. To find which mesh ,the desired object - the weapon automatically fail. There is no logic there...)))to You for weapons, you need 10 textures. Objects dependent on the material, dependent textures, etc.
## Post #243
- Username: xstat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 23, 2017 3:54 am
- Post datetime: 2017-01-22T19:56:14+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Lol
## Post #244
- Username: capkomultra
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 26, 2017 2:21 am
- Post datetime: 2017-02-02T22:30:23+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

It looks like someone made a huge leap forward! Nice work @xstat
## Post #245
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-02-03T00:03:37+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from capkomultra
>
> It looks like someone made a huge leap forward! Nice work @xstat

It's most likely just a texture patch through an external application, nothing special really.

Cheers.
## Post #246
- Username: scott88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 15, 2017 4:25 pm
- Post datetime: 2017-03-15T08:28:19+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

@ xstat

You're still working on it ?
## Post #247
- Username: cosmaty
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 25, 2014 8:57 pm
- Post datetime: 2017-04-02T14:39:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

DRM Dumper does not open files
## Post #248
- Username: minitiv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 01, 2017 12:28 am
- Post datetime: 2017-07-08T10:06:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Is anyone know how work with weapon textures like this one:



Is that possible convert into diffuse or something like that
## Post #249
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-08-13T03:22:46+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Ekey wrote:
Maybe in animation files? btw you have simple block with skeleton from older version?
Here is Lara's model from Tomb Raider: Underworld. Download

Bones start at 0x19EFC0 Each bone sized 0x40 till the end of the file.

I originally thought the same about the Skeleton being stored in animation files. Recent findings make me suspect otherwise. I extracted Lara's hair (xenon-hair.drm) From Rise of the Tomb Raider (PC). The model should have a skeleton yet there are no animation files. I have seen some data ressembling a skeleton in DTP files but loading them results in nothing usable. I'll take another look at that.

Edit:

Breaking news:

Bones have been located!



Now we just need a way of identifying them since they are stored in DTP files. @EKey see "Section 16.dtp" Perhaps first uint "0x6" is a type meaning skeleton. If there is a hash name referencing the skeleton in the mesh file that would be useful. I can't check unless original hash names for sections are known.

Edit:

Confirming that DTP files with the first integer as "0x6" are skeleton files.



@Ekey could you have your unpacker rename those file's extension to ".skl" it would make it easier to identify them. Cheers!

Hi any chance we can get animation too?
that would be great!!
## Post #250
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2017-08-22T09:22:18+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Is there any way to run DRMdumer in command line? I want to extract all drm from a folder .

```
for %%a in (*.DRM) do YOUR_PROGRAM "%%a" "OUTFOLDER\%%a"
```


can't do this
## Post #251
- Username: Feregorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2017 1:31 am
- Post datetime: 2017-10-05T17:58:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Greetings all, I found a mesh file of Lara's hair on the DXMD thread here and want to modify it a bit. I used noesis to export it, but it looks like this in the programs window and in 3dsmax: 



Plus, it's missing any UV map. Is there something I'm doing wrong?
## Post #252
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-05T19:41:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Feregorn
>
> Greetings all, I found a mesh file of Lara's hair on the DXMD thread here and want to modify it a bit. I used noesis to export it, but it looks like this in the programs window and in 3dsmax: 

[img]https://i.imgur.com/RKoK1cS.png[/mg]

Plus, it's missing any UV map. Is there something I'm doing wrong?
It is explained in the DXMD thread aswell that this file isn't exactly a usual mesh. The mesh includes vertex data to calculate curves. Any scripts that treat it as a usual mesh interpret it wrongly, that is why you get that mess.
## Post #253
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2017-10-15T13:55:18+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> http://dropmefiles.com/8axiM
Hi guys, 
sorry to bother you, but does anyone have an updated version of the filelist? It seems this one has gone under since.
## Post #254
- Username: Techrev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 10, 2017 1:02 pm
- Post datetime: 2017-11-10T05:04:27+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

This topic seems dead.  Is it progressing somewhere else, or is it kill?
## Post #255
- Username: Techrev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 10, 2017 1:02 pm
- Post datetime: 2017-11-10T05:13:31+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I guess, the truth is, I came here looking for a way to fix a game that doesn't deserve to be fixed.
## Post #256
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2018-01-05T02:17:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I changed font the character my language successfully, but there is no way to import the DRM again, how to import???
## Post #257
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2018-01-07T08:49:57+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Can you tell me where the subtitle font??
## Post #258
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-05-01T20:02:55+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Just a simple question here

Do anyone know where or what the Trinity mercenaries are called in game files
can't seem to locate them at all..
## Post #259
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2018-05-02T02:53:00+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

guys...
how about import local.bin to bigfile?
## Post #260
- Username: Kathie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 24, 2016 4:30 pm
- Post datetime: 2018-05-11T17:17:30+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Any news about .MUL files conversion/extraction?     
Everyone here saying that they can open/use them, but don't provide additional info.

With many thanks!
## Post #261
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2018-07-09T20:17:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Would be possible to update FileNames.list for TIGER Unpacker (by Ekey) ?
I'd like to extract models from Blood Ties DLC.

Or if someone could explain how to do it, I'll gladly do it and then share the new list
## Post #262
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2018-07-10T03:08:16+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I want to import files and repack archive
How can i do that?
## Post #263
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-07-10T19:25:02+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from halfway
>
> I want to import files and repack archive
How can i do that?
You can't, there's an injector for TR2013 which could be upgraded to work with Rise of the Tomb Raider.
## Post #264
- Username: farlibarcai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 15, 2018 2:38 am
- Post datetime: 2018-07-15T19:32:02+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Is that .tiger file available to download? I want to get the immortal guardian armor meshes.
It is nowhere to be seen.

Thanks in advance.
## Post #265
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-24T19:39:13+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I will also post it here, the PureHair will be fully extractable now.
## Post #266
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-07-25T00:22:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from daemon1
>
> I will also post it here, the PureHair will be fully extractable now.
Any details on how this works? I know the hair is splines but what type of spline?
## Post #267
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-25T15:13:25+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> daemon1 wrote:I will also post it here, the PureHair will be fully extractable now.


Any details on how this works? I know the hair is splines but what type of spline?
no they are not splines, just usual vertices and faces
## Post #268
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2018-07-25T15:58:45+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Wow very nice   
Can you tell more details ? ( or share the hair model if it's possible )
## Post #269
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-25T20:40:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

as usual, i'll publish the tool and you'll be able to get all hairs from this engine
## Post #270
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-02T08:25:28+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

hair tool for DXMD (also work with Lara):
[viewtopic.php?f=16&t=18534](http://forum.xentax.com/viewtopic.php?f=16&t=18534)
## Post #271
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-08-08T07:35:10+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> http://dropmefiles.com/8axiM

Since the link above is dead, I would like to ask if you could upload the file once more.
## Post #272
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2018-08-23T12:30:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Can someone extract content like Classic Skins, relics from 20 Year Celebration Pack ? 
Probably the TIGER Unpacker and DRMDumper need to be updated
## Post #273
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-10-22T07:35:42+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Sorry, I really don't want to sound like a broken record, but is there any chance for a re-upload of the updated filelist?
## Post #274
- Username: PsychoFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 03, 2019 3:53 am
- Post datetime: 2019-06-02T19:56:22+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Okay, the thread hasn't been updated for a while but i have a question and i thought i'd try here.

I want to make the knife Lara wears on her back invisible in game. I'm making a machinima and this would really help. Is this something that's possible with this game?
## Post #275
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-06-05T07:50:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from PsychoFox ↑Mon Jun 03, 2019 3:56 am at Mon Jun 03, 2019 3:56 am
>
> 
I want to make the knife Lara wears on her back invisible in game. I'm making a machinima and this would really help. Is this something that's possible with this game?

To my knowledge - no, not possible. You can extract from the game, but not repack.
But then again there're mods for Rise (and Shadow) that alter textures though I don't know how they work. If you were to find out, perhaps you could make the knife's textures fully transparent.
## Post #276
- Username: PsychoFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 03, 2019 3:53 am
- Post datetime: 2019-06-07T05:45:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Raban ↑Wed Jun 05, 2019 3:50 pm at Wed Jun 05, 2019 3:50 pm
>
> 
PsychoFox wrote: ↑Mon Jun 03, 2019 3:56 am
I want to make the knife Lara wears on her back invisible in game. I'm making a machinima and this would really help. Is this something that's possible with this game?


To my knowledge - no, not possible. You can extract from the game, but not repack.
But then again there're mods for Rise (and Shadow) that alter textures though I don't know how they work. If you were to find out, perhaps you could make the knife's textures fully transparent.

I did try going the alpha channel route, but unfortunately the game refuses to accept any compression methods that have alpha channel information in them. It also refuses uncompressed textures which is odd. However i'm not sure if this is a problem with the game itself or Rescop.
## Post #277
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-10-18T16:41:51+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

am i doing something wrong? i can only unpack bigfile.000.tiger with the unpacker. are we not supposed to unpack bigfile.001.tiger to 7, in order to get all the models and textures of the game?
## Post #278
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-10-19T14:53:17+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from ricmetal ↑Sat Oct 19, 2019 12:41 am at Sat Oct 19, 2019 12:41 am
>
> 
are we not supposed to unpack bigfile.001.tiger to 7, in order to get all the models and textures of the game?

No we are not. The DRM-Dumper will pull data out of those. 

So just run TIGGER-Unpacker on the .000 bigfiles (the addons have those too), then start the DRM-Dumper, click "file" then "open DRM". 
In the now opened file-explorer navigate to folder "Unpacked", follow the subfolders down until you reach "psx64-w" where you'll see all those DRM listed. Extract any you like and use Noesis to preview and export the data.
## Post #279
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-10-19T17:10:38+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Raban ↑Sat Oct 19, 2019 10:53 pm at Sat Oct 19, 2019 10:53 pm
>
> 
No we are not. The DRM-Dumper will pull data out of those.

alrighty-o. thanks!
## Post #280
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-11-25T21:55:59+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

i don't suppose batch conversion with DRMDumper is possible? @ekey?
## Post #281
- Username: Imtiaz5683
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2020 12:05 pm
- Post datetime: 2020-06-15T06:38:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade ↑Fri Nov 06, 2015 4:21 am at Fri Nov 06, 2015 4:21 am
>
> 
Rise of the Tomb Raider - [TR2] - [PC/XENON]/b]




 Requires Noesis version >= 4.177 
fmt_TR2_mesh_1_5.py - Version 1.5 - 07/02/15

Works with EKey's Bigfile/Drm Dumper.

Xbox 360 DRM/Bigfile Tool:
EKey - RTBTIGGERUnpacker_0.0.2b_r4.rar
EKey - RTBDRMDumper_0.0.1_r1.rar

PC DRM/Bigfile Tool:
EKey - ROTTR_TIGGERUnpacker_0.0.3c_r7.rar
Ekey - ROTTR_DRMDumper_0.0.3a_r7.rar

Does this DRMdumper.exe work for Tomb Raider 2013?
I am asking this to you because I could not find DRM dumper for TR9 (Tomb Raider 2013) from anywhere.  And your previous link has been expired.
## Post #282
- Username: alphaZ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 06, 2020 4:23 pm
- Post datetime: 2020-07-24T21:46:26+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey ↑Wed Jan 04, 2017 2:53 am at Wed Jan 04, 2017 2:53 am
>
> 
Updated tools and project base for DLC's. > See below

> Reply from Ekey ↑Wed Jan 04, 2017 4:52 am at Wed Jan 04, 2017 4:52 am
>
> 
http://dropmefiles.com/8axiM

Hello, I have converted and updated the TR2013 tool so that it can inject assets back into Rise's bigfile.update2.000.000.tiger file, and it works with an old version of the game. See below, it is a Lara mesh that I moved one vertex on her shirt and injected back into the game:


However, I cannot get it to work with the latest version of the game on steam, because the bigfile.update3.000.000.tiger file cannot be extracted by any of the tools available in this thread. I understand the above link was maybe an updated tool that could handle this latest archive file? The link is down, does anyone have it?

 I am also trying to write a model exporter, but I am getting stuck on some unknown structured data after the vertex buffer. Maybe it is the blend shapes, I'm not sure
## Post #283
- Username: alphaZ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 06, 2020 4:23 pm
- Post datetime: 2020-09-05T19:01:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Okay, I have figured out a hacky way to extract the DRM files from bigfile.update3.000.000.tiger
First, you must download these newer versions of Ekey's DRMDumper and TIGERUnpacker here: 
[https://cdn.discordapp.com/attachments/ ... RTools.rar](https://cdn.discordapp.com/attachments/718419987097845830/751555985889296495/ROTTRTools.rar)

Then, you use TIGERUnpacker to extract the DRM files from bigfile.update3.000.000.tiger
Unfortunately, the DRM Dumper *still* will not work with update3, as it says the archive is not a recognized ROTTR TIGER file, so you have to do some hacky stuff to trick DRM Dumper into thinking it's extracting from an archive it knows.

So next, rename bigfile.update3.000.000.tiger to bigfile.dlc.mode.endurance.000.000.tiger (and temporarily rename the original endurance file to something else)

Now, download this 010 Editor template and script for DRM files that I made:
[http://www.mediafire.com/file/us0htrs2s ... c.zip/file](http://www.mediafire.com/file/us0htrs2soaq2z0/DRM_template_1sc.zip/file)
...and look at a copy of the DRM file you want to extract with the template. Run the 1sc script on the DRM file in the template to change all references to bigfile.update3 to be to bigfile.dlc.mode.endurance, and save the DRM file.

Now, you should be able to extract the modified DRM file using DRMDumper while your update3 file is temporarily renamed to be Endurance
## Post #284
- Username: ClockworkAssassin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 22, 2016 5:56 am
- Post datetime: 2021-03-21T16:46:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Does anyboy know what bigfile and drm could contain the anctartica outfit from the 20 year celebration pack? It's supposed to have that as well as a few classic TR outfits, but I cant seem to find either.
## Post #285
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-03-29T14:22:20+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from ClockworkAssassin ↑Mon Mar 22, 2021 12:46 am at Mon Mar 22, 2021 12:46 am
>
> 
Does anyboy know what bigfile and drm could contain the anctartica outfit from the 20 year celebration pack? It's supposed to have that as well as a few classic TR outfits, but I cant seem to find either.

I'm betting it's the same as in Shadow of the Tomb Raider, as in you can't open the bigfiles which contain the DLC outfits. I couldn't find the Tunic of the Exiled Fox because it's probably in one of those locked dlc archives in SOTR.
## Post #286
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2021-12-30T16:21:22+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

So as you know, mods don't work on the latest build of ROTTR.
Is it just that the creator of the Mod Injector tool isn't around anymore to add support for the new bigfile or did the file format change in a fundamental way?

Either way, I'd love to know more about the structure of those bigfiles. Can anyone point me in the right direction?
## Post #287
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-02-17T16:10:50+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from CobraGamer ↑Fri Dec 31, 2021 12:21 am at Fri Dec 31, 2021 12:21 am
>
> 
So as you know, mods don't work on the latest build of ROTTR.
Is it just that the creator of the Mod Injector tool isn't around anymore to add support for the new bigfile or did the file format change in a fundamental way?

The author of the mod injector is still around (alphaZomega), he's just busy with other things right now.

The new update introduced a different order in which the assets are stored, which causes the injector to not work anymore since it relied on the order of the files. He mentioned he's probably going to change the system to rely on the assets' hashes rather than the order, but again, it probably won't happen anytime soon.
## Post #288
- Username: Kubsy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 05, 2022 4:53 pm
- Post datetime: 2022-03-05T11:31:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hi Guys 

are the bigfile.001-007 not supposed to be openable? I wanted to extract mul files so that I can convert to fsb then mp3. 

I was able to extract bigfile.000.tiger successfully but not the 001.007
## Post #289
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2022-03-07T22:18:12+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

It should be automatically extracting resources from the 001+ files since they're just extensions of the 000 (= main) file.
## Post #290
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-23T06:53:04+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Thanks to Ekey, Gh0stBlade for all the previous excellent work, and thanks to MrAdults for creating Noesis.
Here's the animation import tool for RotTR, using 3dsmax script.

-------------------------------------------------------------------
Notes:
This tool only works for skeletal animations of the body. I did no research on the facial animations.

Anim files: You can get animation files following Gh0stBlade's instructions, and you will get the same animation files no matter which DRM you choose as long as it's the same character - e.g. (laracroft, laracroft_endurance, laracroft_xxx ... all share the same set of animations)

Skeleton: Each bone has its unique "developer id" which is different with the creating index (Noesis id). Those ids are stored in the skl file and the animation data files.

Mesh: Importing animations doesn't rely on the mesh, but for better preview you can create one from Noesis and export the mesh as .fbx. The bones in this fbx are named after creating order, and their initial rotations are not compatible with anim data. So the bones need to be renamed, and the mesh needs to be re-skinned with the new skeleton created by this script. You need to do the rename work first and save it as another .fbx file, then the new fbx can be imported by the "Load Mesh" button.

---------------------------------------------------------------------
So, if everything goes right, the steps should be:
1. Prepare the files, including the *.skl, the animation files, and the .fbx mesh file.
2. Press the "Create skeleton" button
3. (Optional) Press the "Load mesh" button
4. "Load Animation", and the other buttons are quite self-explainable
[RotTR_Importer.rar](https://xentaxbackup.github.io/file/22253_RotTR_Importer.rar)
## Post #291
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-23T06:53:35+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Here's a sample.
[RotTR_sample_2022-5-23.gif](https://xentaxbackup.github.io/file/22254_RotTR_sample_2022-5-23.gif)
## Post #292
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-25T05:36:38+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hello, do I have to change all the names of the bones?
## Post #293
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-25T06:37:29+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Yes. Practically we only need the first 185 bones, that's the maximum bone count in the animation files. The rest bones can be deleted because their names might mess up with the real id.

I add a new button to make the renaming easier. 
Be careful not to use this button more than once otherwise the bone names will be renamed multiple times and I don't know what the result will be. 
[RotTR_Importer.rar](https://xentaxbackup.github.io/file/22256_RotTR_Importer.rar)
## Post #294
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-26T15:36:15+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Do you upload your model?
## Post #295
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-27T04:54:36+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Do you upload your model?
Sorry, but I don't think it's permitted here to share real game assets. 
You should be able to get one following Gh0stBlade's instructions on the first post of this thread.
And you can rig any other model with the skeleton created by my tool.
## Post #296
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-27T05:07:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

My model is messed up
## Post #297
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-27T05:11:33+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Desktop 5-27-2022 9-39-06 AM-267.jpg (202.86 KiB) Viewed 201 times


> Reply from ChunYu ↑Fri May 27, 2022 12:54 pm at Fri May 27, 2022 12:54 pm
>
> 
Do you upload your model?
Sorry, but I don't think it's permitted here to share real game assets. 
You should be able to get one following Gh0stBlade's instructions on the first post of this thread.
And you can rig any other model with the skeleton created by my tool.
## Post #298
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-27T09:02:03+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

It seems you are trying to import the animations into Noesis. But the bones created by Gh0stBlade's python script are different than the skeleton created by my 3dsmax script for the bones are having different "base rotation". I guess it's the reason of the twisted result in Noesis.

btw, do you have correct animations in 3dsmax?
## Post #299
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-27T16:33:05+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from ChunYu ↑Fri May 27, 2022 5:02 pm at Fri May 27, 2022 5:02 pm
>
> 
It seems you are trying to import the animations into Noesis. But the bones created by Gh0stBlade's python script are different than the skeleton created by my 3dsmax script for the bones are having different "base rotation". I guess it's the reason of the twisted result in Noesis.

btw, do you have correct animations in 3dsmax?

Yes the animation is good at 3ds max
## Post #300
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-27T16:36:16+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from gamer1977 ↑Sat May 28, 2022 12:33 am at Sat May 28, 2022 12:33 am
>
> 
ChunYu wrote: ↑Fri May 27, 2022 5:02 pm
It seems you are trying to import the animations into Noesis. But the bones created by Gh0stBlade's python script are different than the skeleton created by my 3dsmax script for the bones are having different "base rotation". I guess it's the reason of the twisted result in Noesis.

btw, do you have correct animations in 3dsmax?


Yes the animation is good at 3ds max
Of course the animation output after 3ds max
## Post #301
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-27T16:52:12+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Desktop 5-27-2022 9-19-47 PM-123.png (10.4 KiB) Viewed 306 times
## Post #302
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-05-28T02:42:06+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

If the animation looks good in 3dsMax, then the fbx exported should be OK for Noesis or any other game engine. I've tested Noesis and UE4 and they are working all right.
If you are still encounting problems maybe you could check the export options in 3dsmax, I hope that helps. 
[2605.gif](https://xentaxbackup.github.io/file/22268_2605.gif)
## Post #303
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2022-05-28T04:59:58+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from ChunYu ↑Sat May 28, 2022 10:42 am at Sat May 28, 2022 10:42 am
>
> 
If the animation looks good in 3dsMax, then the fbx exported should be OK for Noesis or any other game engine. I've tested Noesis and UE4 and they are working all right.
If you are still encounting problems maybe you could check the export options in 3dsmax, I hope that helps.

Please send me the model you are using to test it to see where I am wrong
## Post #304
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2022-07-17T18:24:42+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from ChunYu ↑Wed May 25, 2022 2:37 pm at Wed May 25, 2022 2:37 pm
>
> 
Yes. Practically we only need the first 185 bones, that's the maximum bone count in the animation files. The rest bones can be deleted because their names might mess up with the real id.

I add a new button to make the renaming easier. 
Be careful not to use this button more than once otherwise the bone names will be renamed multiple times and I don't know what the result will be.

Hi, thanks for the tool, i'm a bit missunderstood, how i need rename skeleton, and re-skin mean i lost original in-game skin wights wich i get from noesis, or i can transfer it or hold for new skeleton? 

It is sound like if noesis plug-in mod in some cases, for name of bones, as equal name for your max script, then i just re-link (re-join) new created skeleton and because names of bones are same, noesis weights can be work then.

Or i don't actualy understand how to keep noesis weights, attach new skeleton and keep it work without different bone names.
## Post #305
- Username: ChunYu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 22, 2021 5:12 pm
- Post datetime: 2022-07-18T03:42:58+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> how i need rename skeleton, and re-skin mean i lost original in-game skin wights wich i get from noesis, or i can transfer it or hold for new skeleton?
The skin weights from Noesis will be copied and transfered to the maxscript skeleton. That's why the rename is neccesary. The "load mesh" button only transfer bone weights between the bones with same names.

> It is sound like if noesis plug-in mod in some cases, for name of bones, as equal name for your max script, then i just re-link (re-join) new created skeleton and because names of bones are same, noesis weights can be work then.
There are two major differences between the Noesis skeleton and the maxscript skeleton:
1.) The names of the bones. Noesis bones names are 1,2,3,4,5...etc, while the maxscript bone names are 1,2,3,84,85...  In fact the id 84, 85 are the real id stored in the original game model and animation files.
2.) The init rotation of the bones. The Noesis version is "Y-axis up", while the maxscript version is "Z-axis up".
It seems the "re-link(re-join)" method can't solve the difference of axis orientation in my opinion.

> Or i don't actualy understand how to keep noesis weights, attach new skeleton and keep it work without different bone names.
The maxscipt is plain text file, and you can open it by any text editor. Look for the "Load Mesh" function and you will see the code details. I hope that helps.  


A detailed tutorial for preparing the "renamed" fbx file for better preview:
1.) Using Noesis to export the lara model as fbx named "A.fbx"
2.) In 3dsMax, open a clean new scene, and import A.fbx using the "File -> Import -> Import "
3.) Run the script tool, then hit the "Rename bones" under the "Mesh" group of the script panel. Now you will see the bone names have been changed from bone001,2,3,4,5 ... to bone001,2,3,83,84...
4.) Select all the bones and meshes, then export them altogether to "B.fbx" using the "File -> Export -> Export"
5.) Delete everything in the current scene manually or by hitting the "Clear All" button on bottom of the maxscript panel.
6.) Fill in the corresponding "Root folder" and "Skl file" path under the "Bone" group of the maxscript panel.
7.) Hit the "Create Skeleton" button on the maxscript panel. Now you will see a set of bones.
8.) Fill in the "Mesh File" string box with the full path of the B.fbx on the maxscript panel under the "mesh" group.
9.) Hit the "Load Mesh" button on the maxscript panel.
10.) After a few seconds of loading the meshes should appear.
11.) Hit the "Load Animation" on the maxscript tool.
## Post #306
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2022-07-18T17:13:09+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

@ChunYu
Thanks for the advanced answer, a try to get step by step with you guide.
At this moment i try to export noesis only 185 bones then rename bone names wich match with max script in fbx, then reattach skel in blender, some place have miss weight painted, but it best at this time. before you answer here. thanks for the tool.  

Update
I try your method and have problems as i have before (mesh are broken in animation), and i solved problem, when i export model "b.fbx", and after that, i just restart max, then continue steps and mesh now look good when load anim.
## Post #307
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2022-08-05T21:47:01+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

I hope the right people are still around to read this: The game can read additional, user-created Tiger archives by creating an accompanying nfo file containing certain properties. I'm not sure if this is known, but if it is, why has no one gone ahead with this approach?

I'm thinking it may be a much less complicated way of installing mods. However, I'm still unable to serialize DRM sections the game can read without error.
## Post #308
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2022-08-08T20:04:21+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

This is on the latest Steam version. Now I have to find out how the game loads assets, maybe I can force it to load them from higher priority archives.
## Post #309
- Username: andreaowlcj
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2021 1:44 am
- Post datetime: 2023-03-18T12:11:34+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

Hey guys, i am new at this website and i want to tell you guys something, i downloaded the drm and tigger unpacker and the noesis script to see the models but when i loaded a model, it doesn't have bones. So is there something that i missed or is the script outdated? Because i want to get the bones to rig them properly.
## Post #310
- Username: andreaowlcj
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2021 1:44 am
- Post datetime: 2023-04-15T14:41:54+00:00
- Post Title: Re: [PC/X360] Rise of the Tomb Raider Bigfile.000.tiger

> Reply from andreaowlcj ↑Sat Mar 18, 2023 8:11 pm at Sat Mar 18, 2023 8:11 pm
>
> 
Hey guys, i am new at this website and i want to tell you guys something, i downloaded the drm and tigger unpacker and the noesis script to see the models but when i loaded a model, it doesn't have bones. So is there something that i missed or is the script outdated? Because i want to get the bones to rig them properly.

*Update:
Nevermind, i know how to do it now,but thanks anyways
