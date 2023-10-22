## Post #1
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2016-11-06T13:09:27+00:00
- Post Title: need help for the nif Noesis Plugin

help Noesis cant inport fallout 3/nv nif
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-06T14:01:22+00:00
- Post Title: need help for the nif Noesis Plugin

maybe - I'm at my old pc atm (old sw versions) where I've only found one supposed NV nif (from vivanto, newvegasnexus) and it can be loaded with Nifskope 1.1.3:



nv_vertibird_interior.JPG (90.41 KiB) Viewed 225 times
## Post #3
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2016-11-06T17:06:08+00:00
- Post Title: need help for the nif Noesis Plugin

> Reply from shakotay2
>
> maybe - I'm at my old pc atm (old sw versions) where I've only found one supposed NV nif (from vivanto, newvegasnexus) and it can be loaded with Nifskope 1.1.3:
The attachment nv_vertibird_interior.JPG is no longer available i am on noesis v4.205 and if i try to load a 3/nv nif noesis do this
[Screenshot 2016-11-06 18.04.54.png](https://xentaxbackup.github.io/file/11885_Screenshot 2016-11-06 18.04.54.png)
## Post #4
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2016-11-09T15:01:08+00:00
- Post Title: need help for the nif Noesis Plugin

it would be really nice if someone could help me with this
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-09T17:57:40+00:00
- Post Title: need help for the nif Noesis Plugin

Guess noone can help you except MrAdults himself.

I made some (ugly) patches to load specific nifs like AncientGiant from  Atlantica Online
but this time it's harder.

(Could be helpful if you uploaded an oblivion nif that is successfully processed by the script.)

Why didn't you try out NifSkope, btw?
## Post #6
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2016-11-09T18:52:44+00:00
- Post Title: need help for the nif Noesis Plugin

> Reply from shakotay2
>
> Guess noone can help you except MrAdults himself.

I made some (ugly) patches to load specific nifs like AncientGiant from  Atlantica Online
but this time it's harder.

(Could be helpful if you uploaded an oblivion nif that is successfully processed by the script.)

Why didn't you try out NifSkope, btw?
because nifskope don't have batch exporting
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-11-10T18:49:00+00:00
- Post Title: need help for the nif Noesis Plugin

> Reply from shakotay2
>
> Guess noone can help you except MrAdults himself.
That's not true. All the Fallout/Skyrim/etc. NIF variants are publicly documented. And the Python script isn't exactly hard to understand. Everything you need is right there in front of you. You can do it! Unless you don't want to do it, in which case I don't blame you, because neither do I. (no idea how much actual effort this would entail, didn't look at the NIF or the differences for FO:NV)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-11T07:48:06+00:00
- Post Title: need help for the nif Noesis Plugin

> Reply from MrAdults
>
> Everything you need is right there in front of you.yeah, I see.  

But I'm too busy with my own projects than to waste lifetime with annoying formats such as "nif".
And as you wrote, that format is "solved", more or less.  I found  the NifConvert project here on my old pc
(guess from skyfox69, [https://github.com/skyfox69/NifUtils/tr ... NifConvert](https://github.com/skyfox69/NifUtils/tree/master/NifConvert)).

Tried it with outfit.nif from Fallout 3\Data\meshes\armor\bosunderarmor\f
and surprisingly the converted nif was loadable by Noesis:



FO3_converted.JPG (35.42 KiB) Viewed 185 times


For other FO3 nifs another Skyrim template might be required!

@philip92dk: if you tried out NifConvert.exe successfully
[http://www.uploadmb.com/dw.php?id=1478849596](http://www.uploadmb.com/dw.php?id=1478849596)

I could think of adding a batch feature to the project.

btw: seems, the skeleton is broken, though
(Shouldn't be a matter of the template because the converter shouldn't deal with bones;
looks like it just copies TriShape from the template.)
