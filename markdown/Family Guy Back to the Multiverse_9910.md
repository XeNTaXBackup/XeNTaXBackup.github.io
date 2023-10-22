## Post #1
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2012-11-24T23:22:03+00:00
- Post Title: Family Guy: Back to the Multiverse

Need help with *.ho files.

Few files:
[http://www12.zippyshare.com/v/54891237/file.html](http://www12.zippyshare.com/v/54891237/file.html)
or
[http://www.sendspace.com/file/dm7fo7](http://www.sendspace.com/file/dm7fo7)

These files use some alignment.
I can not understand how.
## Post #2
- Username: SanGat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 07, 2012 11:56 pm
- Post datetime: 2012-11-25T16:06:50+00:00
- Post Title: Family Guy: Back to the Multiverse

Game Extractor can open this files. 
P.S. Udachi s perevodom.
## Post #3
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2012-11-25T18:41:22+00:00
- Post Title: Family Guy: Back to the Multiverse

> Reply from SanGat
>
> Game Extractor can open this files. 
P.S. Udachi s perevodom.
How?
I'm trying, but it does not work.
## Post #4
- Username: SanGat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 07, 2012 11:56 pm
- Post datetime: 2012-11-26T15:44:04+00:00
- Post Title: Family Guy: Back to the Multiverse

> Reply from MeteoraMan
>
> How?
I'm trying, but it does not work.
Just dblclick on archive. [Img](http://i47.fastpic.ru/big/2012/1126/88/388f3212500ba4d47fc3c4c1e6aa7888.png)
## Post #5
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-12-01T21:10:25+00:00
- Post Title: Family Guy: Back to the Multiverse

Anyone knows in which files are the texts of this game?
## Post #6
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-12-08T14:24:35+00:00
- Post Title: Family Guy: Back to the Multiverse

any help?
## Post #7
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2012-12-09T22:01:43+00:00
- Post Title: Family Guy: Back to the Multiverse

Can anyone else find anything other than dds files?
Ive tried every archive in the players folder and ive looked at a lot of the levels archives, the only thing game extractor seems to find is dds files.. Anyone know how to find 3d objects or anything like that?

Or is anyone working on a model extractor for family guy.. If anyone needs any of the archives i can supply them, just PM me.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-12T13:24:31+00:00
- Post Title: Family Guy: Back to the Multiverse

Maybe someone could write a quick bms script?

I upload as an attachment small copies of the archives from this game made by WATTOs file cutter
It will be helpful.
[MNUS.ho & BULK.ho.rar](https://xentaxbackup.github.io/file/6083_MNUS.ho & BULK.ho.rar)
## Post #9
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-20T22:47:18+00:00
- Post Title: Family Guy: Back to the Multiverse

I've managed to get some model and texture data out of the .ho files.





Theres a lot I haven't figured out yet though.  Like where the pointers are.

It seems the only model data I can find faces for is in the HAVK blocks.

I've found some other vertex data in some of the other blocks though, but with no faces.

Every mesh I've found so far is just a weapon.

For the models I found only verts for, I made my tool output a maxscript that draws spheres where the verts would be.



At least using this method I can see the general shape of the model that the test data represents.

Anyone else taken a look at this game's .ho files?
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-20T23:10:29+00:00
- Post Title: Family Guy: Back to the Multiverse

> I've managed to get some model and texture data out of the .ho files.

Good for us! 

How did you get these models? Are you going to extract other data from this archives?

I cross my fingers for you ;p
## Post #11
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-20T23:16:28+00:00
- Post Title: Family Guy: Back to the Multiverse

> Reply from ikskoks
>
> How did you get these models?

I wrote a tool that can grab data from specified pointers. So if you know the data's pointer offset, and size.  You can attempt to extract it to either tga, or obj depending on if the data is texture data or mesh data.



I'm going to add brute force zlib and lzo in some new tabs soon.  For now it finds image data in every game I've thrown at it.  The mesh extraction works across multiples games too if you know the pointer offsets.

...

I added injection for texture data.

This is the PLYN.ho Brian regular costume with a gradient map over it.





PLYN didn't mod the ingame character though, so I'm going to try some of the other ho files.
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-20T23:32:33+00:00
- Post Title: Family Guy: Back to the Multiverse

So, I'll wait until you release your tool ;p

Do you plan to add an import option of edited textures, models etc. in the future?
## Post #13
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-20T23:54:02+00:00
- Post Title: Family Guy: Back to the Multiverse

The image extraction section works by looking at the scanned section output in this template.



You specify the block number where the texture starts, and specify its resolution.  Its pretty easy to get any resolution image out by looking at this template.

For instance, the texture in the above post is extracted by specifying 32505856 for the data base offset, 118 for the block number, 512 x 512 for the resolution, and 262144 for the image data size.
## Post #14
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-21T00:06:48+00:00
- Post Title: Family Guy: Back to the Multiverse

> Reply from ikskoks
>
> So, I'll wait until you release your tool ;p

Do you plan to add an import option of edited textures, models etc. in the future?

I usually add import options to my tools, I'm not sure what the forum rules are on posting those types of tools though.  Anybody can clear this up for me?
## Post #15
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-21T07:03:58+00:00
- Post Title: Family Guy: Back to the Multiverse

I think that you can upload your utility as an attachment to this topic and you don't have to worry about the rules.
But if you want you can upload your tool [in this section](http://forum.xentax.com/viewforum.php?f=31) and give us a link in this topic.

Is it possible to make extraction process more automatically? 
I don't know too much about offsets and block numbers ;p
If not, it's ok. I'm a fast learner.

Thanks again for the tool! It's great chance to mod and translate this game.
## Post #16
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-21T16:34:17+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

> Reply from ikskoks
>
> Is it possible to make extraction process more automatically?

I've been skimming through the .ho files for pointers.  So far I don't see they way the pointers are used.  Its probably something simple.  Has anyone looked for the data pointers in the .ho files?

Once these are found, I can make the process more automatic.
## Post #17
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-12-22T01:47:44+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

This is a good look at the way the HAVK blocks work.  Some of them contain mesh data for weapons.
I'm not sure what the pointers at the beginning of the block mean, it could be a reference from another base offset.



The MAST and SECT blocks come first, so I was hoping to parse the sub-blocks using them.
## Post #18
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-03-02T23:48:46+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Hey. Did the situation regarding the game changed? I really want to translate it.
EcheloCross, you do great job in analyzing files. I support you.
## Post #19
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-03-03T05:12:55+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

I think the text is also in font.ho
## Post #20
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-06-28T18:44:48+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

I finally came across this and was amazed someone else actually had a similar interest in this game. I was hoping to extract the models properly from this game. Has there been any progress?
## Post #21
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-06-28T19:13:06+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Yeah, I'm still counting on textures and fonts extractor/importer ;D
## Post #22
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-11-01T23:46:47+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

I was wondering if anyone else had picked up on this yet? It seems the project has died and I'm a little worried we may not progress any further. I'd really like to get the models and textures for the characters from this. (Specifically Bertram himself.) I was hoping someone could educate me on how to do so properly?
## Post #23
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-05T16:57:42+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

I never did much more research on this format.  Last I remember, I didn't see the character models anywhere obvious.  Would be a fun game to mod graphics on.
## Post #24
- Username: DecaTilde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 25, 2018 6:11 am
- Post datetime: 2018-04-03T06:12:43+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Sorry for necroposting.

I hope EcheloCross uploads the .HO extraction tool soon.

I tried ripping using NinjaRipper, but the models weren't captured in the T-Pose. And I need ripped models in T-Pose, including the ones for Brian and Stewie, so I can submit them into [the Models Resource](http://models-resource.com), and I'm pretty desperate.
## Post #25
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-01-03T12:34:50+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Please don't tell me all hope is lost modding this game... if anyone is reading this take your time to reply and keep this topic active. I really don't want this to die, think of all the stuff you can do.

You can use cheat engine to mod your money to 999999 ( that's all I know how to do because i'm not pro )
## Post #26
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-01-07T01:11:08+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

[https://p3dm.ru/xfsearch/Family+Guy%3A+ ... ultiverse/](https://p3dm.ru/xfsearch/Family+Guy%3A+Back+to+the+Multiverse/) ( It's a 3D model pack for family guy back to the multiverse I found. )
## Post #27
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-02-11T05:45:48+00:00
- Post Title: Re: Family Guy: Back to the Multiverse


## Post #28
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-02-15T10:03:46+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

PLEASE tell us how you did that, we can make awesome stuff. Finally I was waiting for this, all i'm asking for is how to modify the files and in detail please.
## Post #29
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-02-16T07:06:54+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

[https://www.youtube.com/watch?v=Ubm0RVlOfZI](https://www.youtube.com/watch?v=Ubm0RVlOfZI)
[https://www.youtube.com/watch?v=ThcyZ6VEHgw](https://www.youtube.com/watch?v=ThcyZ6VEHgw)
## Post #30
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-02-21T07:11:13+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

i'm confused on the hex part..
## Post #31
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-02-21T11:31:57+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

> Reply from Vpinee ↑Thu Feb 21, 2019 3:11 pm at Thu Feb 21, 2019 3:11 pm
>
> 
i'm confused on the hex part..

Why does it confuse you?
## Post #32
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-02-22T12:39:23+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Step 3,4,5 ( Could you make a video about it? or just tell me because I don't know what to do. )
## Post #33
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-04-17T07:02:55+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

> Reply from Vpinee ↑Fri Feb 22, 2019 8:39 pm at Fri Feb 22, 2019 8:39 pm
>
> 
Step 3,4,5 ( Could you make a video about it? or just tell me because I don't know what to do. )

I'm sorry, I had other things to do.
If you're still interested, I can make you a video.
## Post #34
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-04-18T00:45:17+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Yes Please!
## Post #35
- Username: llaifa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 22, 2019 9:43 am
- Post datetime: 2019-05-22T02:50:13+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

would it be possible to mod the game in such a way as the multiplayer mode characters are playable in the story campaign?
## Post #36
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-05-29T07:48:34+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

> Reply from llaifa ↑Wed May 22, 2019 10:50 am at Wed May 22, 2019 10:50 am
>
> 
would it be possible to mod the game in such a way as the multiplayer mode characters are playable in the story campaign?
 That's a good question.
## Post #37
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-05-30T09:50:40+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Rgnbgnfant, is the video your making me coming soon? Because I really want to mod the game.
## Post #38
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2019-06-29T13:11:07+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

I don't have much time left.
## Post #39
- Username: Vpinee
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jan 03, 2019 8:29 pm
- Post datetime: 2019-07-03T06:52:25+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

To make the video?
## Post #40
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-10-01T11:38:42+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Sorry to bump on a old thread but I know where is the texts stored, they are all in a file called "FONT.ho" in FGUY\Global_Scenes\ for both PS3 and PC versions

It stores all the languages texts and it seems having XML files.

Can someone look into it?
## Post #41
- Username: DecaTilde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 25, 2018 6:11 am
- Post datetime: 2020-01-20T19:59:40+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

> Reply from MeteoraMan ↑Sun Nov 25, 2012 7:22 am at Sun Nov 25, 2012 7:22 am
>
> 
Need help with *.ho files.

Few files:
http://www12.zippyshare.com/v/54891237/file.html
or
http://www.sendspace.com/file/dm7fo7

These files use some alignment.
I can not understand how.

I hate to be the bearer of bad news, but neither of those links work anymore. Can you please reupload the files?

And I'm sorry for bumping this thread.

Also...

> Reply from EcheloCross ↑Fri Dec 21, 2012 6:47 am at Fri Dec 21, 2012 6:47 am
>
> 
I've managed to get some model and texture data out of the .ho files.





Theres a lot I haven't figured out yet though.  Like where the pointers are.

It seems the only model data I can find faces for is in the HAVK blocks.

I've found some other vertex data in some of the other blocks though, but with no faces.

Every mesh I've found so far is just a weapon.

For the models I found only verts for, I made my tool output a maxscript that draws spheres where the verts would be.



At least using this method I can see the general shape of the model that the test data represents.

Anyone else taken a look at this game's .ho files?

TinyPic went offline, so, I'm afraid you'll have to find a different image hosting site for those JPGs, like Photobucket or Imageshack.
## Post #42
- Username: Rgnbgnfant
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 09, 2017 7:29 pm
- Post datetime: 2020-01-26T06:14:20+00:00
- Post Title: Re: Family Guy: Back to the Multiverse

Why should we reupload the files?
