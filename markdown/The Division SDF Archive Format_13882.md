## Post #1
- Username: sgtfrankieboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 26, 2016 9:11 am
- Post datetime: 2016-01-26T11:51:26+00:00
- Post Title: The Division SDF Archive Format

The Division beta is coming up and I've been looking around the archive format. This is what I've
discovered at the moment. I'm still looking into it but I'm not very skilled with figuring out 
archive formats. 

There are three types of files in the data folder.

SDFVER

sdfver files are text based files. They contain a numeric key value pair separated by spaces.
Each pair is for a different section in the sdfdata files (0 = A, 1 = B, 2 = C, etc.)
The key and value are separated by a colon. Each value consists of 5 numbers divided by a space.

Currently do not know what the numbers mean, I think it has something to do patching / version info.

SDFTOC

sdftoc files are binary based files with the header magic of "WEST". All sdftoc files have a separator(?).
The separator starts with "massive " and end with "ubisoft " (spaces being 0x00) in between there are 20
random characters, this separator is repeated multiple times in a file, and is always at the beginning
of the file at offset 0x1C and at the very end of the file.

Looking at the name I'm assuming the sdftoc files are Table of Content files, the actual content isn't
readable directly.

SDFDATA

sdfdata files are also in a binary format and have the header magic of "BERG". They have the same separator
as sdftoc files but starting separator is at offset 0x08 and also end with it.

I have come across sdfdata files that have plain text in them and bnk files.

A lot of the sdfdata files only contain the word "dummy".

Other Observations

Looking at the data folders, there are two "sdf" and "sdf_streaming". 

The sdf folder contains most of the game data and is about 27GB in size for the PC Beta.
In the folder is a single sdftoc and sdfver file both named "sdf". There are 2700 sdfdata files.
Named "sdf-{0}-{1}.sdfdata". {0} = A, B, or C each section is 1000 files large. {1} = 0000-2699

The sdf_streaming data contains a folder for nyc_manhatten with a lot 
of tile folders and a global folder each of these folders contain a data folder with the previous metioned
sdf data structure. There is also a "tileconfig.txt" file which contains a JSON like structure with the following 
properties "hasGlobal", "tileSize", and "tiles" which is an array with three numeric values per item.

I have a high feeling this data structure is meant to be mounted similar to a hard drive.
## Post #2
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-02-03T13:31:23+00:00
- Post Title: The Division SDF Archive Format

Anything new on this?
## Post #3
- Username: bulihack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 04, 2016 5:06 am
- Post datetime: 2016-02-03T22:01:35+00:00
- Post Title: The Division SDF Archive Format

I hope i can extend the great and investigative post of sgtfrankieboy  with some further notes.

My primary interest in this content was the audio/music so i did experiments with the resources as focusing on this particular type of content. 
About 260+ of the sdfdata resource files seems to contain both Audiokinetic Wwise RIFF Vorbis and  [Wwise_SoundBank](http://wiki.xentax.com/index.php/Wwise_SoundBank_%28*.bnk%29) files as embedded content.

The wwise audio files with RIFF/Wave headers easy enough to split out into individual files using regular splitter tools with header management (vgmtoolbox did a great job on this). The wave headers were "usual" and a very few of them length were illegal causing the splitter to extract multiple wave headers into one file (this only a few files, compared to the some*10k audio files it found and saved properly). Extracting the actual bnk files and using bnkextr might help to get the individual files properly - not tested so far. 

Regardless, the ww2ogg has done a nice job using the --pcb packed_codebooks_aoTuV_603.bin switch, then revorbto do the polishing jobs. The ogg files are coming in mono/stereo/surround with VBR and 48khz sample rate. 

The music content is just perfect for my taste i made up some playlists for personal joy. All the music is in stereo format, i found no evidence of 5.1 version of any of them. Ambiences are mostly 6 channel ogg files, but stereo and mono are happens sometimes too. Looped music content is very usual, that most likely helps the cinematic experience in the gameplay for sure.

Fun-facts, that some of the dialogues (which was never actually the part of the beta gameplay) are already "here" (spoiler alert heh), and a few lines are text-to-read voice recoded for now. I also found one particular speech line that exists both t2r and real voice actor versions, which (i'm speculate to) all indicates the packages maybe not entirely polished or simply rolling forward without cleaning old/unused content, and no replace will occure in later patches either. However, about 25% of the contents are happens to be binary-duplicates (sometimes more than one duplicate in different sdfdata files) and sometimes alternative versions of a given content (music/speech etc) also occures, that strengthens my suspicions about the largely unpolished packages, and may result in duplicates in other contents (3d models, textures etc) too as well. Such a waste of hdd space.

As a side note, the extracted ogg audio files were always complete and i did not hit missing file ends, which indicates (the high possibility of) that the sdfdata files are always complete. This of course doesn't goes against that any/all of the sdfdata contents would be part of a huge virtual disk file. I also speculate that the sdf_streaming data will most likely be (as the folder structure also indicates) the sliced up open-world model w/o the textures, which helps the snowdrop engine to organize and stream in/out far-parts of the environment with the given lod requirements.

I wish the bests for anyone up to the challenge to decyphering the resource format, and i sure hope this bit of information will also prove to be useful in the process.
## Post #4
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2016-02-04T18:27:54+00:00
- Post Title: The Division SDF Archive Format

This page here[http://zenhax.com/viewtopic.php?t=2072](http://zenhax.com/viewtopic.php?t=2072) details how to dump everything from the archives,
But that method produces thousands and thousands of unnamed files which makes finding anything specific pretty hard.

Good news is it seems everything is pretty much regular formats, xml, lua, .dat, dds, and the raw shader sources are there aswell.

If someone could make a tool that dumps everything with the correct folder structure and filenames... that would be great!
## Post #5
- Username: bulihack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 04, 2016 5:06 am
- Post datetime: 2016-02-05T06:23:09+00:00
- Post Title: The Division SDF Archive Format

offzip does indeed extract some content but it's a hit and miss. ran trhu a few audio filled sdfdata files but all i got was junk instead of wem/bnk. this is actually the expected result since it indicates that some parts are zip'ed while others are uncompressed data streams.

i also have tested the sdf/../sdf.sdftoc file with the offzip tool and it quickly revealed that the table of contents is actually there in a ziped format, but the unpack had a broken result, where only partial filenames can be human-readed in the output stream. this indicates that either the ziped stream is malformed, the offzip is broken, the inflated/deflated stream is encrypted or the zip algorithm is altered which makes it harder to get the proper index file out of the stream. Anyway, this index file seems to contain all filenames embeded in the /sdf file resource files which have to be used to recreate the folder structure. the same applies to the .sdftoc files in the sdf_streaming folders too.
## Post #6
- Username: wantoosree
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 22, 2016 3:04 pm
- Post datetime: 2016-02-22T07:11:34+00:00
- Post Title: The Division SDF Archive Format

Has anyone made any progress on recreating the file structures? I've matched a few files up based on their association with other files, but thats about it.

I've also been unable to find extract the image data, both the pngs and the sprite sheets. This is my first time working with offzip so I don't know whether or not it outputs png from the extracted data but none of the files were extracted as png. I also haven't been able to identify any by the file signature.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-22T13:02:10+00:00
- Post Title: The Division SDF Archive Format

I took a look at the SDF format a while ago. It is pretty complex at the moment. Right now, the TOC files need to be decrypted, that's most likely why nobody has written an unpacker because the TOC seems to be obfuscated/encrypted.
## Post #8
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-02-25T21:38:18+00:00
- Post Title: The Division SDF Archive Format

There's no encryption/obfuscation going on in the TOC file.
## Post #9
- Username: mrcatzaa
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-25T21:43:39+00:00
- Post Title: The Division SDF Archive Format

> Reply from Sir Kane
>
> There's no encryption/obfuscation going on in the TOC file.

Then what's this block of data?
## Post #10
- Username: Scrapz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 27, 2016 9:40 am
- Post datetime: 2016-02-27T01:44:04+00:00
- Post Title: The Division SDF Archive Format

offzip takes care of that
## Post #11
- Username: mrcatzaa
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-27T02:23:25+00:00
- Post Title: The Division SDF Archive Format

> Reply from Scrapz
>
> offzip takes care of that

Actually, no it doesn't because that block I highlighted is NOT zlib compressed data.  

The problem here is figuring out how to extract files properly without offzip. It's an interesting file format, I've not seen one like this yet. But I'm fairly certain some information is missing in order to unpack the files properly like the offsets and sizes of the data.
## Post #12
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-02-27T15:38:21+00:00
- Post Title: The Division SDF Archive Format

Names, offsets, sdfdata indices and all that are in the TOC file's zlib compressed chunk. That 0x140 bytes block is probably some signature or something like that.
## Post #13
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2016-03-02T19:12:47+00:00
- Post Title: The Division SDF Archive Format

> Reply from Sir Kane
>
> Names, offsets, sdfdata indices and all that are in the TOC file's zlib compressed chunk. That 0x140 bytes block is probably some signature or something like that.

I wasn't able to get clean enough data to determine that, unless I am not viewing it properly... I used offzip to unzip the sdftoc. Then I opened the single dat file with HxD to view it. I see patterns, but also see data that looks fragmented. Maybe HxD isn't the best viewer for the content.

Example pattern:

```
 ®..1'.—.=ã..C......eventtemplate.mmissionB.
 ®..1å.š.Ôä..C.....uO-£..o_verticalslice_sÿ,£.p ,£.cw,£..bar.mmissionB. 

```
## Post #14
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2016-03-02T21:59:15+00:00
- Post Title: The Division SDF Archive Format

After a little more digging, it appears that there is a more specific pattern at play.

In hex:

```

```


The 42 is what generates the ASCII 'B' at the end of every visible path. 1E is technically considered a Record Separator. Since AE and 1E are always paired, I am assuming that they symbolize the termination of a record.

So a regex pattern for a record match with two sub matches might be:

```

```
## Post #15
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2016-03-08T13:04:25+00:00
- Post Title: The Division SDF Archive Format


## Post #16
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-03-21T17:26:31+00:00
- Post Title: Re: The Division SDF Archive Format

Compressed data block represents binary search tree (for strings), with files in leaves.
sdftoc file has folowing structure:

```
{
    int32 tag;
    int32 ver;
    int32 decomp_size;
    int32 comp_size;
    int32 zero; //??
    int32 block1count;
    int32 block2count;
}
struct ddsblock
{   
    int32 used_bytes;
    byte data[0x94];
}
struct sdf_id
{
    int64 ubisoft;
    int8 data[0x20];
    int64 massive;
};
struct sdftoc_file
{
    header h;
    sdf_id id;
    byte flag1;
    if flag1
    {
        byte unk[0x140]; //signature??
    }
    int32 block1_1[header.block1count];
    sdf_id block1_2[header.block1count];

    ddsblock block2_1[header.block2count];
    byte zlib_bst[header.comp_size]
    sdf_id id_;
}

```

See attachment for extraction tool.
[rouge_sdf.zip](https://xentaxbackup.github.io/file/10619_rouge_sdf.zip)
## Post #17
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-03-21T18:48:57+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from redspike474
>
> 50$ for the first person who makes a tool that works!
If I were you, I wouldn't give money for someone who develops said tool. Just saying.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-22T08:41:49+00:00
- Post Title: Re: The Division SDF Archive Format

is it worth to deal with? Since the offzip-created 3ds meshes seem to be "fragmented", too:



0000e649_3ds_2SM.jpg (87.11 KiB) Viewed 1390 times
## Post #19
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-03-22T12:31:59+00:00
- Post Title: Re: The Division SDF Archive Format

What's that supposed to be?
## Post #20
- Username: mrcatzaa
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-22T13:50:25+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from shakotay2
>
> is it worth to deal with? Since the offzip-created 3ds meshes seem to be "fragmented", too:
0000e649_3ds_2SM.jpg

There shouldn't be anything wrong with the meshes, they look fine to me. They're split into small chunks so you'll have to load them all.
## Post #21
- Username: j0r
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 23, 2016 1:47 am
- Post datetime: 2016-03-22T18:22:12+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> Compressed data block represents binary search tree (for strings), with files in leaves.
sdftoc file has folowing structure:
Code: Select allstruct header
{
    int32 tag;
    int32 ver;
    int32 decomp_size;
    int32 comp_size;
    int32 zero; //??
    int32 block1count;
    int32 block2count;
}
struct ddsblock
{   
    int32 used_bytes;
    byte data[0x94];
}
struct sdf_id
{
    int64 ubisoft;
    int8 data[0x20];
    int64 massive;
};
struct sdftoc_file
{
    header h;
    sdf_id id;
    byte flag1;
    if flag1
    {
        byte unk[0x140]; //signature??
    }
    int32 block1_1[header.block1count];
    sdf_id block1_2[header.block1count];

    ddsblock block2_1[header.block2count];
    byte zlib_bst[header.comp_size]
    sdf_id id_;
}

See attachment for extraction tool.

if i edit a file like change language.. how compress again in original file?
## Post #22
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2016-03-23T21:44:06+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> Compressed data block represents binary search tree (for strings), with files in leaves.
sdftoc file has folowing structure:
Code: Select allstruct header
{
    int32 tag;
    int32 ver;
    int32 decomp_size;
    int32 comp_size;
    int32 zero; //??
    int32 block1count;
    int32 block2count;
}
struct ddsblock
{   
    int32 used_bytes;
    byte data[0x94];
}
struct sdf_id
{
    int64 ubisoft;
    int8 data[0x20];
    int64 massive;
};
struct sdftoc_file
{
    header h;
    sdf_id id;
    byte flag1;
    if flag1
    {
        byte unk[0x140]; //signature??
    }
    int32 block1_1[header.block1count];
    sdf_id block1_2[header.block1count];

    ddsblock block2_1[header.block2count];
    byte zlib_bst[header.comp_size]
    sdf_id id_;
}

See attachment for extraction tool.

I am assuming this is C++? Could you share your exe's entire source, I am curious to understand how the algorithm works. Also, thank you very much!
## Post #23
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-03-29T05:08:30+00:00
- Post Title: Re: The Division SDF Archive Format

Suspicious.Cloud.Gen!c
HEUR/QVM10.1.0000.Malware.Gen
Suspicious.Cloud.5

virus scan on that file is going off. why?
## Post #24
- Username: marked
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 17, 2015 11:37 pm
- Post datetime: 2016-03-30T21:38:35+00:00
- Post Title: Re: The Division SDF Archive Format

Edit: Solved my problem.
## Post #25
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-04-03T04:56:46+00:00
- Post Title: Re: The Division SDF Archive Format

I have a problem with the extractor posted by m0xf.
some textures are incomplete. 



( the black part in a hex editor are 00's)

I used the extractor in the beta and final versions of the game, but the problem with textures is present in exactly the same files regardless of the version of the game.
for example, the texture "cn_jtf_pops_head_n.dds" in the path rogue\baked\art\[characters]\[npc]\[jtf]\cn_jtf_pops is incomplete in the beta and final version using the corresponding sdf.sdftoc.
Can someone bypass this problem?
## Post #26
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-04-03T08:48:53+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from luxox18
>
> 
some textures are incomplete.
It's my bug. Try new version of extractor.
[rouge_sdf_2.zip](https://xentaxbackup.github.io/file/10722_rouge_sdf_2.zip)
## Post #27
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-04-03T10:05:17+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> 
It's my bug. Try new version of extractor.

Perfect! thanks a lot!
## Post #28
- Username: Sefer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 03, 2016 7:31 pm
- Post datetime: 2016-04-03T12:20:24+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> luxox18 wrote:
some textures are incomplete. 

It's my bug. Try new version of extractor.

Is it somehow possible to extract the map from the files? Which tool do I need to view the files?

EDIT: and how to use your tool?
EDIT2: nvm, know how to extract 
EDIT3: Maybe someone is able to rebuild the ingame map. A lot of ppl would love to get hand on it since all available are stitched screenshots
## Post #29
- Username: Tw0F1sh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 04, 2016 2:30 am
- Post datetime: 2016-04-03T19:18:50+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Sefer
>
> 
EDIT: and how to use your tool?
EDIT2: nvm, know how to extract 
EDIT3: Maybe someone is able to rebuild the ingame map. A lot of ppl would love to get hand on it since all available are stitched screenshots

-> Open CMD
-> cd to roug_sdf.exe
-> type rouge_sdf.exe <.sdftoc path> <output directory>
-> Press Enter
-> Done
## Post #30
- Username: kaffeblask
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 29, 2016 7:01 pm
- Post datetime: 2016-04-04T09:11:36+00:00
- Post Title: Re: The Division SDF Archive Format

Hi

Not a programmer, to be onoest im more of a interested hobbyist on modding. i can parse out all the files using the rouge extractor but how do i find the art, textures, all i find is the mphys files and mmb files. I dont know how to find the art files like DDS or the 3D files.

i really do appreciate the knowledge of people here. Hopefully someone can give me a poke to right direction


//cheers
## Post #31
- Username: kaffeblask
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-04T09:32:25+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from kaffeblask
>
> Hi

Not a programmer, to be onoest im more of a interested hobbyist on modding. i can parse out all the files using the rouge extractor but how do i find the art, textures, all i find is the mphys files and mmb files. I dont know how to find the art files like DDS or the 3D files.

i really do appreciate the knowledge of people here. Hopefully someone can give me a poke to right direction


//cheers
Textures should all be plain dds files. Most art assets are located in rogue/baked/art. ".mmb" are the 3D model files but they're not in a native format like textures.

Regards.
## Post #32
- Username: kaffeblask
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 29, 2016 7:01 pm
- Post datetime: 2016-04-04T10:17:01+00:00
- Post Title: Re: The Division SDF Archive Format

did the trick - i didnt decompile the whole project - only parts. thanks for giving me the pointer!
Appreciated!

/cheers!
## Post #33
- Username: kaffeblask
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 29, 2016 7:01 pm
- Post datetime: 2016-04-04T13:54:11+00:00
- Post Title: Re: The Division SDF Archive Format

Since the DDS format is BC7 compression, i found a plugin Intel has made that works for latest Photoshop CC versions. 
This can read the file into photoshop.

link: [http://gametechdev.github.io/Intel-Text ... ks-Plugin/](http://gametechdev.github.io/Intel-Texture-Works-Plugin/)
direct: [https://github.com/GameTechDev/ITW-Beta ... _1.0.4.zip](https://github.com/GameTechDev/ITW-Beta-Test/releases/download/ITW_1.0.4/IntelTextureWorks_1.0.4.zip)


//cheers
## Post #34
- Username: w00t
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2016 11:02 am
- Post datetime: 2016-04-04T13:55:44+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> Compressed data block represents binary search tree (for strings), with files in leaves.

Could you provide any info on the binary search tree structure? I'm able to discern the file names but I'm unable to determine how the data fits together.

My breakdown so far:

```
    0x72, 0xC4, 0x9F, 0x01, 0x00, 0x6E, 0x04, 0xA8, 0x00, 0x00, 0x6D, 0x7D,
    0x9E, 0x00, 0x00, 0x66, 0x28, 0x01, 0x00, 0x00, 0x63, 0x9B, 

    // -- Should bypass this header? if it is a header that is --
    
    0x00, 0x00, 0x00, 0x01, // int32 string length (0x01, 1)
    0x62, // string ( 1 byte, 'b')

    0x6C, 0x77, 0x00, 0x00, 0x00, // unknown

    0x0E, // int32 string length (0x0E, 14)
    0x61, 0x64, 0x5F, 0x77, 0x6F, 0x72, 0x64, 0x73, 0x2F, 0x63, 0x68, 0x61, 0x74, 0x5F, // string (14 bytes, 'ad_words/chat_')
    
    0x66, 0x55, 0x00, 0x00, 0x00, // unknown

    0x0E, // int8, string length (0x0E, 14)
    0x65, 0x6E, 0x5F, 0x62, 0x61, 0x64, 0x77, 0x6F, 0x72, 0x64, 0x2E, 0x63, 0x73, 0x76, // string (14 bytes, 'en_badword.csv')

    0x42, 0xA3, 0x18, 0xBA, 0x1E, 0x00, 0x25, // unknown 
    0x72, 0x0E, // int16, file length of 'badwords/chat_en_badword.csv' which is 3698
            
    0x3F, 0x09, 0x38, 0x01, 0x00, 0xD1, 0xC6, 0x76, 0xF4,  // unknown

    0x0E, // int8, string length, 14 decimal
    0x66, 0x72, 0x5F, 0x62, 0x61, 0x64, 0x77, 0x6F, 0x72, 0x64, 0x2E, 0x63, 0x73, 0x76, // string (14 bytes, 'fr_badword.csv')
    
    0x42, 0xA3, 0x18, 0xBA, 0x1E, 0x00, 0x29, // unknown
    0x5F, 0x0A // int16, file length of 'badwords/chat_fr_badword.csv' which is 2655

```


The combination of those three strings gives the path 'badwords/chat_en_badword.csv' which is valid, but I just do not know what the correct structure should be to read these entries out correctly.

Any help would be appreciated, thanks.

*edited to include the file sizes which I've found
## Post #35
- Username: xastey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 04, 2016 7:47 pm
- Post datetime: 2016-04-04T14:21:31+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Tw0F1sh
>
> Sefer wrote:
EDIT: and how to use your tool?
EDIT2: nvm, know how to extract 
EDIT3: Maybe someone is able to rebuild the ingame map. A lot of ppl would love to get hand on it since all available are stitched screenshots

-> Open CMD
-> cd to roug_sdf.exe
-> type rouge_sdf.exe <.sdftoc path> <output directory>
-> Press Enter
-> Done
Thanks man, needed to extra some assets for an web app i'm building.. this worked perfectly!
## Post #36
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2016-04-05T16:28:09+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from kaffeblask
>
> Since the DDS format is BC7 compression, i found a plugin Intel has made that works for latest Photoshop CC versions. 
This can read the file into photoshop.

link: http://gametechdev.github.io/Intel-Text ... ks-Plugin/
direct: https://github.com/GameTechDev/ITW-Beta ... _1.0.4.zip


//cheers

Some of the textures are DX10, you can open them with VS2015 CE.
## Post #37
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-04-06T18:52:39+00:00
- Post Title: Re: The Division SDF Archive Format

Is there a way to open/convert the .mmb model files to .obj or such?
## Post #38
- Username: skd23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 10, 2016 4:02 am
- Post datetime: 2016-04-09T20:18:07+00:00
- Post Title: Re: The Division SDF Archive Format

Hello, I'm not really a programmer. But is there a way to change Russian files with English? I'm desperate to change to English.
## Post #39
- Username: Sefer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 03, 2016 7:31 pm
- Post datetime: 2016-04-10T10:49:54+00:00
- Post Title: Re: The Division SDF Archive Format

For converting the sound files... Seems like some cannot be extracted and some are broken... Atleast you can use some

[viewtopic.php?p=66311&sid=94de722e28428 ... e2f#p66311](http://forum.xentax.com/viewtopic.php?p=66311&sid=94de722e2842869af2f4141f3bb82e2f#p66311)
## Post #40
- Username: eibw3n
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2016 5:57 pm
- Post datetime: 2016-04-10T14:15:45+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from w00t
>
> m0xf wrote:Compressed data block represents binary search tree (for strings), with files in leaves.

Could you provide any info on the binary search tree structure? I'm able to discern the file names but I'm unable to determine how the data fits together.

My breakdown so far:
Code: Select all	
    0x72, 0xC4, 0x9F, 0x01, 0x00, 0x6E, 0x04, 0xA8, 0x00, 0x00, 0x6D, 0x7D,
    0x9E, 0x00, 0x00, 0x66, 0x28, 0x01, 0x00, 0x00, 0x63, 0x9B, 

    // -- Should bypass this header? if it is a header that is --
    
    0x00, 0x00, 0x00, 0x01, // int32 string length (0x01, 1)
    0x62, // string ( 1 byte, 'b')

    0x6C, 0x77, 0x00, 0x00, 0x00, // unknown

    0x0E, // int32 string length (0x0E, 14)
    0x61, 0x64, 0x5F, 0x77, 0x6F, 0x72, 0x64, 0x73, 0x2F, 0x63, 0x68, 0x61, 0x74, 0x5F, // string (14 bytes, 'ad_words/chat_')
    
    0x66, 0x55, 0x00, 0x00, 0x00, // unknown

    0x0E, // int8, string length (0x0E, 14)
    0x65, 0x6E, 0x5F, 0x62, 0x61, 0x64, 0x77, 0x6F, 0x72, 0x64, 0x2E, 0x63, 0x73, 0x76, // string (14 bytes, 'en_badword.csv')

    0x42, 0xA3, 0x18, 0xBA, 0x1E, 0x00, 0x25, // unknown 
    0x72, 0x0E, // int16, file length of 'badwords/chat_en_badword.csv' which is 3698
            
    0x3F, 0x09, 0x38, 0x01, 0x00, 0xD1, 0xC6, 0x76, 0xF4,  // unknown

    0x0E, // int8, string length, 14 decimal
    0x66, 0x72, 0x5F, 0x62, 0x61, 0x64, 0x77, 0x6F, 0x72, 0x64, 0x2E, 0x63, 0x73, 0x76, // string (14 bytes, 'fr_badword.csv')
    
    0x42, 0xA3, 0x18, 0xBA, 0x1E, 0x00, 0x29, // unknown
    0x5F, 0x0A // int16, file length of 'badwords/chat_fr_badword.csv' which is 2655


The combination of those three strings gives the path 'badwords/chat_en_badword.csv' which is valid, but I just do not know what the correct structure should be to read these entries out correctly.

Any help would be appreciated, thanks.

*edited to include the file sizes which I've found

Did you make any more progress on this? I am basically stuck at the same place at the moment.
My assumption is that those unknown blocks in your post must somehow map to file id (a,b,c / 1-2799), offset inside that file and the a length. You also had the file length at 2 bytes which would only work for 64k file sizes which would be a bit small.

Any help would be appreciated.
## Post #41
- Username: w00t
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2016 11:02 am
- Post datetime: 2016-04-11T04:59:22+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from eibw3n
>
> 

Did you make any more progress on this? I am basically stuck at the same place at the moment.
My assumption is that those unknown blocks in your post must somehow map to file id (a,b,c / 1-2799), offset inside that file and the a length. You also had the file length at 2 bytes which would only work for 64k file sizes which would be a bit small.

Any help would be appreciated.

I haven't gotten any further with it. I've tried finding relationships between the data in the unknown blocks or even just a pattern with how they are structured, but no luck.

You're right that 64k would be too small, especially for textures and audio, but I highlighted what I found because they happened to match up exactly with the sample data. I guess it's possible the byte prior to the file length indicates a 'compression' level of an in32 or 64, so that they don't waste bytes on files which are <64k. I don't know if that's realistic though. I'd need to find a file in the data which was large and test the theory.
## Post #42
- Username: eibw3n
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2016 5:57 pm
- Post datetime: 2016-04-11T11:49:13+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from w00t
>
> 
I haven't gotten any further with it. I've tried finding relationships between the data in the unknown blocks or even just a pattern with how they are structured, but no luck.

You're right that 64k would be too small, especially for textures and audio, but I highlighted what I found because they happened to match up exactly with the sample data. I guess it's possible the byte prior to the file length indicates a 'compression' level of an in32 or 64, so that they don't waste bytes on files which are <64k. I don't know if that's realistic though. I'd need to find a file in the data which was large and test the theory.

Yep, this could be it. 

I'd love if m0xf could release the source for his rogue_sdf.exe since I usually don't trust random executables I find on the internet 
Alternatively if no source, m0xf could chime in and give some more information on the sdftoc format.
## Post #43
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-04-11T13:06:58+00:00
- Post Title: Re: The Division SDF Archive Format

Or you could challenge yourself and try to figure it out on your own!
## Post #44
- Username: eibw3n
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2016 5:57 pm
- Post datetime: 2016-04-11T15:04:43+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Sir Kane
>
> Or you could challenge yourself and try to figure it out on your own!

I fully agree with this. I like a challenge. However I've been stuck at this for a while now and I am starting to think I am missing / not seeing something very basic. That's why I wouldn't mind a pointer in the right direction.

This is not the first such pack file that I want to try to write my own unpacker for but it's the first one that gives me problems. Most I've looked at are very pretty straight forward. They usually have a toc with filenames, at offset and lengths with a bit of compression and special headers mixed in. I haven't seen anything like the format that Division uses before.
## Post #45
- Username: w00t
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2016 11:02 am
- Post datetime: 2016-04-11T15:12:32+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from eibw3n
>
> w00t wrote:
I haven't gotten any further with it. I've tried finding relationships between the data in the unknown blocks or even just a pattern with how they are structured, but no luck.

You're right that 64k would be too small, especially for textures and audio, but I highlighted what I found because they happened to match up exactly with the sample data. I guess it's possible the byte prior to the file length indicates a 'compression' level of an in32 or 64, so that they don't waste bytes on files which are <64k. I don't know if that's realistic though. I'd need to find a file in the data which was large and test the theory.

Yep, this could be it. 

I'd love if m0xf could release the source for his rogue_sdf.exe since I usually don't trust random executables I find on the internet 
Alternatively if no source, m0xf could chime in and give some more information on the sdftoc format.

I've done a bit more poking around and my theory about file sizes falls apart with >64k files. I can't find their sizes anywhere so I'm assuming they are not the file sizes but maybe some kind of offset in the data files for that entry.

It would make sense that the entry after 'chat_en_badword.csv' started at the offset which was the file size of 'chat_en_badword.csv', for example.
## Post #46
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-04-11T18:19:00+00:00
- Post Title: Re: The Division SDF Archive Format

Yeah, the Division's approach is certainly something new. But you probably won't get far without looking at the game's disassembly, because most of the per-file info is encoded in a way that's very hard to deduce from looking at it in a hex editor or something like that.
## Post #47
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-04-12T17:58:24+00:00
- Post Title: Re: The Division SDF Archive Format

In compressed part sdftoc files contains variable-length integers and bit fields. .mmb files, and some other files use similar pronciple. 
It is not easy to describe, so I posted the source code.
[rouge_sdf.zip](https://xentaxbackup.github.io/file/10761_rouge_sdf.zip)
## Post #48
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-04-12T18:32:24+00:00
- Post Title: Re: The Division SDF Archive Format

I haven't seen any variable length integers in MMB files.
## Post #49
- Username: BasicNuclear
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 23, 2016 2:30 am
- Post datetime: 2016-04-22T18:47:12+00:00
- Post Title: Re: The Division SDF Archive Format

Attempting to do this but I cant. Can someone just put all the textures into png format and post a zip file containing them?
## Post #50
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-28T10:32:09+00:00
- Post Title: Re: The Division SDF Archive Format

Did anyone manage to extract the models for this game? I managed to get as far as pulling out skeletons. It's just after the mesh names, there's weird, unknown data. I've no idea how to read that correctly.
## Post #51
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-04-30T11:05:52+00:00
- Post Title: Re: The Division SDF Archive Format

How to Extract MMB files?
[w_smg_krissvector_t3.rar](https://xentaxbackup.github.io/file/10856_w_smg_krissvector_t3.rar)
## Post #52
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-30T11:37:32+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from tathannibal
>
> How to Extract MMB files?
The format is really complex, you'll have to upload many more samples than just that if someone were to look at this further.
## Post #53
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-04-30T11:49:31+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Gh0stBlade
>
> tathannibal wrote:How to Extract MMB files?
The format is really complex, you'll have to upload many more samples than just that if someone were to look at this further.

Okey 

All weapons here.

[https://www.dropbox.com/s/xmvndq9nqg7hb ... s.rar?dl=0](https://www.dropbox.com/s/xmvndq9nqg7hb82/Weapons.rar?dl=0)
## Post #54
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-30T18:41:38+00:00
- Post Title: Re: The Division SDF Archive Format

I made a lot of progress with Meshes today thanks to chrrox. However, I suspect the files provided to me are infact corrupt (file size mis-match). Could someone please upload samples which aren't corrupt?

Cheers.
## Post #55
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-04-30T18:54:08+00:00
- Post Title: Re: The Division SDF Archive Format

Here are some samples [http://puu.sh/oBsZS/d57f9ea3de.rar](http://puu.sh/oBsZS/d57f9ea3de.rar)
## Post #56
- Username: tathannibal
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-30T19:01:50+00:00
- Post Title: Re: The Division SDF Archive Format

Thank you!



However, that specific pistol I loaded does not match the fileSize specified in the header. So I suspect the files aren't actually corrupt then. Could be just a bug in the importer code or a bug in the unpacker. Because the code should definitely work. Will investigate this later.

Regards.
## Post #57
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-30T21:54:09+00:00
- Post Title: Re: The Division SDF Archive Format

pistol_03.jpg (233.89 KiB) Viewed 425 times
## Post #58
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-05-01T21:42:02+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Gh0stBlade
>
> Thank you!



However, that specific pistol I loaded does not match the fileSize specified in the header. So I suspect the files aren't actually corrupt then. Could be just a bug in the importer code or a bug in the unpacker. Because the code should definitely work. Will investigate this later.

Regards.

Great work. Are you going to share the import plugin after it's done by any chance?
## Post #59
- Username: tathannibal
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-02T15:26:03+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from cameleot
>
> Gh0stBlade wrote:Thank you!

However, that specific pistol I loaded does not match the fileSize specified in the header. So I suspect the files aren't actually corrupt then. Could be just a bug in the importer code or a bug in the unpacker. Because the code should definitely work. Will investigate this later.

Regards.

Great work. Are you going to share the import plugin after it's done by any chance?

Yep, it's a work in progress. Almost complete, some small bugs to fix and testing.
## Post #60
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-05-05T21:21:04+00:00
- Post Title: Re: The Division SDF Archive Format

Please hurry: D

> Reply from Gh0stBlade
>
> cameleot wrote:Gh0stBlade wrote:Thank you!

However, that specific pistol I loaded does not match the fileSize specified in the header. So I suspect the files aren't actually corrupt then. Could be just a bug in the importer code or a bug in the unpacker. Because the code should definitely work. Will investigate this later.

Regards.

Great work. Are you going to share the import plugin after it's done by any chance?

Yep, it's a work in progress. Almost complete, some small bugs to fix and testing.
## Post #61
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-06T12:38:15+00:00
- Post Title: Re: The Division SDF Archive Format

Hey Guys,
Is it Possible that Someone can Upload me the HUD UI Files or maybe all Sound Effect Files from the Game?
The Problem i got is im a Console Gamer and don't got a PC im a Mac User.

Im Working on a The Devision Skin for Kodi but i need some Sound Effect Files from the Game Like the Game Menü Beebs and Stuff Like that.
I know there are some around the Internet but all of them that i need.

So i Would be very Thankfull if someone can Upload me those Audio Files or maybe the right .sdf Files so i can try to Extract them by my self maybe.
I dunno if this is the Right Tool for Mac

[http://jmri.sourceforge.net/help/en/pac ... rame.shtml](http://jmri.sourceforge.net/help/en/package/jmri/jmrix/loconet/sdfeditor/EditorFrame.shtml)

i don't got the Game on PC because im a Mac User
So Please can someone Help me out?

I don't need the Voice Sounds i got them Already in all Langauges ISAAC Files i only need all Sound Effects form the Game Like Mneü Sounds Skill Using Sounds and Stuff Like that.
## Post #62
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-06T16:38:45+00:00
- Post Title: Re: The Division SDF Archive Format

Nobody can Extract me Those Files?
Or could anyone Record the 2 Files via the Game?
1 Major Problem is the Audio Files are not Clean because in the Main Menu u got Noise in the Background

It Dowsent Matter if you Turn off Background Music via Ingame to 0
I need the 2 Buttons Sounds the Hover Menu Button Sound and the Back Menu Button Sound.

The Best Solution is the Ingame Extracted Ones but looks like nobody can Upload those Files
On the Internet are only ISAC Sounds (Voice) Some from the Loot and Stuff Like that.
## Post #63
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-06T23:47:37+00:00
- Post Title: Re: The Division SDF Archive Format

I got now Parallels on the Mac with Windows 10 could anyone Explain How i Extract now All Music Files from the .sdfdata Files? in .ogg or .wav Pls?
What Programms do i need and how to Set them Up?
## Post #64
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-08T18:38:54+00:00
- Post Title: Re: The Division SDF Archive Format

Can Someone Help me To Extract all Files .sdfdata with the Right Folder Structure and File Names? i used now rouge_sdf.exe but dunno what it actually does Does it Extract all of it with the right Structure?
## Post #65
- Username: edpedpe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 04, 2016 2:43 am
- Post datetime: 2016-05-08T19:20:38+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Nep05
>
> Can Someone Help me To Extract all Files .sdfdata with the Right Folder Structure and File Names? i used now rouge_sdf.exe but dunno what it actually does Does it Extract all of it with the right Structure?
Just create a batch file in the same folder as the rouge_sdf.exe and the sdftoc file, that runs the exe with the required options... i.e.

```
rouge_sdf.exe "sdf.sdftoc" "extracted"
```
## Post #66
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-05-08T21:50:33+00:00
- Post Title: Re: The Division SDF Archive Format

Where is rogue_sdf.exe located? I am in the rogue folder of Division and theres nothing thats an exe.
## Post #67
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-08T21:52:04+00:00
- Post Title: Re: The Division SDF Archive Format

got it but it's extracting since an hour or so  but are the .wem files also in from the Dos Window it looks like those Audio Files are in .fanim

Yung you have to copy the rogue_sdf.exe in to the Main Folder of the Division Folder
## Post #68
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-05-08T21:57:41+00:00
- Post Title: Re: The Division SDF Archive Format

I don't have a rogue_sdf.exe anywhere in my Ubisoft game launcher folder, or my Division game folder. Is this a different program? Sorry if I'm asking dumb questions.
## Post #69
- Username: Nep05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 06, 2016 8:33 pm
- Post datetime: 2016-05-08T22:10:12+00:00
- Post Title: Re: The Division SDF Archive Format

you can download it from this Thread here. But Those are Damn a lot of Files. Im Only Interested in the Audio Files so i have no Idea how to Extract Them all from the Whole Game with the Right Names and Right Folder Structure i need them in .wem or .ogg I Know a Way with VGMToolBox And Drag and Drop .sdfdata Files with the Riff Header Settings but this throw me unnamed .wem Files and i have no Idea how to get them Named in the Right Folder Structure
## Post #70
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-05-09T01:01:40+00:00
- Post Title: Re: The Division SDF Archive Format

So I got the files ripped out almost, but they are all in .mmb extension. How would one get them in to blender or something with a different extension such as .obj?
## Post #71
- Username: LegionArclight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 10, 2016 10:42 pm
- Post datetime: 2016-05-10T16:04:58+00:00
- Post Title: Re: The Division SDF Archive Format

Can someone point out to me what am I doing wrong? I have tried to extract the sdftoc file but while the program run in the DOS window, no real files were in the extracted folder.

The command used was:

rouge_sdf "D:\Program Files (x86)\Steam\steamapps\common\Tom Clancy's The Division\rogue\sdf\pc\data\sdf.sdftoc" "D:\Program Files (x86)\Steam\steamapps\common\Tom Clancy's The Division\extracted\"

Thank you.
## Post #72
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-05-10T16:22:59+00:00
- Post Title: Re: The Division SDF Archive Format

This was my command line, and it worked for me.
Be sure to have the rouge_sdf.exe in the same folder as sdf.sdftoc

```
rouge_sdf.exe "sdf.sdftoc" "extracted"
```


I dunno who gave me this, but I know the line isn't mine.
## Post #73
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-05-17T05:37:04+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Gh0stBlade
>
> cameleot wrote:Gh0stBlade wrote:Thank you!

However, that specific pistol I loaded does not match the fileSize specified in the header. So I suspect the files aren't actually corrupt then. Could be just a bug in the importer code or a bug in the unpacker. Because the code should definitely work. Will investigate this later.

Regards.

Great work. Are you going to share the import plugin after it's done by any chance?

Yep, it's a work in progress. Almost complete, some small bugs to fix and testing.
Any news? Did you ever finish the plugin?
## Post #74
- Username: edpedpe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 04, 2016 2:43 am
- Post datetime: 2016-05-17T11:12:12+00:00
- Post Title: Re: The Division SDF Archive Format

> Great work. Are you going to share the import plugin after it's done by any chance?
>
> 
>
> Yep, it's a work in progress. Almost complete, some small bugs to fix and testing.
>
> 
>
> 
>
> 
>
> 
>
> Any news? Did you ever finish the plugin?
Would also like to know, been eagerly waiting for it
## Post #75
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-17T11:59:28+00:00
- Post Title: Re: The Division SDF Archive Format

Hey guys! Apologies for the lack of response here. The code hasn't been touched in 10 days as I've not had time to continue it. This has since been resolved and development is continuing from now.

There's still some issues, I have to find the flag which controls the various different vertex formats. So far, I've come across 16 different vertex formats and the current code is too unstable in that regard. I do not have enough samples either, I'm trying to work with what I have but it's clearly not enough.

Regards.
## Post #76
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-05-17T19:45:47+00:00
- Post Title: Re: The Division SDF Archive Format

You need i'm uploading all extracted game files.

> Reply from Gh0stBlade
>
> Hey guys! Apologies for the lack of response here. The code hasn't been touched in 10 days as I've not had time to continue it. This has since been resolved and development is continuing from now.

There's still some issues, I have to find the flag which controls the various different vertex formats. So far, I've come across 16 different vertex formats and the current code is too unstable in that regard. I do not have enough samples either, I'm trying to work with what I have but it's clearly not enough.

Regards.
## Post #77
- Username: edpedpe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 04, 2016 2:43 am
- Post datetime: 2016-05-17T20:20:32+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Gh0stBlade
>
> Hey guys! Apologies for the lack of response here. The code hasn't been touched in 10 days as I've not had time to continue it. This has since been resolved and development is continuing from now.

There's still some issues, I have to find the flag which controls the various different vertex formats. So far, I've come across 16 different vertex formats and the current code is too unstable in that regard. I do not have enough samples either, I'm trying to work with what I have but it's clearly not enough.

Regards.
I have all the assets, apart from the generic textures, uploaded. Feel free to grab them if you want:
[https://mega.nz/#!X4dlUL6I!CLoPnW5MRd37 ... 2CFz5V4Q-0](https://mega.nz/#!X4dlUL6I!CLoPnW5MRd37cvi0GORHuvDl4O3wbjfMX2CFz5V4Q-0)
## Post #78
- Username: tathannibal
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-20T11:58:52+00:00
- Post Title: Re: The Division SDF Archive Format

Edit: Early script available here: [viewtopic.php?f=16&t=14374](http://forum.xentax.com/viewtopic.php?f=16&t=14374)

Regards.
## Post #79
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-05-22T15:59:32+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from edpedpe
>
> Gh0stBlade wrote:Hey guys! Apologies for the lack of response here. The code hasn't been touched in 10 days as I've not had time to continue it. This has since been resolved and development is continuing from now.

There's still some issues, I have to find the flag which controls the various different vertex formats. So far, I've come across 16 different vertex formats and the current code is too unstable in that regard. I do not have enough samples either, I'm trying to work with what I have but it's clearly not enough.

Regards.
I have all the assets, apart from the generic textures, uploaded. Feel free to grab them if you want:
https://mega.nz/#!X4dlUL6I!CLoPnW5MRd37 ... 2CFz5V4Q-0

Thanks for this pack, saved me alot of time, however none of the uvs are really in working condition? Do you know how to fix this? Now with the new Noesis Import Plugin for .mmb, I can't seem to get any of the assets you ripped to actually have correct uv placement?

If you can help I'll be appreciative and also $$
## Post #80
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2016-07-09T20:17:42+00:00
- Post Title: Re: The Division SDF Archive Format

First of all thanks for this tool, it's really awesome but I guess its not perfect? As in does it extract everything because I can't seem to find the scope and or its reticles but mainly the scope texture.
Or am I just seriously blind?

I'm talking about this : [http://oi67.tinypic.com/fuludg.jpg](http://oi67.tinypic.com/fuludg.jpg)
## Post #81
- Username: mrcatzaa
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-09T22:27:18+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from KENNITHH
>
> First of all thanks for this tool, it's really awesome but I guess its not perfect? As in does it extract everything because I can't seem to find the scope and or its reticles but mainly the scope texture.
Or am I just seriously blind?

I'm talking about this : http://oi67.tinypic.com/fuludg.jpg

Everything is extracted. Perhaps you overlooked something.
## Post #82
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2016-07-10T07:16:06+00:00
- Post Title: Re: The Division SDF Archive Format

So this morning I decided to check all folders from bottom to top instead of top to bottom which passed all the textures from the maps

So I actually found the scope parts, if anyone is interested these are the names:

halodistorttwocircles_01_n
halodistortspherical_03
acog

there should be more but these are the ones I actually needed
## Post #83
- Username: thedivi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 05, 2016 3:51 am
- Post datetime: 2016-07-11T20:46:06+00:00
- Post Title: Re: The Division SDF Archive Format

Hey guys. I had a long trip to extract this sdftoc but i'm done.
I wonder if it's possible to reproduce (pack) all those files back together to sdf.sdftoc with the rouge.sdf.exe?

I'm trying to bring back the original NYPD car texture. Hopefully someone can answer me.
## Post #84
- Username: thedivi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 05, 2016 3:51 am
- Post datetime: 2016-07-22T23:09:04+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from m0xf
>
> luxox18 wrote:
some textures are incomplete. 

It's my bug. Try new version of extractor.

And how do You compress those files together?
Is there a "rouge_pack_sdf.exe"

to rip files is one thing   to pack is another thing.


I want to change the car textures and need to compress again....
## Post #85
- Username: essenthy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 13, 2014 10:46 pm
- Post datetime: 2016-09-02T13:09:57+00:00
- Post Title: Re: The Division SDF Archive Format

hey guys, thanks for the unpacker ! any chance of a packing option ?
## Post #86
- Username: GoldFarmer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 27, 2016 8:00 am
- Post datetime: 2016-10-08T23:24:35+00:00
- Post Title: Re: The Division SDF Archive Format

Sorry ahead of time for reviving an old thread.

Interested in extracting data files from The Division for myself, I found this thread and downloaded m0xf's source code, all of its required dependencies (visual studio, boost & zlib), got it to build successfully, and subsequently confirmed that it indeed appears to extract all of The Division's resource files.  If you ever see this - thank you for sharing it, m0xf!

I also reached out to m0xf over a week ago to request permission to publish his source code to a more accessible and collaborative source code repository, but didn't hear back from him.  So I went ahead an published it to GitHub, you can find the repository here: [https://github.com/GoldFarmer/rouge_sdf](https://github.com/GoldFarmer/rouge_sdf).  Note that I've subsequently let m0xf know that I'm happy to transfer ownership of the repository to him if he ever wants it.
## Post #87
- Username: jackiiiiii
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 1:19 am
- Post datetime: 2016-11-09T17:50:05+00:00
- Post Title: Re: The Division SDF Archive Format

Hi!

I tried to unpack the PTS build today, but many files are broken and look very weird:
[http://puu.sh/scAgy/6c7062b49d.jpg](http://puu.sh/scAgy/6c7062b49d.jpg)

It must have something to do with the PTS build of the game, since unpackig the live version works just fine. They must have changed something.
Please can someone update this tool?

Please help!
## Post #88
- Username: xKiRRAx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2016 6:12 am
- Post datetime: 2016-12-09T14:47:22+00:00
- Post Title: Re: The Division SDF Archive Format

New user here so let me first say, HELLO!

Alright, on to business. I have been looking to get some .dds files and .png files from the game (sprite sheets and such) and was hoping to extract the files out. I read this thread several times and was finally confident enough to download the sdf_rouge.exe tool and use it to unpack all the files from the rogue/sdf folder (not the sdf_streaming folder).

Unfortunately TONS of the .dds files show up as either black files with a handful of discolored lines (like it was corrupt or rebuilt incorrectly or something) or some of them showed up as randomly colored images that look like a 5 year old went in MS paint and drew rainbows in odd designs.

Is there some other encoder required to be installed prior to unpacking these files? Is the rouge.exe doing something incorrectly? Am I doing something incorrectly?

Some files come out great, some come out like it's missing data and couldn't be drawn. Any ideas? Sorry my first post had to be a plea for help. =/ Just looking to get some icons and such out of the game files.
## Post #89
- Username: MikeKwokwc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 09, 2017 9:59 pm
- Post datetime: 2017-01-10T05:44:07+00:00
- Post Title: Re: The Division SDF Archive Format

For the UV mapping problem. I found that if I unwrap uvw in 3dsmax, you will find that the mapping needs to be moved back to the texture space and then mirrored horizontally for the texture to work.
## Post #90
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2017-01-10T17:49:18+00:00
- Post Title: Re: The Division SDF Archive Format

Hello all

I tested SDF_Rouge2.exe but alot file is broken ...

New Version is available ?
## Post #91
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2017-08-19T15:50:21+00:00
- Post Title: Re: The Division SDF Archive Format

TESTED 19.8.2017 on Global Event update 

how to start export:

->Open CMD
-> cd to roug_sdf.exe
-> type rouge_sdf.exe "sdf.sdftoc" "output directory"..........
-> Press Enter
-> Done 
 WARNING: make sure u have 30GB free on ur SSD

Confuse ? 

 here is Picture 

[rouge_sdf_2.zip](https://xentaxbackup.github.io/file/13220_rouge_sdf_2.zip)
## Post #92
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2017-08-19T15:55:49+00:00
- Post Title: Re: The Division SDF Archive Format

i was currious on new clothes i can get it from caches so i take a look inside of files what else is there
## Post #93
- Username: Sed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 01, 2017 9:19 pm
- Post datetime: 2017-09-01T16:00:52+00:00
- Post Title: Re: The Division SDF Archive Format

Hey guys.

I've been reading this thread and was hopeful to extract the weapon talent icon files with the convenient rouge_sdf.exe tool. However, as others have reported, a lot of the DDS files seem to be corrupted or otherwise unable to be read by various DDS image viewers. Does anyone have any pointers on how to fix this, or otherwise has access to the spritesheet with weapon talent icons and wishes to share it?
## Post #94
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-09-02T11:03:21+00:00
- Post Title: Re: The Division SDF Archive Format

A lot of the Division textures use the [DXT10](https://msdn.microsoft.com/en-us/library/windows/desktop/bb943983%28v=vs.85%29.aspx) version of DDS files.

Haven't seen anything besides Visual Studio being able to open those for viewing.
## Post #95
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-09-06T03:45:39+00:00
- Post Title: Re: The Division SDF Archive Format

how can i repack this package?!?
this game can read external files from outside of game or not?
## Post #96
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2017-09-07T03:44:36+00:00
- Post Title: Re: The Division SDF Archive Format

Ubisoft's Mario + Rabbids Kingdom Battle uses the SDFDATA archive like The Division but rouge_sdf doesn't work for it.

Mario+Rabbids (1st 4 SDFDATA files, SDFTOC, SDFVER, and sdf-slice.mapping files)
[M+R SDFDATA.rar](https://openload.co/f/m2byPZQsPEI/M%2BR_SDFDATA.rar)
## Post #97
- Username: Charcoa1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 12, 2017 4:42 pm
- Post datetime: 2017-09-12T09:36:06+00:00
- Post Title: Re: The Division SDF Archive Format

I ended up here looking for some Mario & Rabbids info.

The dump I have has an .istorage file that's about 2.3Gb.
In there are multiple references to "BERG" and "WEST" as in the SDFTOC and SDFDATA files.

I've also found this vaguely JSON kind of structure, starting at address 94000878 in my dump:

```
zGWQ#^!D>dLW3ubisoft
0: 112166 452674
6040 11888185077
630758522 108998
43707442177020 3
7287950033140705
90

{
	mappings = {
	{
		pattern = 
		{
			"moria/sdf/nx/data/sdf.sdftoc",
			"moria/sdf/nx/data/sdf.sdfver",
			"moria/sdf/nx/data/sdf-A-*.sdfdata",
		},
		chunkindex = 1,
		chunkid= 1000,
		islaunch = 1,
		dlcIndex = -1,
		dlcEntitlement = "",
	},{
		pattern = 
		{
			"moria/sdf/nx/data/sdf-B-*.sdfdata",
			"moria/sdf/nx/data/sdf-C-*.sdfdata",
		},
	chunkindex = 2,
	chunkid = 1001,
	islaunch = 0,
	dlcIndex = -1,
	dlcEntitlement = "",
	},{
		pattern = "dlc0:/*",        
		chunkindex = 3,           
		chunkid = 1002,
        islaunch = 0,   
        dlcIndex = 0,        
		dlcEntitlement = "RKBDLC00",
	},{
		pattern = "dlc1:/*",          
		chunkindex = 4,
		chunkid = 1003,
        islaunch = 0,     
		dlcIndex = 1,          
		dlcEntitlement = "RKBDLC01",
	},{
		pattern = "dlc2:/*",            
		chunkindex = 5,
        chunkid = 1004,  
        islaunch = 0,       
		dlcIndex = 2,            
		dlcEntitlement = "RKBDLC02",
	},{
		pattern = "dlc3:/*",
		chunkindex = 6, 
		chunkid = 1005,    
		islaunch = 0,         
		dlcIndex = 3,
		dlcEntitlement = "RKBDLC03",
	},{
		pattern = "dlc4:/*",
		chunkindex = 7,   
		chunkid = 1006,      
		islaunch = 0,           
		dlcIndex = 4,
		dlcEntitlement = "RKBDLC04",
	},{
		pattern = "dlc5:/*",  
		chunkindex = 8,     
		chunkid = 1007,        
		islaunch = 0,
		dlcIndex = 5,  
		dlcEntitlement = "RKBDLC05",
	},{
		pattern = "dlc6:/*",    
		chunkindex = 9,       
		chunkid = 1008,  
		islaunch = 0,
		dlcIndex = 6, 
		dlcEntitlement = "RKBDLC06",
	},{
		pattern = "dlc7:/*",      
		chunkindex = 10,        
		chunkid = 1009,           
		islaunch = 0,
		dlcIndex = 7, 
		dlcEntitlement = "RKBDLC07",
	},{
		pattern = "dlc8:/*",       
		chunkindex = 11,         
		chunkid = 1010,            
		islaunch = 0, 
        dlcIndex = 8,      
		dlcEntitlement = "RKBDLC08",
	},{
		pattern = "dlc9:/*",        
		chunkindex = 12,          
		chunkid = 1011,            
		islaunch = 0,  
        dlcIndex = 9,       
		dlcEntitlement = "RKBDLC09",
	}
	,}
,}
```

(I did format the JSON-ish stuff)

Looking at it again, I see that part of that also includes the sdf.sdfver file that !!!!! posted above.
## Post #98
- Username: Atlas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 25, 2017 2:19 am
- Post datetime: 2017-09-24T18:52:46+00:00
- Post Title: Re: The Division SDF Archive Format

Any news on this for M+RKB?
## Post #99
- Username: kornix3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 17, 2017 11:46 am
- Post datetime: 2017-10-19T02:59:33+00:00
- Post Title: Re: The Division SDF Archive Format

does anyone know how can i repack the files again? rogue_Sdf.exe
## Post #100
- Username: blabla88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 20, 2017 6:42 pm
- Post datetime: 2017-10-20T12:09:12+00:00
- Post Title: Re: The Division SDF Archive Format

Freaking Ubisoft and their files composition. I was planning to translate new South Park game, but don't know how to convert it back in to sdftoc  First South Park game had OAF, so it was much easier.
## Post #101
- Username: synthosc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 06, 2017 5:59 am
- Post datetime: 2017-12-11T14:52:47+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from Sed
>
> Hey guys.

I've been reading this thread and was hopeful to extract the weapon talent icon files with the convenient rouge_sdf.exe tool. However, as others have reported, a lot of the DDS files seem to be corrupted or otherwise unable to be read by various DDS image viewers. Does anyone have any pointers on how to fix this, or otherwise has access to the spritesheet with weapon talent icons and wishes to share it?

Does it fail on Noesis too?
## Post #102
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2018-04-21T04:35:43+00:00
- Post Title: Re: The Division SDF Archive Format

Hey there guys, so I think this might be broken after patch 1.8, as a lot of the textures needed are now missing. i could be wrong, it's just a lot of missing textures, like 90% of them are not extracted. 
I could be wrong, but i got my folder to unpack.
## Post #103
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-06-15T22:41:04+00:00
- Post Title: Re: The Division SDF Archive Format

Anybody know if the tool still works on the game?
Or is it outdated?
## Post #104
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2018-12-16T04:18:24+00:00
- Post Title: Re: The Division SDF Archive Format

Is not Working with The Division 2 Alpha
## Post #105
- Username: xp0it
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 20, 2018 3:57 am
- Post datetime: 2018-12-19T20:05:00+00:00
- Post Title: Re: The Division SDF Archive Format

they've upgraded the file format to a newer version for division 2, thats why rogue_sdf isn't working with the TD2 alpha.

while division 1 was sdf version 22, division 2 is sdf version 37.

idk if some other ubisoft game uses version 37, but the file header has changed significally and has more values (probably more block sizes).

it seems that they've splitted the data by language as well, at least there're now some "sdf-C-2000-en-US.sdfdata" files.
## Post #106
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2018-12-23T22:44:11+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from xp0it
>
> they've upgraded the file format to a newer version for division 2, thats why rogue_sdf isn't working with the TD2 alpha.

while division 1 was sdf version 22, division 2 is sdf version 37.

idk if some other ubisoft game uses version 37, but the file header has changed significally and has more values (probably more block sizes).

it seems that they've splitted the data by language as well, at least there're now some "sdf-C-2000-en-US.sdfdata" files.

Any way extract this file ?
## Post #107
- Username: xp0it
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 20, 2018 3:57 am
- Post datetime: 2019-01-11T19:41:57+00:00
- Post Title: Re: The Division SDF Archive Format

sure, but it'll be easier when the game is released and you have a running client.

they've probably encrypted/obfuscated the file, since its not that obvious anymore where the zlib data starts:

TD1:

```

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
240053        0x3A9B5         Zlib compressed data, best compression
```


TD2:

```

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
```
## Post #108
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2019-01-19T12:01:08+00:00
- Post Title: Re: The Division SDF Archive Format

I have Alpha Test client files
## Post #109
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2019-02-05T03:27:55+00:00
- Post Title: Re: The Division SDF Archive Format

I do know this much about the Alpha files:
- 0x685F6 is the start of the compressed binary search tree for the alpha files
- the only data after the compressed data is the ID block which is 0x30 bytes long
- They added 5 new uint32 values to the header
- The compression ratio is about 1% worse than Div1
- the main game executable is roughly double in size
## Post #110
- Username: htk42
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 06, 2018 9:41 am
- Post datetime: 2019-02-06T16:24:52+00:00
- Post Title: Re: The Division SDF Archive Format

hello ,

the tool doent work with the division 2 file, its the same format but we get an error.

Error: Unexcepted byte in file tree
## Post #111
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2019-02-06T18:13:41+00:00
- Post Title: Re: The Division SDF Archive Format

get it guys soon as possible som of models i finish is on [https://p3dm.ru/](https://p3dm.ru/) free to download
## Post #112
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2019-02-07T13:55:46+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from htk42
>
> hello ,

the tool doent work with the division 2 file, its the same format but we get an error.

Error: Unexcepted byte in file tree

It only appears to be the same format. The file structure is the same, however the compressed data has changed and we have yet to identify how it has changed to update the extractor.
## Post #113
- Username: jackiiiiii
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 1:19 am
- Post datetime: 2019-02-08T18:21:08+00:00
- Post Title: Re: The Division SDF Archive Format

Any update on this, now as the beta has arrived?
## Post #114
- Username: imXisheng
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 30, 2016 3:11 am
- Post datetime: 2019-02-08T19:35:00+00:00
- Post Title: Re: The Division SDF Archive Format

Won't be any update until Lunger figures out how to do it.
## Post #115
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2019-02-10T17:24:58+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from htk42
>
> hello ,

the tool doent work with the division 2 file, its the same format but we get an error.

Error: Unexcepted byte in file tree

Uses a different version of the file extension, that's why it's not working. To be expected to be honest.
## Post #116
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2019-02-14T08:28:12+00:00
- Post Title: Re: The Division SDF Archive Format

fix UV maps for backpacks in division1 plz
## Post #117
- Username: MacFalkner
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 18, 2016 3:30 am
- Post datetime: 2019-02-21T12:11:56+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from lunger ↑Thu Feb 07, 2019 9:55 pm at Thu Feb 07, 2019 9:55 pm
>
> 
htk42 wrote:hello ,

the tool doent work with the division 2 file, its the same format but we get an error.

Error: Unexcepted byte in file tree

It only appears to be the same format. The file structure is the same, however the compressed data has changed and we have yet to identify how it has changed to update the extractor.

Thank you, looking forward to your extractor. I'd love to just read whats all in there, not just the models.
## Post #118
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2019-02-23T22:54:07+00:00
- Post Title: Re: The Division SDF Archive Format

Any update ?
## Post #119
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2019-03-02T02:29:03+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from SEB851 ↑Sun Feb 24, 2019 6:54 am at Sun Feb 24, 2019 6:54 am
>
> Any update ?

I think something like this will wait till the 12-15th of March for the full release.
## Post #120
- Username: jackiiiiii
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 1:19 am
- Post datetime: 2019-03-02T18:45:16+00:00
- Post Title: Re: The Division SDF Archive Format

Well the archive format is unlikely to change until release, so...
## Post #121
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2019-03-10T13:49:19+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from jackiiiiii ↑Sun Mar 03, 2019 2:45 am at Sun Mar 03, 2019 2:45 am
>
> 
Well the archive format is unlikely to change until release, so...

Either way we've gotta wait
## Post #122
- Username: master4life
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 09, 2018 2:44 am
- Post datetime: 2019-03-11T16:56:59+00:00
- Post Title: Re: The Division SDF Archive Format

If you are looking for extracting sound files. I've just used Ravioli Explorer to extract those files. [https://i.imgur.com/zCZL0Sz.png](https://i.imgur.com/zCZL0Sz.png)
## Post #123
- Username: jackiiiiii
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 1:19 am
- Post datetime: 2019-03-16T12:26:06+00:00
- Post Title: Re: The Division SDF Archive Format

Any progress?
## Post #124
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2019-03-20T09:59:46+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from jackiiiiii ↑Sat Mar 16, 2019 8:26 pm at Sat Mar 16, 2019 8:26 pm
>
> 
Any progress?

Looks like there is some here, [https://forum.xentax.com/viewtopic.php?f=10&t=19639](https://forum.xentax.com/viewtopic.php?f=10&t=19639) but I dunno where to get the keys.
## Post #125
- Username: coco97
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 09, 2014 11:45 am
- Post datetime: 2019-03-23T06:13:05+00:00
- Post Title: Re: The Division SDF Archive Format

me too. where can find AES key and VI ?
## Post #126
- Username: Balaboy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 27, 2018 4:23 pm
- Post datetime: 2019-04-23T13:13:40+00:00
- Post Title: Re: The Division SDF Archive Format

Is the rouge_sdf.exe broke? When I put in the input and out it keeps phrasing "Tom Clancy's The Division .sdftoc extractor v2
usage: rouge_sdf.exe <.sdftoc path> <output directory>" 

I'm using quotations and not the < >. Is this just simply outdated software?
## Post #127
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-04-23T15:02:47+00:00
- Post Title: Re: The Division SDF Archive Format

Go to page 7 at the top you Will see how to use it
## Post #128
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2019-06-18T10:24:00+00:00
- Post Title: Re: The Division SDF Archive Format

For anyone wanting to extract files from Mario + Rabbids: Kingdom Battle
[https://cdn.discordapp.com/attachments/ ... kb_sdf.bms](https://cdn.discordapp.com/attachments/419711036837330956/590486256094281748/mrkb_sdf.bms)
Edited version of aluigi's quickbms script.
Removes 3 lines from the script.

```
		get fileId long MEMORY_FILE
	endif
```


These lines broke the script for the game.
## Post #129
- Username: gasamsg12
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 02, 2019 5:57 pm
- Post datetime: 2019-06-20T19:33:48+00:00
- Post Title: Re: The Division SDF Archive Format

How get aes VI key?
## Post #130
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2019-07-06T15:53:02+00:00
- Post Title: Re: The Division SDF Archive Format

What is recent AES Key ?
## Post #131
- Username: costelabr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 18, 2019 10:30 pm
- Post datetime: 2020-01-27T01:36:24+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from CosmicDreams ↑Tue Jun 18, 2019 6:24 pm at Tue Jun 18, 2019 6:24 pm
>
> 
For anyone wanting to extract files from Mario + Rabbids: Kingdom Battle
https://cdn.discordapp.com/attachments/ ... kb_sdf.bms
Edited version of aluigi's quickbms script.
Removes 3 lines from the script.
Code: Select allif VER <= 0x16
		get fileId long MEMORY_FILE
	endif

These lines broke the script for the game.
awesome i can extract files now, but i reimport not work
## Post #132
- Username: Mondraconus
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 21, 2016 1:29 pm
- Post datetime: 2020-07-13T18:53:43+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from edpedpe ↑Wed May 18, 2016 4:20 am at Wed May 18, 2016 4:20 am
>
> 
Gh0stBlade wrote:Hey guys! Apologies for the lack of response here. The code hasn't been touched in 10 days as I've not had time to continue it. This has since been resolved and development is continuing from now.

There's still some issues, I have to find the flag which controls the various different vertex formats. So far, I've come across 16 different vertex formats and the current code is too unstable in that regard. I do not have enough samples either, I'm trying to work with what I have but it's clearly not enough.

Regards.
I have all the assets, apart from the generic textures, uploaded. Feel free to grab them if you want:
https://mega.nz/#!X4dlUL6I!CLoPnW5MRd37 ... 2CFz5V4Q-0

Damn, thank you so much for this ^^ at least this save my time and I can get all of New York signs texture... Thank you once again...
I know this is maybe a rude ask, but can you upload all the assets from Division 2 please ? Since you really save my time to dig these textures
## Post #133
- Username: vegasfest56
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 26, 2019 11:38 pm
- Post datetime: 2022-03-09T23:04:11+00:00
- Post Title: Re: The Division SDF Archive Format

Some textures, like the Riker Enforcer's head textures are broken. Does anyone have working textures?
## Post #134
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2022-10-17T21:31:38+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from CosmicDreams ↑Tue Jun 18, 2019 6:24 pm at Tue Jun 18, 2019 6:24 pm
>
> 
For anyone wanting to extract files from Mario + Rabbids: Kingdom Battle
https://cdn.discordapp.com/attachments/ ... kb_sdf.bms
Edited version of aluigi's quickbms script.
Removes 3 lines from the script.
Code: Select allif VER <= 0x16
		get fileId long MEMORY_FILE
	endif

These lines broke the script for the game.

Ubisoft Milan at it again!
Sparks of Hope BMS script.
[https://cdn.discordapp.com/attachments/ ... oh_sdf.bms](https://cdn.discordapp.com/attachments/419711036837330956/1031680667236442123/mrsoh_sdf.bms)
All they changed was making the sdf names use underscores instead of hyphens...
## Post #135
- Username: BanhMi93
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 31, 2021 9:16 am
- Post datetime: 2022-10-19T12:01:48+00:00
- Post Title: Re: The Division SDF Archive Format

> Reply from CosmicDreams ↑Tue Oct 18, 2022 5:31 am at Tue Oct 18, 2022 5:31 am
>
> 
CosmicDreams wrote: ↑Tue Jun 18, 2019 6:24 pm
For anyone wanting to extract files from Mario + Rabbids: Kingdom Battle
https://cdn.discordapp.com/attachments/ ... kb_sdf.bms
Edited version of aluigi's quickbms script.
Removes 3 lines from the script.
Code: Select allif VER <= 0x16
		get fileId long MEMORY_FILE
	endif

These lines broke the script for the game.


Ubisoft Milan at it again!
Sparks of Hope BMS script.
https://cdn.discordapp.com/attachments/ ... oh_sdf.bms
All they changed was making the sdf names use underscores instead of hyphens...

is your script support reimport?
## Post #136
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2022-10-19T13:10:49+00:00
- Post Title: Re: The Division SDF Archive Format

No idea.
## Post #137
- Username: AGANIS13123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 02, 2023 2:12 am
- Post datetime: 2023-05-01T18:14:32+00:00
- Post Title: Re: The Division SDF Archive Format

Hi! I'm new to the Rouge_sdf tool. I can't find the exe file ANYWHERE. Not even in the tool folder. Can someone explain to me how to use the tool,please?
## Post #138
- Username: heraldino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 01, 2023 1:54 am
- Post datetime: 2023-09-13T17:23:16+00:00
- Post Title: Re: The Division SDF Archive Format

Can anyone change the script so I can import those back?
