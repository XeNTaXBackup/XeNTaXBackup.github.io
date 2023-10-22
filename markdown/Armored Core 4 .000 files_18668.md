## Post #1
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-11T18:01:20+00:00
- Post Title: Armored Core 4 .000 files

I was taking a look at the AC4 game files and there are these .000, .001 and 002 files rather than any TCF or FLV files, which leads me to assume these are containers. Anyone knows how to open these?

Here are some samples:
[http://www.mediafire.com/file/ekj60r0ul ... s.rar/file](http://www.mediafire.com/file/ekj60r0uln22lbv/samples.rar/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-12T04:12:03+00:00
- Post Title: Armored Core 4 .000 files

> Reply from Portugalotaku
>
> Anyone knows how to open these?
You can unzip the data with the following BMS commands.

```
goto 0x24
get Zsize long
get Offset long
goto 0x8 0 SEEK_CUR
get Size long
get Name string
string Name + ".dcp"
clog Name Offset Zsize Size

```

Then you can extract the geometry within using hex2obj.
An example for the resulting file hl0010.000.dcp:



hl0010.jpg (246.27 KiB) Viewed 311 times
## Post #3
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-12T18:50:04+00:00
- Post Title: Armored Core 4 .000 files

Thanks for the help, though sadly I cannot use hex2obj. If anyone is willing to make a script for these files, it would be appreciated.

Now to figure out where the textures are...
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-13T03:17:22+00:00
- Post Title: Armored Core 4 .000 files

> Reply from Portugalotaku
>
> Thanks for the help, though sadly I cannot use hex2obj.
Well, you don't want to extract all stuffs manually, of course.
Which platform are the samples from btw? PS3?

> Reply from Portugalotaku
>
> Now to figure out where the textures are...
They're in the same file though I didn't care for them in the first place.
So here's is a BMS script that will unpack the .000 archives you uploaded, and a simple Noesis script for loading the resulting tpf images. 
Only 2 image formats supported currently. 


 AC4.rar
Updated (1.22 KiB) Downloaded 32 times


Let's see if someone would make you a script/tool to load the models.
## Post #5
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-13T16:22:19+00:00
- Post Title: Armored Core 4 .000 files

Yeah, it's ps3.

Thanks for that, I actually had already used your bms parameters to open a couple of files in search of textures, but found nothing.
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-13T16:41:38+00:00
- Post Title: Armored Core 4 .000 files

It seems the script does not work on the sequential files. I updated the samples file with new samples:

[http://www.mediafire.com/file/ekj60r0ul ... s.rar/file](http://www.mediafire.com/file/ekj60r0uln22lbv/samples.rar/file)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T01:43:52+00:00
- Post Title: Armored Core 4 .000 files

> Reply from Portugalotaku
>
> It seems the script does not work on the sequential files.
Script updated.


 AC4Unpacker.rar
(587 Bytes) Downloaded 50 times


Select only .000 files as input.
## Post #8
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-15T11:32:00+00:00
- Post Title: Armored Core 4 .000 files

Thank you, it works. Now we just need a script to open the models. If no one is willing to do it for free, I am willing to pay.
## Post #9
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-22T15:11:48+00:00
- Post Title: Armored Core 4 .000 files

Anyone? My offer still stands.
## Post #10
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-29T22:12:16+00:00
- Post Title: Armored Core 4 .000 files

No takers? I should look further then.
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-08-29T23:36:02+00:00
- Post Title: Armored Core 4 .000 files

Some model samples maybe? I looked and made script for one Armored Core game long ago, don't remember which one.
## Post #12
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-30T14:30:52+00:00
- Post Title: Armored Core 4 .000 files

I apologize, I forgot to upload samples of the models themselves.

[http://www.mediafire.com/file/ekj60r0ul ... s.rar/file](http://www.mediafire.com/file/ekj60r0uln22lbv/samples.rar/file)
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-08-30T16:57:07+00:00
- Post Title: Armored Core 4 .000 files

Hmm, I was wondering which game this format reminds me off, it's some sort of proto version of FromSoftware demon souls/dark souls engine, ninja blade too, I worked on newer Armored Core game, this format is different.



P.S. Can you convert textures from .tpf containers?
## Post #14
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-30T21:29:11+00:00
- Post Title: Armored Core 4 .000 files

Yeah, have a noesis script.
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-08-30T21:40:01+00:00
- Post Title: Armored Core 4 .000 files

Good, less work to do, also there's two model types .mdl and .smd. They are similar, though .smd look like a collision mesh? No uv's, weights just raw geometry and more low-poly

EDIT: And I will need much more .mdl/.smd samples if I'm going to finish this script. You can skip the .tpf files, just models in order to lesser the size of the sample archive.
## Post #16
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-31T17:52:55+00:00
- Post Title: Re: Armored Core 4 .000 files

[http://www.mediafire.com/file/ekj60r0ul ... s.rar/file](http://www.mediafire.com/file/ekj60r0uln22lbv/samples.rar/file)

Here's a whole bunch. If you need more tell me.

I wonder what the mlb files are.
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-08-31T20:25:34+00:00
- Post Title: Re: Armored Core 4 .000 files

.mlb aren't models for sure, some info - materials, some other stuff
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-09-04T13:10:06+00:00
- Post Title: Re: Armored Core 4 .000 files

Portugalotaku, check your PM.
