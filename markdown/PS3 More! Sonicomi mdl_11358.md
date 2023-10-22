## Post #1
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-03-24T09:57:30+00:00
- Post Title: PS3 More! Sonicomi mdl

Could anyone take a look at the mdl files in the ps3 game More! Sonicomi?
Textures are plain gtf files and mtl files seem to be material information.

Sample: [http://www.mediafire.com/download/wvywp ... hood_a.rar](http://www.mediafire.com/download/wvywp7l5s5wtllh/out_nekohood_a.rar)
## Post #2
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-03-25T09:48:56+00:00
- Post Title: PS3 More! Sonicomi mdl

did they use the same .mdl format?
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-03-25T17:21:34+00:00
- Post Title: PS3 More! Sonicomi mdl

One solution is the updated 3D Object Converter:
[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.311_portable.zip)

The out_nekohood_a\out_nekohood_a.mdl file have references to the following file (or material name ?):
out_nekohood_a_ncl1_2      (???)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-25T21:48:07+00:00
- Post Title: PS3 More! Sonicomi mdl

Another solution is the sonicomi py script from Mariusz Szkaradek which I adapted for PS3 More! Sonicomi.
But it's in an experimental state:
[](http://www.pic-upload.de/view-22669047/nekohood_.jpg.html)
## Post #5
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-03-29T09:29:15+00:00
- Post Title: PS3 More! Sonicomi mdl

Nice job on the script shakotay2 I hope your able to make it fully functional and good luck.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-29T17:22:03+00:00
- Post Title: PS3 More! Sonicomi mdl

> Reply from mikulover39
>
> Nice job on the script shakotay2Thx. It wasn't too hard since Mariusz did >90% of the pre work.

> I hope your able to make it fully functional and good luck.
I would need another 3 mdl samples for testing (the mdl only, plz, to keep the zip small).
## Post #7
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-03-29T17:56:44+00:00
- Post Title: PS3 More! Sonicomi mdl

Here you go another sample.
[http://www.mediafire.com/download/isjt0 ... sonico.zip](http://www.mediafire.com/download/isjt09daj3rszco/sonico.zip)

hope it works!
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-30T10:18:37+00:00
- Post Title: PS3 More! Sonicomi mdl

Thx! I've PM'ed you a blend file for testing other samples.

[](http://www.pic-upload.de/view-22712845/nekohood-ex_kill_uv.jpg.html)
## Post #9
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2014-03-30T11:38:12+00:00
- Post Title: PS3 More! Sonicomi mdl

> Reply from shakotay2
>
> Thx! I've PM'ed you a blend file for testing other samples.

Looking forward to your release
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-30T15:44:10+00:00
- Post Title: PS3 More! Sonicomi mdl

Since mikulover39 wrote me that "it works great for mostly everything"
here's the script in a blend file: [http://www.uploadmb.com/dw.php?id=1396173697](http://www.uploadmb.com/dw.php?id=1396173697)

(though I have a strange feeling that the skinning doesn't work. No time to check this atm.
Maybe the parenting of the bones needs some big endian correction.)

Working with blender versions <= 2.49b only.
In the text window press alt-p to start the script and select an mdf file to load.

The PS3 More! Sonicomi script is based on Mariusz Szkaradek's sonicomi blend file.
I didn't adapt anm support so far.
Doesn't work with stage models.

All errors you might meet with this script are caused by my dump adaption
so don't blame Mariusz for it! Never ever!

(I used a fake PHSX chunk as a stop flag for reaching file's end. So don't be surprised to find
'PHSX' in console output even if there's no such chunk in the mdl file.)
## Post #11
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-01T00:08:53+00:00
- Post Title: PS3 More! Sonicomi mdl

mmm... some models are cycling the script lol:

[http://www.mediafire.com/download/xrpa4 ... modelo.rar](http://www.mediafire.com/download/xrpa44j2xaxz76h/modelo.rar)

Edit: never mind, those were moprhs lol.
## Post #12
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-01T02:10:00+00:00
- Post Title: PS3 More! Sonicomi mdl

Actually I found a problem with this model:

[https://www.mediafire.com/?clefr4e37yct1yv](https://www.mediafire.com/?clefr4e37yct1yv)

Array index out of range.
## Post #13
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-04-01T10:03:33+00:00
- Post Title: PS3 More! Sonicomi mdl

The problem is to do with line 363 "for k in range(start,end):"
It seems like the script wont find the end of the 2nd object, changing it to "for k in range(start):" to import it correctly so try that for now.
## Post #14
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-01T15:25:21+00:00
- Post Title: PS3 More! Sonicomi mdl

> Reply from mikulover39
>
> The problem is to do with line 363 "for k in range(start,end):"
It seems like the script wont find the end of the 2nd object, changing it to "for k in range(start):" to import it correctly so try that for now.

Okas, thanks It worked, and for extracting textures, what are you using?? texture finder?? Because I used it and it helped to te determine what kind of texture It is and just put a dtx header.
## Post #15
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-02T15:59:12+00:00
- Post Title: PS3 More! Sonicomi mdl

This is what you can do with Sonico:

[https://www.youtube.com/watch?v=vPujV1jXNVc](https://www.youtube.com/watch?v=vPujV1jXNVc)

Fap as you wish
## Post #16
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-17T19:57:14+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

Hi 

Here is an animation importer for models of Sonico.
It requires Blender 249 and Python 26.

In Blender Text Window press alt+p and select .mdl or .anm file.
Some animations are not supported, so if Blender is freeze, please in blender console press lctr+c


Updated 2014-12-18:
For morhing of face please try this way:
1.import sonico_base.mdl (for solid meshes)
2.import .mdl file with word "morph" in filename (for points meshes)
3.change in Blender Text Window script on morph.py
4.select in Blender Outliner morph mesh with word "eye" or "mouth" in mesh name
5.run script (press alt+p)
[Blender249[MottoSonicomi][PS3][mdl][anm][2014-12-18].zip](https://xentaxbackup.github.io/file/8297_Blender249[MottoSonicomi][PS3][mdl][anm][2014-12-18].zip)
## Post #17
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-12-18T04:43:45+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

> Reply from Szkaradek123
>
> Hi 

Here is an animation importer for models of Sonico.
It requires Blender 249 and Python 26.

In Blender Text Window press alt+p and select .mdl or .anm file.
Some animations are not supported, so if Blender is freeze, please in blender console press lctr+c

Sorry to ask this but, does the importer support target morphs??
## Post #18
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-18T05:32:56+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

> Reply from Szkaradek123
>
> Hi 

Here is an animation importer for models of Sonico.
It requires Blender 249 and Python 26.

In Blender Text Window press alt+p and select .mdl or .anm file.
Some animations are not supported, so if Blender is freeze, please in blender console press lctr+cThank you for your great work, my friends, this script runs perfectly. Can you please support PC2.0, here is a sample file:[https://onedrive.live.com/redir?resid=6 ... file%2crar](https://onedrive.live.com/redir?resid=6A28B826BE5F1236!154&authkey=!ALGq3ftP-WgPd3Q&ithint=file%2Crar)
## Post #19
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-18T08:07:21+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

Hi

@Darko 
i have updated importer for morph targets.

@raykingnihong
Trials games are not supported . After unpacking with nipa  files are corrupted.
## Post #20
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-18T11:04:36+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

> Reply from Szkaradek123
>
> Hi

@Darko 
i have updated importer for morph targets.

@raykingnihong
Trials games are not supported . After unpacking with nipa  files are corrupted.Thank you very much for your reply, thank you my friend
## Post #21
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-19T06:20:54+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

> Reply from Szkaradek123
>
> Hi 

Here is an animation importer for models of Sonico.
It requires Blender 249 and Python 26.

In Blender Text Window press alt+p and select .mdl or .anm file.
Some animations are not supported, so if Blender is freeze, please in blender console press lctr+c


Updated 2014-12-18:
For morhing of face please try this way:
1.import sonico_base.mdl (for solid meshes)
2.import .mdl file with word "morph" in filename (for points meshes)
3.change in Blender Text Window script on morph.py
4.select in Blender Outliner morph mesh with word "eye" or "mouth" in mesh name
5.run script (press alt+p)Hello, my friends, thank you for your update, thank you
## Post #22
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-12-22T15:00:35+00:00
- Post Title: Re: PS3 More! Sonicomi mdl

Thanks for the morphs:

[https://www.youtube.com/watch?v=ZNtBVmuQaQA](https://www.youtube.com/watch?v=ZNtBVmuQaQA)
