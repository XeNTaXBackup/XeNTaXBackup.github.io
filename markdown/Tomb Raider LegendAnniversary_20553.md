## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-05-26T06:54:57+00:00
- Post Title: Tomb Raider Legend/Anniversary

I'm wanting to extract the models from TR Legend and Anniversary, but I can't find any DMR tools that will extract the actual models with their bones/rigging intact (.tr7mesh/.tr7meshv1 files according to this thread:  [https://www.tombraiderforums.com/showth ... p?t=208182](https://www.tombraiderforums.com/showthread.php?t=208182)).  The DMR tools linked to in that thread don't extract any model files, as far as I can tell.

Does anyone have/know of any tools that are capable of this?
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-05-26T22:59:32+00:00
- Post Title: Tomb Raider Legend/Anniversary

I keep reading about a program called Gibbed.TombRaider.DRMEdit, but the only thing I've found is a GitHub project for it  I've tried compiling he project, but so far no luck.

Does anyone have this program?
## Post #3
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-05-27T21:57:49+00:00
- Post Title: Tomb Raider Legend/Anniversary

OK, I've figured out a way to extract the TR Legend meshes with intact skeletons, using the Graverobber program.  Problem is, Graverobber doesn't extract TR Anniversary models.
## Post #4
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-05-28T21:53:13+00:00
- Post Title: Tomb Raider Legend/Anniversary

Really?  No one can/is willing to help?
## Post #5
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-05-30T20:10:02+00:00
- Post Title: Tomb Raider Legend/Anniversary

Does anyone have gibbed.tombraider.drmedit program from here:  [https://www.tombraiderforums.com/showth ... p?t=214300](https://www.tombraiderforums.com/showthread.php?t=214300)?  None of the links work.
## Post #6
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-05T01:13:19+00:00
- Post Title: Tomb Raider Legend/Anniversary

Still trying to figure out Anniversary, not having much luck.

Using Graverobber or Gh0stblade's DMR extractor, I can extract all of the data from both Legend and Anniversary Lara drms, and the files extracted match up pretty closely.  Except that there are no files for the actual models extracted from the Anniversary drm.

For example, both drms have a file with the magic 5304c204, which I've identified as skeleton files.  There are four of these skeleton files in both drms, one for each model in the drm (in Legend's case).  It's the same for all of the different types of files, each drm has a corresponding file, with similar size and data, EXCEPT for the models.

The problem I'm having is I can't find anything that even suggests that the models are stored in the drm files for Anniversary.  Everything else seems to be present, but no model info anywhere.  But if the model data isn't in the drms, where is it?
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-06-06T09:57:42+00:00
- Post Title: Tomb Raider Legend/Anniversary

I already told you. The models for legend and anniversary are extracted fine by my tools. The problem is that the section flag that determines file type is not used properly by the legend or anniversary engine resulting in file extensions being incorrect for 3d models. Theyre there. Saw them myself but good luck parsing the relocation data properly.

Cheers.
## Post #8
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-06T15:30:03+00:00
- Post Title: Tomb Raider Legend/Anniversary

Could you give me an example, Gh0stblade?  Absolutely NONE of the files I get have any vertex indices that would indicate the presence of a model.  And I have no idea where to start with relocation data.
## Post #9
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-06T22:05:19+00:00
- Post Title: Tomb Raider Legend/Anniversary

[Lara](https://drive.google.com/open?id=1L0ZoiEiRaV7J4tSqEDM3XSo7o1kXcXHE)
[Doppelganger](https://drive.google.com/open?id=1ShCXoAP_yXMofInJNcWGk6dfQVrwEzPw)

Bringing the links to a couple of the TRA drms here.
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-06-07T20:12:14+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from nightwolf1982 ↑Fri Jun 07, 2019 6:05 am at Fri Jun 07, 2019 6:05 am
>
> 
Lara
Doppelganger

Bringing the links to a couple of the TRA drms here.

Lara.drm 5_0.gnc is the model section.
## Post #11
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-07T23:16:51+00:00
- Post Title: Tomb Raider Legend/Anniversary

Nope, I've tested that file, it's the skeleton (the header is even an exact match in structure to Legend Lara's skeleton, 2_0.gnc).  All of the files that start with 0x5304C204 are skeletons.  I can pair them up with Legend models I've extracted, and using your importer for noesis I get skeletons every time.  On top of that, the file size is just too small.  Both Legend and Underworld clock in around 1Mb and 1.4Mb each after extraction, so I would expect Anniversary Lara to run a similar file size.  But at this point, I have no idea where this or any of the games models (characters, costumes or environments) are stored.
[Alister w 5_0.gnc.jpg](https://xentaxbackup.github.io/file/16329_Alister w 5_0.gnc.jpg)
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-06-08T01:42:58+00:00
- Post Title: Tomb Raider Legend/Anniversary

> Reply from nightwolf1982 ↑Sat Jun 08, 2019 7:16 am at Sat Jun 08, 2019 7:16 am
>
> 
Nope, I've tested that file, it's the skeleton (the header is even an exact match in structure to Legend Lara's skeleton, 2_0.gnc).  All of the files that start with 0x5304C204 are skeletons.  I can pair them up with Legend models I've extracted, and using your importer for noesis I get skeletons every time.  On top of that, the file size is just too small.  Both Legend and Underworld clock in around 1Mb and 1.4Mb each after extraction, so I would expect Anniversary Lara to run a similar file size.  But at this point, I have no idea where this or any of the games models (characters, costumes or environments) are stored.
This is 100% the mesh section INCLUDING skeleton.

I've been working with Crystal's mesh format for several years now. And I'm a highly experienced reverse engineer. I KNOW what I'm talking about and I have a lot more experience than what you do.

Your argument is the filesize is too small? Do not underestimate the size of 3D models. I already told you the file is much smaller than Legend Lara's file. Just because the file is smaller. It does not in any way invalidate the fact it's a model file.

IIRC the legend mesh format stores multiple lods. That is probably why the filesize in Legend is generally larger.

I see vertices and face indices no problem. It's 100% Lara's model section.

Cheers.
## Post #13
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-08T06:08:02+00:00
- Post Title: Tomb Raider Legend/Anniversary

I'm not doubting your credentials or skills, I'm trying to find some way of getting these models into a more common format.  I work with 3d models all the time, I know how much information can be packed into even the smallest file sizes.

Being condescending and just telling me it's the model isn't going to convince me.  SHOW it.  Yes, I saw the same data you did, the garbled alphabet section that could be face indices, the block of what look like vertices, even the potential UV data right above those.  But so far I haven't even been able to get a basic point cloud with hex2obj, and the file obviously won't work in any 3D program without an import plugin or script.
