## Post #1
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2020-03-21T05:24:50+00:00
- Post Title: Doom Eternal *.resources unpacker

Made a simple command-line unpacker for Doom Eternal *.resources game archives.

Usage:  
```
DoomEX.exe path_to_resources_file output_folder
```


Tool: 

 DoomEX.zip
(17.32 KiB) Downloaded 178 times



Github: [https://github.com/iOrange/DoomEX](https://github.com/iOrange/DoomEX)
## Post #2
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-21T13:50:26+00:00
- Post Title: Doom Eternal *.resources unpacker

Awesome! Will you add support for eternal to your doom resources explorer?

What's the best way to convert the meshes to a "usable" format right now? I'd love to 3d print the main menu podest and the doom slayer on it
## Post #3
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2020-03-21T13:59:15+00:00
- Post Title: Doom Eternal *.resources unpacker

Nice work! A friend also got QuickBMS working with it too: [https://zenhax.com/viewtopic.php?p=54753#p54753](https://zenhax.com/viewtopic.php?p=54753#p54753)
(also posted some info about working with the games string files there, if anyone wants to work on translations)

Any idea how hard it'd be to make a repacker for this?
I know DOOMExtract could repack 2016's files but this new IDCL format seems a lot different, maybe more needs to be figured out first before that can be done...

E: BTW it looks like your tool doesn't handle any decompression? I saw that QuickBMS had support for Oodle decompressing, maybe worth looking into adding that too? (unless the game doesn't even use it, that is...)
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-21T14:12:03+00:00
- Post Title: Doom Eternal *.resources unpacker

Nice work but it doesn't decompress files. Or Am I wrong?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2020-03-21T20:14:16+00:00
- Post Title: Doom Eternal *.resources unpacker

Hmm any idea for the .pck .snd files.
## Post #6
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2020-03-21T23:23:03+00:00
- Post Title: Doom Eternal *.resources unpacker

> Reply from infogram ↑Sat Mar 21, 2020 9:59 pm at Sat Mar 21, 2020 9:59 pm
>
> 
E: BTW it looks like your tool doesn't handle any decompression? I saw that QuickBMS had support for Oodle decompressing, maybe worth looking into adding that too? (unless the game doesn't even use it, that is...)

Unfortunately the game is using Oodle for compression, and Oodle SDK is non-free, so I'm not quite sure how to handle this property.

My next step is to make a converter for textures and models
## Post #7
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2020-03-22T01:13:44+00:00
- Post Title: Doom Eternal *.resources unpacker

Ok, so I added decompression. Just copy "oo2core_8_win64.dll" from Doom Eternal folder to DoomEX folder and run as usual.

Download: 

 DoomEX_v02.zip
(18.05 KiB) Downloaded 164 times



Source code: [https://github.com/iOrange/DoomEX](https://github.com/iOrange/DoomEX)
## Post #8
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-22T08:40:35+00:00
- Post Title: Doom Eternal *.resources unpacker

Decompression seems to work but i couldn't get any of the lightwave models to load in open 3d model viewer and the textures are in BIM format, whatever that is
## Post #9
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2020-03-22T10:14:43+00:00
- Post Title: Doom Eternal *.resources unpacker

> Reply from iOrange ↑Sun Mar 22, 2020 9:13 am at Sun Mar 22, 2020 9:13 am
>
> 
Ok, so I added decompression. Just copy "oo2core_8_win64.dll" from Doom Eternal folder to DoomEX folder and run as usual.

Download: DoomEX_v02.zip

Source code: https://github.com/iOrange/DoomEX

Cool, thanks!
This new IDCL format looks crazy, got no idea how a repacker could be made for this, so many unknowns >.>
Maybe someone will figure out a way to let it load loose files instead of needing to pack, would save a lot of time.

> Reply from Ize ↑Sun Mar 22, 2020 4:40 pm at Sun Mar 22, 2020 4:40 pm
>
> 
Decompression seems to work but i couldn't get any of the lightwave models to load in open 3d model viewer and the textures are in BIM format, whatever that is
I think DOOM 2016 used bimage files for some textures (not all since a lot were mega-texture crap), I guess maybe BIM is the same thing, pretty sure I saw some work on bimage files being posted before.
## Post #10
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-22T11:32:47+00:00
- Post Title: Doom Eternal *.resources unpacker

BIM seems to be almost same as MIB struct but in LittleEndian. But i saw that there is only header but no raw data at least at fonts. Looks like they are most probably in *.streamdb. But no clue where are offsets for them.

EDiT:Also seems like resources are somehow protected against editing. I tried edit plain text from false; to true; 
and left same size of text and game refuse to start. On second run steam re-download whole resources.

EDiT1: Uff streamdb luckily are not protected. I cut half of last streamdb archive and game loads fine. And it was obvious on first look. Missing textures. So there will be fonts textures.

EDiT2: OK I finally find location of font textures if anyone interested. In: gameresources_0_1.streamdb. Now I must find right raw data. I think some clues should be in BIM headers.
## Post #11
- Username: CharlieV
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Dec 30, 2019 5:29 pm
- Post datetime: 2020-03-22T11:36:27+00:00
- Post Title: Doom Eternal *.resources unpacker

Maybe it's just over my head but when I used it all that was extracted were <20kb files referencing the real files in the gameresources .streamdb archives. The tool for Doom 2016 was a great help to me a few weeks ago, but it seems the Wolfenstein games have been a lot of trouble and this will be closer to those, I'm in no rush I'll just be glad to see something comprehensive made for this eventually too no matter how long it may take
## Post #12
- Username: ArtyDoesStuff
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 15, 2019 12:41 am
- Post datetime: 2020-03-22T20:03:27+00:00
- Post Title: Doom Eternal *.resources unpacker

Wow, the unpacker works like a charm! Thanks for that. 

How's the research on texture/model conversion coming, also? I've looked through the unpacked files, and they're all in such strange formats. BITEXTURE, .entities, etc. It looks like It's going to be quite hard getting them ready to extract, though I don't think it's that much different than 2016 except that Mega Textures aren't a thing anymore. But that's just my thoughts, I could be wrong, but it's something to look into.
## Post #13
- Username: infogram
- Rank: n00b
- Number of posts: 19
- Joined date: Sat May 28, 2016 10:55 am
- Post datetime: 2020-03-23T02:05:20+00:00
- Post Title: Doom Eternal *.resources unpacker

> Reply from GRiNDERKILLER ↑Sun Mar 22, 2020 7:32 pm at Sun Mar 22, 2020 7:32 pm
>
> 
EDiT:Also seems like resources are somehow protected against editing. I tried edit plain text from false; to true; 
and left same size of text and game refuse to start. On second run steam re-download whole resources.

Hmm, I did see some mention of hashes in the code that handles the IDCLs, maybe one of the unknown tables contains hashes/signatures. 
I did see some table which had way more entries than the number of files, this could maybe be hashes of blocks inside the files, (no idea what the block-size or anything might be tho), but pretty sure I saw some string mentioning data-blocks anyway.

I saw WolfstoneExtract also has IDCL format pretty detailed too, not sure if it includes much more info than we already know about, but it does handle both version 11 and version 12 IDCLs though: [https://bitbucket.org/ecwolf/wolfstonee ... e_idcl.cpp](https://bitbucket.org/ecwolf/wolfstoneextract/src/master/src/file_idcl.cpp)

(Also kinda off-topic but I decided to try figuring out what all those Oodle unknowns are, but then I found this project which is a pretty detailed disassembly: [https://github.com/powzix/ooz](https://github.com/powzix/ooz)
The kraken.cpp also has prototypes for the Oodle DLL exports (OodleLZ_Decompress / OodleLZ_Compress), which are a lot more complete than any other description I could find on the net:

```
  int codec, uint8 *src_buf, size_t src_len, uint8 *dst_buf, int level,
  void *opts, size_t offs, size_t unused, void *scratch, size_t scratch_size);
  
typedef int WINAPI OodLZ_DecompressFunc(
  uint8 *src_buf, int src_len, uint8 *dst, size_t dst_size, int fuzz,
  int crc, int verbose, uint8 *dst_base, size_t e, void *cb, void *cb_ctx, 
  void *scratch, size_t scratch_size, int threadPhase);

```

Hopefully this'll show up on google if anyone tries looking for them, took me a bit of digging to find, big thanks to powzix of course)
## Post #14
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-23T16:37:18+00:00
- Post Title: Doom Eternal *.resources unpacker

I did some research on BIM so here is what i got so far. Alot of unk flags and skiped some bytes. But it should parse all BIM header.
local int i;

int64 id;
int mipmapflag;
int mainwidth;
int mainheigth;
int null;
int mipmapcount;
int64 null;
byte flag;
int flag;
int compchar; 
int flag;
FSkip(6);
short flag;
short flag;
short flag;
short flag;

for(i=0;i<mipmapcount;i++) {

struct {
    int64 mipnum;
    int width;
    int heigth;
    int flag;
    int mipmaplayersize;
    int flag;
    int64 id; //or something
    } mipmap;
};
## Post #15
- Username: exhaleme
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 10, 2017 10:59 am
- Post datetime: 2020-03-23T18:16:23+00:00
- Post Title: Doom Eternal *.resources unpacker

It seems porter and id-daemon have already figured everyhing out

[https://twitter.com/dtzxporter/status/1 ... 1874179078](https://twitter.com/dtzxporter/status/1241844471874179078)
[https://twitter.com/dtzxporter/status/1 ... 0879270913](https://twitter.com/dtzxporter/status/1242095730879270913)
## Post #16
- Username: iOrange
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2016 10:56 pm
- Post datetime: 2020-03-24T21:07:00+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

> Reply from exhaleme ↑Tue Mar 24, 2020 2:16 am at Tue Mar 24, 2020 2:16 am
>
> 
It seems porter and id-daemon have already figured everyhing out

That's good news, I can get back to Metro now
## Post #17
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2020-03-25T13:53:43+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

hmmm is there any step by step how to extract the gameresources files? i seems don't understand about the previous reply... i have try paste oo2core_2_win64.dll to Doom EX folder. but it still failed (i have drag the file into DoomEX.exe program, i have launch the DoomEX,exe and nothing happen) how can i extract the model from that file?
## Post #18
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-25T14:02:33+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

It's a command line tool. Drag & drop doesn't work. Create bat file and put in it: DoomEX.exe gameresources.resources _unpacked
*.resources and bat file must to be next to the unpacker exe.
## Post #19
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-25T14:06:08+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

> Reply from RuV9999 ↑Wed Mar 25, 2020 9:53 pm at Wed Mar 25, 2020 9:53 pm
>
> 
hmmm is there any step by step how to extract the gameresources files?

I would wait till [https://twitter.com/dtzxporter](https://twitter.com/dtzxporter) releases VEGA since the currently available tools aren't that helpfull if you want to get the models / textures since they are mostly in the streaming files.

I guess in a few days he'll release the first version (hopefully)
## Post #20
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-25T15:51:51+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Just figured out that streamdb has it's own table. I was really blind before...
## Post #21
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-27T15:34:54+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

DTZxPorter has released his exporter / browser VEGA if anyone is still interested: [https://wiki.modme.co/wiki/apps/Vega.html](https://wiki.modme.co/wiki/apps/Vega.html)
## Post #22
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2020-03-27T16:32:46+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Is anyone else experiancing constant crashing when exporting models using DTZxPorter's Vega?
Can't for the life of me export a single model :/
## Post #23
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-27T17:58:39+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

I have exported the standart podium (stone) and printed it successfully (in tiny size for testing), the doomslayer also exported fine.
EDIT: OH... did you copy the oodle dll from doom eternal? else it won't work
## Post #24
- Username: drsmellio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 06, 2017 5:18 am
- Post datetime: 2020-03-27T19:39:38+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

anyone else having a problem with windows defender eating the download due to trojan alert?
## Post #25
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2020-03-28T03:33:42+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

i have extract the files. im getting struggling in model part. the model have .SEMODEL extension i have try both maya/blender plugin for SEtool by DTZXporter in my blender 2.82 and noesis both but none of them are detect/succsess convert it. anyone know how to solve it?

[EDIT] i didn't saw the require is Blender 2.79 i'll try later
## Post #26
- Username: Ize
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 21, 2020 9:47 pm
- Post datetime: 2020-03-28T08:15:46+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

You can also click the settings button and change the model and texture format to fbx for example
## Post #27
- Username: FinalAssault
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 28, 2020 10:09 pm
- Post datetime: 2020-03-28T14:11:25+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

> Reply from iOrange ↑Sat Mar 21, 2020 1:24 pm at Sat Mar 21, 2020 1:24 pm
>
> 
Github: https://github.com/iOrange/DoomEX
hmm, seems like that project was deleted...
## Post #28
- Username: CaptainDumac
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 31, 2020 6:18 am
- Post datetime: 2020-03-30T23:02:34+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

> Reply from GRiNDERKILLER ↑Sun Mar 22, 2020 7:32 pm at Sun Mar 22, 2020 7:32 pm
>
> 
OK I finally find location of font textures if anyone interested. In: gameresources_0_1.streamdb. Now I must find right raw data. I think some clues should be in BIM headers.

Have you managed to extract the font files yet? They're the main resource I've been looking for
## Post #29
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-03-31T08:20:15+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

No luck so far. I can't get nothing usable from that table i find in streamdb. Mostly files are under Oodle compression. And i can't find any expected decompressed size.

I think we should ask the aluigi.

No I found them! all in first streamdb.

```
-------------------------------------------------------------------------------
courier					52154352		150443
dfpop1w5b5				52304800		3760250
dfpop2w9gb				56065056		4313577
dfpop3w12b5				60378640		4251606
dfpop3w12gb				64630256		3923441
eternal_bold				68553712		119038
eternal_bold_jp				68672752		2181137
eternal_numeral_regular			70853904		26991
eternal_regular				70880896		188160
eternal_regular_jp			71069056		2031504
eurostileconreg_mip			73100560		119882
eurostileconreg				73220448		119882
idtactical_regular			73340336		81186
koreansnmm				73421536		1026568
koreantkl				74448112		667678
tt_supermolot_mip			75115792		145946
tt_supermolot				75261744		145946
```
## Post #30
- Username: FinalAssault
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 28, 2020 10:09 pm
- Post datetime: 2020-04-01T13:35:15+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

> Reply from OrangeC ↑Sun Mar 22, 2020 4:14 am at Sun Mar 22, 2020 4:14 am
>
> 
Hmm any idea for the .pck .snd files.
[https://www.reddit.com/r/Doom/comments/ ... m_eternal/](https://www.reddit.com/r/Doom/comments/fn1ra7/guide_extracting_all_the_music_from_doom_eternal/)
## Post #31
- Username: Knightmare077
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 02, 2020 4:21 am
- Post datetime: 2020-04-01T20:25:49+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Any way to repack .rescourse files?
## Post #32
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2020-06-15T23:44:42+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

do you guys know why the specular and normal texture are white after extracting?
## Post #33
- Username: CharlieV
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Dec 30, 2019 5:29 pm
- Post datetime: 2020-07-11T06:54:49+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

I haven't had any issues with textures but I wonder if there will be any further updates. Some of the static models are completely broken when exported no matter which file type they are exported as such as throne_room_kingthrone_a_LOD0 for example.
## Post #34
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2020-07-28T23:32:47+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Yes, static models have bad uv, hope it get updated
## Post #35
- Username: bsaka2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Oct 21, 2020 2:47 pm
- Post datetime: 2020-11-28T10:52:14+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

wow, It's complicated, I like mechanical hell
## Post #36
- Username: vatefaireneculer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 11, 2021 9:12 am
- Post datetime: 2021-01-11T14:19:15+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Hello everybody, does anybody have the actual source code of the extractor? The link to github is dead
## Post #37
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2021-02-12T20:19:22+00:00
- Post Title: Re: Doom Eternal *.resources unpacker

Any update guys ?
