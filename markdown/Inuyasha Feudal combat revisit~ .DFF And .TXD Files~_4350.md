## Post #1
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2010-04-19T06:35:44+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-27T01:14:01+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

This game uses the newer Renderware engine, that Bloody Roar 4 also uses except that the .dff in this game are not compressed, and these files actually have the name each bodypart and article of clothing:

00 00 00 05 04 01 00 01 00 80 #Vertexes, 68, 4bytefloatvertexes(X,Y,Z)
(Padding of zero's in multiples of 4)
00 00 00 05 04 01 00 01 01 80 #TextureCoordinates, 64, 4ByteTextureMappings(U,V)
00 00 00 05 04 01 00 01 02 80 #NormalMappings, 6A, 2byteNormalMappings(X,Y,Z)

At the beginning of the file it is possible instead of 00 00 00 05 04 01 00 01, you will encounter 00 00 00 05 05 01 00 01

These might be load meshes, but they are not part of the main mesh, though in other games that use playstation2 meshes the 00 00 00 05 05 01 00 01 meshes are the main meshes so there is some probably some leeway when the game get compiled.

[http://ps23dformat.wikispaces.com/file/ ... shaw.blend](http://ps23dformat.wikispaces.com/file/view/yashaw.blend)
## Post #3
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-01-03T17:26:54+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Ah that explains why i couldnt get these DFF's to work on anything @.@

Stupid game has to be different >.<;; 

Thanks for your time and research FurryFan~
## Post #4
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-09T19:49:07+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Good to know someone's actually tries to dig into this one!  

Alright, I had really royal hard time researching on this format with no particular result (except the fact I got some tools to extract TXD textures). All I have now is a bunch of half-working GTA III tools that either crash or refuse to import new DFF files. I have two different 3DS MAX script packages for importing (none of hem works) and [HERE](http://sourceforge.net/projects/moomapper/) is a related tool with Delphi sources for GTA3/VC, If that can help.

And I'm lloking forward to cooperate with people from this thread: [viewtopic.php?f=16&t=5497](http://forum.xentax.com/viewtopic.php?f=16&t=5497)

Wait, how did you manage to import this into blender? o_O

Btw, there's this old topic viewtopic.php?f=10&t=2773 where people tried to open these DFF with RW Analyze with no success, BUT I am having no trouble opening them in RW Analyze 0.4 BETA right now.
## Post #5
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-13T06:01:29+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hey, Im doing the same thing, with a different PS2 game which also uses the Bloody Roar system. I have tried every fpk extractor I can find, but none work, since the fpks are extensionless. How do I get one that works? None of them seem to recognize the fpks I have. Perhaps it is the AFS extractor; is there a special AFS extractor I need to get them out in the right format?
Thanks,
Darkscion

EDIT: This turns out NOT to be the problem. I figured out how to extract them, and got working DFFs and TXDs. The problem is, I can't import them into 3ds max... the script I have doesn't work. any ideas on where to get a working DFF import script?
Thanks
## Post #6
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-13T16:36:25+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I've uploaded a fpack extractor tool on my site, read the thread I told about.

And for any clues about DFF you should probably ask FurryFan, not me. I'm still stuck.
## Post #7
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-14T00:00:20+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Never you worry, I have pmed FurryFan. We should get a solution very soon. I will post my findings here, and in my thread.
Thanks
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-01-14T08:25:53+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Take a look at this one?
[http://sourceforge.net/projects/rwsreader/](http://sourceforge.net/projects/rwsreader/)

Hope this help.
## Post #9
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-01-14T15:58:53+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from fatduck
>
> Take a look at this one?
http://sourceforge.net/projects/rwsreader/

Hope this help.

Is it just me or is there no download link for that rws reader? O.o 


i might be looking in wrong place lol
## Post #10
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-14T20:11:56+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

You are right- there are no files for download in that project. Anyone have any other ideas?
## Post #11
- Username: serenedays9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 31, 2010 7:43 am
- Post datetime: 2011-01-15T04:18:44+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

yes there is, browse its [SVN](http://rwsreader.svn.sourceforge.net/viewvc/rwsreader/source/)
So unless Source code is useful to you.......
## Post #12
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-15T10:44:54+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Tried to build it with cygwin and MSVC 6.0. It compiles fine, but does not seem to work.
## Post #13
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-15T10:50:49+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

BRW, there are gtatools sources too, but I don't have any more time to investigate.
## Post #14
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-15T18:15:44+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I can't use source code- I have no programming or compiling knowledge whatsoever. I will keep talking to FurryFan, he seems to have some sort of solution.
## Post #15
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-18T11:06:34+00:00
- Post Title: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hollower script for blender did not work either.  

DarkScion: So, were you able to contact him?
Any progress?
## Post #16
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-18T20:39:37+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Yes, I have been working with him in converting DFFs. He has made considerable progress, and gave me an almost perfect mesh he converted into .3ds using hex editor. He would be able to convert the DFF you want, but I would wait- he is really busy, and having multiple requests for conversions might overload him.
## Post #17
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-18T21:33:20+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Using HEX editor?? How?!
Ok, just give him InuYahsa, Kikyo and Sesshomaru models  (I have some right here if you want)
Also I can give some perfectly converted textures.  
I'll thank him personally too. 
[IY_DFF1.zip](https://xentaxbackup.github.io/file/3816_IY_DFF1.zip)
## Post #18
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-18T23:41:56+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Wait... how did you convert the textures? I will give him the files once he responds again- he has been busy with school and work, and will reply when he can. But first, I would need to know how to work with the TXD files. Can you tell me?
## Post #19
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-01-19T01:44:47+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

i got these two from Furry awhile ago, tho i had to retexture them~ still working on Sesshy XD
## Post #20
- Username: serenedays9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 31, 2010 7:43 am
- Post datetime: 2011-01-19T02:51:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Interesting, these would be great to rig for use in GMOD either as ragdolls or playermodels.
Sucks not having decent .dff importer scripts/plugins,though
## Post #21
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-01-19T15:22:08+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from Nathen41
>
> i got these two from Furry awhile ago, tho i had to retexture them~ still working on Sesshy XD

That's good news.
## Post #22
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-19T20:59:37+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

DarkScion
Use TXD Viewer, [http://www.steve-m.com](http://www.steve-m.com)
It's not completely trivial, though.

Nathen41
What do you men by "retexture"? Their UV mapping was not imported?!

serenedays9
I'll redo them for HL1/XDM fror which they'll suit perfectly. 

Alright, I can supply you with properly converted textures If you wish.
(only IY right now, have no time)

PS: actually, im-game model is quite different from this one from the trailer or previews:
[](http://img694.imageshack.us/i/inuyashafeudalcombat200.jpg/)
I wanted this one so much...  
[inu_tex.rar](https://xentaxbackup.github.io/file/3819_inu_tex.rar)
## Post #23
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-01-19T22:47:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Furrys way of ripping does not include the UVs~
## Post #24
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-01-22T13:40:27+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

LOL, is that so?  

[](http://img411.imageshack.us/i/furryswayofrippingv1.jpg/)


Srsly, this is BAD. Because I can even draw the mesh myself, but no texturing...
## Post #25
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-24T16:03:19+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Furry can get the UV coordinates... he knows how to do all of it. He uses Hex editor to convert the file structure to .obj, or .3ds... Although, he hasn't responded in a long time now, so I don't know what happened. I will check in with him about the models, and see.
## Post #26
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-02T08:56:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Any progress?
## Post #27
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-03T20:49:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Urghh... its the same way with everybody I try to contact... either they completely ignore me, or they talk to me for a while, and then ignore me....   
In any case, he has not contacted me in a long time, and I am doubting that he ever will. Perhaps another source would be better.
## Post #28
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-04T09:35:42+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

chrrox haven't answered me a single time either.

This could probably mean that they've been contacted/abducted/killed by copyrighters (I hope nobody will try to force me to remove my work) or they just don't want to share their achievements on they own. Sad thing. 

Anyway I'm still open for cooperation.
## Post #29
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:50:28+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

i think you should ask mariokart64n cause he is able to extract the 3d model of bloody roar 4 and it use the same format as inuyasha
## Post #30
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-05T01:18:04+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I will contact Mario, but I don't know if he will respond... I think I may have ticked him off with a comment I made once... but I will try anyway
## Post #31
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-06T21:53:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

That was the part where I was supposed to say "Leave the negotiation to me!" or something...  

Meanwhile I could not get any help on other forums. 
Hate damn closed proprietary file formats!
## Post #32
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-07T03:32:03+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

[](http://www.mediafire.com/?cunbshzu4xyl573)
## Post #33
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-07T04:56:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

O.o Even with Cell shading!!! Very nice~
## Post #34
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-07T05:51:14+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

[](http://cid-c59ea3c98a300f31.office.live.com/self.aspx/.Public/Game%20Mods/MikuMikuDance/PMD%20Models/%5E_BETA%20Models/pmd%5E_inuyasha%5E_test.zip)

ported to MMD ...oh yeah... he dances
## Post #35
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-07T06:48:00+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

mario,any chance you're gonna release the maxscript for bloody roar 4 and inuyasha ?
## Post #36
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-07T18:23:46+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

MY goodness you got him with bones as well? O.o
## Post #37
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-02-08T00:55:13+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from jaden
>
> mario,any chance you're gonna release the maxscript for bloody roar 4 and inuyasha ?
I second that, I'm ripping my BR4 too. Please, if you don't mind. mariokart is a pro, I've seen his posts in almost every modding site I've gone through.
## Post #38
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:10:37+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

i think we really should ask mariokart for the maxscript
I hope mario will share the maxscript
## Post #39
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-08T14:43:14+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

A script or a plug-in would be very nice!
Can't wait to port characters to HL1!
## Post #40
- Username: kjw2254
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 04, 2011 11:31 pm
- Post datetime: 2011-02-08T15:44:30+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

please Give me script.. i will be deep deep love u
## Post #41
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-08T18:51:31+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Yeah, how about it Mario? I also want to know how you converted the model in the first place... I have been trying to do that for months now.
## Post #42
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-09T01:48:01+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Yeah,please mario post the maxscript for bloody roar 4 and inuyasha
## Post #43
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-09T03:35:02+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~


## Post #44
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-09T17:56:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

[](http://img25.imageshack.us/i/ahmygoddesstv04snapshot.jpg/)
## Post #45
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-09T21:04:58+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~


## Post #46
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-09T23:53:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~


## Post #47
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T03:18:55+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~


## Post #48
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-10T04:16:56+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

WTF?! when did this turn into an anime posting thread? Did I miss something?    Hmmm... Me thinks I need to lay off the LSD for a while... (just kidding).
But seriously, Mario, share the love. We would all greatly appreciate your support of this awesome project- all it would take would a be a single post, no sweat. How about it?
## Post #49
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T04:33:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

first you want that, now you want this... 

no manners.. man, and the forum is being over run by 15yos begging for models. First off you all forget this is a FILE RESEARCH SITE. its not for sharing models, thus there should not be any posting of 3D content. 

I'd be happy to give you info, heck even tools if you actually had intentions of learning from it. but your all here to leech models.. O_o you might as well enjoy the anime, cause its just as random as these people asking to "give us models"
## Post #50
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-10T04:45:58+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
> WTF?! when did this turn into an anime posting thread? Did I miss something?    Hmmm... Me thinks I need to lay off the LSD for a while... (just kidding).
But seriously, Mario, share the love. We would all greatly appreciate your support of this awesome project- all it would take would a be a single post, no sweat. How about it?

Ack you ruined the moment  lol

i felt like i was actually seeing a conversation with those pics~ XD

starting with mine~ "Aww cmon help us out~" 

then xawari's "Yeah...."

mariokart~ " But i... well... Err..."

jaden "We'l love you for a long time~"

mariokart "lol"
## Post #51
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-02-10T07:38:47+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from mariokart64n
>
> first you want that, now you want this... 

no manners.. man, and the forum is being over run by 15yos begging for models. First off you all forget this is a FILE RESEARCH SITE. its not for sharing models, thus there should not be any posting of 3D content. 

I'd be happy to give you info, heck even tools if you actually had intentions of learning from it. but your all here to leech models.. O_o you might as well enjoy the anime, cause its just as random as these people asking to "give us models"

kudos to that
## Post #52
- Username: serenedays9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 31, 2010 7:43 am
- Post datetime: 2011-02-10T16:24:47+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I'd be interested in said information or possible tools.

Offtopic, learned a lot from your ragdoll tut on FP btw.
## Post #53
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-10T21:09:49+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Well, I could probably understand if copyright owners refuse to make their work freely available to public and get angry at people like us, but... how do I say it... Between us, game hackers and modders, there's an unspoken rule to help each other in our efforts. This topic doesn't seem to fall under that way of things. 

Anyway I've contributed my part and wish luck to those people working on the conversion tool.
I'll keep TXD tool on my site and I can host DFF tools it there'll be any.

> no manners.. man, and the forum is being over run by 15yos begging for models
wtf? dunno for sure, but I thought you missed by about a decade.


[](http://img708.imageshack.us/i/013sml.jpg/)

PS:

> I'd be happy to blahblahblah...Don't make excuses for just being a greedy bastard
## Post #54
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T21:43:39+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

right....

anyway the script isnt mine, so I'll leave it up to the author if he wishes to release it or not. sorry about the anime pics, I thought it was amusing
## Post #55
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-10T22:24:30+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Well am not upset XD~ since it wasnt your script, I totally agree with you holding it and not giving out without the author's permission.
## Post #56
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-10T22:57:14+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

@mariokart64n
The anime picture is amusing and very refreshing
## Post #57
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-11T06:06:12+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

........ I asked for a tool, not models. I HAVE the models, it is the conversion I need. I DO intend to learn from them, in fact 3d modeling is my primary interest in this website. Secondly, I am NOT anywhere close to 15 years old, and I was not being rude. Im sorry if I offended you, but I was just pushing for what everybody else on this thread is looking for. 
Perhaps you could direct us to the author of the tool, maybe he would give permission to use it (although I don't know why it would be kept so hush hush in the first place, when it would obviously help out the game modding/3d modeling community greatly)

For all you Inuyasha/other DFF conversion people in this thread, I have gotten back in contact with FurryFan, who converted one of the DFFs I had from a PS2 game with a very similar format to what you all are interested in converting. I will check out his conversion, and see if he might be able to work out a converter or tutorial for us.
## Post #58
- Username: kjw2254
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 04, 2011 11:31 pm
- Post datetime: 2011-02-11T12:49:24+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

ultra quality yasha3D!!
## Post #59
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-11T14:09:32+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

kjw2254 where did you get that inuyasha model ???
## Post #60
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-11T21:23:30+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

@kjw2254 nice model, looks like its rendered in blender, but a bit lowpoly for a fan created model.. if it was created from scratch they could have subdivided it.. so I'm guessing your not the author of that model.

@DarkScion
chrrox made the script, as for the format its very easy. almost 80% of the PS2 games use the same method of storing geometry. you have 4bytes that give ID,count, and sizes then the verts. faces are generated on the go for every 3 verts.

since this works by giving you an ID, you can just scan through a file can collect and convert all known IDs. the problem with that is, sometime you'll grab data that is not that of what you would expect, and you'd import garbage. I'm guessing thats why the script wasn't posted.. as 70% of the time it wont work, without further modification. how ever I'm pretty good at 3d editing, so its not hard for me to cleanup the model.

also I don't see you guys trying to analyze the format in any way.. so I dont get what your going on about.
## Post #61
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-02-13T02:06:56+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Well I found out that Bloody Roar 3 (and probably 4) don't even have any recognizable formats in them other than .mot and .tim2. there's a few weird ones like .txg, .seq and .jcv. But what they refer to is unknown to me. I might have to start attempting to hack the emulator to spit out some useful data. 


EDIT: Most of the files in chr/"character's name" have tables at the top of the file so I'm sure it's 'rip-able' some how, the .fpk's don't however. You do see some recognizable words though.
Also, since "xawari" posted useful links so will I. 
[http://ps23dformat.wikispaces.com/Bloody+Roar+4](http://ps23dformat.wikispaces.com/Bloody+Roar+4)
[http://ps23dformat.wikispaces.com/How+To+Extract+Models](http://ps23dformat.wikispaces.com/How+To+Extract+Models)
I think "mariokart64" made the site too  .
## Post #62
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-13T03:42:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

yes bloody roar use the same format
As inuyasha
Cause the developer is eighting
## Post #63
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-13T20:34:49+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

TXD/DFF is RenderWare format, has several different versions. There is some difference between PS2 and PC variants of the same version (game).


kjw2254: yours is cute :3
But looks a litle... umm.. as if it was chewed 

PS: just came to join our "screenshot contest" 
[](http://img651.imageshack.us/i/domskytown10036a.jpg/)
## Post #64
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-02-13T21:23:19+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

is that a custom made Inuyasha? O.o or did you get the script from chrrox?
## Post #65
- Username: kjw2254
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 04, 2011 11:31 pm
- Post datetime: 2011-02-13T23:41:21+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

sorry

Iam not so good at english..  
-----------------------------
It is custom model.

1. dff virsion 3.7->3.5 change (2004~2005 ps2 3dmodel.. renderware 3.7)
2. RW3.5 viewer->3dripper capture 
2. rework dff model..  (3dsmax)
## Post #66
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-02-14T06:26:52+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from kjw2254
>
> sorry

Iam not so good at english..  
-----------------------------
It is custom model.

1. dff virsion 3.7->3.5 change (2004~2005 ps2 3dmodel.. renderware 3.7)
2. RW3.5 viewer->3dripper capture 
2. rework dff model..  (3dsmax)

interesting subject...
I have a couple of questions
How to conversion 3.7 to 3.5?
Where can i download RW3.5 viewer
## Post #67
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-14T10:50:33+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from Nathen41
>
> is that a custom made Inuyasha? O.o or did you get the script from chrrox?
It's a partially repainted model converted by mariokart64n. It took many hours to make it fit HL1/XDM.
chrrox did not answer topic/PMs so I consider he does NOT want to cooperate in any way. And that's what I am frustrated about: if someone's made the script, why should everyone else reinvite the bicycle again? That's stupid.
## Post #68
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-15T03:08:20+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hmmm.... I would like to get my hands on that viewer as well... Can someone post a link to it? I have a bunch of DFFs I think are in version 3.7 I would like to check out... they are from a game that came out in 2007.
## Post #69
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-02-15T20:06:44+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Btw, here are some useful links:
[http://www.gtamodding.com/index.php?tit ... tream_file](http://www.gtamodding.com/index.php?title=RenderWare_binary_stream_file)
[http://sourceforge.net/projects/moomapper/](http://sourceforge.net/projects/moomapper/)
[http://www.gtagaming.com/downloads/gta-vice-city/tools](http://www.gtagaming.com/downloads/gta-vice-city/tools)
[http://www.steve-m.com/downloads/tools/rwanalyze/](http://www.steve-m.com/downloads/tools/rwanalyze/)

but none of available tools support IY DFF format now.
## Post #70
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-15T23:39:06+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks
## Post #71
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-20T21:40:02+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Anyone have any luck finding the Renderware 3.5 viewer? (although, a 3.7 viewer would be better)
## Post #72
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-23T16:38:47+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

GTA and Sonic heroes also use this format, try this:

[http://www.steve-m.com/downloads/tools/rwanalyze/](http://www.steve-m.com/downloads/tools/rwanalyze/)

And try to import it into 3ds max with the GTA scripts.
## Post #73
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-23T20:28:10+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hmmmm... that might work, but it seems a bit of a stretch. RWAnalyze seems very difficult to use, and the export option is not user friendly (although, neither is the program itself). Also, it has not been updated to work with RW 3.7, which I'm pretty sure is the format of Inuyasha and the game I am trying to work with.
## Post #74
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-23T20:55:22+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

It probably won't then. It hasn't been updated since 2004, so...
## Post #75
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-03-03T14:26:16+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I tried ALL available GTA tools and none worked.

Btw, anyone converted Kikyo? (^_^)
## Post #76
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-03T23:57:10+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

i think we really should ask mario for the script
## Post #77
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-03-05T21:27:57+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from jaden
>
> i think we really should ask mario for the script
Yeah, but that can backfire. If you've search over most of his post (not just this forum) he dislikes many people who have nothing to offer (seems like it). Kind of like being a contributing member to the online community. So either learn C++ or some programming methods or something else, before you can get anything done. This seems to pertain to unpopular games only though. Like GTA, Soul Calibur, RE 4, L4D2, and so on. It also depends on the length the developers go to encrypt their files. 
In other words, check back in a year.
## Post #78
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-06T02:21:06+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

lol..

thats one way of putting it, basically I got annoyed with people.

like I'd put days or weeks into something, like alot of work.. put it up. and people slam it.. picking at stupid things and what not.
Or if things went well, then people would become ignorant and beg or !demand that I do or give them things.. as if it was expected.

if I ever argued or complained.. I get nearly the same replies.. about the internet being free or I don't own rights to hold back said content.. some crazy bull
then after that you get haters.. and after that you get a bad rep.. and after that you get people saying your a nazi.. <_<

ya.. what sparked this whole event was that DarkScion guy who "Demanded" some "said" content.. and it brought back alot of hate in me..

anyway this has gone a bit overboard.

here's the script chrrox made up for that guy. I tweaked it a bit to read past missing UV sections. but its still glitchy being it scans for 4bytes then assumes the following data is correct. if its not you get alot of garbage.

the script also imports each strip as an individual object. so unless you know your stuff in a 3d editor.. you might aswell slam your head into a wall.

```
caption:"Renderware Importer" \
types: "generic renderware format(*.dff)|*.DFF|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(
    
fn PrintOffset Var =
(
    local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
    Var
)
fn PrintCount Var =
(
    local Var = Var
print ("This is the Count 0x" + (bit.intAsHex Var) as string)
    Var
)

fn Readword fstream = (
return readshort fstream #unsigned
)

fn ReadFixedString bstream fixedLen =
(
    local str = ""
    for i = 1 to fixedLen do
    (
        str += bit.intAsChar (ReadByte bstream #unsigned)
    )
    str
)
with redraw off (
struct Mesh_Info_Struct
(
    Mesh_Name,vertstart,vertend,vertcount,facecount
)


mscale=39.34


Mesh_Offset_Array = #()
UV_Offset_Array = #()
while (ftell f) != fsize do (
        
byte1 = readbyte f#unsigned
if (byte1==0x04) then(
byte2 = readbyte f#unsigned
if (byte2==0x01) then(
byte3 = readbyte f#unsigned
if (byte3==0x00) then(
byte4 = readbyte f#unsigned
if (byte4==0x01) then(
fseek f 3#seek_cur
test2 = readbyte f#unsigned
fseek f -4#seek_cur
if test2 == 0x68 do (
append Mesh_Offset_Array (ftell f)
)
-- if test2 == 0x64 do (
-- append UV_Offset_Array (ftell f)
-- )
)
)
)
)
)
print Mesh_Offset_Array.count
print UV_Offset_Array.count




for a = 1 to Mesh_Offset_Array.count do (

Vert_array = #()  
Normal_array = #()
UV_array = #()
Face_array = #()
fseek f Mesh_Offset_Array[a]#seek_set
Print ("Vert @ 0x"+((bit.intAsHex(ftell f))as string))

byte1 = readbyte f#unsigned
byte2 = readbyte f#unsigned
byte3 = readbyte f#unsigned
byte4 = readbyte f#unsigned
for b = 1 to byte3 do (
vx = readfloat f*mscale
vy = readfloat f*mscale
vz = (readfloat f*-1)*mscale
append Vert_array [vx,vz,vy]
)
-- fseek f UV_Offset_Array[a]#seek_set
for sk = 1 to 40 do (
        
byte1 = readbyte f#unsigned
if (byte1==0x04) then(
byte2 = readbyte f#unsigned
if (byte2==0x01) then(
byte3 = readbyte f#unsigned
if (byte3==0x00) then(
byte4 = readbyte f#unsigned
if (byte4==0x01) then EXIT

)
)
)
)

fseek f 3#seek_cur
test2 = readbyte f#unsigned
fseek f -4#seek_cur
if test2 == 0x64 then (

Print ("TVert @ 0x"+((bit.intAsHex(ftell f))as string))
byte1 = readbyte f#unsigned
byte2 = readbyte f#unsigned
byte3 = readbyte f#unsigned
byte4 = readbyte f#unsigned
for b = 1 to byte3 do (
tu = readfloat f
tv = (readfloat f*-1)+1
append UV_array [tu,tv,0]    
)

)else(
for b = 1 to Vert_array.count do append UV_array [0,0,0]
)

fa=1
fb=2
fc=3
append Face_array[fa,fb,fc]

for x =1 to (Vert_array.count-3) do(
fd=fa
fa=fc
fc=fd
fa+=1
fb+=1
fc+=1
append Face_array[fa,fb,fc]
)


msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]

for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

-- for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
-- selectmore msh
)
-- group selection

--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")
```


PS! be more involved, stop begging.. ask questions but be polite and help where you can.

-mariokart64n
## Post #79
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:34:04+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks a lot mario       
Sorry if i bother you
Yeah i agree with your motto mario,be more involved and and help where you can
I think we all should say thanks to mario because mario is very kind to post his maxscript
Please appreciate him
## Post #80
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-13T02:34:48+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Yeah, Thanks Mario for the script- by the way, I was not "demanding" anything, I just got overzealous. I am not much good at talking to people, especially online where anyone can take anything you say wrong, so if I came off as rude or demanding, I'm sorry. I do have knowledge to offer, and I have helped others various times. I would give this script a test, but a poorly timed (and badly needed) computer reformat lost me all the files I was working with. I may be able to get them again, but for now, I have other things to worry about. Thanks again, though.
## Post #81
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-14T04:13:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks mario

DFF import success
[PS2]Battle Stadium D.O.N v3.7.0.2

[PS2]Bloody Roar 4 v3.5.0.0

[PS2]Fate/Unlimited Codes v3.7.0.2

[PS2]Inuyasha - Feudal Combat v3.7.0.2

[PS2]Rurouni Kenshin Enjou Kyoto Rinne v3.7.0.2

[PS2]Shijyou Saikyou no Deshi Kenichi v3.7.0.2

[PS2]Zoids Struggle v3.6.0.3

Using 3D Object Converter
[PS2]Bleach Erabareshi Tamashii v3.7.0.2
[PS2]Zoids Tactics v3.7.0.2
************************************

DFF import fail
[PS2]Fullmetal Alchemist Dream Carnival v3.7.0.2
[PS2]One Piece Round The Land v3.5.0.0
[Wii]Super Robot Wars NEO v5.8.0.5C
[PS2]Zatch Bell! Mamodo Battles v3.7.0.2
[NGC]Zoids Full Metal Crash v3.7.0.2
## Post #82
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-14T23:16:35+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

WHOA!!!! YOU DID IT!!!............... S-S-S-SWEETNESS! 
Minor problem, however... Young Mark, how did you get the model textured? As our gracious savior Mario said, the models come out with individualized strips... I am somewhat good with max, but I have no idea how to texture the models using the TXD texture in the first place, let alone with hundreds of strips. Got any ideas?

By the way, Mario..... you ROCK, man.
## Post #83
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-15T03:24:17+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
>  WHOA!!!! YOU DID IT!!!............... S-S-S-SWEETNESS! 
Minor problem, however... Young Mark, how did you get the model textured? As our gracious savior Mario said, the models come out with individualized strips... I am somewhat good with max, but I have no idea how to texture the models using the TXD texture in the first place, let alone with hundreds of strips. Got any ideas?

By the way, Mario..... you ROCK, man.


I normally use Metasequoia tool.
## Post #84
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-15T16:17:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Ah. Well, I figured it out- I don't use Metasequoia, but I figured out a tool that extracts .TXD files. It turns out that although the model is split up into individual strips, as a whole it retains the in-game model's texture mapping. So all you have to do is drag-and-drop onto all of the strips, and it comes together nicely.






EDIT: I also figured out (later) that by fusing the strips (using the edit poly: attach tool) into a single mesh, you can then smooth the model using the vertex weld modifier. This is all in 3ds max, of course. So both of the models I posted images for above are smoothed now.
## Post #85
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-16T20:06:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I'm happy to see members getting the models soo well. I was sure I was gonna see alot of replies like "How do I make the texture show?"

since theres a few of us capable of re-assigning the textures properly. why not each of us take on a game title... fix all the models, and swap them with the other members?

right now I'll commit to fixing BloodyRoar4, i'll aim for 1 week and share my results.

if your interested let me know, and we can swap PM's or emails. I don't mind posting tools openly, but I'd rather keep any exchange of the content between those who are contributing.

ps my emails listed no my profile.
-mariokart64n
## Post #86
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-16T20:48:46+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hey Mario,
that sounds like an awesome idea. I am working on fixing all the Kenichi Models (as seen above). There aren't really any problems with them to speak of, so it is mostly just combining the strips, texturing, and smoothing that is necessary. I would Love to get my hands on the other models from the other games mentioned. I noticed Youngmark mentioned the Bleach game, also known as Bleach: Blade Battlers. I would love to get my hands on all of the models from that game.
Thanks for the idea, that would be very cool if we could do that.
## Post #87
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-16T21:25:02+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Alright cool, then I'll trust you'll take care of that game.

**ALSO, PLEASE DO NOT WELD THE STRIPS TOGETHER**

encase you, or someone else assigns the texture wrong, the strips are the only clue we have to setting them properly. some games only use 2-3 textures on a model. but something like bloodyraro4, uses 60 on one character. also some people weld by a high factor, and actually geometry is damaged. so please, don't do anything past assigning materials, as anything more could possibly hinder the quality of the model. it doesnt take more then a few seconds for anyone here to weld and smooth the model
## Post #88
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-17T01:04:41+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Jeesh! 60 on one character!!!   Dang... thank god you are doing that one... well, I should have all the models imported and textured within the week... although, there are multiple outfits for each character, meaning multiple models for each character. What format would everyone like them in? I prefer .max (2010 version) since it is so versatile, but I can export to other formats- Im just not sure how well the Texture IDs would hold up in the conversion process. I have had models lose texture mapping when converted and opened again. 

Another note: If anyone is using 3ds max 2010, be careful and save often when working with these models, especially if you do want to smooth them and combine the strips. vertex weld and the attach tools make 3ds max highly unstable and prone to crashing on these models- and every time this has happened, Max failed to save or recover the model (very frustrating after hours of work). Just to warn you all.

EDIT:
Mario, how would you suggest smoothing the models if vertex weld and strip combining shouldn't be used? I like the models, but they would be even better if they were smooth.
## Post #89
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-17T01:40:36+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I have the latest max, so that's fine with me. although OBJ is a respected format to use, as most programs support OBJ import. the exporter for 3dsmax has always been buggy. the early ones didnt handle materials, and the new one sometimes skips untextured objects. so saving in (*.max) would be the most desired, as it limits the likelihood of data loss.

as for smoothing, your welcome to weld your models, just don't weld the ones your going to share

as for how to smooth in max, without welding:

>select all mesh objects and add a Edit Normal Modifier. 
>enter edit mode turn on welding
>CTRL+A to select all the normals
>use a weld threshhold, of 0.001 or 0.01 .. and weld the normals

this will smooth the model, without compromising the geometry.

remember normals control how light bounces off the surface. vertex welding normalizes your normals which causes the same effect in the end.. however vertex welding can also cause damage to the model, if vertices are too close, when welded.

example, someone sent me a model, he welded by too much. and the characters lips were welded shut. I would have to spend additional time inspecting the model and fixing anymore muck ups. so its best to not weld, when sharing to others. as they may find usefulness in the operated objects.
## Post #90
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:23:05+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Well im a noob to max so i still learning on how to assign the texture
Here is the game list that is extractable with mario script
-(PS2) Rurouni kenshin enjou kyoto rinne
-(PS2) Fate unlimited codes
## Post #91
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-17T13:57:57+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

mariokart64n, nice work on renderware format, I'm appreciated, it's hard to add bones/weights import?
## Post #92
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-17T14:41:00+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Can anyone get started on the Bleach: Blade Battlers game while we are at it? Or at least send me the DATA.AFS from the game so I can import the models. Mario, thanks for the idea... I will try that. Just curious, what is everybody on this thread interested in doing with the models? Personally, I intend to make a Machinima film once I learn more about animation and advanced rendering in 3ds max.
## Post #93
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T23:58:56+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Im gonna use the model to learn more about 3d modeling
## Post #94
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-18T00:47:28+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

you guys realize i gave Mario the script. He just posted it because he got sick of people bitching.
This script just scans the dff format for the vertex chunk id and there is no face data the faces are in order of how you read the verts.
weighting and bones will not be supported due to how this format is read.
## Post #95
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-18T09:03:52+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks for the awesome script chrrox
## Post #96
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-18T10:49:07+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from chrrox
>
> you guys realize i gave Mario the script. He just posted it because he got sick of people bitching.
This script just scans the dff format for the vertex chunk id and there is no face data the faces are in order of how you read the verts.
weighting and bones will not be supported due to how this format is read.
Thank you very so much.
## Post #97
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-18T17:51:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks, Chrrox... although I think we all already knew you wrote it. Mario was careful to cite you as the creator, even though he modified it a bit.
## Post #98
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-19T01:31:55+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Also chrrox how's the mgs4 progress    ??
## Post #99
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-03-19T02:11:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks chrrox
## Post #100
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2011-03-20T13:34:17+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Thanks for the great script, was recently looking for a way to open the models inside BR4 but saw there was no way to do it until now.


Here's Reiji in his 3rd costume; I tried to assign the textures to him the other day 
in 3ds max but it takes way too long since there's so many mesh strips 
scattered everywhere- not to mention his UV map looks like a rat's nest.
## Post #101
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-20T23:38:40+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Mario, any updates with the models you were working on? Mine are almost done, I should have all the models textured and uploaded within a few days.

Does anyone have access to the bleach game files? I would really like to start working on those models too. Youngmark, you listed the bleach game in your post- can you get me the files I need?
Thanks
## Post #102
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-21T00:45:06+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

lol, haven't you been reading the posts above.. BR4 is the hardest to assign mats for.

its not too difficult for me, but it would take 5-10mins per model.. and there are alot of models.

and besides you, there is no one else in the pool. the models you have are nothing, I already have half of them already assigned from last time.
I'm busy with other stuff, so unless others join the pool. I'm in no rush to get BR4 done. <_<
## Post #103
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-21T03:00:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
> Youngmark, you listed the bleach game in your post- can you get me the files I need?
What kind of thing do you want? dff file?

I'm so sorry. Please excuse my poor English
## Post #104
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-21T14:08:16+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Youngmark,
I need the DFF and TXD files for each character from the bleach game... could you get them to me? Please keep the original file structure intact, I need to keep the models seperated. If you could do that, that would be great. 

Mario,
Don't worry about it- I was just asking how progress was going. I have read the above posts, and I can wait for the BR4 models- no rush.  

Would anyone else like to join me and Mario's project? It would speed things up considerably.
## Post #105
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-22T03:27:16+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
> Youngmark,
I need the DFF and TXD files for each character from the bleach game... could you get them to me? Please keep the original file structure intact, I need to keep the models seperated. If you could do that, that would be great. 
y.
cfc.dig & xp.pak in Bleach Blade Battlers series is compressed.
## Post #106
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-22T04:22:24+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

There's no DATA file? How did you get the models to work with originally? As long as I know which TXDs go with which DFF, it should be fine. Do you have access to the model files?
## Post #107
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-22T05:08:48+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
> There's no DATA file? How did you get the models to work with originally? As long as I know which TXDs go with which DFF, it should be fine. Do you have access to the model files?
Sorry..I can't extract cfc.dig file.

Please wait! I will upload cfc.dig file soon.
## Post #108
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-22T06:08:51+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Here
## Post #109
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-03-22T23:21:15+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Oops... sorry... I misread the game names. Bleach: Blade Battlers isn't even the same game... Bleach: Erabareshi Tamashii is the game you said, right? THAT game is in renderware format, meaning it should also have the standard compression methods, .fpk and .AFS. Young Mark, assuming you looked up the game I accidentally asked for, could you get me the files from Erabareshi Tamashii (NOT Blade Battlers, sorry... whoops)? I can bet the files will be in the proper extractable format.
Thanks
## Post #110
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-03-23T08:34:56+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from DarkScion
>
> OBleach: Erabareshi Tamashii
I have only one sample
## Post #111
- Username: kjw2254
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 04, 2011 11:31 pm
- Post datetime: 2011-03-23T13:09:59+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

arigatou!!!
## Post #112
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-03-24T01:51:58+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

this Really blasted off O.O;;;, 

Thank You Mario & Chrrox
## Post #113
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-04-04T20:35:59+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

.......... is that it? Is this the end of the revered Inuyasha DFF and TXD reverse engineering thread? Maybe it's just me, but I thought there was more out there to work on. How 'bout it guys? Lets see some images of models extracted from renderware games! Post some pics, share some models!
## Post #114
- Username: phorks88
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 04, 2011 5:52 am
- Post datetime: 2011-04-04T20:55:41+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Hello,
For a while I've been trying to extract the Bloody Roar models and this scrip by Chroxx and Mario looks like the answer. However I'm having trouble compiling the script; I've never made a C prog before. I don't know what libraries, compiler to use etc, etc,...
If it's no trouble could someone put up a compiled script? Or a small guide? I'd be very grateful.

If i could get the models on 3ds or import to blender I'd start mapping the textures (which I already have) manually, and happily share if I have success... 
Thanks.
## Post #115
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-04-05T01:39:11+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

phorks88, 
the script is very simple to work with, don't worry. It is designed for 3ds max, so all you have to do is copy and paste the script into notepad, and save the document as a maxscript file. I forget the file extension, but it is easy to find using google or looking in your 3ds max script folder.
## Post #116
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-04-05T03:40:13+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

in 3dsmax goto the MAXSCRIPT menu drop down in the application bar. and select NEW Maxscript...

that'll create a new emtpy maxscript where you can copy & paste any script there. press CTRL+E on that window to Execute the script

alternatively if there is a ****.ms maxscript you can just drag and drop it into the 3dsmax screen.

maxscript is flexible, as it does not require compiling, like a program language.. aka C+

C plus is great for portability, and well not having to install max, but its harder to learn.. well for me it is.
## Post #117
- Username: phorks88
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 04, 2011 5:52 am
- Post datetime: 2011-04-06T00:34:52+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I just got 3dsmax and but only now i see the maxscript function. I got the models loaded and am already texturing...

Thanks for clearing that up for me, and thanks mario and chroxx for putting up this cool script.
## Post #118
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-04-16T08:06:47+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Wow I'm really glad you guys got what you wanted so much 

Btw, anyone converted Kikyo? ^_^
## Post #119
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-04-17T03:02:13+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from xawari
>
> Wow I'm really glad you guys got what you wanted so much 

Btw, anyone converted Kikyo? ^_^
   

I use Mario & Chrrox maxscript and I have alot excess edge

I take an hour to del all these edge

All dff I import by a script alway have unnecessary edge
How to i fix it without del these edge?
## Post #120
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-04-18T02:46:06+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

what game is that?
## Post #121
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-04-18T03:30:42+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from mariokart64n
>
> what game is that?
Fate unlimited codes PS2
I have the same problem with Inuyasha .dff import too
Actually this problem happen to all .dff ps2 game i import by a script
## Post #122
- Username: xawari
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Jan 10, 2011 3:35 am
- Post datetime: 2011-04-18T09:09:53+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

> Reply from Trishty
>
> 
   
I use Mario & Chrrox maxscript and I have alot excess edge
All dff I import by a script alway have unnecessary edge
How to i fix it without del these edge?

Since I don't have 3DS max, can you export Kikyo model into OBJ with UVs and stuff for me please?   
As far as I can see those triangles are not "unnecessary" but have some misplaced vertexes due to incomplete chain reading algorithm in importer script. That's very hard to fix manually IMHO.

PS: InuYasha is lonely without her >:)
[](http://img130.imageshack.us/i/file0017e.jpg/)
## Post #123
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-15T13:05:20+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

in max just add an optimize modifier to the mesh it will remove those un used edges.
## Post #124
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-22T03:17:49+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

btw how do i import dff from fma dream carnival?
i pm'ed you chrrox but you didn't reply >_>
## Post #125
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-22T03:23:25+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

I already said in this thread I have no interest in the dff format. that is why i dint post the script in the first place.
The only reason i made the script was to help mario kart out in learning how to do scripts.
so if the dff script does not work on a certain game there is not much i can do to help.
## Post #126
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-22T04:21:32+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

Oh i see. But how do i remove those edges in 3dsmax? The optimize modifier does not work, the vertex weld does but ruins some parts of the mesh.
## Post #127
- Username: Ultraxwing
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 24, 2011 4:02 am
- Post datetime: 2011-05-29T15:37:28+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

hello, i am rather new and starting how to 3d model.

i've been modding homeworld 2 for about 3 years now, and it introduced me to 3d models.

and for a while i made rather mediocre models. well, i want the inuyasha models so i can import them into Super Smash Bros. Brawl.

it's a rather frivilous request. but i wantto learn how to Bone Rig, and as well make appropriate UV maps. as well as seperate polygon 

this is one of my rather mediocre models, lacking UV maps and rigging.
[http://ultraxwing.deviantart.com/#/d3cjgjt](http://ultraxwing.deviantart.com/#/d3cjgjt)

and if someone doesn't mind giving me the fixed Inuyasha models. its sorta the only reason why i'm here, but i might stay to learn how to make appropriate models and better skill.
## Post #128
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-03T02:35:06+00:00
- Post Title: Re: Inuyasha Feudal combat revisit~ .DFF And .TXD Files~

How to Extract the CFC.DIG [https://www.youtube.com/watch?v=vM2J7UnHzqc](https://www.youtube.com/watch?v=vM2J7UnHzqc)
