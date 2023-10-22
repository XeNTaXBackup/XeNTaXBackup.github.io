## Post #1
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2017-01-11T22:50:00+00:00
- Post Title: Trials Fusion "Unboxed"

Hi, I'm urrently trying to edit head meshes and textures of [Trials Fusion](http://store.steampowered.com/app/245490/).

Extraction
The first step is already done, the game's .pak contents were extracted by using information from [this thread](http://forum.xentax.com/viewtopic.php?f=10&t=8861).
Now there's a collection of .gfx, .mdl and ".png.tex" files to comb through, and I hit my first roadblock...


Models
Vertex data seems to be stored in .mdl files. Unfortunately these are absolutely not valve's source engine format. A quick look with HxD reveals a header with the following clear text:
[](http://i.imgur.com/EoFPH57.png)
The rest is binary data. Google doesn't spit out anything useful for any of these keywords. No converter I tried could do anything with these.


Textures
Apparently stored in the .png.tex files, and again, I am quite sure that these are not LaTeX document descriptions. Header seems to be 24 bytes followed by a 16-byte pattern. Starts with "T8X"
[](http://i.imgur.com/meCqzwB.png)
edit: textures now have a noesis script available (see second post)

I've uploaded a [small package with sample files of each type](https://www.dropbox.com/s/l7xxdf9tr7p73nn/TrialsFusionExamples.rar?dl=0).

The .gfx files seem to be irrelevant, containing some sort of directory for possible choices of vehicle parts/driver heads. Some googling lead to a suite of [WiiU resource extraction tools](https://github.com/NWPlayer123/WiiUTools), but that did not help much, either. None of these are contained in the "common model formats" lists. Gldataview shows no hint of a texture, Noesis can't open.
I'm stuck now and would be so grateful for any hint on how to proceed here.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-12T02:42:21+00:00
- Post Title: Trials Fusion "Unboxed"

here is a Noesis python script to open your texture samples  
*updated Jan 27, 2017*


 tex_TrialsFusion_tex.zip
(851 Bytes) Downloaded 35 times


only supports dxt5 because all of your samples were
## Post #3
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2017-01-12T18:42:47+00:00
- Post Title: Trials Fusion "Unboxed"

Thanks AceWell, works like a charm on most of them!

In the meantime I tried to extract the rider parts directly using NinjaRipper, but the model rip data is scrambled and the textures get some heavy tiling, so thats not really an option.
It also seems like the parts I'm really after (the Ubi bonus characters) are locked in another .pak file that can't be extracted by the current quickBMS script, so I might just have to put this project on ice until that is solved 
Thanks for the quick help anyway, appreciate it.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-12T18:49:15+00:00
- Post Title: Trials Fusion "Unboxed"

> Reply from Jaw
>
> works like a charm on most of them!
can you upload some not-working samples so i can try adding support to the script?
## Post #5
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2017-01-12T21:56:27+00:00
- Post Title: Trials Fusion "Unboxed"

Sure, here's [another sample pack](https://www.dropbox.com/s/07ztywltl9rp6pu/TrialsFusionExamples3.rar?dl=0) with what seems to be mostly menu elements and icons.

Aaand... no driver textures to be found, must be included in the mdl files. typical
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-27T14:10:03+00:00
- Post Title: Trials Fusion "Unboxed"

i updated the script here to open your new texture samples   
[viewtopic.php?p=126073#p126073](http://forum.xentax.com/viewtopic.php?p=126073#p126073)
## Post #7
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2017-01-31T21:52:48+00:00
- Post Title: Trials Fusion "Unboxed"

Working like a charm. Can't find any more incompatible tex files so far.

Does anyone happen to know a tool that will piece scrambled textures like this back together? Produced by ninjaripper, since character textures are somehow still absent from the .pak files...
(it's resized - the original was a 65MB dds)
[http://imgur.com/4GSXa7g](http://imgur.com/4GSXa7g)
