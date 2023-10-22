## Post #1
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-07T10:34:37+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

I have no 3dsimed3 and Zmodeler3 so i dont know if it works with those

ForzaTech Engine 

File samples:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/14G99p8E2mFi0AfuFsvrxu8zoX03vsJg-?usp=sharing)
## Post #2
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-07T10:40:00+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

If u need more files like shaders and other stuff just reply
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-07T11:33:16+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from shinzef ↑Sun Nov 07, 2021 6:34 pm at Sun Nov 07, 2021 6:34 pm
>
> 
I have no 3dsimed3 and Zmodeler3 so i dont know if it works with thoseI don't have, too. Works with a 3.5 year old tool of mine ("exterior" chosen, 52 parts):
.



Por718.png (168.96 KiB) Viewed 681 times


Some parts need manual re-positioning, there should be concerning posts on xentax.
(Don't have access to zippyshare any more, so can't tell whether the link in my sig is still active.)
## Post #4
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-07T11:41:50+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

how about textures / glass and wheels does it work for it too?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-07T12:50:49+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

You'll need to try it out. See texture tools from zwrtron (links in his sig): 
> Reply from zwrtron ↑Mon Nov 05, 2018 4:56 pm at Mon Nov 05, 2018 4:56 pm
>
>
## Post #6
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-08T05:46:32+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

so i have tried ur tool
and runned the dir_modelbin.cmd
and used makeh2o_forzahor3-j2 and the other exes but it always closes???

the link that i used
[http://www59.zippyshare.com/v/AhX1Pg1R/file.html](http://www59.zippyshare.com/v/AhX1Pg1R/file.html)

( edit: it seems i need to use the jm9 one but i have no clue on how to use this )
( edit 2: ok i have extracted the models thanks for this tool )
( edit 3: it seems its all in one mesh )
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-08T07:00:00+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from shinzef ↑Mon Nov 08, 2021 1:46 pm at Mon Nov 08, 2021 1:46 pm
>
> 
so i have tried ur tool
and runned the dir_modelbin.cmd  

> and used makeh2o_forzahor3-j2 and the other exes but it always closes???
I have no idea what happened on your system.
You should edit modelbins.txt before loading into an exe.
Such as: delete all lines except exteriors.
Such as: delete all lines except interiors.
Thus you get smaller obj files better to handle in blender.

> ( edit: it seems i need to use the jm9 one but i have no clue on how to use this )Surprise!  
What about reading the readme? (readmeForzaH.txt)

> ( edit 2: ok i have extracted the models thanks for this tool )  

> ( edit 3: it seems its all in one mesh )See above (exterior/interior).

And no, it's not all in one mesh. Usually it's sub meshes. One submesh for each lines in the modelbins.txt. As simple as this.
## Post #8
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-08T07:46:20+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

its one mesh when i imported it idk why

[img][https://imgur.com/a/nCx5sKR/img](https://imgur.com/a/nCx5sKR/img)]

[https://imgur.com/a/nCx5sKR](https://imgur.com/a/nCx5sKR)

i also choosed exterior only and deleted slod
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-08T08:18:49+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

Depends on the model - if it has one .modelbin only then the tool creates one mesh only. Correct.

If there's several .modelbin lines in the modelbins.txt then several sub meshes are being created in the resulting .obj file.
I assume you missed to check "split by group" when importing to blender.
## Post #10
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-08T10:44:49+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

damn thanks for this tool

with some cleanup its a usable model
## Post #11
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-08T13:50:04+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from shinzef ↑Sun Nov 07, 2021 6:34 pm at Sun Nov 07, 2021 6:34 pm
>
> 
I have no 3dsimed3 and Zmodeler3 so i dont know if it works with those

ForzaTech Engine 

File samples:
https://drive.google.com/drive/folders/ ... sp=sharing

What tool did you even use to extract these files if you don't mind me asking?
## Post #12
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-09T01:22:51+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

its just on the game files

FH5/media/cars

all the zips are there
## Post #13
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-09T15:14:10+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from shakotay2 ↑Sun Nov 07, 2021 7:33 pm at Sun Nov 07, 2021 7:33 pm
>
> 

About re-positioning and related posts is there a fix somewhere for not having to reposition everything manually? I am unfortunately getting this error with gr2 to dae:

EDIT: Nevermind, need latest version of the tool. Now I just need to figure out how to properly apply the .dae skeleton to the model.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-09T18:41:57+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

I didn't expect the positioning of parts of Forza models popping into focus again, so here some links, just in case:

positioning (tested with Forza Motorsport only!)

> Reply from shakotay2 ↑Sat Apr 01, 2017 4:59 am at Sat Apr 01, 2017 4:59 am
>
> 

> Reply from shakotay2 ↑Sun Apr 02, 2017 7:39 pm at Sun Apr 02, 2017 7:39 pm
>
> 

The python script mentioned is a two-lines-script at the bottom of the picture in my post as of Fri Mar 31, 2017 9:59 pm

Keep in mind to parent the other child "doorHandleLF" parts such as ??? to their parent "LS0_doorHandleLF_a???"
so that they move all together. (This was for Motorsport, thus I used ??? because the exact names are different for Forza 5, I guess.)
## Post #15
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-10T14:35:22+00:00
- Post Title: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from dimis9138 ↑Tue Nov 09, 2021 11:14 pm at Tue Nov 09, 2021 11:14 pm
>
> 
shakotay2 wrote: ↑Sun Nov 07, 2021 7:33 pm


About re-positioning and related posts is there a fix somewhere for not having to reposition everything manually? I am unfortunately getting this error with gr2 to dae:

EDIT: Nevermind, need latest version of the tool. Now I just need to figure out how to properly apply the .dae skeleton to the model.

would u mind to share the link for gr2 to dae
## Post #16
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-10T16:21:15+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

> Reply from shinzef ↑Wed Nov 10, 2021 10:35 pm at Wed Nov 10, 2021 10:35 pm
>
> 
dimis9138 wrote: ↑Tue Nov 09, 2021 11:14 pm
shakotay2 wrote: ↑Sun Nov 07, 2021 7:33 pm


About re-positioning and related posts is there a fix somewhere for not having to reposition everything manually? I am unfortunately getting this error with gr2 to dae:

EDIT: Nevermind, need latest version of the tool. Now I just need to figure out how to properly apply the .dae skeleton to the model.


would u mind to share the link for gr2 to dae

Just look it up in the motorsport thread, it's called Export Tool, v1.15.10, lmk if you find a way to properly align all parts automatically or the correct scaling x.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-16T13:11:06+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

The tool mentioned to be found here:
[https://github.com/Norbyte/lslib/releases](https://github.com/Norbyte/lslib/releases)
## Post #18
- Username: mrsaturn29
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 17, 2018 8:28 pm
- Post datetime: 2021-11-16T19:02:31+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

Hi, how do I open and convert the avatar/clothing models and textures?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-18T11:49:28+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

I have no idea but I gave the moving of parts another try, Megan RS here:
.



MeganeHood.jpg (52.64 KiB) Viewed 493 times



I changed the position to avoid an overlap at the front of the car but
as you can see there's an assumed gap still. (You need some place for the wipers, yes, but looks strange to me.)

start position x,y,z of hood after obj import to blender: 0.0 -0.10204 0.63490
adding delta 0.0 0.75162 0.95922 manually -> result a) 0.0 0.64958 1.59412

using offsets for hood from skeleton.modelbin (or from .gr2/.dae)
0.000000 0.755660 0.961928  -> result b) 0.0 0,653621 1,596828

(For the trunk it was ok.)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-20T22:40:28+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

Some final thoughts from my side concerning wrong uvs for FH5 models (keep in mind that the tool linked in my sig was for FH3 - I will not dig into this again for FH5.)

But I checked those uvs using hex2obj to get a clue.

The result for wrong uvs: the adresses are "off" (by 12 bytes in this case, wing_race).
Here's a picture (right part:  VW_SciroccoR_11\scene\Exterior\Trunk, wing_race.modelbin)

As you can see on the left, glassF_a uvs are ok
but things go bad for other parts as is wing_race (btw, scale is wrong here, because hex2obj can't correct it).

The wing seems to be devided up "internally" into two parts concerning the uvs, I got one only with a count of 1053 (1453?).
well, complicated, as always... (I thought it were the glassF uvs again, but they're different.)
.



VW_Scirocco.png (196.37 KiB) Viewed 445 times
## Post #21
- Username: mrsaturn29
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 17, 2018 8:28 pm
- Post datetime: 2022-02-08T17:08:36+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

Please, how do I extract the avatar clothing models and textures? Would ninjarip work for getting those models? I really want to access the clothing models in this game, but all I see is about the car models (tried importing clothing model in the one program used for the cars and it didn't work).
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-11T06:59:55+00:00
- Post Title: Re: Forza Horizon 5 ( .modelbin and other bunch of stuff )

Another year has come and gone, so
as I wrote here: 
> Reply from shakotay2 ↑Sun Nov 07, 2021 7:33 pm at Sun Nov 07, 2021 7:33 pm
>
>  5 year old tool for Forza Horizon 3 seems to work for some models in FH5. But no guarantee, so use this on your own risk (read the readme in the zip file).
.


 Make_H2O-ForzaHor3-jm9 (exes).zip
(214.82 KiB) Downloaded 73 times



(Don't have access to zippyshare any more so you may try the link here for yourself 
> Reply from shinzef ↑Mon Nov 08, 2021 1:46 pm at Mon Nov 08, 2021 1:46 pm
>
>  to asure it's the same .zip file.)
