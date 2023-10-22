## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-11-23T03:43:38+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

After banging my head against the Xbox 360 files for months, I finally got hold of the PS3 version of the Force Unleashed 2 DLC, and I finally have a better idea of how this stuff is put together.

After extracting the .arc files with Noesis, The files break down into 3 folders, AUDIO, LEVELPACKS, and NLP.  The LEVELPACKS folder contains the LP files (ENDOR1_PS3.LP, PLAYERBLOODARMOUR.ACTOR.XML_PS3.LP, etc...)  while the NLP folder contains a number of CLUSTER files (CPU#.CLUSTER, GPU#.CLUSTER) and a TEST.LEVELPACKMETADATA.  It's in the CLUSTER files that the models and textures are stored, and the LPMD somehow links everything together.  This is where I'm now hitting a brick wall, though, as I can't seem to find the links between the LPMD file and the CLUSTER files.

links for samples:
ackbar:
[https://drive.google.com/file/d/1lR47Em ... sp=sharing](https://drive.google.com/file/d/1lR47EmYyVX5OsSy9SrKMQ37koddGwkpw/view?usp=sharing)
bloodarmour:
[https://drive.google.com/file/d/19CpBFO ... sp=sharing](https://drive.google.com/file/d/19CpBFOGKiK60WTAtstffmjMWQPitPJTL/view?usp=sharing)
sith starkiller:
[https://drive.google.com/file/d/1a-RoD3 ... sp=sharing](https://drive.google.com/file/d/1a-RoD3Qn-bUdSO0oM3gt81OeMz2dNNnp/view?usp=sharing)
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-15T04:07:55+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

Has anyone taken a look at these?
## Post #3
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-17T22:31:18+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

Seriously, I think this is the key to getting to the Endor DLC models;  I can't believe no one is interested in them, even after all this time.


The LevelPackMetaData files have tables with the file directories and names, and directly references the different CPU and GPU CLUSTER files.  If someone can figure out how these are connected, (this is beyond my meager coding skills, sadly), then we'll have a way to access models we've never been able to get to before.


zaramot? daemon1? Anyone?
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-11-17T23:03:50+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

Yup, now it's all there all the info to build the model. Damn, I remember I had some hard times getting those models out long ago. Especially Leia, since it's not a player costume etc.
Those two models were cool though, sadly have no idea where they are now lol It happens:( 
[https://www.deviantart.com/elonir/art/S ... -549458161](https://www.deviantart.com/elonir/art/Star-Wars-The-Force-Unleashed-2-SK-Blood-Armor-549458161)
[https://www.deviantart.com/elonir/art/S ... -549728029](https://www.deviantart.com/elonir/art/SW-The-Force-Unleashed-2-Starkiller-Jedi-Hunter-549728029)
## Post #5
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-18T00:06:00+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

The question now is how do we build them?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-18T04:18:54+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> Seriously, I think this is the key to getting to the Endor DLC models;  I can't believe no one is interested in them, even after all this time.Seriously, what do you expect? Going just straight into structures (which you do present nothing of)  without talking about models?
Did you try to get a pointcloud at least?



CPU4-Cluster.png (65.5 KiB) Viewed 229 times

(face indices not found so far.)

> The LevelPackMetaData files have tables with the file directories and names, and directly references the different CPU and GPU CLUSTER files.  If someone can figure out how these are connected, (this is beyond my meager coding skills, sadly),Which coding skills do you have then?
And without knowing vertex count and/or face indices count all examining the LevelPackMetaData will end up in wild guessing.

filesizes of CPU0, 4 and 8 in TEST.LPMD:
0x4A85: 0x400000 = 4194304
0x4B15: 0x043000 = 274432
0x4BA5: 0x191000 = 1642496
## Post #7
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-19T00:15:36+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

shakotay2:  There is absolutely no reason to be rude.  I've openly admitted that what little skills I have aren't up to figuring this out.  Every time I've tried to get help, I've been met with either complete disinterest, or open hostility.

I'm sorry;  I haven't had years to build experience and skill in ferreting out which part of the hex code is possibly a vertex and which is referencing file sizes - that's why I'm asking for help.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-19T00:25:49+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> shakotay2:  There is absolutely no reason to be rude.  I've openly admitted that what little skills I have aren't up to figuring this out.  Every time I've tried to get help, I've been met with either complete disinterest, or open hostilityI don't know what you're talking about. If you think I'm hostile (which is nonsense, btw) I'll better leave you alone with your request. 
cheers
## Post #9
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-19T01:01:11+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

shakotay2:  Your response seemed a bit rude to me, as if you thought this was something so easy to figure out anyone could do it.

I never said you were hostile, only that I've encountered hostility in trying to get help with these models.
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-11-19T17:14:05+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

Ah, shakotay2 is most kind and helpful person we could ever imagine lol So, no hostility for sure! As for complete disinterest, well nightwolf1982, friend you should understand - at least me for example. Force Unleashed 2 dlc models it's such an example, when there's a tool for 1 and 2 game, and all models even available on many 3d sites. So, basically someone should put time and efforts to get - how much 10 new models max? Which are right now, completely outdated comparing to quality of modern 3d models (there are tools for Battlefront 2 and most of characters are there). Yes, yes I understand there are some fans, and you love those models - but generally - this just doesn't worth it for most of people. I extracted DLC models long time ago for a great friend of mine, and to say the truth, it was least what I could do xD If they were still in my possession - be sure, I would send them to you, but they were lost. Lol all this mess I wrote just to clarify how I see this situation, please don't be upset:)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-19T17:48:58+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

> Reply from zaramot
>
> So, basically someone should put time and efforts to get - how much 10 new models max?yeah, so some efforts from the requester are needed.

@nightwolf1982: so you might wait another year 'til someone hopefully gets a model for you or decide to improve your coding skills. The problem is not the vertices (which are shown by hex2obj as a point cloud) but the face indices.

Trying autocreated faces (buttons: 'Strip' 'Fake') results in an ugly mesh.
That's due to the doubles which you could remove manually if you can't do it via coding.



CPU4-CLUSTER-vertices.png (64.09 KiB) Viewed 184 times


I can't promiss, though, that the mesh will be fine after having removed dozens of doubles!

(test.obj, created after pressing the 'mesh' button)
# 0x3285: verts= 2165
v 0.074714 1.640210 0.013302 
v 0.074714 1.640210 0.013302 # delete
v 0.077186 1.643950 0.018280 
v 0.068202 1.647185 0.011111 
v 0.068202 1.647185 0.011111  # delete
v 0.115428 1.635206 0.000563 
v 0.114793 1.635083 0.003641 
v 0.100902 1.634500 0.000476 
v 0.100902 1.634500 0.000476  # delete
v 0.100902 1.634500 0.000476  # delete
v 0.071353 1.651835 0.010310 
[...]
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-19T18:36:10+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

ok, that didn't do the trick - I removed about 140 doubles but as you can see from the resulting mesh there's 2 or three more rules to be followed which I don't know (quads, winding, face culling, whatever):



doublesRemoved.png (99.46 KiB) Viewed 182 times
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-11-19T18:57:02+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

Wow, wow shakotay2, my friend - you don't have to "generate" anything, please check GPU6 file too, I bet it will make more sense xD
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-19T20:39:29+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

I see, thanks!  (I'll check it tomorrow).
## Post #15
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-19T23:22:58+00:00
- Post Title: New Progress on Force Unleashed 2 DLC

I have been trying to extract models on my own, but there's only so much online tutorials can teach.  For example, the few tutorials I've read all state that the face indices are usually stored as integers, and the data will look like a scrambled alphabet in text view.  There are at least two or three blocks of data that fit that description in these files;  but none of them seem to be the indices.  Or if any of them are, I haven't found the right starting address.

Then there's the vertex info.  I think I know how the starting address is being found (the hex value reads xx xx xx xx 3F), but there are far more entries that follow this than are being read by hex2obj.  But if I put anything in other than the info shown in the examples, either nothing happens or I get weird looking point clouds.  Except these are supposed to be full character models.

I'm not asking for help just to be lazy or not get better, I'm asking bcause I genuinely just don't know where to go next.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-20T19:57:54+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

I checked cpu6.cluster (as advised by zaramot   ) and this is the result:



GPU6-CLUSTER.png (129.22 KiB) Viewed 137 times



H2O file:
0x0 12000
Vb1
32 99
0x5E0C 2166
120000
0x0 255

(uvs not checked so far)
## Post #17
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-20T22:25:50+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

I think we're a bit off from what I was trying to accomplish here.  I'm trying to find a way to extract character models (specifically Jedi Leia) from the larger Endor DLC files.  I do appreciate shakotay2's efforts, but I'm not seeing how he's getting the results he's getting.

This is all I've gleaned so far, based on the examples posted and the tutorials I've looked at:

The GPU files appear to store both the face indices and the vertex information for the models (based on shakotay2's last post)

The vertices seem to be coded in hex in the pattern of 3d xx xx xx 3f, though not every set is a vertex

The face index count is roughly the length of the data chunk divided by 2 (again based on shakotay2's last post)
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-21T07:48:21+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> I think we're a bit off from what I was trying to accomplish here.  I'm trying to find a way to extract character models (specifically Jedi Leia) from the larger Endor DLC files.  I do appreciate shakotay2's efforts, but I'm not seeing how he's getting the results he's getting.Again I don't know what you are talking about.
I checked the files from the 2nd link in your opening post:
[https://drive.google.com/file/d/19CpBFO ... tPJTL/view](https://drive.google.com/file/d/19CpBFOGKiK60WTAtstffmjMWQPitPJTL/view)
especially GPU6.CLUSTER.

You can get the head by copying the 6 lines (which I wrote in my previous post) into a text file and rename it to whatever_head.H2O.
Load the GPU6.CLUSTER into hex2obj (File/Open) then File/Open H2O to open the H2O file.
Press the mesh button and the head should be displayed.

(Also keep in mind that it's big endian here, so 00 00 80 3F is 3F 80 00 00 in the files.)

Guess the basic problem is that you don't know how to get the vertices start address. You need some experience for this. There's some trial and error when you try to create point clouds but it's not "magic" especially because the FVFsize is given (32).
(If you don't know what FVFsize is I would suggest to read the tutorial again (tut button in hex2obj) and try out some simple models in the dozens of posts using hex2obj.)

I'm off now; good luck with your further research.
## Post #19
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-24T03:25:19+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

I finally figured out what I was doing wrong with Hex2Obj, I wasn't using the correct FVF sizes.  So, now I've found the face/vertex data for the Endor Leia Costume (Image 1).  However, I haven't been able to figure out the UV's yet.  

Another problem is that GPU51 seems to be the only file that has mesh information, but the whole file only holds the Endor Leia costume.  In the rest of the files that might contain models, each potential model has a section of code that doesn't appear to be vertex data (Image 2) followed by a section that might contain vertex info; but I haven't been able to get any useful point clouds (Image 3).
[Image 1.png](https://xentaxbackup.github.io/file/15228_Image 1.png)
## Post #20
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-24T03:26:01+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

second image:
[Image 2.png](https://xentaxbackup.github.io/file/15229_Image 2.png)
## Post #21
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-24T03:26:34+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

third image:
[Image 3.png](https://xentaxbackup.github.io/file/15230_Image 3.png)
## Post #22
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-11-24T03:43:39+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

I've uploaded the H2O and GPU files for the Endor Leia costume as well as the files I think have possible model data.

Leia Endor:
[https://drive.google.com/open?id=1mL9YH ... j5qJ4RG4BD](https://drive.google.com/open?id=1mL9YHbXUuZk-5RuD_F0y1Gj5qJ4RG4BD)

GPU Files:
[https://drive.google.com/open?id=12mfOp ... aaWBQyFc9N](https://drive.google.com/open?id=12mfOppmU78TENwPminBH6yaaWBQyFc9N)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-24T06:40:08+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> I finally figured out what I was doing wrong with Hex2Obj, I wasn't using the correct FVF sizes.Very cool that you skipped this hurdle! 

> Reply from nightwolf1982
>
> So, now I've found the face/vertex data for the Endor Leia Costume (Image 1).  However, I haven't been able to figure out the UV's yet.That's where some experience would come in handy:



GPU51-CLUSTER.png (48.73 KiB) Viewed 110 times


approach to start of uvs (0x8780C):
start of vertices 0x7F500 + vcount 1676 x FVFsize 20 = 0x877F0

(As I wrote in other threads: there's no general recipe to get the uvs. In most cases they are in the FVF block but here they're not. After having analyzed some dozens of different 3D formats you'll know more.)
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-24T11:09:13+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

In GPU16.CLUSTER mesh uses half floats, uvs use shorts ("WordUV"). Search for threads where a workaround for hex2obj is described (since it doesn't provide this combination. You can SaveAs mesh with HF_all selected then switch to WordUV, again SaveAs mesh and copy/overwrite the uvs  from that obj to the first one).



GPU16-CLUSTER.png (119.47 KiB) Viewed 104 times
## Post #25
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-02T05:30:21+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

Big thanks to shakotay2, I'm now getting meshes from some of the files.  Unfortunately, I'm still not finding the one model I'm wanting, Jedi Leia.

I've been taking a close look at the LPMD files, and this is what I've found:

```
0x04 = 0000000b - Version?
0x08 = ???? - 0047b000 for all of the Player Outfits
0x0c = ???? - 07dc0000 for the Endor1 and Endor2 files, 00f19999 for all of the Player Outfits
0x10 = ????
0x14 = 00000034
0x18 = 00000001
0x1c = Hex Address 28 bytes from ENUS
0x30 = ????
0x34 = 00000000
0x38 = ffffffc7
0x3c = ????
0x40 = ????
0x44 = Hex Address 67 bytes from STRG / 83 bytes from the string table
0x48 = ????
0x4c = 00000000

0x50 = f0e0d413 - Found throughout two sections of the file, immediately before and after the ENUS section

ENUS - Address varies from file to file

	Unit32 - ENUS
	Unit32 - File Count
	Unit32 - File Number
	Unit32 - ?
	Unit32 - ?
	Unit32 - File Size
	Unit32 - Pad
	Unit32 - Pad
	Unit32 - ?
	Unit32 - ?
	Unit32 - ?

Immediately after the STRG table, there are data blocks for each CLUSTER file, including the full path and name of the file.
```
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-02T06:10:12+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> I've been taking a close look at the LPMD files
you should've treated these samples like an archive from the beginning since all the offsets and 
names etc are given, break it down to smaller manageable files and it could be easier to work from.
if aluigi had seen these files he could have possibly had an extraction script on the same day.
## Post #27
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-02T23:43:42+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

The problem I'm having is that while I can partly break down the LPMD file, I'm not experienced enough to figure out how it links out to the CLUSTER files.

For example, I suspect that the hex value f0e0d413 is somehow linked to individual files, but I have no idea how that works.  I'm also not certain how the CLUSTER data blocks at the end of the file work.
## Post #28
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-06T04:33:23+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

Little bit more info

```
0x04 = 0000000b - Version?
0x08 = ???? - 0047b000 for all of the Player Outfits
0x0c = ???? - 07dc0000 for the Endor1 and Endor2 files, 00f19999 for all of the Player Outfits
0x10 = ????
0x14 = 00000034
0x18 = 00000001
0x1c = Hex Address 28 bytes from ENUS
0x30 = ????
0x34 = 00000000
0x38 = ffffffc7
0x3c = ????
0x40 = ????
0x44 = Hex Address 68 bytes from STRG / 84 bytes from the string table
0x48 = ????
0x4c = 00000000

0x50 = f0e0d413 - Found throughout two sections of the file, immediately before and after the ENUS section
       
       f934f180 - Found Before and after ENUS; lines up with f0e0d413; Always appears 28 bytes before "GPU" and immediately after "GPU"

      1d9e31ba - Found before and after ENUS; lines up with f0e0d413; Always appears after "LCPU", "SCPU", and "SGPU"

ENUS - Address varies from file to file

	Unit32 - ENUS
	Unit32 - File Count
	Unit32 - File Number
	Unit32 - ? - Can be 0x00 or 0x01
	Unit32 - 0x02
	Unit32 - File Size
	Unit32 - Pad
	Unit32 - Pad
	Unit32 - ?
	Unit32 - ?
	Unit32 - ?

Immediately after the STRG table, there are data blocks for each CLUSTER file, including the full path and name of the file.
```
## Post #29
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-06T19:32:02+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

Success!! I've found Jedi Leia!  I've managed to extract most of her mesh, but I'm running into an issue with her skirts [https://drive.google.com/open?id=1kqVOM ... 53TlxQ02cG](https://drive.google.com/open?id=1kqVOMxU7Af_legM6vT_EpL53TlxQ02cG)

I can get what should be the mesh, but it's full of holes, and I haven't been able to pin down the UVs.

I've uploaded the CLUSTER and h2o files I've got here.  [https://drive.google.com/open?id=1kbZmj ... D9nkxY7PCS](https://drive.google.com/open?id=1kbZmjkMxyYt6HxheZ0WjNmD9nkxY7PCS)
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-06T20:19:32+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> Success!! I've found Jedi Leia!  I've managed to extract most of her mesh,Great!  
I always wish  that people make progress - seems you're one of them.

Switch to (triangle) Strip(s) for the shirt, uvs are a little bit tricky here (I started with 0x2A80 and increased by 4 until they matched, so just brute force:D)

(6 lines for H2O file):

0x1780 450
Vb1
20 99
0x1B80 188
121000
0x2A8C 56

(One face seems to be missing, though. Dunno why.)
## Post #31
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-06T22:30:37+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

YES!!  Success!!  A HUGE thank you to shakotay2 for all of his help, I finally extracted Jedi Leia!
[Jedi Leia.jpg](https://xentaxbackup.github.io/file/15284_Jedi Leia.jpg)
## Post #32
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-06T22:40:56+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

> Reply from nightwolf1982
>
> Little bit more info....
guess you didn't get the hint in my last post.   
unless you are taking this on as a personal challenge you 
should create a new thread in the Game Archive section of 
zenhax and aluigi will most likely know what to do with it.
## Post #33
- Username: GPChannel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2021 3:42 pm
- Post datetime: 2021-01-31T12:17:15+00:00
- Post Title: Re: New Progress on Force Unleashed 2 DLC

Hey everyone!
Maybe someone can help me to port Darth Malak from TFU2 ps3 DLC?

I have the CPU files of Malak,but i have no experience with coding,so maybe can someone help?
