## Post #1
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-06-06T19:32:39+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

Hello all, I've been searching high & low for a method of extracting texture files from Chronicles of Riddick (Butcher's Bay/Dark Athena).

I have the Watto Extractor but it does not recognize the .xtc files as archives.

Dragon UnPacker recognizes the .xtc archives and is able to extract (some) diffuse .dds textures, but it completely mangles all the .dds normal maps.

Has anybody found a method or tool to successfully extract all .xtc textures?

Any help is appreciated.
## Post #2
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-06-07T13:33:02+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

I found [this post](https://forum.xentax.com/viewtopic.php?f=16&t=9121&hilit=syndicate) which says the normal map .dds files extracted by Dragon UnPacker can be edited with a hex editor — changing the file from dxt1 to dxt5 — to make them work.

I've looked and looked, but haven't found a proper tutorial or clear information on hex editing a .dds file

Does anyone have experience doing this? Could you share those steps?

Another thought: Is there a way to get Dragon Unpacker to extract .dds files as DXT5 instead of DXT1?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-07T19:09:57+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

Can you upload a few XTC samples?
## Post #4
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-06-07T19:58:21+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

> Reply from ikskoks ↑Wed Jun 08, 2022 3:09 am at Wed Jun 08, 2022 3:09 am
>
> 
Can you upload a few XTC samples?

Hi Thanks for the reply! I've attached one of the xtc files (zipped)
[T_W36.zip](https://xentaxbackup.github.io/file/22336_T_W36.zip)
## Post #5
- Username: fudgonaut
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-08T22:41:20+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

Hi, format is known and it's partially documented here
[http://wiki.xentax.com/index.php/Starbr ... CD_XWC_XTC](http://wiki.xentax.com/index.php/Starbreeze_Studios_XCD_XWC_XTC)

I've checked some programs and scripts from the wiki, but nothing
really works with your sample.

You can probably rip some textures with TextureFinder,
but more research needs to be done on this format to automatically extract this sample XTC file.
## Post #6
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-06-09T18:38:58+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

Thank you for taking a look at this.

> Reply from ikskoks ↑Thu Jun 09, 2022 6:41 am at Thu Jun 09, 2022 6:41 am
>
> 
You can probably rip some textures with TextureFinder,
but more research needs to be done on this format to automatically extract this sample XTC file.

I found TextureFinder and tried using it, I set the normal .dds to DXT5 and here is the result (diffuse map on top, normal map below)



diffuse-broken-normal.jpg (87.65 KiB) Viewed 80 times



It seems like the output is close, but with some obvious errors. I don't really know anything about DDS formats or using TextureFinder. Is there a tutorial anywhere, I could not find one?

Thanks again for taking the time to respond, I appreciate it!
## Post #7
- Username: fudgonaut
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-09T20:09:36+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

Sadly, there is no tutorial for using TextureFinder.

There is some info on the DDS file format here [http://wiki.xentax.com/index.php/DDS_Image](http://wiki.xentax.com/index.php/DDS_Image)
Also you can google "DDS file format" for more info.
## Post #8
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-06-09T20:32:27+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

That's too bad.   

The days/hours I'll have to invest in learning to successfully extract these textures far outweighs the usefulness of those textures. 

But I thank you for your time!
## Post #9
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-10-10T16:55:47+00:00
- Post Title: Extracting textures from .xtc (Chronicles of Riddick)

I contacted Watto, and they fixed their extractor, now the program can extract .xtc files into usable textures
