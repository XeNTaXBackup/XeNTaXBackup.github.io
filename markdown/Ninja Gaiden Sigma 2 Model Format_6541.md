## Post #1
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-05-02T20:26:44+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

Hello I'm new here but I would like someone to take a look at the Ninja Gaiden Sigma 2 model format which is .gmd (Note this is not the format for Game Maker and it is not the same as the .gmd type found in the Ninja Gaiden 2 Xbox 360 game.) 

Here is the link for the original forum where Surveyor did a TON of work on creating tools for Ninja Gaiden 2 and Ninja Gaiden Sigma.

[viewtopic.php?f=16&t=3741](http://forum.xentax.com/viewtopic.php?f=16&t=3741)

Unfortunately the thread died before Sigma 2 was looked at.

If anyone can figure it out that would be great.

I also put a link here for NGS2 Sample files, its in the middle of the page and was posted by Mariokart54n.

[viewtopic.php?f=16&t=3741&start=135](http://forum.xentax.com/viewtopic.php?f=16&t=3741&start=135)
## Post #2
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-02T22:09:34+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

i started looking into this back then originally, but got side-tracked and forgot about it, heh.

For the most part things are mostly the same, a few things have been changed and/or moved around though.

i'll see if i can pick up where i left off when i get the chance.
## Post #3
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-05-02T22:35:32+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

Revelation if you could do that I sure would appreciate it! Thank you for replying.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-03T00:38:53+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

ditto, the character models are x10 better in simga2, cant wait to see them :"P
## Post #5
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-05-03T21:10:27+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

> Reply from mariokart64n
>
> ditto, the character models are x10 better in simga2, cant wait to see them :"P

Exactly, also according to the game files they actually have a model for Kasumi who apparently makes a couple of cameos but you can only see her from behind and in the dark. Considering all the detail that they gave Ayane I'm somewhat hoping that we can see the full model.
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-11T04:28:02+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

textures show a full face for kasumi, but its a recycled from another model
## Post #7
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-05-24T04:46:18+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

Hey revelation have you had any time to look at this at all? I know you have your own life and everything but I don't want this topic to die out if the solution is relatively simple. Also what do you use/ what do you do to look at the model formats? I'm a bit curious is all.
## Post #8
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-25T15:13:51+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

i got started on it, but have not finished mapping the changes yet.

i work on a lot of formats, and bounce between then in order to not get to burnt out on any single one.  Also time away from a roadblock usually makes it easier to spot what i may have been overlooking otherwise.  Not to say that was the case here, but i also have a list of games that interest me most, usually the ones that got me interested in reverse engineering in the first place, so its often that those end up retaking priority when new findings/inspiration popup, heh.

For the most part i use a mixture of 010 Editor and if necessary a good disassembler.  The template/script support of 010 Editor has proven to be of great use to me as i can usually proof my findings as i go and the language is basically c/c++ so i can usually use the structures i create directly in my code with little to no modifications.  Either way for most formats a good deal of things can be figured out directly in any decent hex editor.

From there is mainly comes down to knowing, or having a good idea of, what you are looking for and the various forms it will usually be present (for graphics data usually floating point values in groups of 3 (vectors), 4 (vectors/quaternions), 16 (matrices), etc....so being able to recognize common patterns and formatting of floats can be very beneficial).

i'll see if i can allocate more time to complete looking into things, but since i did not create the original plugin for Noesis, i can't really modify it anyway, but i can pass the information along once determined and see.
## Post #9
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-05-25T19:41:05+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

Thanks for the reply revelation! I completely understand bouncing around to prevent burnout and other games that interest you more take priority. Also thank you for giving that info on what exactly you have to do. 

For the Noesis plugin couldn't you submit a specific plugin for just Ninja Gaiden Sigma 2? It would make the plugin submission easier and it seems less complex than melding two different formats with the same name together for one plugin, but then again I'm not a programmer so I could be wrong. 

Even so thank you for offering your expertise on this!
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-26T09:48:12+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-26T11:02:06+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

i created edges :
1 edge = vert[0]+vert[1]
2 edge = vert[1]+vert[2]
3 edge = vert[2]+vert[3]
4 edge = vert[3]+vert[4]
...
but i don't know how it use.
[hip.jpg](https://xentaxbackup.github.io/file/4382_hip.jpg)
## Post #12
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-07-07T04:19:33+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

Any news about this formar??
## Post #13
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-07-17T07:37:56+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

hope this thread is not dead yet, looking forward to this as well
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-18T18:51:21+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

i started looking at this format last night... got to the point where you extract all the OBJGEO/GEODECL pairs. some things confuse me though, like:

following the name of the object, there is some data... usually the name till the end of the OBJGEO section is 32 bytes, but sometimes it's longer (OBJGEO is usually 112 bytes total, but when it's larger there is some crap data at the end I can't figure out what it is).

here is some code... it just outputs text files for the three ps3 models someone posted up above.
[tolwo.rar](https://xentaxbackup.github.io/file/4505_tolwo.rar)
## Post #15
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-08-02T05:28:41+00:00
- Post Title: Ninja Gaiden Sigma 2 Model Format

I am going to starting learning, wish I took cryptography so I can recognize the patterns easier.

but please keep us updated with your progress, thanks.
## Post #16
- Username: MSG1000
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 10, 2011 3:18 am
- Post datetime: 2011-08-07T23:25:16+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Alright, I've been really busy for the past few weeks which is why I haven't commented on the progress. I just want to say thank you to the people who are devoting effort into this topic and I appreciate the work that has already been done.
## Post #17
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-09-23T08:15:03+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

any one still on this task?
## Post #18
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-10-22T06:35:34+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

so which file contain the face coordinates? I looked over the different gmd files but I think they are all body files.

all the other files don't have the geodec descriptions in there. man, this is way more different than the ninja gaiden 2 format
## Post #19
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-11-05T01:43:10+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from howfie
>
> i started looking at this format last night... got to the point where you extract all the OBJGEO/GEODECL pairs. some things confuse me though, like:

can you explain to me what geo means? what is OBJGEODATA and what is GEODECLDATA?
also what exactly do these numbers mean? if these pairs are descriptions for the memory location of individual parts, it should have address offset to get the memory range where the voxel coordinates are right? I seriously can't tell what's what just looking at these numbers without label.

this is the result of running the code howfie supplied and I can't understand a thing lol

OBJGEODATA[0]
   5720251331590946816
   4278190336
   48
   2928
   4
   4
   0
   96
   0
   112
   0
   131072
   0
   4
   2
   1
   0
   0
   0
   MOTreichest
   368
   976
   1712
   2320
GEODECLDATA[0]
   5144640488890133504
   4278190336
   48
   256
   4
   4
   0
   48
   0
   0
   0
   64
   112
   160
   208
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-05T06:38:41+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

I will come back and look at this again in December; no time right now .
## Post #21
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-12-11T23:56:58+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

howfie, can you answer my question now? I still have no idea what that list is for.
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-12T00:04:26+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Hey Muffin, as soon as I finish up with the Gundam one I'll look back into this. I just don't remember where I ran into trouble and would have to review my notes on the format. It's tough looking at hex all day and moving in between the hex of different games. . But if I remember right I never even found the points... I was just examining the data in the headers.
## Post #23
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-02-25T04:59:12+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

apparently someone already had this, but I have no idea how he did it.

[http://kamillho.deviantart.com/gallery/#/d4h1v0h](http://kamillho.deviantart.com/gallery/#/d4h1v0h)

I'd love to know if there's a rip out there already.
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-25T23:09:00+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

wow his dA page is just full of him making rape faces to a bunch of naked 3D girls O_o
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-26T00:03:03+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

And naked body builders.
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-26T07:10:23+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

That model is not from sigma 2, that's the sigma 1 model.
## Post #27
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-02-26T12:19:12+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from howfie
>
> That model is not from sigma 2, that's the sigma 1 model.

considering that I couldn't even find sigma 1 version of rachel (it actually existed before, that's why there are RE4 mod with rachel's body) I'd like to obtain any version right now.
## Post #28
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-28T00:44:27+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from MuffinMan123
>
> howfie wrote:That model is not from sigma 2, that's the sigma 1 model.

considering that I couldn't even find sigma 1 version of rachel (it actually existed before, that's why there are RE4 mod with rachel's body) I'd like to obtain any version right now.

There's actually a model from NG from the first xbox and I haver her.
## Post #29
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-09T14:15:30+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

anyone still working on this please??
## Post #30
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-05-02T01:12:15+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

some what off topic

[http://www.youtube.com/watch?v=hF8b-9qGcxw](http://www.youtube.com/watch?v=hF8b-9qGcxw)

is this done by save file editing or by game file substitution?
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-02T01:20:57+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

it looks like they just swapped ryu and ayane's files.
## Post #32
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-05-02T06:21:06+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

is it really as simple as swapping a file in NGS 2??


edit: at the end of video at around 8:29, the guy show a screenshot with some highlighted hex in colors and some japanese text lol I can't read that maybe someone can and share some info.
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-02T10:30:22+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

yeah he is editing the xex file to swap the model files.
you could edit the xex like he shows or swap the actual files.
## Post #34
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-05-03T10:12:28+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

the default.xex file, you mean?

How do I even know what hex data corresponds to which character/outifts etc.??  

how much effort is required if I am to try to find that out myself?  lol
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-03T10:28:09+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

the first reply in the comments section says what the costumes are.
you can see the offset in the video where he wants you to edit.
being it is Japanese the offset may be different in the us release so you may just have to search for those hex patterns.
## Post #36
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-10-18T19:09:34+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

this is only doable on modded ps3 right? I was hoping for a save file mod, possibly a ninja cinema file mod.
## Post #37
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-02-08T06:51:54+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

this thread deserves a bump
ng2 was possible, hope there be good news on sigma...
## Post #38
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-08T10:14:55+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

anyone could add support for sigma if they want now because the edge compression is supported in noesis and in native python.
## Post #39
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-02-08T17:35:04+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from chrrox
>
> anyone could add support for sigma if they want now because the edge compression is supported in noesis and in native python.
Does that mean importing bones and animation are possible now too ? Has anyone recently worked on this or any plugin for noesis to support ng2s ? Would be nice if the ng3/doa5 works on sigma too but they r not
## Post #40
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-07-17T05:49:58+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

alright, I was so noob when I 1st looked at the save files for the model swapping. I forgot that the save file could be encrypted. I only realized this when I was looking for the code for another game.

all you need to do is decrypt the save files with bruteforce save data and edit using hex editor. the character codes are the same as that video. the problem is you can only swap ryu's models with girls', but not girls' model with ryu's because the girls' chapters have offset for their costume codes so the range is always 00~05



00~05 are ryu's models, so far I know that, 0303 is blue demon ryu, 0404 is dynasty warrior, 0505 is joe's costume
06~0B are rachel's models. 0606 is her default, 0707 is long flowing hair
0C~0F are ayane's models. I was able to use 0F0F DLC ayane costume, but it crashed my game when i do it on chapter 4.
10 and beyond are momiji's costumes.

this should work for both story save files and chapter challenge save files, but not replay cinema files because the cinema records costume specific data, changing the models like that will affect the interaction completely.

for the chapter challenge, the there are 17 chapters, chapter 1 is chat_000.dat and so on.

you can access the dlc costumes too even if you haven't bought them.

rachel swimming in chapter 2 challenge with true dragon sword
## Post #41
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-07-17T15:05:15+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

That's pretty cool. It's nice to see some progress on this game.  Does any of this put us any closer to extraction from the game, or is the encryption still a big issue for the games data files?
## Post #42
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-07-18T05:03:25+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

save file editing and model extraction are like apple and orange. they are completely different things.
unless we get this model extraction thing done, it's not going to happen on its own.

btw, Musou Orochi 2 Ultimate is scheduled to come to ps3/x360 again, it sports yet another version of rachel's character model. maybe you can wait for that game to be data mined?
## Post #43
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-10-16T12:20:49+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Sorry to resurrect a long time thread from the dead! 

I was checking Noesis and apparently a stealth feature got added for Ninja Gaiden 2, bones/vertex weights now work, so I thought I'd look into any progress on Sigma/Sigma 2.  Thanks to PSN tools over the years apparently decryption is no longer an issue.  The NGS2 files look really close to usual TN formats.  Best I can tell for now is that GMD holds most data with Vertex Data in the TTGL.  I won't be able to do much other than trial and error my way through to figuring out how to get stuff working in Hex2Obj, but that won't help with Weights & Textures.  So if there's anyone with the Will & Skillz to either update one of the TK Blender scripts or even modify a Noesis plugin, etc I've posted some files.  I included the same model from both X360 & PS3 version for comparison.  

I also included some files from NGS1.  I think they can be pulled using AFSExplorer, but that is as far as I got with current time.  Of course all of this is moot if there is already extraction for any of this and I was just unaware, lol. 

Ninja Gaiden Sigma (Ryu, Rachel, Ayane)
[https://www.mediafire.com/file/7lbqlb5i ... acters.zip](https://www.mediafire.com/file/7lbqlb5iaavqlxt/NGS_Characters.zip)

Ninja Gaiden 2 (Xbox 360) - Tactical Ninja
[https://www.mediafire.com/file/2az3hvmv ... lNinja.zip](https://www.mediafire.com/file/2az3hvmv78frcwk/NG2_X360_TacticalNinja.zip)

Ninja Gaiden Sigma 2 (PS3) - Tactical Ninja
[https://www.mediafire.com/file/2b4gfetq ... lNinja.zip](https://www.mediafire.com/file/2b4gfetq755gkbm/NGS2_PS3_TacticalNinja.zip)
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-16T19:20:59+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Your post is full of riddles for me.

> Reply from Protocol X27
>
> I was checking Noesis and apparently a stealth feature got added for Ninja Gaiden 2, bones/vertex weights now work,what are you talking about? Which script? Which stealth feature? (You mean the format is handled internally?)

> The NGS2 files look really close to usual TN formats.What is the TN format? (Link to a post?)

> I won't be able to do much other than trial and error my way through to figuring out how to get stuff working in Hex2Obj,which "stuff"? The mesh?

> but that won't help with Weights & Textures.yep, but you have to start with the mesh, generally.

> So if there's anyone with the Will & Skillz to either update one of the TK Blender scripts or even modify a Noesis plugin,TK blender scripts? Link? 
Which Noesis plugin?

> I also included some files from NGS1.  I think they can be pulled using AFSExplorer, but that is as far as I got with current time.Again I don't get it, sry. You "think" they can be pulled but you did not try AFSExplorer?
## Post #45
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-10-17T01:30:58+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Sorry, lol, riddles it is.  When it comes to extraction, I tend to assume everyone knows more than me on the subject since I lack the academic piece of tearing apart a file and knowing how to explain it properly or from a structure standpoint.  I only know parts of the files from DOA modding, so I only know how to explain stuff once someone explains data locations to me.

Re: Noesis, the version I used a few months back didn't have weight/bone support for Xbox 360 Ninja Gaiden 2 models. Now it does. I did not add any additional plugins, so when I mean stealth feature, I mean its being handled internally and don't follow updates close enough to know when things like that are added.

Re: TN format.  Team Ninja has used similar structures for their files across DOA5 Xbox, DOA5LR PC and DOAX3 Vita, so when I saw format I'm referring to knowledge of what I've seeing in the files.  They tend to flip flop on whether or not they put vertex & index data in the primary file or move it to another.  In the case Ninja Gaiden Sigma 2 PS3 files it looks like the main file is the GMD and the vertex / index data inside the TTGL.  

Re: Hex2Obj / 'stuff'.  Yes, I meant the mesh.  Once I knew where vertex data was for DOAX3 I was able to write a helper to get the key values to plug into Hex2Obj.  I was hoping to do that here as well, but after spending a couple of hours on the GMD, I could not figure out which values were the vertex buffer lengths and/or starting points of each mesh group.  A lot of the file guts, I recognize, but it has a few differences that I'm not familiar with.

Re: AFSExplorer.  This was related to the Ninja Gaiden Sigma 1 PS3 files in afs format.  I did try them and extracted one file.  When I did, it did show a TMC file header, but I did not progress past that point since I know older TMC's were probably different as well.

... and the links ... I don't recall sources since it's just stuff I've collected over the last couple of years.

Blender Plugins: [https://www.mediafire.com/file/dw8xwgw1 ... lugins.zip](https://www.mediafire.com/file/dw8xwgw1bxw1f1k/TK%20Blender%20Plugins.zip)
Each of these three is used for different generations of Tecmo Koei files.  TMC-GMD was the newer DOA5 & NG3 stuff, TPR-TMC was previous gen like DOAX2 & NG2 (I think) and I believe XPR was before that, I don't have anything to test that on.

AFSExplorer: [https://www.mediafire.com/file/xzn0sd9d ... plorer.zip](https://www.mediafire.com/file/xzn0sd9dgzbtc8g/AFSExplorer.zip)

DOA5LR PC Container Sample for Reference: [https://www.mediafire.com/file/fjxpd4d2 ... 0Files.zip](https://www.mediafire.com/file/fjxpd4d2c7s5h7m/DOA5LR%20PC%20Sample%20Files.zip)

I hope that long winded mess helps and that I'm not generalizing too much.  If I didn't answer something or I can explain anything on the current DOA5 format, let me know. 

Thanks!
## Post #46
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2017-10-17T04:05:07+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

I don't know if you hadn't seen this:

[https://doax-venusvacation.jp/](https://doax-venusvacation.jp/)
## Post #47
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-10-17T04:13:38+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from Darko
>
> I don't know if you hadn't seen this:

https://doax-venusvacation.jp/

I know of it, but I don't have time for more grind fests from TN let alone even more alternate region and registration obstacles.  I can only hope that it lends itself to more accessible models, since I haven't heard of any progress on the PS4 front yet.   Screenshots look really nice,
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-17T17:48:46+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from Protocol X27
>
> I hope that long winded mess helpsyep, thx!
Now I'd need to know what exactly you want to achieve?
Getting a mesh/obj file from NG Sigma 2, right?

So far I used AFSExplorer to export a .tmc file from chr_ayane.afs.



AFS.jpg (101.31 KiB) Viewed 383 times


But when using the io_import_TMC-GMD.py with blender it imported nothing:
<!> event has invalid window
end() executed in 0 seconds
## Post #49
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-10-17T18:12:48+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Cool, I probably clouded the issue by adding multiple items.  

The desired goal is a means of extracting meshes, weights,  uvs & textures from Ninja Gaiden Sigma 2.  A secondary goal would be same thing for Ninja Gaiden Sigma models too, but I know 'some' content from that is accessible in newer games.   I'm indifferent if the extraction process is Noesis or Blender as long as the mentioned items are extractable.

So, the .afs files are from Ninja Gaiden Sigma 1.  I do not know of an extraction method for those yet. I just included them as a reference in case they were helpful.  Even though they are .tmc format, after being extracted from the AFS, Team Ninja moved stuff around.  The TMC-GMD script you tried though does work with the Tactical Ninja (Xbox 360) files for the GMD/TTGL (These work via Blender Script OR Noesis).  The Tactical Ninja (PS3) files from Sigma 2 are supposed to represent the same character, but the data has been separated across the GMD/TTGL differently (These do not work by Script or Noesis).  So I'm hoping that someone's knowledge of structures combined with comparison to a working case might yield an import method.  

I think I spoke incorrectly regarding that Blender plugin previously.  TMC-GMD.py so far only works up to Xbox 360 DOA5/NG3 files. I don't think it works on DOA5 PC files.  The DOA5 PC samples in my last post should work with this plugin, if it helps has a reference. 

[http://www.mediafire.com/file/25etrcllb ... 0.17.0.zip](http://www.mediafire.com/file/25etrcllbt8pteu/for_Blender_TMC%28PC%29_Importer_0.17.0.zip)
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-17T19:01:27+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

point cloud for e_bni_a-XBOX.gmd looks ok - problem is to find the suiting face indices block:



e_bni_a-XBOX-gmd.jpg (150.19 KiB) Viewed 379 times


gosh, of course it was the last possible address - while I was starting from the lowest. 

(uvs? well, don't seem to be contained in the FVF block.)
## Post #51
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-10-17T19:28:33+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Very nice. 

So from what I'm seeing in this Xbox format, it doesn't have pretty points at the beginning of the file like newer formats, plus its using the older VBuf/Ibuf method for indexing which I don't get.  I don't see buffer lengths like in the newer stuff.   There are matching VBuf & IBuf counts, so if they stacked them all together finding the first index block should match the first vertex block.  

Just guessing here, 
0x00001000: Index for Texture, Vertex & Index data
0x0000D000: Looks like the Start of Vertex Data
0x004AF000: Looks like the Start of Index Data, would this be the face data as you're calling it?


Edit: 
D'Oh, you beat me to it, lol. You found it while I was typing...

Edit 2: 
Yeah, no dice on the UV matching the DOAX3 FVF which is the only one I've used H2O for so far.  In that case the UV was 4 bytes less than the FVF and I had to use HF_UV.
## Post #52
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-11-07T21:34:54+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

NGS2 models are going to be ported able for now?
## Post #53
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-14T09:33:54+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Re: TN format.  Team Ninja has used similar structures for their files across DOA5 Xbox, DOA5LR PC and DOAX3 Vita, so when I saw format I'm referring to knowledge of what I've seeing in the files.  

@Protocol X27 If you don't care about the quality,you can take a look at the .GMD file in Ninja Gaiden Sigma 2 Plus.It seems to be a TN format, similar with DOA5LR PC.

And again,thank you for your reasarch on DOAX3 Vita  

Please forgive me my lousy English. 
[AYA_C.zip](https://xentaxbackup.github.io/file/13546_AYA_C.zip)
## Post #54
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-14T13:46:02+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@DeeepLonE Thanks    I do know they are somewhat similar, Xbox vs PC is mostly just Endian difference, and PC to X3 Vita are just restructures.  Since I had been digging around I was hoping that revisiting might find someone who can better locate the verts and stuff that we don't have already have importers/extractors for.  Years back the encryption was the issue, now that's no longer the hurdle.

Dang, thanks for the tip on the Vita + version. I was shooting for the HD version first, but it it's that similar it's worth looking into.  It is almost identical indeed albeit the same as NG3, but with an endian flip.  It looks like it's missing the textures.  Was there a corresponding TTGL or TMCL file with the GMD?


@ngovandang not yet, but here's hoping.  

Edit: It looks like the Verts & Faces are missing from GMD as well.  I may be able to adapt my X3 tools to get the data for starters, but I'll need to figure out which files have the missing data first.  I'll track those down later today.
## Post #55
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-14T16:06:05+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Re:It looks like it's missing the textures.  Was there a corresponding TTGL or TMCL file with the GMD?
@Protocol X27

Hi Protocol X27,
I'm sorry about my rudeness, I should say hello first.
I'm totally a muggle on coding but a big fan of Ninja Gaiden.
May be there are some relationship between.GMD file and .TTGL file? (My guess)  
And the AYA_B.GMD file is much bigger,a suspicious one.  
You may already know that,sorry for being useless.  

Forget about my lousy English,please.
## Post #56
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-14T17:08:42+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Hey, don't worry at all.  I did not take that you said as rude or useless.  If anything I didn't think to take into consideration tone change from any form of translation.    I almost even posted without referencing the file you posted which is actually very helpful because I do not have the data yet. 

Did you see other files?  If there is TTGL files I guarantee those are probably related.  It looks like GXT headers are in the GMD, but not the actual image data.  This is also similar to X3, so will probably need all related to files to properly pull everything.  AYA_B, just may have more poly's.  She has like 4 costumes in total for the game, or more including the pre-order costumes.
## Post #57
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-15T14:33:21+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@DeeepLonE  How did you extract the AYA_C.GMD?  I found some data, but I'm stuck with the databin.lnk    Let me know which method you used.  Otherwise, I'll have to dig through my old files to see if old DOA extractors work on it... :-/
## Post #58
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-15T15:07:36+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@Protocol X27

I will try my best to help you, wish you good luck, bro.
## Post #59
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-15T18:31:38+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@Deeep

Thanks, that saved me the time of trying different tools.  

Edit: Archive Tool was not working originally, but I realized normal Extract was not working, but Right Click > Extract was.  Problem solved.

I got both GMD/TTGL's extracted.  Looks like I mispoke.  Images are in the GMD, but the Face/Vertex data is much like DOAX3 in that both are contained in the TTGL.  I'm going to try rearranging some things to either get the mesh showing in Hex2Obj or manual rip an image if I can find the start/end points.


Edit 2: Image Success! Images are same format as DOAX3, manually ripped method works, just need to update my script accordingly.
## Post #60
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-16T03:47:05+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@Protocol X27

Wow, you are so cool, man. You did it! 

Can't wait to meet the new script.  

Edit: 
Did I express myself in a proper way?  
Forget about the details, please.
## Post #61
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-17T02:55:17+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Yep, you're good. Nothing to worry about.  

Aight, slight issue, but reasonably working Image Extractor for Ninja Gaiden Sigma 2 +  

(Edit: Updated version posted)

Looks like I was previously wrong in both cases.  Image data may be in GMD/TTGL may not XD  TN was rather inconsistent.  Sometimes image data is in the GMD, sometimes its in the TTGL.  I had to make exceptions to handle both.  There is still some bugs for some containers.  I have tested with half a dozen characters and it's working.  Most of the AYA_A/B/C style files work, but the ones that start with R_CHARNAME, may not at the moment. I'll update it as soon as I get a chance.  Then I'll move on to messing with the meshes.
## Post #62
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-17T09:02:29+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

You know, when I saw the MURAI.GMD file in the NGS2P data, I could not believe my eyes!
It's time to find out more secrets.
Hoping some big guy can bring Murai back to NGS2P.
Or please do tell me how to make it. 
Thanks. 

Edit:
The only sure thing I know is that the sound file's format--XWS, is a stream of AT9. You can separate them by using hex, then save as AT9, convert it to WAV freely by using at9tool. And after finish editing, import the sound by hex.
## Post #63
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-17T16:14:53+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Good to know. I would not have expected Murai to have files in the game.  That's useful until Ninja Gaiden 1 is extractable.  I am not sure if you are suggest to mod him into the game, but he may be extractable if ideas here are successful.  

I fixed the problem with my previous release, so for now, all GMD/TTGL files that I know of 'should' be texture extractable.

[https://www.mediafire.com/file/6ztsqkjo ... r_V1.0.zip](https://www.mediafire.com/file/6ztsqkjoc1nuiik/NGS2P_GXT_Ripper_V1.0.zip)

I still have some things to figure out with my mesh script, but doing a manual rip like with the texture did work in Hex2Obj.  Here's a sample of Ayane's face, so things should be possible at least to get static meshes.  Skeletons & weighted meshes will depend on someone's willingness to modify one of the existing Blender scripts already available.  Any takers? lol  I can post the DOA5 scripts if anyone knows Blender & python well enough to do a couple of light adjustments.
## Post #64
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-18T02:15:03+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Mission 1 (or .5 or whatever it is) Accomplished! 

This is the extent of my skills for now.  We still need help with breaking down the NGS1 (PS3), NGS2 (PS3) formats, and could use someone's help on an importer for NGS2+ (Vita) but at least until then we know can at least extract static Ninja Gaiden Sigma 2 Plus Models & Textures.   This is a multi step process involving extracting meta data from the files, then plugging data into Hex2Obj and the importing .obj files.

NGS2P_Mesh_Helper: [https://www.mediafire.com/file/7xy5y3ja ... Helper.zip](https://www.mediafire.com/file/7xy5y3japcvcrd1/NGS2P_Mesh_Helper.zip)

Thanks to raidergale for sharing knowledge on Vita formats & Hex2Obj, xperiagenerator for explaining GTX formats, DeeepLonE for suggesting Sigma 2+ and Shakotay & any involved with crafting Hex2Obj.





As mentioned before, help is welcome if anyone can help with scripts or format breakdown.  I don't know proper way to explain file formats, so I get specific question or request for assets, I'll gladly add on to what's already posted here.
## Post #65
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-18T02:47:27+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

oh!oh!oh! impressive!@Protocol X27, you are my hero. Thank you so much. 

Edit:
Oh, about the HD version, I wonder if we can find something in rpcs3's shader cache...my guess(run away)
## Post #66
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-20T20:56:24+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

I found there were some other models not working properly, so I made an update.  The 'R_CharName' files should be working now.  The game uses some pre-render cut scenes, so I'm not sure why there are duplicates of some models.  The R_ models do have higher res textures and their models are better separated, so those are likely more useful than the combat models.  I also found that Ayane's Sword didn't work either, I_KOD (Kodachi), so that is working now too.  Hopefully there aren't too many other variations.  TN was all over the map.  Even the vertices were sometimes in the GMD, sometimes in the TTGL.  

NGS2P Mesh Helper: [https://www.mediafire.com/file/3gqz38e2 ... r_V1.1.zip](https://www.mediafire.com/file/3gqz38e2z661b46/NGS2P_Mesh_Helper_V1.1.zip)

@Deeep
I'm not familiar with that.  Any chance you could offer more detail? 

Thanks!
## Post #67
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-11-21T07:48:54+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Oh, forget about it. I have looked into it and found nothing useful. It's a wrong path.
## Post #68
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-27T18:42:55+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Thanks to some assistance, I got a PS3 image ripper working for NGS2 [PS3], so there's one more item down.  Unless anyone comes along with mind to help with meshes, weights/scripts for Vita/PS3, I'll probably move onto Sigma 1 once I get data & time. 

If anyone wants just the utility: [https://www.mediafire.com/file/m7myca7e ... r_V1.0.zip](https://www.mediafire.com/file/m7myca7eq3a1ayb/NGS2_DDS_Ripper_V1.0.zip)

If anyone wants the technical details leading up to it, check this thread: [viewtopic.php?f=18&t=17315](http://forum.xentax.com/viewtopic.php?f=18&t=17315)
## Post #69
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-09T20:26:23+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Ok, about to download some updates on ya's.  

I finally looked into Sigma 1 and thankfully, I was able to make a lot more sense of the format over NGS2.  Plus I was able to re-purpose most of what I'd already written with some slight changes.  I give you, Ninja Guts... just a name for all of the current tools rolled into one bundle for now.  I've added AFS Unpacker, DDS Ripper & Mesh Helper for Sigma 1 [PS3] and GXT Ripper & Mesh Helper for Sigma 1 Plus [Vita].  There is an image format I'm not familiar with in PS3 version, so once I get some help with that I will update accordingly.  

Ninja Guts V1.1: [https://www.mediafire.com/file/mgvbd7og ... s_V1.1.zip](https://www.mediafire.com/file/mgvbd7oghz2d7sa/Ninja_Guts_V1.1.zip) (Updated 12/10/17)

That takes me about to the extent of my skills for now.  If any help comes along for the NGS2[PS3] format I can create a similar mesh helper.  I know it's similar, but I haven't found the vtx/idx offsets yet.  Beyond that, not likely I'll have time to learn the means of full blown importers, so I'll mostly stick to bug fixes or related updates.  Automatic stuff would be nice, but given how long it took to get this kind of progress, I'm not going to hold my breath, lol.

Happy Extracting!   (that is, if anyone is crazy enough as me to care about extracting from the series anymore , lol   )
## Post #70
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2017-12-10T08:44:47+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

AWESOME!!!
It looks like I am on the train to success.
It is my honor to see the birth of a master.
I have to study python and blender hard in order to catch up with you guys.  
How about bring Tomonobu Itagaki(板垣伴信) san into his own game, make his profile as a costume of RYU in sigma 2 plus?  
And thank you Protocol X27.
[Hayate or Tomonobu Itagaki.jpg](https://xentaxbackup.github.io/file/13671_Hayate or Tomonobu Itagaki.jpg)
## Post #71
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-10T18:55:28+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Thanks, Deeep! 

Sounds like a cool idea! Just take things one step at a time, and keep the goal in mind.  Vita modding is beyond me, but I know it is possible.  It'll take some hex modifications if no tools exists for that, but if you keep the goal in mind, it'll help you focus on the skills you need to make it a reality.  

That's what happened for me with this one.  Been wanting NGS so long.  I've always been willing to do it myself, but only recently have I felt confident enough to think skills were ready to handle it.  Thankfully, some others have answered questions that would have otherwise been a hurdle to getting all the known formats and oddities working.


Utility Update

Version 1.1: Updated NGS[PS3] - DDS Ripper to include DXT3 texture format AND read from containers that ONLY have the textures in the TMC.  Thanks again to AceWell for help with image formats.

Ninja Guts V1.1: [https://www.mediafire.com/file/mgvbd7og ... s_V1.1.zip](https://www.mediafire.com/file/mgvbd7oghz2d7sa/Ninja_Guts_V1.1.zip)

Oh, and just to prove I'm not blowing smoke on what these are good for...    Rigging will suck, but at least that's doable compared to custom making meshes & textures.
## Post #72
- Username: Qmemavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 30, 2016 9:32 pm
- Post datetime: 2017-12-12T15:36:06+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Edit: Problem solved.Although I didn't do anything, now everything is working.



Great work Protocol X27, thank you for your effort.

I am new to all of this and I am trying to get things starting. I have a problem, hopefully someone will help me.

I started python.exe version 3.63 , which opened a cmd window. After dragging in that command window the NGS_AFS_Unpacker.py there is an Error Message: "Syntaxerror: <unicode error> `unicodeescape´ codec can't decode bytes in postition 2-3: truncated \UXXXXXXXX escape".

What am I doing wrong?
## Post #73
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-12T20:06:38+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@Qmemavos

Thanks & no prob.   Glad you got it figured out whatever it was.  Once python 3 is installed you should just be able to double click one of the apps to run them.  I did not setup drag & drop though, so I don't know if that was the issue or not.  

When I installed python I remember installing Tkinter being an option, so in case something similar is an issue for anyone hopefully it isn't that.  I do use tkinter to allow the apps to run as windows.
## Post #74
- Username: Qmemavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 30, 2016 9:32 pm
- Post datetime: 2017-12-14T14:33:17+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Yup, that was exactly what has happened. The files weren't associated with python, that's why they couldn't be opened and drag and drop isn't working. Again thank you dearly, after two years of searching, I can finally browse NGS texture files.
## Post #75
- Username: ArcRay
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 16, 2018 1:59 pm
- Post datetime: 2018-02-16T06:56:42+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

if anybody is still here, maybe you guys could help me with something kind of specific?
## Post #76
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-02-27T04:13:05+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

I check occasionally, best to just ask and people can try to help once they check in. 

I'll do my best to answer questions related to this.
## Post #77
- Username: koonbozorg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 02, 2018 12:20 am
- Post datetime: 2018-06-01T16:36:55+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

BUMP.


With all 3 Ninja Gaiden games going in-game with RPCS3 emulator and Ninja Gaiden Sigma being fully playable, I am hoping to see an increase and revival in mod activity.

Using Protocol's tools ( thank you Protocol ), I was able to extract from the AFS files and now I was wondering how might I go about doing a simple costume swap replacing the default or maybe sky blue retro outfit with the long sleeve & traditional ninja garb Ryu features in the beginning of the game?
[Screenshot (6).png](https://xentaxbackup.github.io/file/14418_Screenshot (6).png)
## Post #78
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-06-13T12:58:40+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@koonbozorg

Wow, thanks for sharing that.  I didn't even know about that emulator.  Not a problem on the tools, I hope people find them helpful.   Unfortunately, I don't know the other KT formats as well as DOA5, but part of the challenge will be keeping file sizes the same until someone knows how to pad or shift addresses around.  My best guess would be to start with addresses of the images within any one of the containers.  With that you could jump to the image location in hex, and then paste a modified image (if it's the same byte size) over the old one. After doing that it should be possible to past the modified container back into the afs.   That's all in theory of course if the game does not run any other kind of byte checks.  :-/    I don't have real specifics on that at the moment, because I forget this stuff real easily when I'm away from it for more than a few days.

So does that emulator run DLC as well?  NG games are the only reason I'm hanging onto my PS3, I would love to consolidate if I know Sigma 2 DLC works correctly.
## Post #79
- Username: koonbozorg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 02, 2018 12:20 am
- Post datetime: 2018-07-01T20:41:21+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

All DLC works just fine in all Ninja Gaiden games via RPCS3.  I've completed Sigma 1 on the emulator numerous times including all the missions and survival dlc with no issue.

Sigma 2 and Razor's Edge the same though they have minor kinks that need to get worked out before they become playable.  

Still, the graphics render correctly and you can go about in game on both no problem.
## Post #80
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2018-07-02T03:31:34+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from koonbozorg
>
> All DLC works just fine in all Ninja Gaiden games via RPCS3.  I've completed Sigma 1 on the emulator numerous times including all the missions and survival dlc with no issue.

Sigma 2 and Razor's Edge the same though they have minor kinks that need to get worked out before they become playable.  

Still, the graphics render correctly and you can go about in game on both no problem.

This forum is for ripping models and content from videogames for modding pupouses, It's not a forum dedicated to emulation.
## Post #81
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2018-07-13T19:23:35+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

Easy killer, he was just replying to my question which was indirectly related on account of the file format discussion he brought up.  Yes, that's what it is for, but I was just curious since I didn't even know that emulation of the stuff was possible.  Sometimes it is helpful to ask someone knowledgeable on a subject since Google can't actually answer everything otherwise this forum wouldn't exist either.  

@koonbozorg, Thanks for answering. I did figure stuff out, but for some reason NG2 didn't work.  I'll leave it at that or PM, so things get back on topic.
## Post #82
- Username: HentaiBorg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 18, 2019 8:46 am
- Post datetime: 2019-12-14T08:32:59+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

From what I understand after reading and testing a bit with the tools only the model of the Vita version are extractable.

I am not familiar with the vita version but I assume the files are stored in the LNK file of the vita game just like DOA5.
I extracted NG2 Plus Vita version with the DOA5Archivarius tools and got a the GMD and TMGL files as expected.

But when I tried to use the NG2Mesh Helper on them, I got some kind of index error. 
I think I messed up and used the wrong tool to open that LNK files. 

Can someone tell me what I need to use correctly get the files inside that LNK file?
## Post #83
- Username: drywater
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 09, 2008 10:50 am
- Post datetime: 2020-12-27T08:10:36+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

> Reply from HentaiBorg ↑Sat Dec 14, 2019 4:32 pm at Sat Dec 14, 2019 4:32 pm
>
> 
From what I understand after reading and testing a bit with the tools only the model of the Vita version are extractable.

I am not familiar with the vita version but I assume the files are stored in the LNK file of the vita game just like DOA5.
I extracted NG2 Plus Vita version with the DOA5Archivarius tools and got a the GMD and TMGL files as expected.

But when I tried to use the NG2Mesh Helper on them, I got some kind of index error. 
I think I messed up and used the wrong tool to open that LNK files. 

Can someone tell me what I need to use correctly get the files inside that LNK file?

You have to check force decompression in Archive Tool 1.2.1. Not sure if Archivarius has an equivalent. After that the files you get are going to be gigantic, a bunch of junk data (00s, and the sizes produced vary from file to file pair-ttgl/gmd) has to be stripped from the end of the file using a hex editor. Worth leaving an even number of 00 bytes (16 or 32) after the legit data just in case a few of those are needed. The UVW will need to be flipped and possibly moved upward a bit to realign with textures properly.
## Post #84
- Username: GEO
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 01, 2019 2:25 pm
- Post datetime: 2021-02-23T03:48:57+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

So has anyone been able to fully extract models with the "Ninja Guts v1.1 that was posted?
## Post #85
- Username: ryu haybusa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 10, 2021 12:09 am
- Post datetime: 2021-06-07T21:36:18+00:00
- Post Title: Re: Ninja Gaiden Sigma 2 Model Format

@Protocol X27 
I was able to get around the byte check for file size by subtracting the bytes of the two files and using that number to add padding to the file. The only issue is this will only work if the target file is greater than the input filesize. Not sure how to get around "de-padding" to do the opposite.

[https://www.youtube.com/watch?v=erN1IeRRLQM&t=1s](https://www.youtube.com/watch?v=erN1IeRRLQM&t=1s)
