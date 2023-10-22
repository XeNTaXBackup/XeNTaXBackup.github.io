## Post #1
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-01T08:37:04+00:00
- Post Title: Ninety Nine Nights 2

Hi there, how are things,
There is this game (N3-2) that I've been messing with and I was able to extract the models, both stages and characters, these aren't the best models out there but it was worth the effort. More to come soon.
[N3-2 debut.JPG](https://xentaxbackup.github.io/file/3572_N3-2 debut.JPG)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-01T10:51:15+00:00
- Post Title: Ninety Nine Nights 2

Cool nice job.
## Post #3
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-02T10:20:12+00:00
- Post Title: Ninety Nine Nights 2

Ok, first things first, we need to extract the data out of those fpd files, unfortunately, I couldn't decode the filename table, the archive structure is the same as Lost Odyssey, only offsets and sizes are visible, and thus a lot of data will be ignored, but as long as we can locate the models, we're fine  This N3-2 Data Extractor (attached below) will do the job for you, a little too much maybe, just put it where default.fpd, default.fpi and xenon_bg.fpd are.
default.fpd contains the game data and xenon_bg.fpd holds the stage data, after extraction, the mcts directory will hold the stage data and mnks will have the models, feel free to delete the rest of the directories if you don't need them. The musics are in xwav.
Next, we will take care of those stages even if they are so dull.
[N3-2 Data Extractor.zip](https://xentaxbackup.github.io/file/3576_N3-2 Data Extractor.zip)
## Post #4
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-03T09:15:54+00:00
- Post Title: Ninety Nine Nights 2

This tool works on the mcts files that hold the stages, put it in the MCTS directory and execute, the 65 MCTS files must all be present. The good thing about those mcts files is that they contain filenames, which means that the extracted data will have correct names. The bad thing is that the so called DDS files aren't true DDS and are compressed in a an unknown manner, if you have time, take a look and maybe you can figure out the compression. The decompression should be similar to the the tex files in the tex directory (with lots of zeros).
The extracted data is easilly identified:
-dds: textures
-ligt: lights
-lmch: lightmaps?? or collision
-matr: materials
-mest: mesh
-shdr: shaders
[N3-2 Mcts Extractor.zip](https://xentaxbackup.github.io/file/3578_N3-2 Mcts Extractor.zip)
## Post #5
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-04T10:18:57+00:00
- Post Title: Ninety Nine Nights 2

Yeah, those dull stages seem to show perfectly!! I'll upload the obj exporter soon.
[N3-2 stage.JPG](https://xentaxbackup.github.io/file/3580_N3-2 stage.JPG)
## Post #6
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-06T11:07:31+00:00
- Post Title: Ninety Nine Nights 2

Hi,
Now here's the stage exporter, it processes MEST files and outputs OBJ files, only position data is hanldled right now, no tex UV's or colors, maybe when when we have working textures.
Enjoy.
[N3-2 Stage Exporter.zip](https://xentaxbackup.github.io/file/3584_N3-2 Stage Exporter.zip)
## Post #7
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2010-11-07T12:22:09+00:00
- Post Title: Ninety Nine Nights 2

Really good job   
Thanks
I love to see a characters converter soon
Thanks again Surveyor
## Post #8
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-08T09:53:24+00:00
- Post Title: Ninety Nine Nights 2

The MNKS extractor:
Will parse the mnks files and extract some useful data (models and anims) the rest of the data is ignored since every type needs its own parser (and there are many).
Put the program in the MNKS directory, there is an mnks list that you can modify to your own needs. One thing I'm still not sure of is there's only one texture per model, no normals, specular maps, nothing!!! Maybe one texture holds all of them, we'll see that when we have working textures.
[N3-2 Mnks Extractor.zip](https://xentaxbackup.github.io/file/3586_N3-2 Mnks Extractor.zip)
## Post #9
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-15T10:14:20+00:00
- Post Title: Ninety Nine Nights 2

Hi
Skinning works too, the model exporter will be available soon.
[N3-2 skin.JPG](https://xentaxbackup.github.io/file/3609_N3-2 skin.JPG)
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-11-15T10:16:14+00:00
- Post Title: Ninety Nine Nights 2

> Reply from Surveyor
>
> Hi
Skinning works too, the model exporter will be available soon.
So great, thanks!
## Post #11
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2010-11-20T15:15:57+00:00
- Post Title: Ninety Nine Nights 2

Cool nice job.
## Post #12
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-11-20T15:27:56+00:00
- Post Title: Ninety Nine Nights 2

A really great job man!!!
## Post #13
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-11-21T09:03:07+00:00
- Post Title: Ninety Nine Nights 2

Hello,
Here's the MESK exporter, it's experimental only so there's no UV coords, no normals, just proper skinning (and this isn't nothing)
The exporter is very easy to use, it generates an MS file that you'll need to drag into 3dsmax, Just make sure the .joint file is also there since it holds the skeleton data.
Enjoy.
[N3-2 Mesk Exporter.zip](https://xentaxbackup.github.io/file/3629_N3-2 Mesk Exporter.zip)
## Post #14
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2010-11-21T23:54:27+00:00
- Post Title: Ninety Nine Nights 2

A Real man's job ! Thx
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-11-29T17:52:54+00:00
- Post Title: Ninety Nine Nights 2

Surveyor,

Please,add uv-mapping for your great tools.
Mayby uv use  "half-precision floating-point number" for  2 bytes.
## Post #16
- Username: bondlaw
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Apr 15, 2010 5:46 am
- Post datetime: 2011-02-19T21:59:57+00:00
- Post Title: Re: Ninety Nine Nights 2

> Reply from Surveyor
>
> Hello,
Here's the MESK exporter, it's experimental only so there's no UV coords, no normals, just proper skinning (and this isn't nothing)
The exporter is very easy to use, it generates an MS file that you'll need to drag into 3dsmax, Just make sure the .joint file is also there since it holds the skeleton data.
Enjoy.
AMAZING!! i like this game a lot!! your tools are great!! is there any news in the uv coords?
## Post #17
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-18T18:47:24+00:00
- Post Title: Re: Ninety Nine Nights 2

> Reply from bondlaw
>
> Surveyor wrote:Hello,
Here's the MESK exporter, it's experimental only so there's no UV coords, no normals, just proper skinning (and this isn't nothing)
The exporter is very easy to use, it generates an MS file that you'll need to drag into 3dsmax, Just make sure the .joint file is also there since it holds the skeleton data.
Enjoy.
AMAZING!! i like this game a lot!! your tools are great!! is there any news in the uv coords?Hello everyone, this game is only half done, pity, hope that God can have a perfect tool, it can directly import textures and models are very grateful.
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-09-06T06:59:42+00:00
- Post Title: Re: Ninety Nine Nights 2

Hi guys! Just in case if textures from this game will be supported some day (or someone will do a RAM dump), I'm leaving a maxscript (3ds max 2009-2012) to import models with uv's/bones/weights here


[N-3-2.7z](https://xentaxbackup.github.io/file/7781_N-3-2.7z)
## Post #19
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2015-06-29T06:09:13+00:00
- Post Title: Re: Ninety Nine Nights 2

Hi guys.
Who found the text files? I search, but not found.
## Post #20
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2015-10-23T14:44:32+00:00
- Post Title: Re: Ninety Nine Nights 2

> Reply from gula
>
> Hi guys.
Who found the text files? I search, but not found.

BUMP
