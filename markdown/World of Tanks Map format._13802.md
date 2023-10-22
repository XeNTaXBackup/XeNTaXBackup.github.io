## Post #1
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T13:37:52+00:00
- Post Title: World of Tanks Map format.

Hello...
I created an app over the course of a couple years of hacking the .pkg files that loads World of Tanks Maps.
[http://worldoftanks.curseforge.com/wot- ... ne/images/](http://worldoftanks.curseforge.com/wot-mods/terra-3d-tactical-battle-designe/images/)

The last version of World of Tanks has removed the .chunk files from the .pkg files.
.chunk files contain all the information about what models belong to each chunk and their transforms.
Maps are made of "chunks' put together to from a much larger area.

It looks like all this chunk information has been moved to a single and fairly large file called "space.bin"

What I know so far.
The beginning of the file is nothing more than a table.
Each entry has a 4 character heading followed by 5 int32 values.
The first table entry describes the table its self.
The 2nd int32 in this the length of the table including the first row.
The 5th int32 looks to be the additional number rows in the table. Each row is 24 bytes long or 6 int32s (including the 4 byte character heading)
We can test this.
For the ENSK map.. the entry count is 18 hex or 24.
24 * 24 = 576. The 1st row says the table length is 258 hex or 600.
IF we add the 24 for the very first row they equal each other.

1st... The order of table entries is probably not going to be the same on every map.
Wargaming likes to scramble things when they export things from their tools.
The first table entry starts with "BWTB" I'd guess this means "BigWorld Table".. BigWorld is the game engine.

The 2nd row in the table has a heading of "BWST" ST could mean "Section Table"
In this row, the 2nd int32 after the header characters = 258h which is the start of the data. (also the total lenght of the table)
the 4th entry + 258h points to the end of the first section. It is the length of the data for this table entry.

Looking at the start of this data, It looks like  a list of 4 int32s that are info on the sections.
String length, some index? data index? Chunk end?

I need help sorting this out if anyone wants to give it a try.
## Post #2
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T16:04:50+00:00
- Post Title: World of Tanks Map format.

This is what I have figured out so far....
[space_file_format_1.jpg](https://xentaxbackup.github.io/file/10297_space_file_format_1.jpg)
## Post #3
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-01-12T17:21:16+00:00
- Post Title: World of Tanks Map format.

This is really interesting.... Maybe we could use this on older versions of WoT to acquire the maps WG removed.
## Post #4
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T17:37:50+00:00
- Post Title: World of Tanks Map format.

> Reply from Portugalotaku
>
> This is really interesting.... Maybe we could use this on older versions of WoT to acquire the maps WG removed.
I can already read the old maps.. Its the new way they are storing the data thats screwed me over.

There is a file called Map_list.txt or something like that in the install folder of Terra!.. It tells the app what maps to look for.
You could edit that and remove all the maps and add in only the ones you want.
CURSE has info on all this and how to edit that file.
Be aware.. you can NOT load any maps after the last WoT update.
## Post #5
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T17:48:08+00:00
- Post Title: World of Tanks Map format.

Ok..
Here is a partial dump of the items in the first table:

```
content/Buildings/bld4505_coverright2/normal/lod2/bld4505_coverright2_lod2.primitives/indices
content/Environment/env030_MilkCans/env030_MilkCans_NM.dds
maps/spots/Nature/Grass_edge_NM.dds
content/Environment/env440_borders/border_c2_90.model
content/Environment/envWGL_001_Banner/normal/lod0/WGL_Banner_08.primitives
fffffffco.cdata/terrain2
content/Environment/env012_Chairs/env012_Chairs.dds
content/Buildings/bld002_MiddleWoodShed/bld002_MiddleWoodShed_NM.dds
g_useNormalPackDXT1_safe
content/MilitaryEnvironment/mle016_BoxesHowitzer/mle016_BoxesHowitzer.dds
content/Environment/env415_TownBench/normal/lod0/env415_TownBench2.primitives/indices
content/Buildings/bld6113_shed/normal/lod0/bld6113_shed_lod0.model
content/Environment/env610_HorizontalBar/normal/lod0/env610_HorizontalBar.primitives
content/Environment/env019_Rubbish/normal/lod0/env019_Rubbish3.primitives/vertices
content/Buildings/bld6101_thouse/bld6101_02_details_SM.dds
content/Environment/env208_Log_Firewood/normal/lod0/env208_Log_Firewood07.primitives/indices
inf_env004_Telega_01
content/Buildings/bld6112_shed/normal/lod1/bld6112_shed_lod0.primitives/indices
content/Buildings/bld6108_thouse/normal/lod2/bld6108_thouse.primitives/indices
content/Environment/env601_BunchLogs/normal/lod1/env601_BunchLogs5.primitives/vertices
maps/spots/Damage/RoadTrash_01.dds
content/Buildings/bld_Constructor01/bld_Constructor01R.dds
content/Railway/rw004_Carriage/normal/lod0/rw004_Carriage4.primitives
content/GatesAndFences/gaf005_FactoryGates/normal/lod0/gaf005_FactoryGates.model
content/Environment/env414_Pole/normal/lod0/env414_Pole3.primitives/indices
content/Buildings/bld4204_rHouse/normal/lod0/bld4204_rHouse.primitives/vertices
content/Buildings/bld003_LittleWoodShed/normal/lod0/bld003_LittleWoodShed.primitives/indices
content/Environment/envWGL_001_Banner/normal/lod0/WGL_Banner_10.model
content/Buildings/bld000_base/normal/lod0/bld000_base.model
inf_env610_HorizontalBar

```


Looking at this has me thinking they are storing the models in this space.bin file.. Maybe not but seeing what looks like are parts of the .visual in here as well tells me there is a lot data from all the models that make up a map.

I wonder if this is a python dump of some kind. They are doing that with WoWS.
I don't know python well enough to know what it looks like.

This data is all from 06_ensk.pkg
Look in /spaces/



I attached the entire list of items. (Actually.. this is just the first group of string entries. There are more)
[ensk_space_itmes_dump.zip](https://xentaxbackup.github.io/file/10298_ensk_space_itmes_dump.zip)
## Post #6
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T18:11:10+00:00
- Post Title: World of Tanks Map format.

I have been digging in the scripts folder for WoTs and
I see they have a obfuscators.pyc file in there.

This may make it totally impossible to figure this out.
If you don't know what obfuscation is, read [THIS](https://en.wikipedia.org/wiki/Obfuscation_%28software%29)
## Post #7
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-01-12T20:43:04+00:00
- Post Title: World of Tanks Map format.

> Reply from Coffee
>
> This may make it totally impossible to figure this out.
Looks like it's used for password storing:

```
import base64
from debug_utils import LOG_CURRENT_EXCEPTION

class XORObfuscator:
    __PREFIX = '#obfuscate:'

    def __init__(self, key):
        if len(key) < 1:
            raise ValueError, 'Key length must be at least one character'
        self.__key = key

    def __doXor(self, data):
        kIdx = 0
        processed = []
        for x in range(len(data)):
            processed.append(chr(ord(data[x]) ^ ord(self.__key[kIdx])))
            kIdx = (kIdx + 1) % len(self.__key)

        return ''.join(processed)

    def obfuscate(self, data):
        return base64.b64encode(self.__PREFIX + self.__doXor(data))

    def unobfuscate(self, data):
        if len(data.strip()) % 4 != 0:
            return data
        try:
            decode = base64.b64decode(data)
        except:
            LOG_CURRENT_EXCEPTION()
            return data

        if decode.startswith(self.__PREFIX):
            return self.__doXor(decode[len(self.__PREFIX):])
        return data


class PasswordObfuscator(XORObfuscator):

    def __init__(self):
        XORObfuscator.__init__(self, '416c34666745786b'.decode('hex'))
```
## Post #8
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-12T20:52:00+00:00
- Post Title: World of Tanks Map format.

Where is that code from?
Can you decompile Python?
## Post #9
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-01-12T21:21:06+00:00
- Post Title: World of Tanks Map format.

> Reply from Coffee
>
> Can you decompile Python?
Of course I can :)))
[http://sourceforge.net/projects/easypythondecompiler/](http://sourceforge.net/projects/easypythondecompiler/)
## Post #10
- Username: TheSeeker
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Sep 29, 2015 8:36 am
- Post datetime: 2016-01-13T03:12:07+00:00
- Post Title: World of Tanks Map format.

> Reply from Andrakann
>
> Coffee wrote:Can you decompile Python?
Of course I can ))
http://sourceforge.net/projects/easypythondecompiler/
yeah, I've no idea why WoT scripts can be decompiled and WoWS scripts can't
## Post #11
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-13T10:59:58+00:00
- Post Title: World of Tanks Map format.

Your topic on Russian language -> [http://www.koreanrandom.com/forum/topic/29351-/](http://www.koreanrandom.com/forum/topic/29351-/)
## Post #12
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-01-13T15:01:34+00:00
- Post Title: World of Tanks Map format.

> Reply from TheSeeker
>
> yeah, I've no idea why WoT scripts can be decompiled and WoWS scripts can't
WoWS devs obfuscated all python scripts because they dont want python mods in game with near cheating possibilites, like in WoT.
So, they got mods for aiming point without using python - sad but true
## Post #13
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-14T10:35:40+00:00
- Post Title: World of Tanks Map format.

I too did some digging. I noticed those strings

content/Buildings/bld4505_coverright2/normal/lod2/bld4505_coverright2_lod2.primitives/indices
content/Environment/env019_Rubbish/normal/lod0/env019_Rubbish3.primitives/vertices

now, indicies and vertices are actually parts of primitives file. So I dug out those .primitives files refered (note, that most of .primitives and .dds files used in maps dissapeared or been moved to shared_content_sandbox), took those parts (vertices/indicies) and halleluja, found a match inside .bin file.
So the contents most likely aren't encrypted/compressed.

Also notice, that LOD (level of detail) is actually directly referred in these. That is weird, because now user can't change quality of objects on map....

EDIT: the primitives are inside the BWSG chunk
EDIT2: contents of last primitive mentioned in that list of string aren't at the end of the BWSG chunk. Maybe there are more parts, that aren't identified by string....
## Post #14
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-14T13:24:00+00:00
- Post Title: World of Tanks Map format.

UDOS - User Data Object Section
CENT - Content
## Post #15
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-16T18:42:38+00:00
- Post Title: World of Tanks Map format.

BSMI points at matrices.
16 floats per item

It looks like the first int32 in a data section is the length of the data for each entry.
I already figured out that the next int32 is the number of entries in that data section.

Some other basic info..
Any time you see a .dds image, this is a decal. Decals are laid over the top of the terrain to add more detail.
Decal's have a matrix just like any other item.
The above is WRONG... There seems to be image files for models as well in the data. WHY???

So I can get the items names and the items transforms... That is..  if the matrices are listed in the same order as the list of items that are in string format.
There is some trick shit going on because the matrix count = 4584. There are only 1585 items in string format listed for the items.
BUT... a lot of items are reused .. like light poles or fence sections. One item might have 5-10 or even 20 matrices that are associated with it.
That being said, there must be a list in the data some where that tells us how many of each item there is on the map.
## Post #16
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-16T21:49:26+00:00
- Post Title: Re: World of Tanks Map format.

Regarding the dds files, they are probably inside the BIN file, but I wasn't able to match any part of any existing dds file inside. I'm guessing they're probably compressed or in different format.
## Post #17
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-17T16:23:26+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Regarding the dds files, they are probably inside the BIN file, but I wasn't able to match any part of any existing dds file inside. I'm guessing they're probably compressed or in different format.

Yes.. I just looked to and there is nothing under misc/maps/spots/ but one folder  "tankOcclusion"

So.. they have packed the DDS files in to this bin as well some how.
I'll search the file for DDS headers and see if I can find some.
Well.. DDS(space) is the header and I cant find it so Im assuming its stripped or the files are scrambled.

This is a nightmare.
## Post #18
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-17T16:28:02+00:00
- Post Title: Re: World of Tanks Map format.

You can still find them (the textures) in shared_content_sandbox.pkg if you want to do some tests
## Post #19
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-17T16:59:59+00:00
- Post Title: Re: World of Tanks Map format.

so maybe the textures are not stored in the space.bin

I can't figure this out.
There is one huge chunk called BWSG and it has table after table after table in it.
## Post #20
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-17T18:50:50+00:00
- Post Title: Re: World of Tanks Map format.

I have been working with Ensk because its small in size
This data is from the start of BWSG .. 
It has the same general format at the start of all tables in the data.

OK.. this works for "BWST"
[space_format_BWSG.jpg](https://xentaxbackup.github.io/file/10327_space_format_BWSG.jpg)
## Post #21
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-17T18:55:03+00:00
- Post Title: Re: World of Tanks Map format.

The first entry in the above hex is the length of each entry in THIS table.
The 2nd is the number of entries in the THIS table and the 3rd is the total length of the table.

The first actual entry in the table is the offset from the start of the string table.
The 2nd int32 is the length of the string. (all strings are terminated with 0 but are not included in the length of the string)
The 3rd number is the one that I am confused about.
It can not be a pointer in to the data. Its to large.

Here is an image of the string section.. the Highlighted section is 52 hex in length. You can see the 0 terminator at the end of the string.
[space_format_BWSG_2.jpg](https://xentaxbackup.github.io/file/10328_space_format_BWSG_2.jpg)
## Post #22
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-17T19:13:10+00:00
- Post Title: Re: World of Tanks Map format.

The table below is the table right after the string table.
I deleted the first 2 int32s to align the data for viewing.
Whats it all mean???
[space_format_BWSG_3.jpg](https://xentaxbackup.github.io/file/10329_space_format_BWSG_3.jpg)
## Post #23
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-18T17:13:57+00:00
- Post Title: Re: World of Tanks Map format.

What it is?



Снимок экрана (172).png (54.5 KiB) Viewed 62 times



0xffffffff is not float-like bytes...
## Post #24
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-18T19:57:09+00:00
- Post Title: Re: World of Tanks Map format.

You are probably outside that data chunk..
Let me look at its length.
If you do the math... 
There are 4584 entries in the 1st table. Each is 64 bytes long. (16 floats)
Add 8 to this for the data length and the count at the very beginning we get 0x74A08
This is the start of the 2nd table in the data.
At the start of this table is the length of the data type.. It this case its 8. next is the number of entries.
0x11e8 = 4584... the same count as there are matrices.
So 4584 * 8 + 8 = 36680 = 0x8f48.
0x8f48 + 0x74a08 = 0x50950 (the start of the 3rd table)
The 3rd table starts with 0x04 (4 bytes per data item).. the 2nd int32 = 0x11e8 = 4584 (same as the other tables)
(4584 *4) + 8 = 0x47a8 = 18344
0x50950 + 0x47a8 = 0x550f8 (start of 4th table) This is the start of the data you posted a image of.
The 1st table are matrices. 
The 2nd table I have no idea what its data means. 
The 3rd table I also have no idea but looks like index numbers. The highest number I can find is 1cd or 461.
the 4th and last table also makes no sense.. All 0xffffffff
## Post #25
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-18T20:09:02+00:00
- Post Title: Re: World of Tanks Map format.

Снимок экрана (176).png (46.29 KiB) Viewed 58 times
## Post #26
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-18T20:12:31+00:00
- Post Title: Re: World of Tanks Map format.

End of BSMI block:



Снимок экрана (177).png (54.6 KiB) Viewed 57 times
## Post #27
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-18T21:19:25+00:00
- Post Title: Re: World of Tanks Map format.

Each table in the main header table list seem to be made of smaller tables.
I am not sure ALL tables are like this.
Also.. Some tables do not list the total size of the data.

There has to be a way to re-assemble these tables in to meaningful data.

Ensk is a small map. It is made of 8 x 8 chunks if I remember right. 600m x 600m is the map playable area. Each grid on the minimap is 60m.
This data should contain what chunk each item belongs to. This is how it was done before and each chunks location had to be added to any items translation to position it correctly. I cant dint this information but...
Looking at the transform numbers, they may already be transformed by the chunks location.
## Post #28
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-18T22:27:00+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> The 2nd table I have no idea what its data means. 
The 3rd table I also have no idea but looks like index numbers. The highest number I can find is 1cd or 461.
the 4th and last table also makes no sense.. All 0xffffffff
Sadly...
## Post #29
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-19T16:45:49+00:00
- Post Title: Re: World of Tanks Map format.

I dumped the matrices for BSMI in to a text file.
[http://209.159.152.184:8080/junk/BSMI.txt](http://209.159.152.184:8080/junk/BSMI.txt)

Here is a section of it.
You can see that the transforms (last row) is clearly larger than 100. This means the transforms will work with out knowing what grid they are sitting on.

```
	000.83525700	000.00000000	000.00000000	000.00000000
	000.00000000	000.83525700	000.00000000	000.00000000
	000.00000000	000.00000000	000.83525700	000.00000000
	-316.57570000	007.11425700	-308.33920000	001.00000000
index:0001
	000.86728400	000.00000000	000.00000000	000.00000000
	000.00000000	000.86728400	000.00000000	000.00000000
	000.00000000	000.00000000	000.86728400	000.00000000
	-327.59740000	011.91113000	-325.82480000	001.00000000
index:0002
	-001.40854200	-000.02422100	000.20917900	000.00000000
	-000.01477700	001.13263000	000.03165200	000.00000000
	-000.20975400	000.03661500	-001.40818400	000.00000000
	-309.15170000	019.66447000	-375.09310000	001.00000000
index:0003

```

There are 4584 entries. (0 to 4583)
Some where there must be a way to bind each one of these matrices to an object.
If we can find a table that has an index that goes as high as 4583 it will help sort this out.
## Post #30
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-19T17:00:07+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> If we can find a table that has an index that goes as high as 4583 it will help sort this out.
The index can be in a uint32 with bit shift...
## Post #31
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-20T07:39:56+00:00
- Post Title: Re: World of Tanks Map format.

Those matrixes are objects positions (probably just objects, but it's only speculation). Tried to visualise them on hills map:



Visualisation 2016-01-20 08_35_56-WoT Tank Viewer.jpg (208.51 KiB) Viewed 40 times



Also:
BWSG contains only vertices
BWST probably contains aggregated .visual files ... but only names and keys? BWSS looks suspisious

The string lists in both of those files contains filenames AND keywords. For example, in BWSS, along with .dds files and .model files you can find strings:

```
diffuseMap
diffuseMap2
doubleSided
```


all those keys can be found in .visual file

Last word: textures probably aren't packed inside space.bin after all?
## Post #32
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-20T15:09:42+00:00
- Post Title: Re: World of Tanks Map format.

I see you figured out how the terrain is stored  That's good.

I can clearly see the location of the fences and even the olive shrubs in that image.
Also the location of the mine entrance model.

Yes.. The matrices are for sure the objects positions( trees, decals, anything that has a location on the map)

Knowing that each item has a matrix and they can be different types might help sort this out.
The 2 tables that have the strings in them "BWST" and "BWSG" have the entry list at the start.
The data length is 3 int32s or 12 bytes.
The first of these is a cryptic number followed by the length of the string and its offset from the start of the string data.

Figuring out what this that int32 is and what it's used for would be a great step towards sorting out this file.
That int32 is not a pointer.. it becomes to large and at some point is larger than the entire files length.
It could be an index and a pointer mixed mixed together some how. It could also be an ID number.


We know that there are at least 3 types of objects.
Models like houses.. rocks... fences..
Tree Models..
Decals..

I think looking through the list of strings and picking out the same types and than comparing them with that cryptic number might help?
## Post #33
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-20T16:27:31+00:00
- Post Title: Re: World of Tanks Map format.

Off topic..
Some people are trying to hack my server :
IP 61.216.2.13
Taipei, T'ai-pei (03), Taiwan
and
IP 80.254.121.85
Rostov-on-don, Rostov (61), Russian Federation

If any of you own this IP.. you had better stop trying to hack my FTP.
If you don't.. I will band the entire country by IP mask!
This means you will NEVER get download addresses again!!!
## Post #34
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-20T16:51:38+00:00
- Post Title: Re: World of Tanks Map format.

I dumped the string entries for BWSG and BWST.
These text files have the hex code that is associated with them.
It might help some one sort this out.
[http://209.159.152.184:8080/junk/](http://209.159.152.184:8080/junk/)
## Post #35
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-20T17:41:24+00:00
- Post Title: Re: World of Tanks Map format.

Ok...
I striped out all the cdata strings from BWST
These are the map sections.
Ensk has 64 grid sections ( 8 x 8 ) 
The cryptic:nnnn is the cryptic Int32 in the index list at the start of BWST
[http://209.159.152.184:8080/junk/BWST_cdata_list.txt](http://209.159.152.184:8080/junk/BWST_cdata_list.txt)
## Post #36
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-20T20:56:11+00:00
- Post Title: Re: World of Tanks Map format.

Ok...
SpTr starts with the length of the data type... followed by the number of entries
After this is the data list:
16 floats.. A Matrix. + 3 int32s 

the data length is 0x4C or 76 bytes or 19 int32s
## Post #37
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T14:24:50+00:00
- Post Title: Re: World of Tanks Map format.

I am having no luck so far figuring out what those Int32 are for.
Like the SpTr file list has a matrix, (16 floats) the int32 and then 2 more int32s that are always = to 1.

```
00000000 D87F393F 00000000 00000000
01CB605B F0000000 A3E62BBC 00000000
08BF9AC3 FD53AE41 1DA4BDC3 0000803F
77BDC315 01000000 01000000
```


Here is the list of all trees in ensk.

```
0001: Cryptic:15d77cf5 : speedtree/06_Ensk/Spruce_1.spt
0002: Cryptic:49dea56c : speedtree/06_Ensk/BirchFall.spt
0003: Cryptic:70b77084 : speedtree/06_Ensk/DryTree_1.spt
0004: Cryptic:91a713e5 : speedtree/06_Ensk/HorseChestnut_1.spt
0005: Cryptic:b80b2442 : speedtree/06_Ensk/AppleTree.spt
0006: Cryptic:bfef5841 : speedtree/06_Ensk/Shrub.spt
0007: Cryptic:c6d3233b : speedtree/06_Ensk/Linden_1.spt
0008: Cryptic:f68c7360 : speedtree/06_Ensk/Maple.spt
0009: Cryptic:fdeacdc6 : speedtree/06_Ensk/Oak.spt

```

[del_seki.jpg](https://xentaxbackup.github.io/file/10345_del_seki.jpg)
## Post #38
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T14:31:09+00:00
- Post Title: Re: World of Tanks Map format.

I just spotted a match in the code above.

Reverse the cryptic for the first tree and it matches the cryptic in the matrix. The 17th int32.
The cryptic in the list of trees is backwards because of little endian. It's shown as its actual value.
Hmmmm....
## Post #39
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T14:36:36+00:00
- Post Title: Re: World of Tanks Map format.

Good job so far! Tried everything to match those cryptic numbers with positions in file or table but with no results.
I tried reading it asi two uint16, reading the size as only uint16 and then reading uint32 and uint16 .... but it never pointed to any plausible location.

I'm currently having my finals, so I don't have much time
## Post #40
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T14:57:30+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> 
I'm currently having my finals, so I don't have much time

Stay on those FINALS... This is NO WHERE near as important as your education!!!
## Post #41
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T15:29:57+00:00
- Post Title: Re: World of Tanks Map format.

Ok... 
Doing a search of the SpTr section I found 207 matches for the first trees cryptic int32.
The interesting thing is, at the end of the file there are some left over values.
I would bet these are what associates all of these trees with some more info.

Trees have a special shader and some other flags that are set.
If we can figure out how these last numbers are associated with the hidden .visual info, I think it will unlock all the files formats.
Here are those last int32s in the SpTr section.

```
0000C8C3
3CDF27C0
0000C8C3
0000C843
00000000
00000000
```

I doubt the last 2 are meaningful.. Probably just padding to align the data??
## Post #42
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T15:31:32+00:00
- Post Title: Re: World of Tanks Map format.

I am uploading all the split off sections from the space.bin (ensk map)
This will take some time.. its something like 36 meg of data.
Edit:
Its done uploading.
These splits will make it easier to look at the data.
They are named the same as the sections in the space.bin
There are also some other helpers in there that I created by extracting just some of the data.
The space.bin is the ENSK file.. 
Ensk is 8 x 8 sections. It is the smallest map in the game. I chose this because of its size. Its less data to weed through.

[http://209.159.152.184:8080/junk/](http://209.159.152.184:8080/junk/)
You can right click and save these to your local hard drive.
## Post #43
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T15:38:20+00:00
- Post Title: Re: World of Tanks Map format.

Hey, maybe using the hangar_v2 space would make things easier? There aren't any trees, but it's much smaller ...
## Post #44
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T15:52:38+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Hey, maybe using the hangar_v2 space would make things easier? There aren't any trees, but it's much smaller ...
That's a good idea but I have been staring at the ensk files for so long its like a friend now...
## Post #45
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T15:59:41+00:00
- Post Title: Re: World of Tanks Map format.

```
0000C8C3
3CDF27C0
0000C8C3
0000C843
00000000
00000000
```

I found a match in "BWT2"
I'm assuming T2 = Terrain 2
At the start of this file there are int32s that = the maps cdata names and some other data.
[matched_1.jpg](https://xentaxbackup.github.io/file/10346_matched_1.jpg)
## Post #46
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T20:07:08+00:00
- Post Title: Re: World of Tanks Map format.

BWSG Progress!
After the string table in BWSG, there is another table, that has the same start

entry_size uint32   (in my case 20)
entry_count uint32 (in my case 19 - 2 less than previous table)
unknown, uint32?

a the end of each entry in this table, there is weird uint32 ... which matches the uknown number in the string table!
This is how the table looks inside hangar_v2 .bin file .... I split each entry into 4 uint32, last being the cryptic value, which is probably some kind of ident?
The string at the end is string from first table which has matching unknown value....

```
00000000,00000001,0000007E,38680637,6E8602DF particles/mesh_particles/lights/Hangar_v2_lights/hangar_v2_uplights.primitives/vertices
00000001,00000002,00000024,38680637,47C44BA1 xyznuvtb
00000002,00000003,0000001D,38680637,CAEEF31E content/Environment/hangar_v2/group/normal/lod0/group5.primitives/vertices
00000003,00000004,0000001A,38680637,8CC42139 content/Environment/hangar_v2/group/normal/lod0/group2.primitives/vertices
00000004,00000005,00000008,38680637,64E2E7A5 content/Environment/hangar_v2/group/normal/lod0/group6.primitives/vertices
00000005,00000006,00000028,EC1E4741,FFA9D14C xyznuv
00000006,00000008,00000014,EC1E4741,8BBE133F content/Environment/env616_Background_trees/env616_Background_Trees_04.primitives/vertices
00000008,00000009,00000128,38680637,D7BB4F5C content/Environment/env616_Background_trees/env616_Background_Trees_03.primitives/vertices
00000009,0000000A,00000DF3,38680637,B4B63C62 content/Environment/hangar_v2/backgroung/normal/lod0/Background1.primitives/vertices
// NOTICE THE INDEX SKIPPED ONE HERE
0000000A,0000000C,00002E39,38680637,309D82D0 content/Environment/hangar_v2/group/normal/lod0/group4.primitives/vertices 
0000000C,0000000D,00000008,38680637,B94DA052 content/Environment/hangar_v2/hangar/normal/lod0/hangar_v2_part02.primitives/vertices
0000000D,0000000E,00001AB5,38680637,5A5DA05B content/Environment/hangar_v2/hangar/normal/lod0/hangar_shadow_part01.primitives/vertices
0000000E,0000000F,000008B5,38680637,49275C42 content/Environment/env616_Background_trees/env616_Background_Trees_02.primitives/vertices
0000000F,00000010,00000010,38680637,2F2AE981 content/Environment/env616_Background_trees/env616_Background_Trees_01.primitives/vertices
00000010,00000011,000019F9,38680637,E98D8899 content/Environment/hangar_v2/hangar/normal/lod0/envIN_007_hangar_v2_props_09_03.primitives/vertices
// NOTICE THE INDEX SKIPPED ONE HERE
00000011,00000013,000002E0,38680637,BD19F57E content/Environment/hangar_v2/group/normal/lod0/group1.primitives/vertices
00000013,00000014,00002527,38680637,4A26E0EF content/Environment/hangar_v2/hangar/normal/lod0/hangar_shadow_part02.primitives/vertices
// NOTICE THE INDEX SKIPPED ONE HERE
00000014,00000016,00000982,38680637,DB0C79B6 content/Environment/hangar_v2/group/normal/lod0/group3.primitives/vertices
00000016,00000017,0000013D,38680637,00000014 //FAILED TO FIND MATCH IN FIRST TABLE
```


Those strings from first table were left unmatched

```
38680637 content/Environment/hangar_v2/backgroung/normal/lod0/Background2.primitives/vertices
EC1E4741 content/Environment/hangar_v2/hangar/normal/lod0/Floor_part01.primitives/vertices
```
## Post #47
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T20:54:23+00:00
- Post Title: Re: World of Tanks Map format.

Ok...
Looking at the strings in BWSG... 
0270: Cryptic:ec1e4741 : content/MilitaryEnvironment/mle019_GerBoxes/normal/lod0/mle019_GerBoxes3.primitives/vertices
If I search further in BWSG I find this
[matched_2.jpg](https://xentaxbackup.github.io/file/10347_matched_2.jpg)
## Post #48
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T20:57:19+00:00
- Post Title: Re: World of Tanks Map format.

Ok, I think I figured it out now:
BWSG
1. table -> Table of strings associated to keys
2. table -> Uses said strings to ??

1.table

```
4  uint32 size of string
8  uint32 key

```


Example of contents:

```
64E2E7A5 content/Environment/hangar_v2/group/normal/lod0/group6.primitives/vertices
00000658 particles/mesh_particles/lights/Hangar_v2_lights/hangar_v2_godrays.primitives/vertices
E98D8899 content/Environment/hangar_v2/hangar/normal/lod0/envIN_007_hangar_v2_props_09_03.primitives/vertices
FFA9D14C xyznuv
....
```


2. table

```
4  uint32 some kind of index, bigger then first
8  uint32 uknown?
12  uint32 key refering to first table
16 uint32 key refering to first table

```


Example contents:

```
00000000,00000001,0000007E,38680637,6E8602DF
00000001,00000002,00000024,38680637,47C44BA1
00000002,00000003,0000001D,38680637,CAEEF31E
....

```


can be then converted to:

```
key2 particles/mesh_particles/lights/Hangar_v2_lights/hangar_v2_uplights.primitives/vertices

key1 content/Environment/hangar_v2/backgroung/normal/lod0/Background2.primitives/vertices
key2 xyznuvtb

key1 content/Environment/hangar_v2/backgroung/normal/lod0/Background2.primitives/vertices
key2 content/Environment/hangar_v2/group/normal/lod0/group5.primitives/vertices

```


I'm smelling something similiar to packed XMLs
## Post #49
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T21:01:32+00:00
- Post Title: Re: World of Tanks Map format.

Nice work..

Notice my posted image how the highest index = 01B2 (B2010000) in that table...
Now.. Look at the total length of the next table.
Each data length is 0x14 long and the total entries are 01b2!
## Post #50
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T21:04:09+00:00
- Post Title: Re: World of Tanks Map format.

I think there is something wrong with my code .... I'm 100 % sure those two keys should be
xyznuv content/Environment/hangar_v2/group/normal/lod0/group6.primitives/vertices
or
xyznuvb content/Environment/hangar_v2/group/normal/lod0/group6.primitives/vertices

(vetrices type -> vertices name) ... key1 is repetetive (2 values in file I'm scanning), key2 is changing every line
## Post #51
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T21:06:27+00:00
- Post Title: Re: World of Tanks Map format.

XYZNUVTB and like items describe what type of vertex it is.
there are at least 3 used on the map
## Post #52
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T21:10:44+00:00
- Post Title: Re: World of Tanks Map format.

I have more info on what I have found in the BWSG section.
The last table in the BWSG (for enks) has 9 entries of 4 bytes in lenght.
Each int32 is the length of the next section. They are LONG sections of data.
I added all these together and it does indeed = the total length of the remainder of the file.
## Post #53
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T21:11:02+00:00
- Post Title: Re: World of Tanks Map format.

Yes. I'm suspecting the table format is wrong.
It should be
TABLE

```
4 uint32 entry_count

```

then each entry

```
4 uint32 position
8 uint32 size

```
## Post #54
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T21:17:55+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> 

Example contents:
Code: Select allIndex1  | Index2 |Unknown | Index1 | Index2 
00000000,00000001,0000007E,38680637,6E8602DF
00000001,00000002,00000024,38680637,47C44BA1
00000002,00000003,0000001D,38680637,CAEEF31E
....

You are off by the first column here.
The first column is right after the entry count.
## Post #55
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T21:20:03+00:00
- Post Title: Re: World of Tanks Map format.

OK BWSG file so far:
1. TABLE

```
4 uint32 entry_count
```

then you read each entry as follows

```
i + 4  uint32 position
i + 8  uint32 size
```

Then you can read size of strings table:

```
8 + entry_count * entry_size uint32 size of strings
```

You can then use read string for each entry, where position is relative to

```
8 + entry_count * entry_size + 4
```


2. TABLE
Begins right when 1. table ends (position: 8 + entry_count * entry_size + size_of_strings + 4)

```
4 uint32 entry_count
```


then you read each entry as follows

```
i + 4  uint32 unknown
i + 8  uint32 unknown
i + 12 uint32 uknown
i + 16 uint32 key2 (vertices type)
```


There is hoewer bit of data with unknown contents after this, which should contain positions of vertices in file
## Post #56
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T21:21:02+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> 
You are off by the first column here.
The first column is right after the entry count.

Yes, you're right, I was off by one column in both tables. My new description should be correct thought...
Also, you were correct about last table, there is definetly 3.TABLE. Contents are unknown toughgt:

```
00000000,00000020,00000480,00000000,00000FC0
00000000,00000020,000003A0,00000000,00001440
00000000,00000020,00000340,00000000,000017E0
00000000,00000020,00000100,00000000,00001B20
00000000,00000018,000003C0,00000000,00001C20
00000000,00000018,000001E0,00000000,00001FE0
0000000A,00000008,000000A0,00000000,000021C0
00000000,00000020,00002500,00000000,00002260
00000000,00000020,0001BE60,00000000,00004760
00000000,00000020,0005C720,00000000,000205C0
0000000A,00000008,000171C8,00000000,0007CCE0
00000000,00000020,00000100,00000000,00093EB0
00000000,00000020,000356A0,00000000,00093FB0
00000000,00000020,000116A0,00000000,000C9650
00000000,00000020,00000200,00000000,000DACF0
00000000,00000020,00033F20,00000000,000DAEF0
00000000,00000020,00005C00,00000000,0010EE10
0000000A,00000008,00001700,00000000,00114A10
00000000,00000020,0004A4E0,00000000,00116110
00000000,00000020,00013040,00000000,001605F0
0000000A,00000008,00004C10,00000000,00173630
00000000,00000020,000027A0,00000000,00178240

```
## Post #57
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T21:47:05+00:00
- Post Title: Re: World of Tanks Map format.

Here's script that extract all informations currently known by me:
[http://cerno.ch/~kamen/upload/test-bswg.py](http://cerno.ch/~kamen/upload/test-bswg.py)

3. TABLE -> purpose uknown
4. TABLE -> one item, length of rest of the file

We now have entire BWSG file covered!
## Post #58
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T21:59:12+00:00
- Post Title: Re: World of Tanks Map format.

The very last part of the BWSG is where most of the data is stored.
For ensk, it has 9 sections each rather large.
Im guessing that some of these unknown uint32s point in to these chunks
Seeing how there are 9 chunks.. we need find where this index is and that none of the other indexes are larger than one of these chunks.

```
09000000 : COUNT followed by each sections size (and they are large!)
E0FF3F00
B0FD3F00
D0FA3F00
E0FC3F00
50FB3F00
60FD3F00
40FC3F00
70FE3F00
20281000

```

As I said before.. I added all these together and it equals the length of the rest of the file.
If some of those unit32s are indexing in to this, there should be a length of the data as well.
## Post #59
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T22:06:33+00:00
- Post Title: Re: World of Tanks Map format.

3. TABLE item

```
16 uint32 position relative to item in 4.table
```


4. TABLE contains only single entry in hangar_v2.bin which is pointer to start of the vertices data
In larger maps, 4. Table actually has (as you said) more entries pointing to various parts of file...

EDIT: YES! Uint32 at 12 is actually index (counting index, no key or something) in 4. TABLE
## Post #60
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T22:47:05+00:00
- Post Title: Re: World of Tanks Map format.

This look right?
This is table 3.
[table3_index.jpg](https://xentaxbackup.github.io/file/10348_table3_index.jpg)
## Post #61
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T22:52:58+00:00
- Post Title: Re: World of Tanks Map format.

You're right, it's table index and offset. I just cracked entire bswg file and extracted the vertices parts from it.
Just give me some time to write script and description how it works.

There are still some unfigured data, but finally, entire file is described!

Sorry I wasn't answering your questions, but I'm just so excited I finally found something! Also I was deep inside the code.
## Post #62
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T23:03:25+00:00
- Post Title: Re: World of Tanks Map format.

Great!

Yes.. I'll need a detailed layout of the format. I program in .NET and I barely can read python.
Make sure this works with ENSK OK?
## Post #63
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-21T23:06:49+00:00
- Post Title: Re: World of Tanks Map format.

I know they have converted a lot of string numbers in to actual real floats in the data.. Like matrices.
We will need to be able to associate the correct matrix with each models vertices and indices.
Also.. almost all buildings on the maps contains 2 sets of UVs and 3 textures...
Some have 4 textures if they are also using the PBS shaders.
## Post #64
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-21T23:22:42+00:00
- Post Title: Re: World of Tanks Map format.

I described the format here:
[http://wiki.vbaddict.net/pages/BWSG](http://wiki.vbaddict.net/pages/BWSG)

I hope it's descriptive enought. I'll attach the scripts tomorrow, I'm too tired now.
## Post #65
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-22T11:31:59+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Here's script that extract all informations currently known by me:
http://cerno.ch/~kamen/upload/test-bswg.py

3. TABLE -> purpose uknown
4. TABLE -> one item, length of rest of the file

We now have entire BWSG file covered!
Please write your scripts compatible with Python3  

It is not difficult => [http://www.koreanrandom.com/forum/topic ... /?p=310323](http://www.koreanrandom.com/forum/topic/29351-/?p=310323)
## Post #66
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T14:27:33+00:00
- Post Title: Re: World of Tanks Map format.

Here is complete script (py3 compatible   )

[http://cerno.ch/~kamen/upload/test-bswg.py](http://cerno.ch/~kamen/upload/test-bswg.py)

It takes the BWSG file and extracts its contents into vertices folder. Which is useless, but it demonstrates the positions and sizes.
## Post #67
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T15:04:40+00:00
- Post Title: Re: World of Tanks Map format.

Note that table structure is reocurring theme,
BWST is only table of key -> string
BWMO contains only tables in this format (with some references to BWST - BW strings?)
## Post #68
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T15:09:41+00:00
- Post Title: Re: World of Tanks Map format.

Nice work on the page SkaceKachna

Basically everything we sorted out yesterday.
Id recommend you bracket "( )" the math. I have seen strange things happen in different compilers.

I can help a lot with the cdata files and also how the ctree data works.

For now Lets figure out how to reassemble the data for the models.


I know that the SpTr file contains matrices, each followed by its key and than 2 unt32s both always equaling 1.
At the end of this file there is some extra data. Some of these are floats and on ensk.. match the 1/2 width of the map. This could be a coincidence. There is what appears to be a key in there. One thing I said before is all the trees will use the same shader and flag settings.
ONLY BWSG contains the speedtree paths.
Consider SpTr hacked!

There is something I noticed about BWSG.
Almost every entry ends with "/vertices"
Where, BWST contains all kinds of names including .dds texture names.
Also.. BWST has no other tables than the index and the strings.
You can find the keys in BWST's index table in BWSG's 2nd table.
This in turn points in the the large chunks at the end.
I have a feeling (not tested) that these large chunks are a list of keys from
both the BWST and BSMI or some other matrix file. BMSI contains 4585 matrices.

There is no matching keys in the BSMI (matrix file) for entries in BWST.
They must come from some where else.
Also,
there are duplicate names in BWST.
I WAS WRONG.. THERE DOES NOT APPEAR TO BE DUPLICATE NAMES IN BWSG
There has to be a matrix for every model on the map so
this makes since.
The mission as I see it is to find where all the keys are to put the names in groups that are in BWST.
I believe BWST contains the data for creating the .visual needed for each model. It contains many more strings than BWSG.
## Post #69
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T15:14:57+00:00
- Post Title: Re: World of Tanks Map format.

Yes, so far keys from BWST are used in:
WGSD ((multiple times, always pointing to strings that ends with .dds)
BSMO (multiple times, always pointing to strings that ends with .primitive)

- both consists only of tables (same format as other)
## Post #70
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T15:22:34+00:00
- Post Title: Re: World of Tanks Map format.

That makes sense.
WGSD :  WarGaming Section DDS
BSMO : Bigworld Section Map Object?
## Post #71
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-22T15:34:05+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Here is complete script (py3 compatible   )
http://cerno.ch/~kamen/upload/test-bswg.py
I love to nitpick. 
Python code #2 -> [http://www.koreanrandom.com/forum/topic ... /?p=310323](http://www.koreanrandom.com/forum/topic/29351-/?p=310323)
## Post #72
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T15:44:23+00:00
- Post Title: Re: World of Tanks Map format.

BSMA - contains informations about materials:

1. table -> uknown (size: 12)
2. table -> only shader paths (size: 4 -> index in BWST table)

Example:
(0, 'shaders/std_effects/PBS_ext_dual.fx')

3. table -> [key -> value] thingy,
 size: 12
 0 -> BWST key, key of list
 4 -> ?
 8 -> BWST key or value ... value of list

Example:
(0, 'diffuseMap')
(8, 'content/Environment/env616_Background_trees/env616_Background_Trees.dds')

4. table -> unknown (size: 64)
5. table -> unknown (size: 16)
## Post #73
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T16:45:43+00:00
- Post Title: Re: World of Tanks Map format.

Nice work..

Here are all the keys for gaf010_FenceTile2.primitives I can find using the .visual as reference
There are 312 found keys matching 37066838 in BWSG
BWSG:
37066838  gaf010_FenceTile2.primitives/vertices
1FEFB938  xyznuvtb

BWST:
93446CBA  gaf010_Fence.dds
3BEDC63F  gaf010_Fence_NM.dds
250638E5  gaf010_Fence_SM.dds
DB756A17  diffuseMap
74F50CF6  normalMap
B2F70F7B  doubleSided
0E5639FE  alphaTestEnable
379B7275  alphaReference
DB50B7BF  specularMap


138CFE57  normalmap_specmap.fx

Some where all this is tied together.
## Post #74
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T17:12:42+00:00
- Post Title: Re: World of Tanks Map format.

Lot of fence tile sections..
There are indeed 311 entries in table 2 for these models for the ENSK map.

In order to place the models on the map I need at least the transform matrix data for each model.
If the models are in the sandbox, I can get everything else from there.
## Post #75
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T17:18:10+00:00
- Post Title: Re: World of Tanks Map format.

I won't be able to progress next few days, need to study. Just note almost every chunk has the more ENTRY_SIZE and ENTRY_COUNT structures with some entries pointing to BWST...
## Post #76
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T18:56:50+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> I won't be able to progress next few days, need to study. Just note almost every chunk has the more ENTRY_SIZE and ENTRY_COUNT structures with some entries pointing to BWST...

No big.. Like I said.. Education is more important than hacking files.
## Post #77
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:16:57+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Nice work..

Here are all the keys for gaf010_FenceTile2.primitives I can find using the .visual as reference
There are 312 found keys matching 37066838 in BWSG
BWSG:
37066838  gaf010_FenceTile2.primitives/vertices
1FEFB938  xyznuvtb

BWST:
93446CBA  gaf010_Fence.dds
3BEDC63F  gaf010_Fence_NM.dds
250638E5  gaf010_Fence_SM.dds
DB756A17  diffuseMap
74F50CF6  normalMap
B2F70F7B  doubleSided
0E5639FE  alphaTestEnable
379B7275  alphaReference
DB50B7BF  specularMap


138CFE57  normalmap_specmap.fx

Some where all this is tied together.

Interestingly enough, gaf010_FenceTile2.primitives is the crushed version of the model
gaf010_FenceTile1.primitives is the normal version. A9E380CD is it's key.
There is something extremely strange going on. There is only ONE entry for this model in BWSG
## Post #78
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:24:58+00:00
- Post Title: Re: World of Tanks Map format.

Id like to jump in ensk and take a bunch of screen shots..
Anyone?
## Post #79
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T20:30:27+00:00
- Post Title: Re: World of Tanks Map format.

I can join to training battle and be afk if you need, i have the game launched
## Post #80
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:31:13+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> I can join to training battle and be afk if you need, i have the game launched
prefect
Im in game now
## Post #81
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:36:02+00:00
- Post Title: Re: World of Tanks Map format.

I'm on the USA East server
## Post #82
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-22T20:36:55+00:00
- Post Title: Re: World of Tanks Map format.

Uh, I'm on the EU server ... that would be a problem
## Post #83
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:42:49+00:00
- Post Title: Re: World of Tanks Map format.

I guess we cant hook up.... We are in the wrong areas.
## Post #84
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T20:51:59+00:00
- Post Title: Re: World of Tanks Map format.

gaf010_fencetile1 contains 97 0x61 polys : 192 0xc0 vertices and : 97 * 3 indices (0x0123 total)
gaf010_fencetile2 contains 118 0x76 polys : 0xF7 247 vertices and : 118 * 3 indices (0x0162 total)
## Post #85
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-22T23:37:39+00:00
- Post Title: Re: World of Tanks Map format.

I have no idea.
Everything is so scrambled.

BSMO has a bunch of matrices at the end and tables that describe how many matrices belong to a item but Im not sure about the item keys or anything else in the file.

BWSG ends with huge blocks split by what the earlier tabled describe but they are still rather large and contain no floats.
This is NOT vertices or indices.. The chunk is to small to be an image. It looks more like a shit load of keys.
For example... If I follow the known data all the way down the file for gaf010_FenceTile2, I wind up with a chunk of data that is 0x12c0 in size (4800 bytes or 1200 uint32s) if these are keys.. It's hopeless to sort this out.

I am lost and with only 2 people working on this.. I don't see this getting solved.
Maybe there is a script in the game data that packs this crap.
## Post #86
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T06:24:19+00:00
- Post Title: Re: World of Tanks Map format.

I was expecting to be able to grab the tree string names based on the key in the SpTr section.
This however does not work.

```
	row0   -000.909669    000.000000    000.340237    000.000000
	row1    000.000000    000.971215    000.000000    000.000000
	row2   -000.340237    000.000000   -000.909669    000.000000
	row3   -311.023900    019.951210   -347.169100    001.000000

Id:0009 : key: 15c3bd77 : speedtree/06_Ensk/Bush.spt
	row0   -000.436155    000.037103   -000.202641    000.000000
	row1    000.010645    000.415855    000.053230    000.000000
	row2    000.205643    000.050216   -000.433434    000.000000
	row3   -344.273400    021.634730   -365.479200    001.000000

Id:0010 : key: c69d9b83 : content/Environment/env608_Sovbus/normal/lod0/env608_Sovbus.primitives/indices
	row0    000.885222    000.000000   -000.540578    000.000000
	row1    000.000000    000.762800    000.000000    000.000000
	row2    000.397555    000.000000    000.651013    000.000000
	row3   -337.628200    021.527810   -384.843400    001.000000

Id:0011 : key: f66e46c0 : content/Environment/env420_OldGLightVan/env420_OldGLightVan_01_crash1.dds
	row0    000.020693    000.000000   -000.654109    000.000000
	row1    000.000000    000.654438    000.000000    000.000000
	row2    000.654109    000.000000    000.020693    000.000000
	row3   -372.280200    022.458480   -374.640300    001.000000

Id:0012 : key: bfe9cd95 : content/Railway/rw005_locomotive/rw005_locomotive_crash.dds
	row0    002.814305   -000.088831    000.655548    000.000000
	row1    000.047083    001.839109    000.047083    000.000000
	row2   -000.760707   -000.063910    003.257095    000.000000
	row3   -329.624100    001.430664   -218.848500    001.000000

Id:0013 : key: 15577a9f : content/Environment/envWGL_001_Banner/normal/lod0/WGL_Banner_Stand.primitives/indices
	row0    001.128071   -000.055924   -000.071683    000.000000
	row1    000.044936    000.877621    000.022468    000.000000
	row2    000.070136   -000.032496    001.129086    000.000000
	row3   -340.420100    001.437500   -204.986300    001.000000

Id:0014 : key: bfe9cd95 : content/Railway/rw005_locomotive/rw005_locomotive_crash.dds
	row0    001.546900    000.000000    001.682528    000.000000
	row1    000.000000    001.454906    000.000000    000.000000
	row2   -001.946954    000.000000    001.790011    000.000000
	row3   -317.522700    001.650390   -234.485100    001.000000

Id:0015 : key: bfe9cd95 : content/Railway/rw005_locomotive/rw005_locomotive_crash.dds
	row0   -001.635760   -000.018756    000.732598    000.000000
	row1    000.000000    001.140614    000.029203    000.000000
	row2   -000.848011    000.048446   -001.892215    000.000000
	row3   -309.886900    001.299804   -227.332700    001.000000
```
## Post #87
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T16:20:02+00:00
- Post Title: Re: World of Tanks Map format.

I had some free time and cracked BSMA:
[http://wiki.vbaddict.net/pages/BSMA](http://wiki.vbaddict.net/pages/BSMA)

Example script:
[http://cerno.ch/~kamen/upload/bsma.py](http://cerno.ch/~kamen/upload/bsma.py)

Note that, there is not a single bit undescribed in this chunk
## Post #88
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T16:54:24+00:00
- Post Title: Re: World of Tanks Map format.

BSMO - this is probably where models are connected to materials and vertices and position matrix
WGSD - Shared decals? This is where decals are defined probably
## Post #89
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T17:22:58+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> BSMO - this is probably where models are connected to materials and vertices and position matrix
WGSD - Shared decals? This is where decals are defined probably

If you seacrh the WorldOfTanks.exe for these section header strings, it will give you an Idea of what they are.

BSMO = BigWorld Static Model Manger
[exe.jpg](https://xentaxbackup.github.io/file/10353_exe.jpg)
## Post #90
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T17:24:51+00:00
- Post Title: Re: World of Tanks Map format.

Im starting to think they are XOR'ing some of the data.
I know for a fact they are doing this with some data in the .primitives_processed model files.
## Post #91
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T17:34:03+00:00
- Post Title: Re: World of Tanks Map format.

Cracked WGSD:
[http://wiki.vbaddict.net/pages/WGSD](http://wiki.vbaddict.net/pages/WGSD)

all important info is now known about those decals? There is a lot of uknown data, but you have matrix (=position,rotation,scale) and paths to textures, what more would you need?

> Reply from Coffee
>
> Im starting to think they are XOR'ing some of the data.
I know for a fact they are doing this with some data in the .primitives_processed model files.

That would be hard to discover. Maybe the indicies are XORed in some way? And textures? I was unable to match either indicies or textures inside bin file. They have to be there, how else would you be able to construct the models?
## Post #92
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T18:19:01+00:00
- Post Title: Re: World of Tanks Map format.

I found out something..

in BWSG the last Uint32 before the actual strings is the length of the total string section.
This is the same for BWST as well..
So the 3rd entry at the start is the Key.
## Post #93
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T18:20:57+00:00
- Post Title: Re: World of Tanks Map format.

Yes, that's all described inside the wiki I linked...

( [http://wiki.vbaddict.net/pages/BWSG](http://wiki.vbaddict.net/pages/BWSG) )

Also progress: BSMO contains primitives and their groups and materials for each group. Trying to link this all together now, it should yield the models...
## Post #94
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T19:48:41+00:00
- Post Title: Re: World of Tanks Map format.

I have big part of BSMO decrypted! It contains same data as .visual files, but in binary form.
Some things are still unsorted, will publish when everything will be known.
## Post #95
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T20:10:02+00:00
- Post Title: Re: World of Tanks Map format.

Good job..
I understand must of the sections formats as well... That is.. as far as how things are stored..
The thing is, It doesn't mean anything if I cant figure out how to use the data.

It would be nice to load everything using the space.bin. It would for sure be faster than loading the model and its visual from the .pkg files.
I have been writing code to break up the BWSG.
It is by far the largest section in the data.
I'm going to dump each sub chunk in to its own file so I can try to figure out what these are and how to get anything useful from them.
## Post #96
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T20:14:09+00:00
- Post Title: Re: World of Tanks Map format.

BWSG contains vertices and maybe even indicies. That's all, if you try to run script provided with python, you should be able to extract its contents. I'm 100% sure about this as I compared some files. Not sure about the indicies part.

BSMO actually links everything together ... I'm about 68% sure
## Post #97
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T20:46:16+00:00
- Post Title: Re: World of Tanks Map format.

I dumped all the end parts of the BWSG in to its own file.
I uploaded this to [http://209.159.152.184:8080/junk/BWSG_DUMP.zip](http://209.159.152.184:8080/junk/BWSG_DUMP.zip)

I see no indices, vertices or any floats in these sections.
At least look at it and see if these match the chunks you get from your script.
The format of the file names is chunk_n1_n2.
n1 = the section 0 to 8 and n2 is just the running index.
## Post #98
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T21:02:49+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Cracked WGSD:
http://wiki.vbaddict.net/pages/WGSD

all important info is now known about those decals? There is a lot of uknown data, but you have matrix (=position,rotation,scale) and paths to textures, what more would you need?
Coffee wrote:Im starting to think they are XOR'ing some of the data.
I know for a fact they are doing this with some data in the .primitives_processed model files.

That would be hard to discover. Maybe the indicies are XORed in some way? And textures? I was unable to match either indicies or textures inside bin file. They have to be there, how else would you be able to construct the models?

I have never used the decals .. I could never figure out how to apply them to the texture.
I pretty sure they use a shader that does the blend along with the transforming.
It would be cool to add them though.
## Post #99
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T21:05:22+00:00
- Post Title: Re: World of Tanks Map format.

Ok, for example:
Chunk_08_0430
This is chunk assigned to (you can find how in the description of BWSG...):
content/Buildings/bld_Constructor01/bld202_vhouse/normal/lod0/bld202_vhouse01.primitives/vertices

if you compare contents of this chunk with actual file (you can find it in shared_content.pkg):
content/Buildings/bld_Constructor01/bld202_vhouse/normal/lod0/bld202_vhouse01.primitives_processed

you will find that part of the file (probably the vertices part) does actually match the chunk.

(match starts at 0000 008C)
## Post #100
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T22:50:41+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> I dumped all the end parts of the BWSG in to its own file.
I uploaded this to http://209.159.152.184:8080/junk/BWSG_DUMP.zip

I see no indices, vertices or any floats in these sections.
At least look at it and see if these match the chunks you get from your script.
The format of the file names is chunk_n1_n2.
n1 = the section 0 to 8 and n2 is just the running index.

The vertex counts for the models looks to be correct. The values look strange as floats in my hex editor.
This is good.. I can load the models directly from the space.bin once we figure out the rest.
## Post #101
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-23T22:55:07+00:00
- Post Title: Re: World of Tanks Map format.

in this table for BWSG

P	Type	Desc
0	uint32	key 1 - vertices name (ends with .primitives/vertices usually)
4	uint32	block from - starting index of blocks containing data of this model
8	uint32	block to - ending index of blocks containing data of this model
12	uint32	unknown
16	uint32	key 2 - vertices type (xyznuvtb and such...)

the Unknown is the vertex count 

Nice work.. Keep it up!
## Post #102
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-23T23:00:54+00:00
- Post Title: Re: World of Tanks Map format.

Good find! That was one of the last unknown values in that chunk.
## Post #103
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T00:11:02+00:00
- Post Title: Re: World of Tanks Map format.

Ok.. I found more to finish up BWSG

each item then looks:

P	Type	Desc
0	uint32	unknown (probably describing block type?)
4	uint32	unknown (probably describing block type?)
8	uint32	block size
12	uint32	chunk index
16	uint32	offset inside chunk

The 2nd Uint32 is the stride of each vertex. Each vertex type has a different amount of data 
so the distance from vertex to vertex in bytes changes depending on its type.
xyznuv has a stride of 0x18
xyznuvtb has  a stride of 0x20

The first uint32 is 0x0a if the section is skipped. Other wise, its zero.
I believe these skipped areas contain the models 'crashed' state
## Post #104
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T05:13:52+00:00
- Post Title: Re: World of Tanks Map format.

Ok my friend....
I found the missing entries for WGSD.

```
0	uint32	 ? - always 0 so far
4	16 * float32	decal matrix
20	uint32	key referencing BWST - diffuse map
24	uint32	key referencing BWST - normal map
28	uint32	key referencing BWST - ?
 ?	 ?	rest is unknwon, altrought it seems to be static
```


BTW.. I think your P offsets are incorrect in that table?

I got the structure from looking at a old .chunk file I still have.

Here is my structure for the data in the order it appears in the data.

```
        Public unknown_1 As UInt32
        Public matrix() As Single '16 floats
        Public diffuseMapKey As UInt32
        Public normalMapKey As UInt32
        Public u_key As UInt32
        Public unknown_2 As UInt32
        '
        Public Flags As UInt32
        '
        Public off_x As Single
        Public off_y As Single
        Public off_z As Single
        Public off_w As Single
        '
        Public uv_wrapping_u As Single
        Public uv_wrapping_v As Single
        Public visibilityMask As UInt32
        '---------------------------
        'The strings below is not in the data.
        Public diffuseMap As String
        Public normalMap As String
        Public extraMap As String
    End Structure
```

This does indeed pull the correct decal DDS files.
It how ever does not for the extreMap.. I think this might be a key to the grid this decal is on.
It would make sense as this has to be blended with the textures on a specific map grid.
BWT2 might need to be decoded next. I'm sure its the info on the map's grid layout.
EDIT: I can't find that 3rd u_key in the BWT2 data.. It's has to be some where else.

A Single is the same as a Float.. It occupies 4 bytes of data.
## Post #105
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T05:49:44+00:00
- Post Title: Re: World of Tanks Map format.

OK.. SpTr works fine..
It was an error in my code..   
It's pulling the correct trees for each key now.
## Post #106
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-24T09:05:06+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Ok my friend....
I found the missing entries for WGSD.
Code: Select allP	Type	Desc
0	uint32	 ? - always 0 so far
4	16 * float32	decal matrix
20	uint32	key referencing BWST - diffuse map
24	uint32	key referencing BWST - normal map
28	uint32	key referencing BWST - ?
 ?	 ?	rest is unknwon, altrought it seems to be static

BTW.. I think your P offsets are incorrect in that table?

You're right, I must have had brainfart ... corrected them now:
[http://wiki.vbaddict.net/pages/WGSD#1._TABLE](http://wiki.vbaddict.net/pages/WGSD#1._TABLE)
## Post #107
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-24T11:21:31+00:00
- Post Title: Re: World of Tanks Map format.

Here is some info about BSMO
[http://wiki.vbaddict.net/pages/BSMO](http://wiki.vbaddict.net/pages/BSMO)

Note: Each model structure is:

Model HAS nodes
Node HAS primitive groups
Primitive group HAS material and vertices and indicies
## Post #108
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T15:03:59+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Here is some info about BSMO
http://wiki.vbaddict.net/pages/BSMO

Note: Each model structure is:

Model HAS nodes
Node HAS primitive groups
Primitive group HAS material and vertices and indicies

I'll have a look later.. I'm trying to decode BWT2. I have all the tables worked out.. Im trying to figure how how to use the data
## Post #109
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T15:18:34+00:00
- Post Title: Re: World of Tanks Map format.

If you want to create a page for the SpTr:

```
Entry Length Uint32
Entry Count Uint32

Entry Structure:

16 floats = matrix
Key Uint32   = speedtree key in BWST
E1 Uint32     = unknown : always = 1
E2 Uint32     = unknown : always = 1
```


There is some data at the end I don't know about and won't need.
I think this is associated with a shader but not sure.
## Post #110
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T20:06:29+00:00
- Post Title: Re: World of Tanks Map format.

Ok... 
BWT2 has a bunch of tables and I only need the 2nd one to get what I need.
I actually don't even needs this. I could get the prefix locations from the .cdata file names.
At the start of the section there are 6 numbers (int32s and floats) I don't need.
All the grids MUST BE 100meters x 100meters.
Using the location numbers and offsetting by 50 in x and y I get the centers of each grid.

```
:fffcfffd:fffdfffd:fffefffd:fffffffd:0000fffd:0001fffd:0002fffd:0003fffd:
:fffcfffe:fffdfffe:fffefffe:fffffffe:0000fffe:0001fffe:0002fffe:0003fffe:
:fffcffff:fffdffff:fffeffff:ffffffff:0000ffff:0001ffff:0002ffff:0003ffff:
:fffc0000:fffd0000:fffe0000:ffff0000:00000000:00010000:00020000:00030000:
:fffc0001:fffd0001:fffe0001:ffff0001:00000001:00010001:00020001:00030001:
:fffc0002:fffd0002:fffe0002:ffff0002:00000002:00010002:00020002:00030002:
:fffc0003:fffd0003:fffe0003:ffff0003:00000003:00010003:00020003:00030003:
```


```
( 350.0:-250.0) ( 250.0:-250.0) ( 150.0:-250.0) ( 050.0:-250.0) (-050.0:-250.0) (-150.0:-250.0) (-250.0:-250.0) (-350.0:-250.0) 
( 350.0:-150.0) ( 250.0:-150.0) ( 150.0:-150.0) ( 050.0:-150.0) (-050.0:-150.0) (-150.0:-150.0) (-250.0:-150.0) (-350.0:-150.0) 
( 350.0:-050.0) ( 250.0:-050.0) ( 150.0:-050.0) ( 050.0:-050.0) (-050.0:-050.0) (-150.0:-050.0) (-250.0:-050.0) (-350.0:-050.0) 
( 350.0: 050.0) ( 250.0: 050.0) ( 150.0: 050.0) ( 050.0: 050.0) (-050.0: 050.0) (-150.0: 050.0) (-250.0: 050.0) (-350.0: 050.0) 
( 350.0: 150.0) ( 250.0: 150.0) ( 150.0: 150.0) ( 050.0: 150.0) (-050.0: 150.0) (-150.0: 150.0) (-250.0: 150.0) (-350.0: 150.0) 
( 350.0: 250.0) ( 250.0: 250.0) ( 150.0: 250.0) ( 050.0: 250.0) (-050.0: 250.0) (-150.0: 250.0) (-250.0: 250.0) (-350.0: 250.0) 
( 350.0: 350.0) ( 250.0: 350.0) ( 150.0: 350.0) ( 050.0: 350.0) (-050.0: 350.0) (-150.0: 350.0) (-250.0: 350.0) (-350.0: 350.0) 

```

This image's coordinates are inverted because its drawn with OpenGL from DirectX model data.

All maps are square.
Not all playable areas are centered on the map. A good example is Himmelsdorf.
## Post #111
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T20:19:41+00:00
- Post Title: Re: World of Tanks Map format.

"Overlord" has a uneven map size. It's 15x15 in size.
Don't assume anything.
## Post #112
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T21:08:27+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Coffee wrote:Ok my friend....
I found the missing entries for WGSD.
Code: Select allP	Type	Desc
0	uint32	 ? - always 0 so far
4	16 * float32	decal matrix
20	uint32	key referencing BWST - diffuse map
24	uint32	key referencing BWST - normal map
28	uint32	key referencing BWST - ?
 ?	 ?	rest is unknwon, altrought it seems to be static

BTW.. I think your P offsets are incorrect in that table?


You're right, I must have had brainfart ... corrected them now:
http://wiki.vbaddict.net/pages/WGSD#1._TABLE
I posted the format for the missing info earlier
## Post #113
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T22:33:01+00:00
- Post Title: Re: World of Tanks Map format.

I can't wait to get the models back in Terra!
It took a month to figure out how to blend the textures (up to 4 per grid) and deal with the low res texture mixing with distance.
I worked for another 5 weeks getting the shader to do the texture translation correctly.
It's still not exactly like the game but it is very close.
## Post #114
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2016-01-24T22:53:45+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> I can't wait to get the models back in Terra!
It took a month to figure out how to blend the textures (up to 4 per grid) and deal with the low res texture mixing with distance.
I worked for another 5 weeks getting the shader to do the texture translation correctly.
It's still not exactly like the game but it is very close.
But why? For whom?
## Post #115
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-24T23:11:45+00:00
- Post Title: Re: World of Tanks Map format.

That looks pretty neat! I spent about month of time decrypting and decoding replays and I finally have working replay player, but without objects on maps ... it just looks weird:
[H4ctORS.jpg](https://xentaxbackup.github.io/file/10362_H4ctORS.jpg)
## Post #116
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T23:49:27+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from ShadowHunterRUS
>
> Coffee wrote:I can't wait to get the models back in Terra!
It took a month to figure out how to blend the textures (up to 4 per grid) and deal with the low res texture mixing with distance.
I worked for another 5 weeks getting the shader to do the texture translation correctly.
It's still not exactly like the game but it is very close.
But why? For whom?

Terra! is a 3D tactical battle designer I started on about 3 years ago.
I used to be very active in Clan wars and didn't like any of the planners.
I have worked on it when I had time and many times, spent more than an entire night sorting things out.

Up until this last update, I have been able to fix slight changes but this last one has removed all the info on whats on the map.
Its there but, as you know in the space.bin.

We have sorted out a lot of the data but there is a lot more to be done.
I need to know how to get the water info. Also.. For what ever reason. Terra can't find the skydome now. This is probably because of a path change. WarGaming tends to do this a lot.
## Post #117
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-24T23:52:35+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> That looks pretty neat! I spent about month of time decrypting and decoding replays and I finally have working replay player, but without objects on maps ... it just looks weird:

Thats cool...

Well.. we are going to sort this out and than you will have the other models.

Do the tanks move like a regular replay?

Where do the tank models come from? Game.. Something you created to export them?
## Post #118
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T16:22:58+00:00
- Post Title: Re: World of Tanks Map format.

I found this...
It is an offline world of tanks map viewer mod.
All items and effects are the same as in a match. Only YOU are on the map.
This makes it nice to look around.

Place the files that are under 9.12 in the 9.13 res_mods folder.

After you start the game and get to the login screen, there will be a new icon at the bottom right of the window.
Click it and select the mod.
After, select the map... Don't bother selecting a tank.. it wont show up.
To driver around us the A-D-W-S keys and the mouse to point where you are going.
The mouse wheel moves you up and down.
To exit. use ALT+F4
[SOmeOne_OfflineMapViwer.zip](https://xentaxbackup.github.io/file/10363_SOmeOne_OfflineMapViwer.zip)
## Post #119
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T17:56:14+00:00
- Post Title: Re: World of Tanks Map format.

OK... getting back to decoding here.

I'm working on helping sort out BSMO

It looks like and entry in table 2 that has 'From - To' indexes that = 0xFFFFFFFF have no matching String Key in BWST.
If it is 0xFFFFFFFF than the string key is ZERO.
## Post #120
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-25T18:02:53+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> OK... getting back to decoding here.

I'm working on helping sort out BSMO

It looks like and entry in table 2 that has 'From - To' indexes that = 0xFFFFFFFF have no matching String Key in BWST.

Yeah, I noticed that there are some objects without BWST name there (having 0xFFFFFF or 0x000000 as key), I have no clue what is their purpose or why're they nameless

> Reply from Coffee
>
> 

Thats cool...

Well.. we are going to sort this out and than you will have the other models.

Do the tanks move like a regular replay?

Where do the tank models come from? Game.. Something you created to export them?

Yes, it works like regular replay, tanks move, shoot, aim ....
It's all in browser, so I had to export all models into obj and same with heightmaps. I use [https://github.com/SkaceKamen/wot-model-converter](https://github.com/SkaceKamen/wot-model-converter) for exporting objects ... (I started writing it, but now It's community project with multiple contributors)
## Post #121
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T18:16:21+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
>  I use https://github.com/SkaceKamen/wot-model-converter for exporting objects ... (I started writing it, but now It's community project with multiple contributors)

I found that before.. Some of the code is straight out of my Model Editor..  Yes.. I'm AKA Phux_and_the_Wheel_Bearing.
It's no big.. all you needed to do was PM me and I would of gave you the code.. (Or.. maybe I did already .. My memory is bad)
EDIT:  I figured out how to unpack those 8_8_8 normals... the code is posted here : [viewtopic.php?f=16&t=12567&start=705](http://forum.xentax.com/viewtopic.php?f=16&t=12567&start=705)
Anyway. I will need something like this later for Terra to manage the tanks one can put on the map.

Back to BSMO...
So these look to be dead entries but they have valid Bounding Box data.. But with out and index key.. they are useless.
We need to look at the code that puts these node entries together and make sure the indexes for the dead entries are NOT used!
## Post #122
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-25T18:27:33+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> 
I found that before.. Some of the code is straight out of my Model Editor..  Yes.. I'm AKA Phux_and_the_Wheel_Bearing.
It's no big.. all you needed to do was PM me and I would of gave you the code.. (Or.. maybe I did already .. My memory is bad)

Oh, so it was you! Sorry for stealing ("borrowing" ) your code. I found some obscure exe capable of converting models and I was desperate to make my converter working. I had no idea from where it originated, and frankly I was just happy I finally had some clue how to do it. I added you to credits.

> Reply from Coffee
>
> 
Back to BSMO...
So these look to be dead entries but they have valid Bounding Box data.. But with out and index key.. they are useless.
We need to look at the code that puts these node entries together and make sure the indexes for the dead entries are NOT used!

OK, while you're looking at BSMO, I'll try to match entries in BSMI with models in BSMO. I have map renderer ready, so it should be easy to decide if the index is right or wrong...
## Post #123
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T20:35:25+00:00
- Post Title: Re: World of Tanks Map format.

Thanks for the Credit 
It really is no big.

So far your BSMA tables is working out fine.

Here is some insight.  If the FX type contains "dual" at the end, it has 2 UV coordinate sets.
## Post #124
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-25T22:36:59+00:00
- Post Title: Re: World of Tanks Map format.

Cracked most important informations from BSMI:

[http://wiki.vbaddict.net/pages/BSMI](http://wiki.vbaddict.net/pages/BSMI)

1. Table contains matrixes (OK)
3. Table contains model indexes for each matrix (multiple matrixes can refer one model)

So we now have: models, their geometry (partially), material (but no textures) and their position/rotation/scale.
We're so close!
## Post #125
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T22:54:08+00:00
- Post Title: Re: World of Tanks Map format.

Ok.. here is my dataset for getting the materials

```
    Public Structure visual_sections_
        Public shader As String
        Public entries() As visual_entries_
    End Structure
    Public Structure visual_entries_
        Public Property_name As String
        Public Proerty_value As Object
    End Structure
```


And this is my (sloppy) code to get the data from the BSMA data

```

    Public Sub get_BSMA_data(ByVal t_cnt As Integer)
        'ms is pointing at the BSMA secion after this next line
        Dim ms As New MemoryStream(table_Rows(t_cnt).data)
        Dim br As New BinaryReader(ms)
        ms.Position = 0
        BSMA.t1_start = br.BaseStream.Position
        BSMA.t2_dl = br.ReadUInt32
        BSMA.t1_dc = br.ReadUInt32
        ReDim BSMA.bsma_t1(BSMA.t1_dc)
        For k = 0 To BSMA.t1_dc - 1
            BSMA.bsma_t1(k).fx_index = br.ReadUInt32
            BSMA.bsma_t1(k).index_start = br.ReadUInt32 ' t3 ref
            BSMA.bsma_t1(k).index_end = br.ReadUInt32 ' t3 ref
        Next
        BSMA.t1_start = br.BaseStream.Position
        BSMA.t2_dl = br.ReadUInt32
        BSMA.t2_dc = br.ReadUInt32
        ReDim BSMA.bsma_t2(BSMA.t2_dc)
        For k = 0 To BSMA.t2_dc - 1
            BSMA.bsma_t2(k).bwst_key = br.ReadUInt32
            BSMA.bsma_t2(k).shader_string = find_str_BWST(BSMA.bsma_t2(k).bwst_key)
        Next

        BSMA.t3_start = br.BaseStream.Position
        BSMA.t3_dl = br.ReadUInt32
        BSMA.t3_dc = br.ReadUInt32
        Dim pos = BSMA.t3_start + 8 + (BSMA.t3_dl * BSMA.t3_dc)
        br.BaseStream.Position = pos
        BSMA.t4_start = br.BaseStream.Position
        BSMA.t4_dl = br.ReadUInt32
        BSMA.t4_dc = br.ReadUInt32
        ReDim BSMA.bsma_t4(BSMA.t4_dc)
        For k = 0 To BSMA.t4_dc - 1
            ReDim BSMA.bsma_t4(k).matrix(16)
            For i = 0 To 15
                BSMA.bsma_t4(k).matrix(i) = br.ReadSingle
            Next
        Next
        BSMA.t5_start = br.BaseStream.Position
        BSMA.t5_dl = br.ReadUInt32
        BSMA.t5_dc = br.ReadUInt32
        ReDim BSMA.bsma_t5(BSMA.t5_dc)
        For k = 0 To BSMA.t5_dc - 1
            BSMA.bsma_t5(k).vector4.X = br.ReadSingle
            BSMA.bsma_t5(k).vector4.Y = br.ReadSingle
            BSMA.bsma_t5(k).vector4.Z = br.ReadSingle
            BSMA.bsma_t5(k).vector4.W = br.ReadSingle
        Next

        br.BaseStream.Position = BSMA.t3_start + 8
        ReDim BSMA.bsma_t3(BSMA.t3_dc)
        For k = 0 To BSMA.t3_dc - 1
            BSMA.bsma_t3(k).Property_key = br.ReadUInt32
            BSMA.bsma_t3(k).value_type = br.ReadUInt32
            BSMA.bsma_t3(k).value_type_string = BSMA_PropertyType(BSMA.bsma_t3(k).value_type)
            BSMA.bsma_t3(k).value = br.ReadUInt32
            BSMA.bsma_t3(k).value_string = BSMA.bsma_t3(k).value.ToString
            BSMA.bsma_t3(k).Property_string = find_str_BWST(BSMA.bsma_t3(k).Property_key)

            Select Case BSMA.bsma_t3(k).value_type
                Case Is = 0
                Case Is = 1
                    If BSMA.bsma_t3(k).value = 1 Then
                        BSMA.bsma_t3(k).value_string = "True"
                    Else
                        BSMA.bsma_t3(k).value_string = "False"
                    End If
                Case Is = 2
                    BSMA.bsma_t3(k).value_string = CSng(BSMA.bsma_t3(k).value).ToString("0.000000")
                Case Is = 3
                    BSMA.bsma_t3(k).value_string = BSMA.bsma_t3(k).value
                Case Is = 4
                    'this never gets hit on with ENSK map.
                    Console.WriteLine(BSMA.bsma_t3(k).Property_key.ToString("x"))
                Case Is = 5
                    Dim v As vect4 = BSMA.bsma_t5(BSMA.bsma_t3(k).value).vector4
                    BSMA.bsma_t3(k).value_string = _
                        v.X.ToString("00.000000") + " " + _
                        v.Y.ToString("00.000000") + " " + _
                        v.Z.ToString("00.000000") + " " + _
                        v.W.ToString("00.000000")
                Case Is = 6
                    BSMA.bsma_t3(k).value_string = find_str_BWST(BSMA.bsma_t3(k).value)
                Case Is = 7
                    ' this only gets hit when BSMA.bsma_t3(k).Property_string  = "g_useNormalPackDXT1_safe"
                    BSMA.bsma_t3(k).value_string = "True"
            End Select


            'If BSMA.bsma_t3(k).value_type_string = "?" Then
            '    Console.WriteLine(BSMA.bsma_t3(k).Property_string)
            'End If
        Next

        ReDim visual_sections(BSMA.t1_dc)
        Dim index As Integer = 0
        For n = 0 To BSMA.t1_dc - 1
            If BSMA.bsma_t1(n).index_end <= BSMA.t3_dc Then 'ignore &hFFFFFFFF entries
                visual_sections(index) = New visual_sections_
                ReDim visual_sections(index).entries((BSMA.bsma_t1(n).index_end - BSMA.bsma_t1(n).index_start))
                visual_sections(index).shader = BSMA.bsma_t2(BSMA.bsma_t1(n).fx_index).shader_string
                For k = BSMA.bsma_t1(n).index_start To BSMA.bsma_t1(n).index_end
                    Dim ind = k - BSMA.bsma_t1(n).index_start
                    visual_sections(index).entries(ind) = New visual_entries_
                    visual_sections(index).entries(ind).Property_name = BSMA.bsma_t3(k).Property_string
                    visual_sections(index).entries(ind).Proerty_value = BSMA.bsma_t3(k).value_string
                Next
                index += 1
            End If
        Next
        ReDim Preserve visual_sections(index)

    End Sub
```
## Post #126
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T23:06:37+00:00
- Post Title: Re: World of Tanks Map format.

And this is some sample of what this code produces.

```
g_defaultPBSConversionParams : False
g_metallicConversions : 00.020000 00.080000 04.040000 00.620000
g_glossConversions : 00.050000 00.160000 01.500000 02.000000
specularMap : content/Environment/env440_borders/env440_border_SM.dds
alphaReference : 0
alphaTestEnable : False
doubleSided : False
normalMap : content/Environment/env440_borders/env440_border_NM.dds
diffuseMap : content/Environment/env440_borders/env440_border.dds

shader: shaders/std_effects/normalmap_specmap_dual.fx
diffuseMap2 : content/Buildings/bld6115_chouse/bld6115_thouse_UV2.dds
specularMap : content/Buildings/bld6115_chouse/bld6115_16_details_SM.dds
alphaReference : 0
alphaTestEnable : False
selfIllumination : 0.000000
doubleSided : False
normalMap : content/Buildings/bld6115_chouse/bld6115_16_details_NM.dds
diffuseMap : content/Buildings/bld6115_chouse/bld6115_16_details.dds

shader: shaders/std_effects/normalmap_specmap_dual.fx
diffuseMap2 : content/Buildings/bld6115_chouse/bld6115_thouse_UV2.dds
specularMap : content/Buildings/bld6101_thouse/bld61_roof3_SM.dds
alphaReference : 0
alphaTestEnable : False
selfIllumination : 0.000000
doubleSided : False
normalMap : content/Buildings/bld6101_thouse/bld61_roof3_NM.dds
diffuseMap : content/Buildings/bld6101_thouse/bld61_roof3.dds

shader: shaders/std_effects/normalmap_specmap_dual.fx
diffuseMap2 : content/Buildings/bld6115_chouse/bld6115_thouse_UV2.dds
specularMap : content/Buildings/bld6101_thouse/bld61_wall3_SM.dds
alphaReference : 0
alphaTestEnable : False
selfIllumination : 0.000000
doubleSided : False
normalMap : content/Buildings/bld6101_thouse/bld61_wall3_NM.dds
diffuseMap : content/Buildings/bld6101_thouse/bld61_wall3.dds
```
## Post #127
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T23:11:36+00:00
- Post Title: Re: World of Tanks Map format.

Its all sorted but the Matrix.. Im not sure what code will show up.
ENSK has NO matrices in the BSMA data.. Its a zero length table.
## Post #128
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-25T23:26:30+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Cracked most important informations from BSMI:

http://wiki.vbaddict.net/pages/BSMI

1. Table contains matrixes (OK)
3. Table contains model indexes for each matrix (multiple matrixes can refer one model)

So we now have: models, their geometry (partially), material (but no textures) and their position/rotation/scale.
We're so close!

If you found the indices for the models and their matrices, we can build the models.
There are LOTs of the same model on a map. light poles is a good example. Each with it's own matrix but common materials.

I'm going to go back to sorting out the rest of BSMO.
## Post #129
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-25T23:33:41+00:00
- Post Title: Re: World of Tanks Map format.

I already found the matrices for models in BSMO ( [http://wiki.vbaddict.net/pages/BSMI](http://wiki.vbaddict.net/pages/BSMI) 3. Table assigns matrices to objects) ... so the last problem is indicies.
## Post #130
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T05:10:17+00:00
- Post Title: Re: World of Tanks Map format.

BSMO tables 8, 9 and 10 are empty


The Last table 11 has a uint32 and than a matrix

Uknown Uint32 Key?
16x float  Matrix
## Post #131
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T06:29:51+00:00
- Post Title: Re: World of Tanks Map format.

Whoohooo!

I found the UV2s.

Remember this table in BWSG?

```

P	Type	Desc
0	uint32	unknown (probably describing block type?)
4	uint32	stride
8	uint32	block size
12	uint32	chunk index
16	uint32	offset inside chunk
Now, chunk index refers to next table which finally points to raw data.
```

If the unknow at the top is zero.. this block is vertices.
if it is 10 (0xa) than it is UV2 coordinates. Stride will = 8 (2 floats per UV coord)
UV2 coordinates are streamed unlike the other UVs that are indexed as part of the vertices.

for k = 0 to poly_cnt-1
p1 = indi_1
p2 = indi_2
p3 = indi_3
v1 = vertex(p1) <-- indexed
v2 = vertex(p2)
v3 = vertex(p3)
UV2 = uv2_array(K) <--- this is NOT indexed. it is stored as a stream.
## Post #132
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T08:04:14+00:00
- Post Title: Re: World of Tanks Map format.

Nice!
## Post #133
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T15:54:17+00:00
- Post Title: Re: World of Tanks Map format.

I was up until 4 am looking for the Indices.
I can't find them.


The models that can be crushed have 2 states. Things like fence sections.
Also... Some models have collision models. This is easy to find.. they never have a texture to go with them.
There must be some settings for these in the data.

Here is a pic of the blr201_Piggaery.primitives_processed

The blue areas are the collision model.
[collision.jpg](https://xentaxbackup.github.io/file/10364_collision.jpg)
## Post #134
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T17:17:05+00:00
- Post Title: Re: World of Tanks Map format.

OK...
BWWa is the info on the water.

I will created the data set and post it here so you can see it.
It's just a bunch of settings.
## Post #135
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T18:22:09+00:00
- Post Title: Re: World of Tanks Map format.

Good, water is important, too. For the indicies, the suspect is "BWSS.chunk", based solely on its size. Or maybe it contains textures? Isn't it too small for textures?
My attempt to decode it was unsucessfull, as it isn't just tables, it has some raw data inside ....

The collision groups are a bit stupid, why don't they use same system as tanks ... well, we'll have to think with lemons
## Post #136
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T18:37:59+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Good, water is important, too. For the indicies, the suspect is "BWSS.chunk", based solely ony its size. Or maybe it contains textures? Isn't it too small for textures?

The collision groups are a bit stupid, why don't they use same system as tanks ... well, we'll have to think with lemons

I don't think any actual texture data is stored in the space.bin. The data would be huge.
I looked at BWSS but can't find any thing that looks like indices.

2nd .. Yes.. it could of been done a lot easier. I think this is why they are packing the data in to the space.bin.
Less crap to read.

There is a lot of crap in the BWWa that could be used if you wanted to actually do animated water but for me, its not worth the effort.
Here is the critical data needed to get the water on the map
The section has the standard data_length, data_count header than:

```
        width As float 
        height As float 
        orientation as float (rotation about Y)
```

There is another table at the end.. Probably links other things to the water.. Once again.. I don't need this stuff.
## Post #137
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T18:42:34+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
>  I don't think any actual texture data is stored in the space.bin. The data would be huge.
I looked at BWSS but can't find any thing that looks like indices.

Well, the BWSS has to contain something ... The indicies could be packed in some way?

> Reply from Coffe
>
> 
There is a lot of crap in the BWWa that could be used if you wanted to actually do animated water but for me, its not worth the effort.
Here is the critical data needed to get the water on the map
The section has the standard data_length, data_count header than:
        position As vect3 (3 floats)
        width As float 
        height As float 
        orientation as float (rotation about Y)
There is another table at the end.. Probably links other things to the water.. Once again.. I don't need this stuff.

Thanks, I'll update the wiki as soon as possible.
## Post #138
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T18:49:20+00:00
- Post Title: Re: World of Tanks Map format.

I agree.. it must be used for something and it's size makes sense its the Indices.

Let me look..
## Post #139
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T21:11:30+00:00
- Post Title: Re: World of Tanks Map format.

If they are in there I can't find them.
Also.. there is only one reference to BWSS in the .exe where all the others have a lot.

It could have something to do with the sound. BWSS SS = sound system?
The sound files are listed in the BWST
## Post #140
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T21:32:32+00:00
- Post Title: Re: World of Tanks Map format.

Ugh, you're right, it's probably sounds. Haven't even thought about it  

We're so close! [https://i.imgur.com/wpreGiq.jpg](https://i.imgur.com/wpreGiq.jpg) (I painted the vertices without faces)
## Post #141
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T21:41:20+00:00
- Post Title: Re: World of Tanks Map format.

Well..
I got some more update for BWSG

Table 2 block type

we know we have:
Type 0 (0x0)= vertices
Type 10 (0xA) = UV2s

Drum roll please........
And....
Type 11 (0xB) is Colour (or color if you spell it like me)
They are Uint32s
Vertex Stride is 4
Colour is also a stream like the UV2s
## Post #142
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-26T21:57:26+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Ugh, you're right, it's probably sounds. Haven't even thought about it  

We're so close! https://i.imgur.com/wpreGiq.jpg (I painted the vertices without faces)

Nice!
## Post #143
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T22:47:43+00:00
- Post Title: Re: World of Tanks Map format.

OK, I'm out of ideas about those indicies. Not a single chunk looks like it could contain them.
1. The indicies are implied by something?
2. The indicies are actually read from .primitives file?

Because I looked into each chunk, and there isn't a single one that could contain them
## Post #144
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T23:06:54+00:00
- Post Title: Re: World of Tanks Map format.

Maybe ...
BSMI - Model indicies?

EDIT: It doesn't look like it
## Post #145
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-26T23:52:05+00:00
- Post Title: Re: World of Tanks Map format.

Oh My God ... seriously wargaming ... you had to compile vertices into .bin file, but indicies? NAH, not worth the effort!

Just did following experiment:

1. Found big model on map
2. Found his file in shared_content_sandbox
3. Updated some random indicies and repacked back
4. Launched replay on said map
5. Model is modified in game

Conclusion:

1. Indicies are loaded from .primitivies
1. 2. Are the geometries even used?

OR

2. Some objects ignore .bin file a use the .primitive
2. 2. Maybe only some objects?
## Post #146
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-27T00:44:47+00:00
- Post Title: Re: World of Tanks Map format.

WOW!

That's just stupid. Why pack the vertices and not the indices??
Another thing is WTF are they doing by changing a few dozen bytes in the models????
The 8_8_8 normal format is less accurate!

I was starting to think I was crazy here.

Thanks for figuring out that the indices are not there.

At this point i guess I'll load the entire model from the sandbox.
## Post #147
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-27T00:55:31+00:00
- Post Title: Re: World of Tanks Map format.

This just dumb...

So I have to load huge file just to get what??????
SpeedTree info and Translations????????? 
I'm going to have to load the models anyway just to get the indices.. LOADING is where time is killed!!!!

I can get the map layout from the .cdata file names
I dont need that part in the space.bin

I can get all the texture names from the primitive's visual file.
I dont need that part in the space.bin either.

What a complete waste of time decoding all this shit.
## Post #148
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-27T00:58:24+00:00
- Post Title: Re: World of Tanks Map format.

Oh well...
Im going to start incorporating this in to Terra!
## Post #149
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-27T05:08:14+00:00
- Post Title: Re: World of Tanks Map format.

Well...

I had to change more than I wanted.
All my data types where buried in side the map data sets.

Took a while to clean it up.
Any way...
Trees are back  .. Ill do the models tomorrow.. I'm to damn tired.
[SandRiver_trees.jpg](https://xentaxbackup.github.io/file/10369_SandRiver_trees.jpg)
## Post #150
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-01-27T21:20:51+00:00
- Post Title: Re: World of Tanks Map format.

This is getting somewhere ! Are you saying also that the huge goddamn updates this game needs constantly, clogging up diskspace, are really not necessary?
## Post #151
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-28T03:55:09+00:00
- Post Title: Re: World of Tanks Map format.

Hi Mr.Mouse...

Pretty much.
 I'm not sure why they have created the space.bin.... It looks to me like it's soul purpose is to scramble the maps. NOT reduce size. There are no (as far as we can find) indices to go with the gigantic chunk of vertices in the data.
ENSK has 34 meg of vertices data in the space.bin. Its pointless because you have to LOAD the models anyway to get the indices. If your going to load the models, get ALL the data there.. don't double it up.
You gotta remember that probably 1/3 of the models are reused on the maps.. this means they have added duplicate data in the the space.bin. So now.. this data is all over the place and not just in a single model. It could be in 10 maps. We are talking about GIGS of duplicated data. 

I was thinking hard about why they put this format out.. I have 3 answers.
1. They don't know what they are doing...   
2. They released the version unfinished to meet dead line.
3. They are leaving enough there to allow us hacks to figure out the data.

I suspect they will remove all the models and embed them in the space.bin files at some point.
This is actually not a horrible thing. Must of the XMLs are reduced to binary and the load times will be much faster.
There won't be any need to bounce all over the drive, loading hundreds of models, model, visual and primitive files.
I doubt the saving in space from converting the xmls verses all the duplication will save space.. Its more than likely going to increase the size of it.

In any case.. It's so popular ( one of the most successful online games in history) people will deal with the nth hour downloads.
## Post #152
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-28T09:06:09+00:00
- Post Title: Re: World of Tanks Map format.

well, I'm pretty sure the entire purpose of space.bin file is to speed up loading, instead of loading and decompressing 100 xml files, you have all data in binary form (much faster to load) inside one file.

Also you supposedly don't need to use .visual files to load models on map, since all info is inside the bin file. Only thing missing are the indicies...

I'm inclined to belive they actually didn't finish the format (as coffee said) and in next patch, the indicies will be there. We'll see...
## Post #153
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-28T09:52:57+00:00
- Post Title: Re: World of Tanks Map format.

Got the models loading again.
[siegfried_line.jpg](https://xentaxbackup.github.io/file/10376_siegfried_line.jpg)
## Post #154
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-01-28T10:21:53+00:00
- Post Title: Re: World of Tanks Map format.

Just did one more check. The vertices inside .primitives aren't used. Only the indicies part. So the vertices data inside bin file are used... why indices aren't there is still beyond me
## Post #155
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-01-28T21:09:47+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Got the models loading again.

What tool is that in your screenshot ?
## Post #156
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-01-29T14:03:20+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Got the models loading again.
Ability to export full scene to FBX would be really usefull
## Post #157
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-29T17:15:22+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Mr.Mouse
>
> Coffee wrote:Got the models loading again.

What tool is that in your screenshot ?

That is 'Terra!'
It's what I call it.
I started on this 3 years ago but Wargaming broke it with the removal of the .chunk files from the pkgs.
This is what we have been doing is to hack the space.bin which has all the info for what models and their transforms are on the maps.
I have figure out 98% of the .ctree files and how the layered terrain textures works.
There is one more file in the layered textures I need to understand. Its dominantTextures.
I got a list of whats in it from some one.. I just need to decode it and figure out how to use it.
Although my render'er does a close job, its not perfect. The mix of the textures is not perfect.
I think the dominantTextures file has the info I need. I just never bothered hacking it yet.
Also.. the textures are not always in the same order so mixing one in with a high percentage might work for a few grids, it wont work on the entire map. I think that is the purpose of the dominantTextures file.
## Post #158
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-01-29T17:31:03+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Andrakann
>
> Coffee wrote:Got the models loading again.
Ability to export full scene to FBX would be really usefull

Exporting the terrain in FBX would be a monumental task.
There are up to 4 layers per grid. I don't think there is even a way Max or Maya can mix 4 maps.
I could write code to create 2 mixed textures. One for the color and one for the normal map.
Yes.. I guess one could use the terrain shader and render to textures in stead of the screen.
You could use the map location name as the file names for the 2 textures. I.E. FFFFFFFF_AM.png and FFFFFFFF_NM.png.

OMG... so much work.
I need to fix a bunch of issues before I do anything else.
## Post #159
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T03:41:36+00:00
- Post Title: Re: World of Tanks Map format.

SkaceKachna,

I gave you credit for all your work at sorting out space.bin!

Thank you !

[http://worldoftanks.curseforge.com/wot- ... ages/main/](http://worldoftanks.curseforge.com/wot-mods/terra-3d-tactical-battle-designe/pages/main/)
## Post #160
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T03:59:49+00:00
- Post Title: Re: World of Tanks Map format.

I uploading Terra! to my VPS so you can play with it.
Read the help file.. 

[http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)
## Post #161
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T17:57:25+00:00
- Post Title: Re: World of Tanks Map format.

Ok.. 
I am still trying to improve on this.

There are a bunch of files that make up the .cdata.

What I know:
.cdata are zip files.
In the file is a folder called terrain2.
In this file there are these key files needed to build the terrain.
heights
normals
layer1 to layer 4
lodTexture.dds
dominateTextures
====================================
heights format is like this:
uint32 magic
uint32 width in x
uint32 height in z
uint32 junk
uint32 version
float min height in y
float max height in y
uint32 header ( gnpq ) or qpng
PNG data. Each is a float

The interesting part of this file is its size in x,y
After many hours I found that if I store this in an array(69*4, 69*4)
and start at offsets (2,2) and read only 64 floats per line. (Drop the first 3 on x and z)
I am able to get the terrain looking correct.
Because I'm using Opengl, I have to flip how they are stored in my array in z. (Directx z is backwards to OpenGL)

Each chunk (Not player grid size) is 100 x 100 units. This never changes on any map
In order to draw the terrain correctly, you have to draw for 1 to 63 and leave 64 for the seam.
The seam will need data from 2 adjoining sets of height data.
====================================

The normals file:
Uint32 header
bunch of useless padding (all zeros)
We only care about the PNG that starts at 16 bytes in from the start.
This is a png of 64 x 64 x 2 bytes.
The 2 bytes represent X and Z components of the normal vector.
Y will be calculated in the shader. You will need to convert this data in to
a texture and store the X,Z as the R,B part of the color.
In the shader you would create the Y component like this.
Y = sqrt( 1.0 - ((X*X) + (Z*Z)) )
Depending on how you created you map, you may need to invert Z after.
Y will always be positive and that's fine.. there will never be terrain pointing down 

====================================
Layers 1 to Layers N
Why N? Not all chunks have all 4 textures.
Each layer file is exactly in the same format:
uint32 magic
uint32 X size
uint32 Y size

vec4 texture U transform ( x y z w )
vec4 texture V transform ( x y z w )

uint32 version?
uint32 TEXTURE COUNT
ulong ( 8 bytes) padding.
Uint32 Str Length
bytes * strlen  the string data (texture file name)
byte (always zero) String terminator

PNG file
this contains the mix level for this layer at every XY on the map.
Its X,Y sizes are stored in the PNG.
This data in the PNG is the amount this texture will be mixed in to the finial color
at location X,Y on the chunk.
You will want to convert all of these in to a single RGBA texture and send that to the shader.
You could on the other hand, create a texture for each mix channel. (waste of space and SLOW!!!)
In the shader you will add each of the layer maps after multiplying it by its mix.

```
Coutmix  = t4 * MixLevel.a;
Coutmix += t3 * MixLevel.b;
Coutmix += t2 * MixLevel.g;
Coutmix += t1 * MixLevel.r;

```


There can be more than one texture name per file.
Usually there is a matching normal map file but not always.
IMPORTANT: One of these layers will have the MAIN texture in it. (color_Tex.dds)
This texture is HUGE and covers the entire map where the other textures are chunk based
You will need to be tagged in your data and a flag passed to
the shader to let it know what layer this texture belongs to.
you will also need to pass the current X and Y on the grid so you 
can offset and scale the UVs for the main texture.
Also very IMPORTANT.....
You will need to BLUR the mixmap!
I had problems with bleeding at the edges so I wound up creating
one giant texture called mix_atlas. I added 4 extra rows and
columns to each texture to allow for the bleeding.
I use a shader to do the blurring and a 2nd FBO. Its not a small
undertaking to get the terrain looking like the game.

====================================
I still have a few things I need to do.
One is Decals. There are a number of ways to do this but
the easiest looks like using a 'mega texture'. This is basically
creating a huge (4096 x 4096) texture and using a shader to
render the decals over the top of it before creating a OpenGL texture.
I'll post how this has worked out.

I am at a loss on how to use the dominateTextures.
I figure out its format.
for Abby, its a zipped list of bytes in X,Y size.
I converted this in to a texture by shifting the values left 5 bits
so I can see it as shades of color. ( a good way to visualize what it is )
I attached this image.. I am not 100% sure but I believe this is the order
the textures need to be added together. In the image you can clearly see
there are 4 shades.

This is as far as I have gotten with the terrain. I would love some help finishing it up.
I don't care about the effects.. Smoke and all that because this is not running in real time.
It only updates if you move the camera.

If you are going to attempt creating the terrain from World of Tanks,
take the time to create tools to visualize things! Below you can see
I have the chunk Id's  names and what data member they belong to.
I also can turn of visualizing the Chunks (C key) and the player grids (G key).
You can get to my shaders by pressing the E key. Changing them can cause horrific problems!
SS is the low rez shader
render is the high rez shader
Bump is for the models and .. trees is for ... duh.. trees.
It has been a total nightmare trying to balance the lighting between low rez and high rez.
Adding in the bump mapping to the high rez causes a shift in lighting. I have code in the shaders
to get the distance from the camera to the vertex. I use this to control the mix between the resolutions
and to help balance the lighting. Its not perfect but its better than NO balancing!
[dominate.jpg](https://xentaxbackup.github.io/file/10400_dominate.jpg)
## Post #162
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-01T21:09:36+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> 
PNG file
this contains the mix level for this layer at every XY on the map.
Its X,Y sizes are stored in the PNG.
This data in the PNG is the amount this texture will be mixed in to the finial color
at location X,Y on the chunk.
You will want to convert all of these in to a single RGBA texture and send that to the shader.
You could on the other hand, create a texture for each mix channel. (waste of space and SLOW!!!)

May I ask how to map X,Y in the PNG to X,Y in textures? I tried to scale texture to size of the PNG.
(the layer 1 PNG size is 256x256 and referenced texture is 1024x1024, so I scale the texture to 256x256 then applied the PNG)
That obviously won't work for the color_tex map, which covers the entire map ...
## Post #163
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T22:48:53+00:00
- Post Title: Re: World of Tanks Map format.

You dont need to scale it.
all the layer sizes (x and y ) in a chunk should be the same size.

create an image that is (x * y * RGBA ) in size. .
Add each one of the layers (1 to n) to color channels R,B,G and A in this image.
Once this is done, you can use this texture in a shader and pull the mix value for that pixel.
You treat the mix texture as any other texture as far as binding it in OpenGL/
## Post #164
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T22:50:05+00:00
- Post Title: Re: World of Tanks Map format.

The mix texture is course.. this is why it needs to be blurred or it will look very blocky.
## Post #165
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-01T22:57:33+00:00
- Post Title: Re: World of Tanks Map format.

So just scale the texture to the chunk size? But how to use the color_tex then ... I can't scale i to chunk size, color_tex must cover entire map.
Do I need to treat the color_tex differently than rest of the textures? If so, is there any other way to identify color_tex other than it being the first layer?
Currently I just use the color_tex as background and then apply the other layers, which works and looks nice, but somehow I feel this isn't the right way
## Post #166
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T23:01:21+00:00
- Post Title: Re: World of Tanks Map format.

BTW....
In opengl.. GLSL... when you try to use a texture that has nothing bound to it, it will return unexpected results.

Do this also...
you must create a dummy texture the same size as the layer textures.
If there is NO layer for say... number 4.. use this dummy and bind it to that texture position.
This is why I have a variable I save called layer_count.
When I do the reading of the layer files.. I update this variable.
You can also use this variable in the shader if you need it for some reason.
I found adding an empty texture had no effect on the overall mix as long as RGBA = 0 0 0 0

Also.. your mix texture should be set to RGBA = 0 0 0 0 when you first create it.
I use Devil and it works well for creating empty textures. I dont know if you can use it
## Post #167
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T23:08:21+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> So just scale the texture to the chunk size? But how to use the color_tex then ... I can't scale i to chunk size, color_tex must cover entire map.
Do I need to treat the color_tex differently than rest of the textures? If so, is there any other way to identify color_tex other than it being the first layer?
Currently I just use the color_tex as background and then apply the other layers, which works and looks nice, but somehow I feel this isn't the right way

See.. This is a huge issue I had.. The color_Tex can wind up in layer 1 to 4.
The only way to know is to check the string and see if it matches.
The thing is... It doesn't seem to matter as far as the final mix.

To deal with the size( 4096 x 4096) you can scale the UV coords for the other textures
If the map is say... 12 x 12 chunks...
pass the map location in X,Y to the shader along with the size.. in this case 12.
Now... to scale it take U and divide it by the map size (12) and add (1.0/12.0) * location X
You would do the same for V.
Use these new UV coords in the shader to look up the color_tex RGBA
## Post #168
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T23:10:17+00:00
- Post Title: Re: World of Tanks Map format.

What I actually did was to cut up the color_tex in to a bunch of smaller textures.
It works but is slow and scaling a UV for it is a better solution.
## Post #169
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-01T23:15:23+00:00
- Post Title: Re: World of Tanks Map format.

I actually use one big texture, containing all chunks in one image, composed using image operations only (no 3D, GL etc) (it's better solution if you're loading images using browser, loading 144 images would take much more time)

Thanks for providing more insight
## Post #170
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T23:24:24+00:00
- Post Title: Re: World of Tanks Map format.

no problem...

Actually...
there are usually 4 images per chunk so for a 12 x 12 map that's 144 *4 plus the low rez map and its normal data.
Loading the texture is by far the slowest part of my app.
Even loading the models is a pain.
But.. I reuse any textures already loaded.. so this saves a lot.
## Post #171
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-01T23:33:06+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> 
Currently I just use the color_tex as background and then apply the other layers, which works and looks nice, but somehow I feel this isn't the right way

There is nothing wrong with this...
As long as you are actually using the mix values. If not.. it wont even be close to the game's terrain.
Also.. there are the UV transforms that need to be done.. This could be done before applying them to the main texture.
## Post #172
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-02T22:07:30+00:00
- Post Title: Re: World of Tanks Map format.

I get an error with Terra though. Clean full HD install of WoT. 
I want to select the map Abby and then:



error_terra.png (48.76 KiB) Viewed 32 times



```
van JIT-foutopsporing (Just In Time) in plaats van dit dialoogvenster.

************** Tekst van uitzondering **************
System.IO.DirectoryNotFoundException: Kan een gedeelte van het pad C:\!!_ENSK\BWSG_DUMP\Chunk_00_0000.bin niet vinden.
   bij System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   bij System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   bij System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   bij System.IO.File.InternalWriteAllBytes(String path, Byte[] bytes, Boolean checkHost)
   bij System.IO.File.WriteAllBytes(String path, Byte[] bytes)
   bij Terra.Mod_Space_Bin_Functions.get_BWSG_data(Int32 t_cnt)
   bij Terra.Mod_space_bin.get_spaceBin_data(Byte[] spaceBindata)
   bij Terra.modZlib.open_pkg(String name)
   bij Terra.frmMain.pb1_MouseDown(Object sender, MouseEventArgs e)
   bij System.Windows.Forms.Control.OnMouseDown(MouseEventArgs e)
   bij System.Windows.Forms.Control.WmMouseDown(Message& m, MouseButtons button, Int32 clicks)
   bij System.Windows.Forms.Control.WndProc(Message& m)
   bij System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   bij System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   bij System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   bij System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Geladen assembly's **************
mscorlib
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1063.1 built by: NETFXREL3STAGE
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
Terra
    Assembly-versie: 0.1.0.3
    Win32-versie: 0.1.0.3
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Terra.exe
----------------------------------------
Microsoft.VisualBasic
    Assembly-versie: 10.0.0.0
    Win32-versie: 14.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualBasic.dll
----------------------------------------
System
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Core
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Windows.Forms
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System.Drawing
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Runtime.Remoting
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.Remoting/v4.0_4.0.0.0__b77a5c561934e089/System.Runtime.Remoting.dll
----------------------------------------
Tao.Platform.Windows
    Assembly-versie: 1.0.0.5
    Win32-versie: 1.0.0.5
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Tao.Platform.Windows.DLL
----------------------------------------
System.Configuration
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
Tao.FreeGlut
    Assembly-versie: 2.4.0.2
    Win32-versie: 2.4.0.2
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Tao.FreeGlut.DLL
----------------------------------------
Tao.OpenGl
    Assembly-versie: 2.1.0.12
    Win32-versie: 2.1.0.12
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Tao.OpenGl.DLL
----------------------------------------
Tao.DevIl
    Assembly-versie: 1.6.8.3
    Win32-versie: 1.6.8.3
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Tao.DevIl.DLL
----------------------------------------
System.Data
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_32/System.Data/v4.0_4.0.0.0__b77a5c561934e089/System.Data.dll
----------------------------------------
System.Data.DataSetExtensions
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Data.DataSetExtensions/v4.0_4.0.0.0__b77a5c561934e089/System.Data.DataSetExtensions.dll
----------------------------------------
System.Numerics
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Numerics/v4.0_4.0.0.0__b77a5c561934e089/System.Numerics.dll
----------------------------------------
PresentationCore
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1063.1 built by: NETFXREL3STAGE
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_32/PresentationCore/v4.0_4.0.0.0__31bf3856ad364e35/PresentationCore.dll
----------------------------------------
WindowsBase
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1063.1 built by: NETFXREL3STAGE
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/WindowsBase/v4.0_4.0.0.0__31bf3856ad364e35/WindowsBase.dll
----------------------------------------
Ionic.Zip
    Assembly-versie: 1.9.1.8
    Win32-versie: 1.9.1.8
    CodeBase: file:///H:/Tools/Coffee_/Terra!/Ionic.Zip.DLL
----------------------------------------
mscorlib.resources
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/mscorlib.resources/v4.0_4.0.0.0_nl_b77a5c561934e089/mscorlib.resources.dll
----------------------------------------
System.Windows.Forms.resources
    Assembly-versie: 4.0.0.0
    Win32-versie: 4.6.1038.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms.resources/v4.0_4.0.0.0_nl_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------

************** JIT-foutopsporing **************
Als u JIT-foutopsporing wilt inschakelen, moet in het configuratiebestand voor deze
toepassing of computer (machine.config) de waarde
jitDebugging in het gedeelte system.windows.forms zijn ingesteld.
De toepassing moet ook zijn gecompileerd terwijl foutopsporing
was ingeschakeld.

Bijvoorbeeld:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

Wanneer JIT-foutopsporing is ingeschakeld, worden onverwerkte uitzonderingen
naar het JIT-foutopsporingsprogramma gestuurd dat op de computer is geregistreerd
en worden niet door dit dialoogvenster verwerkt.

```
## Post #173
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T06:17:08+00:00
- Post Title: Re: World of Tanks Map format.

Probably because it cant find the lighting settings file..

I'll be updating a new version soon.
## Post #174
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T06:29:59+00:00
- Post Title: Re: World of Tanks Map format.

Well....
It took for god damn ever but I managed to figure out how to project the decal textures.

I'm doing it with the CPU so its not real fast creating the meshes. I may look in to finding a way to do it using a shader or I might even save the meshes and export them..


In this Image you can see the decals mesh deformed to fit the terrain. Its made of a 32 x 32 cell mesh.


In this image, I have turned on solid fill, blend and added the decal texture.


Now The terrain is rendered as usual along with the new decals.


Buildings and trees turn on.


I had already wrote a function to find the Y point anywhere on the terrain's mesh..
I found out that it had a very BAD bug and it took me the better part of a day to find it.
Integers cant hold floating real numbers.. DUH!!!!

I have not verified the textures are not flipped.. 
I was so excited to share this I didn't take the time.. LOL!!!

EDIT: Yep.. Textures were flipped on V... All fixed now
## Post #175
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T07:41:43+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Mr.Mouse
>
> I get an error with Terra though. Clean full HD install of WoT. 
I want to select the map Abby and then:

I found the problem.. 
I left a write to the hard drive in the app.. It was for debugging and never took it out..
Sorry
## Post #176
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-03T07:50:10+00:00
- Post Title: Re: World of Tanks Map format.

Wow, really good job. It looks like ingame now!
## Post #177
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-03T08:02:34+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Mr.Mouse wrote:I get an error with Terra though. Clean full HD install of WoT. 
I want to select the map Abby and then:


I found the problem.. 
I left a write to the hard drive in the app.. It was for debugging and never took it out..
Sorry

Yeah, I figured it was a hard-coded path left somewhere. 
Is the new version up for download? I'll host it at Xentax as well if you like.
## Post #178
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T14:40:59+00:00
- Post Title: Re: World of Tanks Map format.

I will update in a bit..
I have some clean up to do first.

A temp work around is to create these folders.
"C:\!!_ENSK\BWSG_DUMP\" 

It was used to export all the vertex chunks when I was sorting that out.
## Post #179
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T14:42:23+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Wow, really good job. It looks like ingame now!

Thanks 

Now I need the shadows.
## Post #180
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T17:10:23+00:00
- Post Title: Re: World of Tanks Map format.

I am having real issues with the decals that over lap fighting the Z-buffer..

Does anyone an idea how to solve this?

I tried turning off depth testing but that causes more problems.

EDIT: I'm working on a shader for the decals... They need a lot more bump mapping!
## Post #181
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-03T18:52:30+00:00
- Post Title: Re: World of Tanks Map format.

Ok...

I fixed the z-buffer fighting..

I draw the decals after the sky dome and before anything else.

1. shut off rendering to color buffer.. leave z-buffer writing on.
2. draw all the decals.
3. turn off depth testing.
4. turn writing to color buffer back on.
5. draw decals again.

It sucks because I have to draw them twice WITH textures or the entire decals mesh blocks the rendering of the terrain.

.
## Post #182
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T05:08:15+00:00
- Post Title: Re: World of Tanks Map format.

I have a couple of new problems...

1. When the underlying terrain is very contorted, the decal doesn't wrap the decal mesh unless its very tessellated.
2. I am not sure how to fix the order the decals are rendered. I think there was a value in the original chunk files that was called 'priority'. This is probably still in the space.bin.
3. Blending the terrain with the decals is proving to be on hell of a bitch. The color mismatch is amazing.

I can solve problem 1. but will slow the load of the decals to a crawl.
Basically it would goes like this:
Adjust the tessellation of the decal's mesh based on the contortion of the underlying terrain.
This could be done by creating a medium poly mesh and deform it to the terrain and after, check how extreme the X, Y and Z points move across the mesh. This would work but is very slow. The time killed is coming from finding the point's Y location on the terrain mesh. I am pondering the idea of creating some kind of lookup table to get get rid of the brute force method I'm using to find what grid the point is in.

I was adjusting the tessellation based on the scaling of the decal but this has proven to fail horribly.
Anything under 32x32 and it wont deform accurate enough and... even at this scale, on rough terrain, some of it breaks through the decal's mesh.
## Post #183
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-04T11:04:57+00:00
- Post Title: Re: World of Tanks Map format.

I never actually delt with decals, but wouldn't it be possible to add new texture to map and use uv2 coordinates instead of separate mesh?
## Post #184
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-04T15:18:25+00:00
- Post Title: Re: World of Tanks Map format.

By the way, how did you extract the trees? I noticed some inidices in .ctree file, did some random tries and discovered that there is
2x:
number of vertices
  vertices, each 54 (x,y,z,nx,ny,nz,u,v ... ?)
number of lods .. for each lod
  number of indices
  .... indices ...

this works perfect, first model is root, second model are branches, but then there is different format:

1x:
number of vertices
  vertices, each 88 (x,y,z,nx,ny,nz,u,v ... ?)
number of lods .. for each lod
  number of indices
  .... indices ...

it appears that there are 3 vertices on same position ... is there something hidden inside those 88 bytes?
## Post #185
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T16:08:07+00:00
- Post Title: Re: World of Tanks Map format.

There are 3 different types in the ctree data

Let me find my notes...
   
```
        'As im typing this, it has been 2 weeks of constant
        'work. In the end.. I guessed at what the data was
        'and got it working.
        'There are differet vertex data types in each file
        'and they change depending on the plants geo.
        'I have no idea how to pre-detect the types so..
        'the code branches depending on what it finds.
        'Not the best way but it works ok.
        'There are still a few trees that are not created 100%
        '
        'ctree files are pre-calculated tree structures.
        '
        'Alot of the code is hacked together to get things to work
        'due to the fact that there are so many different variations
        'of the same thing. Why it's like this, I have no idea.
        '
        'It creates (if its there)
        '   1. trunk/branch models
        '   2. Fronds. Some look like small branches.
        '   3. Leafs. Some trees have no leafs such as Palms
        '   4. 360 degree view billboards.
        '
```

I normally NEVER do this but be cause you have been a fantastic asset at figuring out the space.bin..
Here ya go... The attached is my code to build the trees.

Look at the last sub.
The thing about these files.. I could never find any thing the explain what the next chunk is..
Is it a Trunk? Branch? Leaf? Frond? Bill-board?
I do it by looking at that data that's there.. If a file name is before the data.. blah blah blah.. Its a mess.
There are 4 types and 2 different types of node formats.
[ctree_source.zip](https://xentaxbackup.github.io/file/10422_ctree_source.zip)
## Post #186
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T16:12:56+00:00
- Post Title: Re: World of Tanks Map format.

You will need to create an array to store the crap in.. A structure.. or data type.. 
Also.. There is a tree_cache.
I never RELOAD a model that's already been loaded.. I look in the cache.. if its there I get its Id's..
If I have to load it.. I add it to the cache after its loaded
## Post #187
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T16:27:07+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> I never actually delt with decals, but wouldn't it be possible to add new texture to map and use uv2 coordinates instead of separate mesh?

This sounds ok until you get close to the decal than it will become very blurred.

I fixed some of the order issue.. I was right about the priority.
If its 1, it gets drawn first. So.. I sort them after getting them from the WGSD section.
## Post #188
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-04T17:07:38+00:00
- Post Title: Re: World of Tanks Map format.

Thanks for all the info! I have a feeling this will be long night...
## Post #189
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T18:45:48+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Thanks for all the info! I have a feeling this will be long night...
No problem..
Don't forget to thank me
## Post #190
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-04T19:52:34+00:00
- Post Title: Re: World of Tanks Map format.

In Terra, the colours and map looks like this (not right). Should it be better?



wot.png (754.31 KiB) Viewed 41 times
## Post #191
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-04T22:37:13+00:00
- Post Title: Re: World of Tanks Map format.

Trees loaded!

[https://i.imgur.com/UeQn82z.jpg](https://i.imgur.com/UeQn82z.jpg)

I found out, that the leaves aren't supposed to be treated as mesh, but billboards that always face camera (you can see that in the offline map viewer - thanks for that tip!). (You basically take the 4 vertices, use their UV values to get correct image in texture, position is always same so only add position once)

This type of billboards is often used for particles and GL have built-in support for this. Bascially you create geometry, where every vertice is separate position where the billboard will be drawn and material that has map, which will be the billboard. I don't know any specifics about implementation as I use gl wrapper to make things easier...
## Post #192
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-04T23:50:53+00:00
- Post Title: Re: World of Tanks Map format.

So you are drawing a leaf at every one of the 4 vertices?
EDIT.. I get it.. it's a view aligned quad.
I'm a little lost but your trees look better than mine 


And NO Terra is NOT like that.. some thing is for sure wrong with loading the models..

I'm still struggling with the decals.. I am almost done though.
## Post #193
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-05T07:54:26+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> 
And NO Terra is NOT like that.. some thing is for sure wrong with loading the models...

Okay, is that some setting I must fix, or is Terra in need of a fix?
## Post #194
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-05T17:11:57+00:00
- Post Title: Re: World of Tanks Map format.

Its broke..
Sorry..
You could try playing with the light levels..
It looks like everything is whited out.
## Post #195
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-05T21:50:47+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Trees loaded!

https://i.imgur.com/UeQn82z.jpg

I found out, that the leaves aren't supposed to be treated as mesh, but billboards that always face camera (you can see that in the offline map viewer - thanks for that tip!). (You basically take the 4 vertices, use their UV values to get correct image in texture, position is always same so only add position once)

This type of billboards is often used for particles and GL have built-in support for this. Bascially you create geometry, where every vertice is separate position where the billboard will be drawn and material that has map, which will be the billboard. I don't know any specifics about implementation as I use gl wrapper to make things easier...

Can you post how you handle this?
Are you passing an Index to the shader?
## Post #196
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-05T22:02:11+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Its broke..
Sorry..
You could try playing with the light levels..
It looks like everything is whited out.

Okay, so it is Terra being broke? I'll just wait for a new release then.
## Post #197
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-05T22:15:21+00:00
- Post Title: Re: World of Tanks Map format.

Well, as I said, I'm using webgl wrapper for javascript, so I never directly work with GL...

I took a look into it and the main difference is, that instead calling:

_gl.drawArrays( _gl.TRIANGLES, start, count );

you call:

_gl.drawArrays( _gl.POINTS, start, count );

Now instead of rendering normal models, GL will render each vertex as point. So you only need one of those 4 vertices in the geometry to get correct position, you use the rest to get correct UV coordinates.
I attached parts of shader, it isn't complete, but that's all I could get from the wrapper ... I don't understand shaders much
[shader.zip](https://xentaxbackup.github.io/file/10428_shader.zip)
## Post #198
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-05T23:06:53+00:00
- Post Title: Re: World of Tanks Map format.

Thanks for the info..

I was about to start writing a glsl program using the geo shader but wanted to wait for your replay.

So.. 
I could send one vertices which is the center of the quad and 4 uv coords to the geo shader and let it create the quad.
## Post #199
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-06T03:13:53+00:00
- Post Title: Re: World of Tanks Map format.

shit.. I can't get this working 

I don't under stand how to pass the UVs to a single point.
I need 4 uvs passed
What Im doing now is using gl_Multitexcoord but it does't seem to bind and UVs to a point.
I tried turning on point_sprite... that don't work.
## Post #200
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-06T08:31:43+00:00
- Post Title: Re: World of Tanks Map format.

I'm sorry, we must be living in oposite timezones ... I just woke up.

I forgot to mention ... I never use the entire texture with combination of UV coordinates. I use the UV coordinates to create separate texture (cut it out), which I then assign to rendering. It isn't ideal, but it works.
## Post #201
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-06T09:06:19+00:00
- Post Title: Re: World of Tanks Map format.

By the way, I updated wot-python-lib, it can now read the space.bin files and newest primitives:

[https://github.com/SkaceKamen/wot-python-lib](https://github.com/SkaceKamen/wot-python-lib)
## Post #202
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-06T15:01:01+00:00
- Post Title: Re: World of Tanks Map format.

Yes.. Different Time zones 
I live in not so beautiful Erie, Pa.. on the tail end of Lake Erie.

The problem I'm having is it isn't using the shader at all.
I have been screwing with this for 2 days just trying to sort out why this is.
It all 3 parts vertex, geo and fragment compile with no errors and I get a valid ID for the shader program but it just does NOT make a differences if it use it or not. I send points and the damn thing does nothing but draw a POINT!
I cant effect the color or anything in the shader!!!!

> By the way, I updated wot-python-lib, it can now read the space.bin files and newest primitives:
Cool..  Did you update the wiki's as well?
## Post #203
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-07T21:18:07+00:00
- Post Title: Re: World of Tanks Map format.

Ok...
You can check out this version.
I changed the Tree leaves and fixed a bunch of bugs.
I also added decals.. 
The lighting is not 100% perfect on the decals or trees yet.
You will need to set the path at startup.
You will need to mess with the light settings to get the best look.
It saves each light setting for each map.

Version 22
[http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)

EDIT:
There is a bug with the primary texture map getting screwed up.
I have not found what is causing this and after 5 hours I gave up.
I'll go back later and sort it out.
## Post #204
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-07T21:32:51+00:00
- Post Title: Re: World of Tanks Map format.

It looks pretty good now.
Not perfect and it never will be. I don't understand how to get the layers mixed perfectly.
## Post #205
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-07T21:53:11+00:00
- Post Title: Re: World of Tanks Map format.

All that crap... almost 3 full days trying to get other peoples code working to align a quad with the view plane..
LMAO.. this is soooo simple and works with out a shit load of translations.


I send each corner of the quad to the shader in UV coordinate and its center as the vertex.
Than I just do this in the vertex shader.. SO SIMPLE!

```
      vec4 p =  gl_ModelViewMatrix * gl_Vertex;
    p.xyz += gl_MultiTexCoord1.xyz;
    p           = inverse(gl_ModelViewMatrix) * p;
    gl_Position = gl_ModelViewProjectionMatrix * p;

```
## Post #206
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-08T13:55:14+00:00
- Post Title: Re: World of Tanks Map format.

no comments 
Is Terra working?
## Post #207
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-08T14:13:30+00:00
- Post Title: Re: World of Tanks Map format.

Sorry, been busy with some other stuff.

The screenshots look good, but I'm unable to launch the Terra locally.
1. My antivirus (Avast) is insiting that it's virus
2. Once I managed to overthrow him, I tried to set the path. Once I do File > Set path, the application closes, without any error or anything, just shuts down. I looked to .settings file and path wasn't set, so I manually changed it there. Then map list shows, when I select any map this shows:
[https://i.imgur.com/uziG8EH.png](https://i.imgur.com/uziG8EH.png)
## Post #208
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-08T15:58:02+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Sorry, been busy with some other stuff.

The screenshots look good, but I'm unable to launch the Terra locally.
1. My antivirus (Avast) is insiting that it's virus
2. Once I managed to overthrow him, I tried to set the path. Once I do File > Set path, the application closes, without any error or anything, just shuts down. I looked to .settings file and path wasn't set, so I manually changed it there. Then map list shows, when I select any map this shows:
https://i.imgur.com/uziG8EH.png

Virus could be coming from the fact that Terra has a built in server for people to log in to to watch some on setup a layout. It interesting.

Terra shuts down once the path is set.. It can't continue with out first initializing every thing it needs from the games data.
I can probably fix this by moving all this to a sub and calling it after the path is set.
If the settings file is not being updated there is something very strange going on.
The path should point to the games root folder.. Something like this "C:\games\World of Tanks\"
I'm pretty sure you have the path right or Terra would not find the "\res\scripts\destructibles.xml" file. If it can't find this file it triggers the 'path not set' alarm.
BTW.. this file list every material type that is destructible. I use it to cancel loading models parts that are crushed.
This has always worked in previous versions of World of Tanks but this last version seems to have broken this. Terra is loading parts of builds that are crushed now. I'm still looking for why this is.
While I was typing this, I decide to look at the destructibles.xml file.. It looks like it's format has changed. I'm not 100% sure.. I have not dealt with this file in years.

I'll look in to all this...

Also.. There is something strange about the trees.. I'm missing something about a scale factor or something.
Pine trees seem to have a taper in the game that my tree creator doesn't duplicate.
## Post #209
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-08T18:11:32+00:00
- Post Title: Re: World of Tanks Map format.

I was wrong.
"\res\scripts\destructibles.xml" file actually contains the names of the materials that are NOT in a destructed state.
Told ya it has be a long time lol
## Post #210
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-08T20:12:49+00:00
- Post Title: Re: World of Tanks Map format.

terra.png (469.7 KiB) Viewed 25 times



What am I doing wrong, I downloaded the latest version, but the models still won't show. I can tweak the lighting to get the right colours more or less, though.
## Post #211
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-08T21:25:41+00:00
- Post Title: Re: World of Tanks Map format.

Mr. Mouse,
What is the make of your video Card?

It looks like the shader is not working right or the textures are not found.
The trees and decals have the correct textures so its not a path problem.
## Post #212
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-09T14:56:31+00:00
- Post Title: Re: World of Tanks Map format.

So I can't do anything right now to fix terra?

Also, do you load lights settings from world of tanks or do you use your own?
I'm interested if there is any way to load original lights from the game to achieve best looks.
## Post #213
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-09T20:42:13+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Mr. Mouse,
What is the make of your video Card?

It looks like the shader is not working right or the textures are not found.
The trees and decals have the correct textures so its not a path problem.

I'm running on a Radeon HD 7800. I'm having the latest WoT installed on HD texture mode.
## Post #214
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-10T01:01:10+00:00
- Post Title: Re: World of Tanks Map format.

I think I found the problem..

In nVidia, it is perfectly legal to pass a matrix from the vertex shader to the fragment shader.
This IS a OpenGL spec. However.. I just tested this using one of AMDs tools and it fails.
I moved the building of the matrix (used for lighting) from the vertex to the fragment.
This means that rather than creating the matrix per vertex, it is now being done per PIXEL.
This will slow things down but on my G-Force 660 Ti, I'm not seeing much.
Maybe because this nVidia card of mine has 1344 CUDA cores.
[http://www.geforce.com/hardware/desktop ... ifications](http://www.geforce.com/hardware/desktop-gpus/geforce-gtx-660ti/specifications)

Anyway.. The shaders compile fine now using AMDs analyzer tool.

I have been trying to get the trees closer to the game.
There is something serious I'm missing in the scaling of the leaves.
There are 22 floats in a leaf vertex data set. There are 2 leaf formats.
The 2nd type scale perfectly. There is nothing that has to be done to these types.
The 15th float tells you how to interpret the data.
If it is < 4 than this 15th float is a index (0, 1 , 2 , 0, 2, 3) in to an array that defines each corner of a polygon. (2 triangles)

```
        vy()  = {1.0!, 1.0!, -1.0!, -1.0!}

```

If it is 4 or greater, you just use the vertices to build the polygon.
There is scaling information in those 22 floats.. I thought it was the 12 and 13th ones for Y and X. Yes.. they appear to be backwards.
Its not consistent from tree to tree. The leaves might look right on one tree but are too big or small on another.
I tried scaling them by the scale of the entire tree using its matrix.
This works for getting the scale from a float(16) matrix:

> sx = Sqrt((m(0) ^ 2) + (m(1) ^ 2) + (m(3) ^ 2))
>
>         sy = Sqrt((m(4) ^ 2) + (m(5) ^ 2) + (m(6) ^ 2))
>
>         sz = Sqrt((m(8) ^ 2) + (m(9) ^ 2) + (m(10) ^ 2))
This does not fix it either.

I'll upload an update even tho the trees are FUBAR!
Version 24 [http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)
## Post #215
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-10T09:37:27+00:00
- Post Title: Re: World of Tanks Map format.

I too noticed some leaves have wrong scale. For now, I set them to be 3x the specified size ... it looks a bit better, but still, weird. Also somehow the World of Tanks leaves actually have light shading ... how :O
## Post #216
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-10T17:19:08+00:00
- Post Title: Re: World of Tanks Map format.

I found out I was scaling them wrong and my projection was wrong.
I change the code I posted above.

Anyway...
to scale the trees.. 
Get the length of rows 0 1 and 2. These are the scales
"^" means power or you can do "(M(0) * m(0))" for example.
sx = Sqrt((m(0) ^ 2) + (m(1) ^ 2) + (m(3) ^ 2))
sy = Sqrt((m(4) ^ 2) + (m(5) ^ 2) + (m(6) ^ 2))
sz = Sqrt((m(8) ^ 2) + (m(9) ^ 2) + (m(10) ^ 2))

And average them..  Multiplying by 1/3 (its faster then division)
tree_scale = (sx + sy + sz) * 0.3333

There are 6 vertices in each leaf. These create 2 triangles.
I look up the corners using the 2 arrays:
        Dim vx() As Single = {-0.5!, 0.5!, 0.5!, -0.5!}
        Dim vy() As Single = {0.5!, 0.5!, -0.5!, -0.5!}
...
Here is my code. I'm still trying to get the lighting correct.

```
        Dim sx = Sqrt((m(0) ^ 2) + (m(1) ^ 2) + (m(3) ^ 2))
        Dim sy = Sqrt((m(4) ^ 2) + (m(5) ^ 2) + (m(6) ^ 2))
        Dim sz = Sqrt((m(8) ^ 2) + (m(9) ^ 2) + (m(10) ^ 2))
        Dim tree_scale As Single = (sx + sy + sz) * 0.3333

        Dim vx() As Single = {-0.5!, 0.5!, 0.5!, -0.5!}
        Dim vy() As Single = {0.5!, 0.5!, -0.5!, -0.5!}


        For i = 0 To tree_data.l_indices.Length - 3
            'struct LeafVertex
            '
 '00 00 Vec3     position;
 '12 03 Vec3     normal;
 '24 06 Single   texCoords(2)
 '32 08 Single   windInfo(2)
 '40 10 Single   rotInfo(2)
 '48 12 Single   geomInfo(2)
 '56 14 Single   extraInfo(3)
 '68 17 Single   pivotInfo(2)
 '76 19 Vec3 Tangent; ' 3 floats

            p.x = -tree_data.l_vert((tree_data.l_indices(i) * 22) + 0)
            p.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 1)
            p.z = tree_data.l_vert((tree_data.l_indices(i) * 22) + 2)

            norm.x = tree_data.l_vert((tree_data.l_indices(i) * 22) + 3)
            norm.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 4)
            norm.z = tree_data.l_vert((tree_data.l_indices(i) * 22) + 5)

            uv.x = tree_data.l_vert((tree_data.l_indices(i) * 22) + 6)
            uv.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 7)

            rot.x = tree_data.l_vert((tree_data.l_indices(i) * 22) + 17)
            rot.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 18)

            vn = tree_data.l_vert((tree_data.l_indices(i) * 22) + 15) ' corner index
            vn2 = tree_data.l_vert((tree_data.l_indices(i) * 22) + 16)
            If vn2 <> 1.0 Then
                Stop ' has NEVER been hit. It is always 1.0
            End If
            sizey = tree_data.l_vert((tree_data.l_indices(i) * 22) + 12)
            sizex = tree_data.l_vert((tree_data.l_indices(i) * 22) + 13)

            pivot.x = tree_data.l_vert((tree_data.l_indices(i) * 22) + 10)
            pivot.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 11)

            'not sure 100% sure.. This might also be the BiNormal
            tangent.x = tree_data.l_vert((tree_data.l_indices(i) * 22) + 19)
            tangent.y = tree_data.l_vert((tree_data.l_indices(i) * 22) + 20)
            tangent.z = tree_data.l_vert((tree_data.l_indices(i) * 22) + 21)
            'debug string
            sb.Append(rot.x.ToString("0.000000") + "  " + rot.y.ToString("0.000000") + vbCrLf)

            If vn < 4 Then  'less than 4 means this is the special case
                If cnt > 5 Then
                    cnt = 0
                    'Stop ' debug stop at end of each set of 6
                End If
                idx.x = vx(vn)
                idx.y = vy(vn)
                Dim corner As vect3
                corner.x = vx(vn) '- pivot.x
                corner.y = vy(vn) '+ pivot.y
                corner.x *= tree_scale
                corner.y *= tree_scale
                corner.x *= sizex
                corner.y *= sizex
                Gl.glMultiTexCoord3f(0, -uv.x, uv.y, 0.0)
                Gl.glMultiTexCoord3f(1, corner.x, corner.y, 0.0)
                Gl.glMultiTexCoord3f(2, tangent.x, tangent.y, tangent.z)
                Gl.glNormal3f(norm.x, norm.y, norm.z)
                Gl.glVertex3f(p.x, p.y, p.z)

                 cnt += 1
            Else
                ' just use these directly.
                lx = p.x
                ly = p.y
                lz = p.z
                Gl.glMultiTexCoord3f(0, -uv.x, uv.y, 0.0)
                Gl.glMultiTexCoord3f(1, 0.0, 0.0, 0.0)
                Gl.glMultiTexCoord3f(2, tangent.x, tangent.y, tangent.z)
                Gl.glNormal3f(norm.x, norm.y, norm.z)
                Gl.glVertex3f(p.x, p.y, p.z)
            End If
        Next

```

I posted this code as part of that zip but this section is updated.
I'm not sure about the pivot... I don't know how to use it.
I send the center point as the vertex and the corner as a UV coordinate.
In my shader program I do this at the start of the vertex stage.

```
    vec4 p =  gl_ModelViewMatrix * gl_Vertex;
    p.xyz += gl_MultiTexCoord1.xyz;
    p           = inverse(gl_ModelViewMatrix) * p;
    gl_Position = gl_ModelViewProjectionMatrix * p;

```

This gets my corner on the screen at the correct location.

Im not sure it you can add custom shaders to your GL wrapper.
If so.. I might be able to help create one once I get my shader lighting correctly.
I am really not sure about the tangent.. It could be a BiNormal.
## Post #217
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-10T20:25:52+00:00
- Post Title: Re: World of Tanks Map format.

Sadly. no textures on the models still. 



wotterra024.png (706.34 KiB) Viewed 27 times
## Post #218
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-10T21:14:14+00:00
- Post Title: Re: World of Tanks Map format.

I have no idea..
for get what I posted..
I deleted it.
## Post #219
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-10T21:33:01+00:00
- Post Title: Re: World of Tanks Map format.

I updated to version 25.
I doubt this will fix the textures on the models.
## Post #220
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-10T21:34:30+00:00
- Post Title: Re: World of Tanks Map format.

If anyone else is checking out Terra, can you please report anything thats not working, OK?

[http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)

version 25
## Post #221
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-10T21:56:01+00:00
- Post Title: Re: World of Tanks Map format.

It finally tried to load the map, but got following exception:

(The exception was in my native language and I had to translate it to english)

```
   v Microsoft.VisualBasic.CompilerServices.Conversions.ParseDouble(String Value, NumberFormatInfo NumberFormat)
   v Microsoft.VisualBasic.CompilerServices.Conversions.ToDouble(String Value, NumberFormatInfo NumberFormat)
   --- End of tracing of inner exception stack ---
   v Microsoft.VisualBasic.CompilerServices.Conversions.ToDouble(String Value, NumberFormatInfo NumberFormat)
   v Terra.modZlib.get_team_locations(String& name)
   v Terra.modZlib.open_pkg(String name)
   v Terra.frmMain.pb1_MouseDown(Object sender, MouseEventArgs e)
   v System.Windows.Forms.Control.OnMouseDown(MouseEventArgs e)
   v System.Windows.Forms.Control.WmMouseDown(Message& m, MouseButtons button, Int32 clicks)
   v System.Windows.Forms.Control.WndProc(Message& m)
   v System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   v System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   v System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   v System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)

```

I actually know excatly what is the problem: My windows uses my local globalization settings, including number format. In my globalization settings, floating point is ',' not '.'.
I don't remember how to fix it, but I think you can force the globalization settings somehow.
## Post #222
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T02:35:42+00:00
- Post Title: Re: World of Tanks Map format.

Yes.. its trying to read a period and it needs a comma because of your localization.

Let me see what I can find out...

And.. How do you think they manage to put decals over EVERYTHING?

Could this be deferred rendering?
[projected_decal.jpg](https://xentaxbackup.github.io/file/10467_projected_decal.jpg)
## Post #223
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T03:38:27+00:00
- Post Title: Re: World of Tanks Map format.

Ok.. I uploaded version 26.

See if this will work with your culture.

I basically try to read a value of "0.1234"
if it fails, I replace all the periods in the .visual after its read.
It should work but will slow it down a little... 
No worries though, I have found its still faster than jumping through hoops with the all other code that's needed to make it "Culture aware".
## Post #224
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-11T09:04:59+00:00
- Post Title: Re: World of Tanks Map format.

It still throws excpetion (is it the same?)

```
   v Microsoft.VisualBasic.CompilerServices.Conversions.ParseDouble(String Value, NumberFormatInfo NumberFormat)
   v Microsoft.VisualBasic.CompilerServices.Conversions.ToDouble(String Value, NumberFormatInfo NumberFormat)
   --- Konec trasování zásobníku pro vnitřní výjimku ---
   v Microsoft.VisualBasic.CompilerServices.Conversions.ToDouble(String Value, NumberFormatInfo NumberFormat)
   v Terra.modZlib.get_team_locations(String& name)
   v Terra.modZlib.open_pkg(String name)
   v Terra.frmMain.pb1_MouseDown(Object sender, MouseEventArgs e)
   v System.Windows.Forms.Control.OnMouseDown(MouseEventArgs e)
   v System.Windows.Forms.Control.WmMouseDown(Message& m, MouseButtons button, Int32 clicks)
   v System.Windows.Forms.Control.WndProc(Message& m)
   v System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   v System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   v System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   v System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
```
## Post #225
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T15:22:32+00:00
- Post Title: Re: World of Tanks Map format.

yes.. exactly the same.

The first time it tries to read one of the team locations, its expecting a comma for the decimal. -400.0 should be in -400,0 format.
Let me try again
## Post #226
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T16:45:19+00:00
- Post Title: Re: World of Tanks Map format.

Ok.. I found the solution.

I added this to the start of the program:

```
        nonInvariantCulture.NumberFormat.NumberDecimalSeparator = "."
        Thread.CurrentThread.CurrentCulture = nonInvariantCulture


```

What this does its tell it to treat the period as the decimal character regardless of culture.
This should fix it

I uploaded version 27 for testing.
[http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)

I still have not found a way to fix the shader for the models. It works well here so its hard to debug.
I do not own a AMD video card of any kind so I can't test anything.
The shader stages are bump_vertex.glsl and bump_fragment.glsl

Mr. Mouse's images look like the terrain is rendering fine and that shader is VERY complex.
Also the trees and decals look ok. (Decals need more work)
This makes me think that it may not be 100% related to the bump shader.
## Post #227
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-11T16:58:54+00:00
- Post Title: Re: World of Tanks Map format.

Nice! It now works!

[https://i.imgur.com/kOVfTSq.jpg](https://i.imgur.com/kOVfTSq.jpg)

Thanks for fixing it  

(also nice looking trees, I don't think it will ever be nicer)
## Post #228
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T17:41:53+00:00
- Post Title: Re: World of Tanks Map format.

Mr. Mouse...

I have something else you can try.

The bump shader was missing the version definition line. AMD don't that.

Find this folder....
C:\Program Files (x86)\Coffee_\Terra!\shaders
in there is a file called "bump_vertex.glsl"
It is just a text file with a different suffix. .glsl in stead of .txt
Open it and replace the entire file with the code below.
1st... some short cut keys in case you don't know them.. I'm sure you do. I watched your videos 
CRT+A (select all)
CTR+C (copy)
CTR+V (Paste)
CRT+X (delete and move to clipboard)

> //bump_vertex.glsl
>
> // used to render all building and other models
>
> 
>
> #version 120
>
> varying vec3 rgb;
>
> varying vec3 vVertex;
>
> varying vec3 g_vertexnormal;
>
> varying vec3 g_viewvector;
>
> varying vec3 lightDirection;
>
> varying vec2 TC1;
>
> varying vec2 TC2;
>
> varying vec3 T;
>
> varying vec3 BN;
>
> uniform mat4 ModelMatrix1;
>
> 
>
> uniform vec3 camPos;
>
> 
>
> void main(void)
>
> {
>
> 
>
>     TC1 = gl_MultiTexCoord0.xy;
>
>     TC2 = gl_MultiTexCoord1.xy;
>
> 
>
>     mat3 ModelMatrix = mat3(ModelMatrix1);
>
>     vec3 T = normalize(ModelMatrix * gl_MultiTexCoord2.xyz);
>
>     vec3 BN = normalize(ModelMatrix * gl_MultiTexCoord3.xyz);
>
> 
>
>     g_vertexnormal = normalize(ModelMatrix *  gl_Normal);
>
> 
>
>     vVertex = vec3(ModelMatrix1 * gl_Vertex);
>
> 
>
>     gl_Position    = ftransform();
>
>     lightDirection = gl_LightSource[0].position.xyz - vVertex;
>
> 
>
>     g_viewvector = camPos - -vVertex;
>
>     g_viewvector.z *= -1.0;    
>
> 
>
>     rgb = lightDirection;
>
> 
>
> }

save the file.
start Terra and see if it renders the buildings.

Let me know OK?
## Post #229
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T17:47:22+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Nice! It now works!

https://i.imgur.com/kOVfTSq.jpg

Thanks for fixing it  

(also nice looking trees, I don't think it will ever be nicer)

WOOOOOOHOOOOOOOO!!!!!
There is a God!!!!!

I'm so glad this fixes the culture problem.
I can use this in the the model editor i'm working on !
## Post #230
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-02-11T18:32:51+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> SkaceKachna wrote:Nice! It now works!

https://i.imgur.com/kOVfTSq.jpg

Thanks for fixing it  

(also nice looking trees, I don't think it will ever be nicer)

WOOOOOOHOOOOOOOO!!!!!
There is a God!!!!!

I'm so glad this fixes the culture problem.
I can use this in the the model editor i'm working on !

Model editor? You mean as in a sequel to the wot model editor? Sounds pretty good.
Awesome Terra app you made btw, this is not exactly the same as exploring the maps on your own, but its the next best thing.
## Post #231
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T18:38:51+00:00
- Post Title: Re: World of Tanks Map format.

To move around on the map...

Use the left mouse to change view direction;
To move around the map..
Press and hold SHIFT + Left Mouse Button and drag the mouse.
You can jump to areas on the map by clicking on the MiniMap.

To change the Y camera's position, Press and hold CTR + Left Mouse Button.
Moving the mouse up and down will change the altitude.

Terra! has a number of short cut keys.
1,2,3 and 4 turn on mesh view for Decals, Models, Trees and Terrain in that order.
C turns on chunk outlines.
G turns on Player Grid Lines.
V opens the Texture Viewer. This will let you look all the terrain and model textures.

F2 Orbits the light.
F3 puts the camera in fly mode.

E opens the shader editor.. BE CAREFUL with that.. Changing shaders is not a good idea if you do not know how to program them.
===================================================
On the bottom of the screen there is some information.
FPS .. This only updates when you move the mouse or put the app in fly or light orbit mode.
Terra does NOT update non-stop. Its a waste of power to do so for static imaging.
Location. This is what player grid you are in on the MiniMap.
X,Y and Z is world space in meters
GX and GY are the mesh blocks in each chunk. I used this for debugging more than anything.
If the Terrain is being drawn as a mesh, you will see a RED square around this GX and GY location. Also.. used for debugging.

You can hide EVERYTHING that is in the window.
Got to Settings on the menu bar and UN-Check everything.

Also.. there are buttons one the left of the menu to zoom up and down and hide the MiniMap.

To set up a team layout. Read the Help file.
There are a number of tank models to chose from to build your teams.
Once you have your team setup.. Don't forget to SAVE it!

When you load a Team Setup, Terra will load the map as well.

NOTE:
I am still trying to find out why the main texture is being corrupt.
Some where in those thousands of lines of code, there is something being initialized incorrectly.
## Post #232
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-11T18:52:32+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Portugalotaku
>
> 

Model editor? You mean as in a sequel to the wot model editor? Sounds pretty good.
Awesome Terra app you made btw, this is not exactly the same as exploring the maps on your own, but its the next best thing.
Thank you..
Yes.. It's not a prefect looking but.. you can use Terra to design strategic team setups for Clan Wars.

Yes.. I'm re-writing the WoT Model Editor.
The new formats and games need support.
As it stands now, you can load an entire ship from World of WarShips and export the entire thing as an FBX.
The new version 30.0.9 only works with World of WarShips and you can NOT export in .primitive yet.
This has turned out to be a tremendous amount of work. I actually had to write a 2nd app to digest the gamesparams.data file in order to get all the sub models details for the ships.
If you want to follow the thread from the start to end, here's the link to the forum thread:
[viewtopic.php?f=16&t=12567](http://forum.xentax.com/viewtopic.php?f=16&t=12567)

You can download the latest version here: [http://209.159.152.184:8080/WoW/](http://209.159.152.184:8080/WoW/)

And here is a pic from the app..
## Post #233
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-02-11T19:07:12+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Portugalotaku wrote:

Model editor? You mean as in a sequel to the wot model editor? Sounds pretty good.
Awesome Terra app you made btw, this is not exactly the same as exploring the maps on your own, but its the next best thing.
Thank you..
Yes.. It's not a prefect looking but.. you can use Terra to design strategic team setups for Clan Wars.

Yes.. I'm re-writing the WoT Model Editor.
The new formats and games need support.
As it stands now, you can load an entire ship from World of WarShips and export the entire thing as an FBX.
The new version 30.0.9 only works with World of WarShips and you can NOT export in .primitive yet.
This has turned out to be a tremendous amount of work. I actually had to write a 2nd app to digest the gamesparams.data file in order to get all the sub models details for the ships.
If you want to follow the thread from the start to end, here's the link to the forum thread:
viewtopic.php?f=16&t=12567

You can download the latest version here: http://209.159.152.184:8080/WoW/

And here is a pic from the app..

It's looking great, can't wait for the updates!
## Post #234
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-11T21:21:06+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Mr. Mouse...

I have something else you can try.

The bump shader was missing the version definition line. AMD don't that.

Find this folder....
C:\Program Files (x86)\Coffee_\Terra!\shaders
in there is a file called "bump_vertex.glsl"
It is just a text file with a different suffix. .glsl in stead of .txt
Open it and replace the entire file with the code below.
1st... some short cut keys in case you don't know them.. I'm sure you do. I watched your videos 
CRT+A (select all)
CTR+C (copy)
CTR+V (Paste)
CRT+X (delete and move to clipboard)
//bump_vertex.glsl
// used to render all building and other models

#version 120
varying vec3 rgb;
varying vec3 vVertex;
varying vec3 g_vertexnormal;
varying vec3 g_viewvector;
varying vec3 lightDirection;
varying vec2 TC1;
varying vec2 TC2;
varying vec3 T;
varying vec3 BN;
uniform mat4 ModelMatrix1;

uniform vec3 camPos;

void main(void)
{

    TC1 = gl_MultiTexCoord0.xy;
    TC2 = gl_MultiTexCoord1.xy;

    mat3 ModelMatrix = mat3(ModelMatrix1);
    vec3 T = normalize(ModelMatrix * gl_MultiTexCoord2.xyz);
    vec3 BN = normalize(ModelMatrix * gl_MultiTexCoord3.xyz);

    g_vertexnormal = normalize(ModelMatrix *  gl_Normal);

    vVertex = vec3(ModelMatrix1 * gl_Vertex);

    gl_Position    = ftransform();
    lightDirection = gl_LightSource[0].position.xyz - vVertex;

    g_viewvector = camPos - -vVertex;
    g_viewvector.z *= -1.0;    

    rgb = lightDirection;

}


save the file.
start Terra and see if it renders the buildings.

Let me know OK?

Sadly, no. Doesn't help.
## Post #235
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T02:35:18+00:00
- Post Title: Re: World of Tanks Map format.

I am sorry Mr, Mouse.

I will keep looking for the cause as I work on other things.
You could try setting this to low rez and reloading a map.

I don't think memory is a real problem as no map should even get close to 1 gig of Vmem.
The 7800 series has 2 gig of VDDR5... Its some of the fastest memory on the planet.
It's the same memory my nVidia card uses.

If there is anyone reading this thread that knows the in's and out's of AMD's GLSL and any workarounds, feel free to post info!
I know there is one major issue and... that's not being able to pass Matrices from the vertex stage to the fragment stage.
I fixed that in the shader.. but it still doesn't work. No errors either which is strange.
This may not even have anything to do with the shaders but I don't see how it could load the textures on almost all other systems.
It has nothing to do with the fact I use display list and not VBOs. Every thing I have read has said display lists are a better and usually faster method than VBOs for rendering static meshes. They are for sure less complicated to setup and use.
## Post #236
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T03:45:26+00:00
- Post Title: Re: World of Tanks Map format.

Ok Mr. Mouse...

I did some more reading at a few sites.

I found that my fragment program has a few things AMD cards are known to not like.

1. No direct cast from Int. This means it interrupts 1 the same as 1.0... This could be breaking the If- Then statements. I int(n) around any value that IS an integer.

2. TexCoords.  AMD sometimes fails when you dont include the swizzles st...
Example: 
```
bumpMap.xy = (2.0 * texture2D(normalMap, TC1.st).ag - 1.0);
```

Note the .st after TC1. AMD cards like this to be there.. Nvidia assumes what you want is the UV addresses s and t. Why its s and t and not U and V.. who knows??!!!

Start Terra.. press E and select bump from the drop down at the bottom.
Select the Fragment Program Tab at the top.
Replace all of the existing code with the code below...
Press the Compile button.

It will save the new shader code so this only has to be done once.

Let me know if this works

```
// used to render all building and other models
#version 130
uniform sampler2D normalMap;
uniform sampler2D colorMap;
uniform sampler2D colorMap_2;
uniform int enable_fog;
uniform int is_GAmap;
uniform float l_texture;
uniform float gray_level;
uniform int is_bumped;
uniform int is_multi_textured;
uniform float gamma;
uniform int alphaRef;
uniform int alphaTestEnable;
uniform float ambient;
in vec3 T;
in vec3 BN;
in vec3 g_vertexnormal;
in vec3 g_viewvector;
// camera pos - vertex pos
in vec2 TC1;
in vec2 TC2;
in vec3 vVertex;
in vec3 lightDirection;
in vec4 rgb;
////////////////////////////////////////////////////////////////////////////////////
void main (void)
{
    float invmax = inversesqrt( max( dot(T,T), dot(BN,BN) ));
    mat3 TBN = mat3( T * invmax, BN * invmax, -g_vertexnormal );
    vec3 bump;
    float alpha;
    float harshness = 1.4;
    float boost = 1.5;
    float a;
    vec3 bumpMap;
    // get normal map based on type

    if (is_GAmap == int(1) )
   {
       bumpMap.xy = (2.0 * texture2D(normalMap, TC1.st).ag - 1.0);
        ;
        bumpMap.z = sqrt(1.0 - dot(bumpMap.xy, bumpMap.xy));
        bumpMap.x *= -1.0;
        bumpMap   = normalize(bumpMap);
        harshness = 1.4;
        a         = textureLod(normalMap, TC1.st, int(0)).r;
        if (alphaTestEnable != 0) {
            alpha = 1.0-float(alphaRef/255);
            if (a < alpha) {
                discard;
            }

         }
   }
else
{
    bumpMap = (2.0 * texture2D (normalMap, TC1.st).rgb - 1.0);
        bumpMap.xz *= -1.0;
        bumpMap = normalize(bumpMap);
        a       = textureLod(colorMap, TC1.st, int(0)).a;
        if (a < 0.3) {
            discard;
        }

    }
 

    vec4 color = texture2D(colorMap, TC1.st);
    if (is_multi_textured == int(1) ) {
        vec4 d2 =  texture2D(colorMap_2, TC2.st);
        color *=d2;
        color *= 1.5;
    }

    // debug stuff
    //float ml = 1.0;
    //color = mix(vec4(ambient,ambient,ambient,color.a), color, ml);
    color.xyz *= l_texture;
    vec4 final_color = color * vec4(ambient,ambient,ambient,1.0);
    vec3 N = normalize(g_vertexnormal);
    // Get the perturbed normal
vec3 PN = normalize( TBN * bumpMap );
    // light position
vec3 L = normalize(lightDirection);
    //caclulate lighting


float lambertTerm= max(dot(PN,L) , 0.0);
    float light_diffuse = 0.2;
    if (is_bumped == int(0)) {
        lambertTerm = 0.3;
    }

   final_color += (light_diffuse * max(lambertTerm,0.0)) * color;
    vec3 E = normalize(g_viewvector.xyz);
    vec3 R = normalize(reflect(L, PN));
    float specular = pow( max(dot(R, E), 0.0), 300.0)*0.01;
    final_color +=  specular;
    gl_FragColor.xyz = rgb.xyz;
    gl_FragColor     = final_color *3.0*boost;
    vec3 vG = vec3(harshness , harshness , harshness);
    gl_FragColor.rgb = pow(gl_FragColor.rgb, vG/gamma);
    vec3 co = gl_FragColor.rgb;
    float cl = length(co);
    if (cl == 0.0)
{
        cl = 1.0;
    }

gl_FragColor.rgb = gl_FragColor.rgb / ( (co.rgb/cl) / (1.0-gray_level) )
+ ( gl_FragColor.rgb * gray_level);

//======================================================
//debug junk
//gl_FragColor.rgb =  RGB.rgb;
//======================================================

// FOG calculation
 const float LOG2 = 1.442695;
    float z = gl_FragCoord.z / gl_FragCoord.w;
    float fogFactor = exp2( -gl_Fog.density * gl_Fog.density * z * z * LOG2 );
    fogFactor = clamp(fogFactor, 0.0, 1.0);
    if (enable_fog == int(1) )
{
        gl_FragColor = mix(gl_Fog.color, gl_FragColor, fogFactor );
    }

else
{
        gl_FragColor = gl_FragColor;
    }
}

```
## Post #237
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-12T09:15:37+00:00
- Post Title: Re: World of Tanks Map format.

Doesn't help. Just one single colour. No mapping of any texture. 
Is there a way to just map the texture without any fancy other stuff, just to see if it works? 
Perhaps there should also be some kind of extra debugging implemented at crucial points, just to see what is going wrong at a certain point. 
Is it normal that each time I start I first get some MSI install dialog briefly?
## Post #238
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T15:52:35+00:00
- Post Title: Re: World of Tanks Map format.

Yes... the configuring message is normal.

Ok.. let me write come test code.
1st.. Ill take the shader out and just use the old stuff.

This may sound dumb but press the V key and look at the model textures and see if they have loaded, OK?
## Post #239
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-12T17:37:42+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> Yes... the configuring message is normal.

Ok.. let me write come test code.
1st.. Ill take the shader out and just use the old stuff.

This may sound dumb but press the V key and look at the model textures and see if they have loaded, OK?

Yes, I can see the images of the model textures, so I guess they loaded.
## Post #240
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T17:58:31+00:00
- Post Title: Re: World of Tanks Map format.

Thanks...
I'm looking....
## Post #241
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T18:27:00+00:00
- Post Title: Re: World of Tanks Map format.

For Pete's sake...
I have un-initialized UV mapping.
I can't believe this EVER worked at all!!!

Let me get this fixed and we'll try again.
## Post #242
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-12T19:17:58+00:00
- Post Title: Re: World of Tanks Map format.

Ok...
Try version 28
[http://209.159.152.184:8080/terra/](http://209.159.152.184:8080/terra/)
## Post #243
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-12T22:31:10+00:00
- Post Title: Re: World of Tanks Map format.

I think we need more playtesters here. It doesn't help. I do delete the old version from it's location though, to make sure I do a clean install. Unless you're doing something with the registry, or dll files ? 
I can't imagine why it wouldn't work, since the game also works fine. There must be something fishy going on. 

I'm running on Windows 10, btw. 

Perhaps I can also find another computer to start it on. I tried my Surface Pro, but Terra failed on that, OpenGL error. I've got some more, but I need to get them up and running first. Would help if other people dropped in and tried it.
## Post #244
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-13T05:13:52+00:00
- Post Title: Re: World of Tanks Map format.

I don't get it...
I thought for sure that was the problem.

I also don't think running Windows 10 has anything to do with it. Most everything is rendering correctly.

Did you try unchecking "Bump Map Models"? under the settings--> Graphics?
That will by pass the shader all together.

I don't understand how it can load the trees and their textures and yet the textures not work on the models. We know they are loading.

And yes.. It would help if others that are downloading this (Yes there ARE others) would report any thing strange or.... at least comment on it working or not.
## Post #245
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-13T21:27:17+00:00
- Post Title: Re: World of Tanks Map format.

terra28.jpg (185.67 KiB) Viewed 79 times



That is with Bump map models off. See also that the Watchtower textures for instance seem to load fine.

Also, I notice some hardcoded paths in the .exe like:

```
C:\
C:\Games\World of Tanks

```


My game is not on C, by the way, and I do not have this Textured Sphere path.
## Post #246
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-14T12:23:31+00:00
- Post Title: Re: World of Tanks Map format.

thanks...
I didn't work on this much.

I believe those paths are commented out.
I'll double check.
If they are there is a single quote mark in front of them. This kind --> '

EDIT:
Those are default settings.. File open dialog is one of them... It gets it's path replace in the code to the to WoT root folder when you open a team layout.

This is so strange.

On a good node... I did manage to figure out how to stop the decals from Z-fighting and layer the decals sorta correctly.
## Post #247
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-14T13:15:55+00:00
- Post Title: Re: World of Tanks Map format.

Looking at that image I can tell that the textures are bound but the UVs are not working.
Each model is a different color unless they are the same model like the tanks in the foreground.
This means its picking up a color from the texture map but painting the entire model with it.
## Post #248
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-18T02:47:40+00:00
- Post Title: Re: World of Tanks Map format.

Well...
I added a couple things and fixed the main texture getting screwed up after loading a new map.
I can't figure out why it wont render the models with textures on Mr. Mouse's system.  

I uploaded a new version 29.
Same link as before.. 

Here's a pic for ya.
[lakeville_refections.jpg](https://xentaxbackup.github.io/file/10502_lakeville_refections.jpg)
## Post #249
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-18T17:25:19+00:00
- Post Title: Re: World of Tanks Map format.

I uploaded version 30.
I disabled the ability to select tanks using the mouse center button and forgot to re-enable it after adding back in model selection.

I am going to consider this project complete for now and move back to working on the editor.

If anyone is testing this and has input.. I wanna here it!!!

Thanks..
## Post #250
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-18T17:36:50+00:00
- Post Title: Re: World of Tanks Map format.

Have you tried fetching lights settings from the game? I was searching for any light data but with no luck
## Post #251
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-18T18:51:06+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from SkaceKachna
>
> Have you tried fetching lights settings from the game? I was searching for any light data but with no luck

In the space.settings xml there are these lines:

```
 <skyGradientDome>system/data/sky06_Ensk.xml</skyGradientDome>
 <flora>spaces/06_ensk/flora.xml</flora>

```

TimeOfDay points at the file that contains all the settings regarding the lights color, position and all that.
## Post #252
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-18T19:01:45+00:00
- Post Title: Re: World of Tanks Map format.

I don't use any of that information.
I get the dome model and its texture.
I translate the dome to where ever my camera is and draw it first with depth testing shut off.
There is no need to try to draw the dome so it covers the entire map.

I found that if I rotate the map +90 in the y axis, I get a better match to the game.
This rotation might be in that file I mentioned above. 

If you really wanted to make it exactly like the game, you would need 2 cube maps and the dome.
I believe the cube maps are for PBS but I haven't really looked in to that much.

Oh... and the fog settings are in that file as well.. I also don't use them.
In the game they use volume-metric fog. I don't know how to do that (yet).
## Post #253
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-18T19:15:57+00:00
- Post Title: Re: World of Tanks Map format.

The water texture I use, I found on the internet.
Its a dds and too turquoise so I tent it in the render pass and make it more blue.
[water2.zip](https://xentaxbackup.github.io/file/10504_water2.zip)
## Post #254
- Username: SkaceKachna
- Rank: advanced
- Number of posts: 66
- Joined date: Thu Jan 14, 2016 6:32 pm
- Post datetime: 2016-02-18T19:27:10+00:00
- Post Title: Re: World of Tanks Map format.

Ok, thanks, I already bumped into those files, didn't think it has enought data to generate proper lighting ... I'll have to do some experiments
## Post #255
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-19T14:31:08+00:00
- Post Title: Re: World of Tanks Map format.

No problem..
You might want to look at the horizionShadows in the cdata \terrain2 folders.
It looks to be the shadow map for all static items.
I messed around with it some but never got it working. The sun has to be fixed.
## Post #256
- Username: PureOOP
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 20, 2014 1:28 pm
- Post datetime: 2016-02-20T18:14:01+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> No problem..
You might want to look at the horizionShadows in the cdata \terrain2 folders.
It looks to be the shadow map for all static items.
I messed around with it some but never got it working. The sun has to be fixed.

Dear Coffee, Help !!!!!
I download the newest version of Terra! v30, when I select any map such as "Abby", I will got an exception here as below

```
System.Runtime.InteropServices.ExternalException (0x80004005): A generic error occurred in GDI+.
   at System.Drawing.Image.RotateFlip(RotateFlipType rotateFlipType)
   at Terra.modTerrain.blur_image(Int32& image, String orientatin, Boolean filter)
   at Terra.modOpenGL.get_main_tex_bmp(MemoryStream ms)
   at Terra.modZlib.open_pkg(String name)
   at Terra.frmMain.pb1_MouseDown(Object sender, MouseEventArgs e)
   at System.Windows.Forms.Control.OnMouseDown(MouseEventArgs e)
   at System.Windows.Forms.Control.WmMouseDown(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.18063 built by: FX45RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
Terra
    Assembly Version: 0.1.0.30
    Win32 Version: 0.1.0.30
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Terra.exe
----------------------------------------
Microsoft.VisualBasic
    Assembly Version: 10.0.0.0
    Win32 Version: 11.0.50709.17929 built by: FX45RTMREL
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualBasic.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.34238 built by: FX452RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.17929 built by: FX45RTMREL
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.34251 built by: FX452RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.18021 built by: FX45RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Runtime.Remoting
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.34245 built by: FX452RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.Remoting/v4.0_4.0.0.0__b77a5c561934e089/System.Runtime.Remoting.dll
----------------------------------------
Tao.Platform.Windows
    Assembly Version: 1.0.0.5
    Win32 Version: 1.0.0.5
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Tao.Platform.Windows.DLL
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.18060 built by: FX45RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.34234 built by: FX452RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
Tao.FreeGlut
    Assembly Version: 2.4.0.2
    Win32 Version: 2.4.0.2
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Tao.FreeGlut.DLL
----------------------------------------
Tao.OpenGl
    Assembly Version: 2.1.0.12
    Win32 Version: 2.1.0.12
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Tao.OpenGl.DLL
----------------------------------------
PresentationCore
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.18060 built by: FX45RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_32/PresentationCore/v4.0_4.0.0.0__31bf3856ad364e35/PresentationCore.dll
----------------------------------------
WindowsBase
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.18060 built by: FX45RTMGDR
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/WindowsBase/v4.0_4.0.0.0__31bf3856ad364e35/WindowsBase.dll
----------------------------------------
Tao.DevIl
    Assembly Version: 1.6.8.3
    Win32 Version: 1.6.8.3
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Tao.DevIl.DLL
----------------------------------------
System.Data
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.17929 built by: FX45RTMREL
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_32/System.Data/v4.0_4.0.0.0__b77a5c561934e089/System.Data.dll
----------------------------------------
System.Data.DataSetExtensions
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.17929 built by: FX45RTMREL
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Data.DataSetExtensions/v4.0_4.0.0.0__b77a5c561934e089/System.Data.DataSetExtensions.dll
----------------------------------------
System.Numerics
    Assembly Version: 4.0.0.0
    Win32 Version: 4.0.30319.17929 built by: FX45RTMREL
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Numerics/v4.0_4.0.0.0__b77a5c561934e089/System.Numerics.dll
----------------------------------------
Ionic.Zip
    Assembly Version: 1.9.1.8
    Win32 Version: 1.9.1.8
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Ionic.Zip.DLL
----------------------------------------
Microsoft.mshtml
    Assembly Version: 7.0.3300.0
    Win32 Version: 7.0.3300.0
    CodeBase: file:///C:/Windows/assembly/GAC/Microsoft.mshtml/7.0.3300.0__b03f5f7f11d50a3a/Microsoft.mshtml.dll
----------------------------------------
Pngcs
    Assembly Version: 1.0.96.1
    Win32 Version: 1.0.96.1
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/Pngcs.DLL
----------------------------------------
ICSharpCode.SharpZipLib
    Assembly Version: 0.86.0.518
    Win32 Version: 0.86.0.518
    CodeBase: file:///D:/Program%20Files%20(x86)/Coffee_/Terra!/ICSharpCode.SharpZipLib.DLL
----------------------------------------

************** JIT Debugging **************
```


I run Terra on 64bit Win7 Sp1, is here any problem with my enviorment? Help
## Post #257
- Username: Coffee
- Rank: ultra-veteran
- Number of posts: 518
- Joined date: Fri Aug 07, 2015 12:57 am
- Post datetime: 2016-02-21T11:06:20+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from PureOOP
>
> 
Dear Coffee, Help !!!!!
I download the newest version of Terra! v30, when I select any map such as "Abby", I will got an exception here as below
Code: Select all************** Exception Text **************
System.Runtime.InteropServices.ExternalException (0x80004005): A generic error occurred in GDI+.
   at System.Drawing.Image.RotateFlip(RotateFlipType rotateFlipType)
  

I run Terra on 64bit Win7 Sp1, is here any problem with my enviorment? Help

A Generic GDI+ Error?
How much memory is in your system.
I run Win7 64 bit SP1 on my system too.
I also have 8 gig of ram.
Try changing some of the settings before loading a map.
Check Low quality textures.
Uncheck high quality models.
This should lower the memory usage a lot.

The way video hardware works is like this...
If it can't fit all the graphics (display list, textures and shaders) in to its own memory, it will start swapping items to and from system memory as they are needed.
On my system with Abby loaded with best quality, Task manager is showing Terra as using 415,948k of memory. That's almost 1/2 gig.
It seems like a lot.. but Google Chrome is using around 1/10th of a gig just to load these forums.

Oddly... Terra crashed the first time I loaded Abby but ran fine the second time.
I got NO error message at all.. the window just closed.
This is the first time I have ever seen Terra do this so there probably is a bug some where.
I'll do some digging.
## Post #258
- Username: PureOOP
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 20, 2014 1:28 pm
- Post datetime: 2016-02-24T10:19:19+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Coffee
>
> PureOOP wrote:
Dear Coffee, Help !!!!!
I download the newest version of Terra! v30, when I select any map such as "Abby", I will got an exception here as below
Code: Select all************** Exception Text **************
System.Runtime.InteropServices.ExternalException (0x80004005): A generic error occurred in GDI+.
   at System.Drawing.Image.RotateFlip(RotateFlipType rotateFlipType)
  

I run Terra on 64bit Win7 Sp1, is here any problem with my enviorment? Help

A Generic GDI+ Error?
How much memory is in your system.
I run Win7 64 bit SP1 on my system too.
I also have 8 gig of ram.
Try changing some of the settings before loading a map.
Check Low quality textures.
Uncheck high quality models.
This should lower the memory usage a lot.

The way video hardware works is like this...
If it can't fit all the graphics (display list, textures and shaders) in to its own memory, it will start swapping items to and from system memory as they are needed.
On my system with Abby loaded with best quality, Task manager is showing Terra as using 415,948k of memory. That's almost 1/2 gig.
It seems like a lot.. but Google Chrome is using around 1/10th of a gig just to load these forums.

Oddly... Terra crashed the first time I loaded Abby but ran fine the second time.
I got NO error message at all.. the window just closed.
This is the first time I have ever seen Terra do this so there probably is a bug some where.
I'll do some digging.

Dear Coffee, Is here any way to export this map into 3dmax? We all looking forward it.
## Post #259
- Username: Kalith
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 04, 2016 12:40 am
- Post datetime: 2016-04-04T11:01:56+00:00
- Post Title: Re: World of Tanks Map format.

I can't really get this to work. It starts, but whenever I try to load a map I get this error.

```
System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at Terra.Mod_Space_Bin_Functions.get_BWSG_data(Int32 t_cnt)
   at Terra.Mod_space_bin.get_spaceBin_data(Byte[] spaceBindata)
   at Terra.modZlib.open_pkg(String name)
   at Terra.frmMain.pb1_MouseDown(Object sender, MouseEventArgs e)
   at System.Windows.Forms.Control.OnMouseDown(MouseEventArgs e)
   at System.Windows.Forms.Control.WmMouseDown(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)

```


This is on windows 10 pro x64, gtx 570.
## Post #260
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2016-11-09T07:30:46+00:00
- Post Title: Re: World of Tanks Map format.

> Reply from Kalith
>
> I can't really get this to work. It starts, but whenever I try to load a map I get this error.
Code: Select all************** Exception Text **************
System.IndexOutOfRangeException: Index was outside the bounds of the array.

I have this error too. On windows 7, radeon 5850.

Please, help somebody.
## Post #261
- Username: ShadowHunterRUS
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 13, 2016 6:04 pm
- Post datetime: 2017-04-09T18:13:10+00:00
- Post Title: Re: World of Tanks Map format.

Just gonna leave this here...
[https://bitbucket.org/SkepticalFox/wot-space.bin-utils/](https://bitbucket.org/SkepticalFox/wot-space.bin-utils/)
