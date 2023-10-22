## Post #1
- Username: Jak
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 22, 2006 8:19 pm
- Post datetime: 2006-05-22T12:32:30+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

Hi imn noob hear ,need mod this  .sfs .mis files enybod knows how to open?
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-05-24T10:04:08+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

You know perhaps that Il-2 series and all other Oleg's titles are extra protected against any unauthorised entry. This is the reason why people who occassionaly like to snoop into files are so   there, or in many cases  rather completely stay away. Me being just such a example specimen.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-24T17:49:33+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

About the SFS files, here's what I found out so far (based on the files found here: [viewtopic.php?t=1708&highlight=il2](http://forum.xentax.com/viewtopic.php?t=1708&highlight=il2) ) .  See the attached image below. 

Besides that, it seems the first table is XOR encrypted with a string of 6 bytes: 

```
72, 7D, BB, E6, 36, A3
```


so, for each byte in the table, that is 218 entries of 32 long, you should rotate  through the array of encrypt bytes and XOR the current byte. 

Something similar is the case with the second table, my guess is the encrypt byte array is :

```
BB, 36, 72, 65, A3
```


The second table is padded at the end to a size of 0x1000. 

How I come to these conclusions? Well, most variables in a table are 32-bit right? And most of the time, the highest byte will be 0. So, these bytes are also encrypted. But 0 encrypted with some code will be the code itself. Thus, with a little logic and deducing and looking for patterns I came up with the above. I still don't know what the table entries actually mean. I would need a whole archive, or maybe even more archives. 

It does seem the files in there start with a magic word: "RSAV".
[example.jpg](https://xentaxbackup.github.io/file/749_example.jpg)
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-05-24T23:39:20+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

Nothing is "sacred" over here   
What are those *.sfs files ? *.mis I assume stands for mission.
## Post #5
- Username: Jak
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 22, 2006 8:19 pm
- Post datetime: 2006-05-31T16:48:46+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

> Reply from Xela
>
> Nothing is "sacred" over here   
What are those *.sfs files ? *.mis I assume stands for mission.

Just thinking if i can mod new maps in this game ,thinka that .sfs files includet information maps.
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-05-31T21:19:07+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

Talk to me , I like terrainmaking in the games. Unfortunately I am dead clueless about Oleg's games, because they are so bent to protect their content. Let us just say I respect that
## Post #7
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2006-06-09T02:52:30+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

And I thought my il2 request was forgotten  

no, their archives are not sacred, no matter how stubborn they are about them. at least not when access to them is needed to do more than add skins and missions.  We buy a game, we have every right to change things about it(but the buying part is sacred)

I did some poking around a while ago about what an .sfs was.  I think it might be this thing called Single File System....tools you can buy for packing together tons of files into one file.  some guy claimed to get into the files with a vaguely referenced program "file extractor"
## Post #8
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2006-07-14T02:42:55+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

Sorry for double posting, but someone has managed to crack the sfs archives.

[http://il2mania.com/](http://il2mania.com/)<- in spanish, use a translator

You'd think this news would be all over, but the tight*** community stubbornly refuses to understand the whole point of modding games.
## Post #9
- Username: UberDemon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 17, 2006 8:53 am
- Post datetime: 2006-07-17T00:56:15+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

FYI,

I stumbled here by accident and saw this post... Against my better judgement, I guess I'll add my two cents...  not trying to start a fight or anything, just share some info.  The biggest issue the IL-2/FB/AEP/PF/Pe-2 community has with modding is not modding per se, but unfair (non-historical) advantage and cheating in online games.  Offline modding, frankly, who cares.  The producer of the series, Oleg Maddox has stated that the IL-2 engine is moving towards a more modding friendly environment anyway in the link below.

[http://forums.ubi.com/eve/forums/a/tpc/ ... 80943/p/14](http://forums.ubi.com/eve/forums/a/tpc/f/63110913/m/8371080943/p/14)

Here is the quote:

> We also plan to give third party more free hands to build themselves without our control objects, small online maps, planes and cockpits.... 
>
> 
>
> DON'WORRY!
>
> This means that we will have two rooms for multiplay:
>
> 
>
> 1. Standard our staff room where custom made third party planes can't fly...
>
> 2. the room of online gameplay for our standard set and the planes of third party...
>
> 
>
> If user community and we ourselves will find that som guy of third party did the right job, then we will move such plane in a standard set as well.
>
> 
>
> In this case we will be more free to make new things and feature than to support third party models and community will decide which plane to play or not from third party...
>
> 
>
> I also expect to replace by such things the industry around the MS add-ons 
>
> 
>
> It is in all we plan and it isn't all that will be released righ with the release of the sim. 
>
> Say tools we will release after ther release of the sim itself... and first tools will be for objects and maps, then later for planes... if possible 
>
> 
>
> Note for the third party developers about these features of BoB: 
>
> we don't give full access to source code. We give access just for some basic tunings of FM and animations which will be possible to use only in single play custom made special room missions and only in special online room for such planes.
>
> If it will be not possible to make such a scheme then we will cancel the work over custom planes... and will keep just objects and maps.
>
> And will repeat we don't give ability to create the big maps, which we will keep for ourselves that to make new sims of new theaters.

As far as people decrypting/decompressing SFS files, it was just a matter of time.  Two people came out on the record saying that they successfully decrypted the files, changed parameters of the game, and then packed them back, and played the game with changes.  Neither of the two said they will make their applications available to the public, unless the developer fixes the next release... not sure what that means.

1 - The first one was Kegetys in Finland, he is revered as a great modder in the Operation Flashpoint circles.  I have no idea how he developed it, but he showed the most obvious proof of his claims with a video.  In the video, he flies in an AI only plane, the Morko Morane, using the cockpit of a Brewster Buffalo.  More impressive, he gets out of the plane with the pilot, and controls the pilot, walks around the plane, and then jumps back into the cockpit and takes off.  It is not a made up movie, it is a real in game sequence.  Also note that when he is running around the plane, the lower left of the screen shows the direction changing according to the way the "pilot/player" is facing.  His video is available from one of his websites at [http://koti.mbnet.fi/kegetys/il2-morane.avi](http://koti.mbnet.fi/kegetys/il2-morane.avi)

His post is at [http://www.simhq.com/simhq3/sims/boards ... 005391;p=3](http://www.simhq.com/simhq3/sims/boards/bbs/ultimatebb.php?ubb=get_topic;f=144;t=005391;p=3) and is quoted below:

> I  made something like this a while ago, ie. a program that allows extracting everything from the SFS files and then modifying them. I'm not sure if someone else has done the same or if the rumours are just now surfacing about my tool, but doing it was very easy, and I would be surprised if someone else would not have already done the same thing years ago. Upon experimenting with this, I found that the game has absolutely zero cheat protection; You can do whatever changes you want and it will work online, the server doesn't verify anything the clients do which is a disaster, and I would say it might even be quite likely that some people could have been using something like this for a long time already to cheat online.
>
> 
>
> Since the game is about 95% coded with Java, and the java files are there in the SFS files, they can be decompiled and recompiled to make the game do pretty much whatever you could ever want. For example, I made a little experiment mod that allows you to jump out of the plane, run around on the ground and then go back in and continue flying. I also made the MÃ¶rkÃ¶ Morane and some other planes flyable, with cockpits from other planes... I also added some extra controls like a key that when held down, shows the gunsight view with full zoom. all of these were quite easy to do and are just some examples of what is possible. Here's a video showing some of these.
>
> 
>
> Anyway I have not released my tool because of the cheating problem, though as I said it wasn't very difficult to do so some other people could have done the same thing. It is, in my opinion, a quite bad and inexcusable mistake from the developers to not include any kind of cheat protection in the game from the start.
>
> 
>
> What is a bit odd though is that the developers were notified about this somewhere around April/May already (When I made my tool and found out about the lack of cheat protection), and now they're saying that 4.06 was "already released" back then?

2 - Second person is a fellow that goes by QTim, and posted about his application "SFS Extractor" at forum.sukhoi.ru .  The actual thread is [http://forum.sukhoi.ru/showthread.php?t=41236](http://forum.sukhoi.ru/showthread.php?t=41236) , but I have no idea what is being discussed as it is in Russian... and with Babble Fish, it gets even more confusing.  Oleg stated that this guy did it only for fun and that he did not share it with anyone.  I have no idea what this guys did exactly, and I am not sure what the P-11 video proves.  In the [http://forum.sukhoi.ru/showthread.php?t=41236&page=3](http://forum.sukhoi.ru/showthread.php?t=41236&page=3) link, he shows a few pictures of a mod he claims to have done in which the smoke of the train displays "CCCP" (USSR = Soviet Union)... at least that is what I make of it.  Here they are...

[http://forum.sukhoi.ru/attachment.php?a ... 1151341330](http://forum.sukhoi.ru/attachment.php?attachmentid=57782&d=1151341330)
[http://forum.sukhoi.ru/attachment.php?a ... 1151341330](http://forum.sukhoi.ru/attachment.php?attachmentid=57783&d=1151341330)
[http://forum.sukhoi.ru/attachment.php?a ... 1151341330](http://forum.sukhoi.ru/attachment.php?attachmentid=57784&d=1151341330)
[http://forum.sukhoi.ru/attachment.php?a ... 1151341330](http://forum.sukhoi.ru/attachment.php?attachmentid=57785&d=1151341330)
[http://forum.sukhoi.ru/attachment.php?a ... 1151341330](http://forum.sukhoi.ru/attachment.php?attachmentid=57786&d=1151341330)

I guess someone with a whole lot of time could have done it in Photoshop, but I don't think so.  What is more interesting is that he shows a recording of his application at work.  He opens one of the Map SFSs, and it decompresses all the fies... and it all is there, the graphics, etc.  The video is located at: [http://slil.ru/22876410](http://slil.ru/22876410) (name of the file is sfs.avi) but it is so slow that you won't be able to download it unless you have some type of download manager like FreshDownload and have some patience.  What is interesting is that you can see in his directory tree that he used Borland C++ Builder 5.

Best Regards,
Uberdemon
[http://www.uberdemon.com](http://www.uberdemon.com)
## Post #10
- Username: UberDemon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 17, 2006 8:53 am
- Post datetime: 2006-07-24T04:56:20+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

And a couple of other things that Kegetys seems to be working on relating to free zooming in a IL-2 cockpit... pretty impressive stuff:

[http://koti.mbnet.fi/kegetys/il2-tirvec.avi](http://koti.mbnet.fi/kegetys/il2-tirvec.avi)

and

[http://www.youtube.com/watch?v=FFTRsBcSyk8](http://www.youtube.com/watch?v=FFTRsBcSyk8)

... as mentioned above, also done by manipulating SFS files.
## Post #11
- Username: QTim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 26, 2006 8:13 pm
- Post datetime: 2006-07-26T12:30:24+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

Hello guys!

Great post, Uberdemon!

If you have some questions about SFS, and the game itself, post them here - I'll try to answer. But don't expect too much. I keep my words, so I don't want to release this stuff to the public.

P.S. Let's wait for BoB.

P.P.S. Yes, I love C++Builder. What's so funny?
## Post #12
- Username: UberDemon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 17, 2006 8:53 am
- Post datetime: 2006-07-27T01:28:20+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

> Reply from QTim
>
> Hello guys!

Great post, Uberdemon!

If you have some questions about SFS, and the game itself, post them here - I'll try to answer. But don't expect too much. I keep my words, so I don't want to release this stuff to the public.

P.S. Let's wait for BoB.

P.P.S. Yes, I love C++Builder. What's so funny?

Hello.  Not that I find it funny or anything... I actually used Borland C++ 3 years ago, but I am very rusty.  I got lazy and old and since I am not a professional programmer, I just "program", if you can call it that, in VB... I know... perhaps not the most advanced language, but fun and easy nevertheless.

I don't have many questions.  I figure we'll see what happens, and hopefully Oleg will make the online protection better.  Very interesting that you decrypted SFS... I was thinking maybe it was AdAim's Single File System for a while, but in reality it was more of a curiosity I had.

I am having less and less time for my hobby in creating 3rd party apps for IL-2 these days, but I like to follow what is going on in the community.

UberDemon
## Post #13
- Username: QTim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 26, 2006 8:13 pm
- Post datetime: 2006-07-27T11:16:53+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

The first thing I have tried is to change something in the game. Then I tried to decompile Java classes and recompile them back. Note that not all classes can be successfully decompiled. As far as I know, JAD is the only program allowing to do it (all the GUI programs are based on JAD).
So I started with screenshots. As you know, the game saves them in TGA format. Every time you should convert it to JPG if you want to show it to somebody. I have rewritten that class to save the screenshots as JPGs. And it wasn't difficult (I have never used to program in Java before).
The other problem is to do something bigger, like that finnish guy did. Recently, I have seen a movie, showing 6DOF in the cockpit. It's a nice feature, what do you think?
## Post #14
- Username: UberDemon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 17, 2006 8:53 am
- Post datetime: 2006-07-29T05:22:43+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

The 6DOF stuff is very impressive, and so is the control of pilots and using existing cockpits in other planes.  Oleg should hire you and Kegetys...     

Understand JAD.  I guess I am puzzled how you actually got to SFS.  That is some impressive encryption I think.  Anyway, I am not really asking you to reveal anything.  Just mentioning that is impressive.

Back in the day I tried to "hack" IL-2 as much as possible for Oleg just to find weaknesses in the online engine (that was done in support of the pre release testing, and with Oleg's knowledge).  With the help of some other testers we discovered a few flaws and reported them to Oleg's team.
## Post #15
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2006-07-31T21:29:48+00:00
- Post Title: IL-2 Sturmovik .SFS  .MIS

So how can someone without encryption/C++ knowledge mod sfs files?

Apparently its easy enough to do, if someone would just post a how to, we could keep il2 interesting.  Not being able to fly the P-36 at pearl harbor or anywhere else, nor the morane fighters and most ground attack planes, and having a small map choice in QC, things get boring pretty quickly.
## Post #16
- Username: QTim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 26, 2006 8:13 pm
- Post datetime: 2006-08-01T08:00:53+00:00
- Post Title: 

this is the question of time. just wait for 4.07 patch.
## Post #17
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2006-08-06T00:54:36+00:00
- Post Title: 

yeah but then they'll change and make the encyrption harder.

  Or are they just planning to actually perform a check for online games to make sure the files are unaltered?
## Post #18
- Username: QTim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 26, 2006 8:13 pm
- Post datetime: 2006-08-12T08:44:51+00:00
- Post Title: 

> Reply from Eraser
>
> yeah but then they'll change and make the encyrption harder.

  Or are they just planning to actually perform a check for online games to make sure the files are unaltered?
afaik, there will be continuous, delayed checks. and not only of SFS files, but also of inner files.
## Post #19
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2006-08-13T12:59:35+00:00
- Post Title: 

So they're not changing the encryption so we could still get into the SFS files and change stuff?
## Post #20
- Username: Eraser
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 24, 2006 5:15 am
- Post datetime: 2007-01-17T20:12:19+00:00
- Post Title: 

IL-2 1946 with 4.07 and checks against cheating online...Now how to get in and mod stuff QTim?
## Post #21
- Username: Amadeus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 17, 2007 2:42 pm
- Post datetime: 2007-07-31T15:03:01+00:00
- Post Title: 

Hello all together!

With my first posting, i would like to know, if ther're some new informations about the Opening of the .sfs-files of IL 2 1946?

For information: I'm a single-player and i never play online. I only wanna change some things for myself.
## Post #22
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-01-26T22:09:46+00:00
- Post Title: 

I was (I still am) looking for an SFS unpacker for Theater of War when I stumbled upon this web page:
[http://www.timqwerty.narod.ru](http://www.timqwerty.narod.ru)
You can find a tool there that supposively (I do not have the game, so I could not try) extracts the SFS files from IL2.
I tried it with a ToW SFS file - naturally it shows garbage.
Anyway, you have a tool now. If you find one that extracts the Theater of War SFS files as well, please let me know.
Thanks.
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-27T08:44:02+00:00
- Post Title: 

Thanks!

I've uploaded it to my tools folder: 

[http://www.xentax.com/uploads/author/mr ... eta_11.rar](http://www.xentax.com/uploads/author/mrmouse/sfs_extractor_v2.0_beta_11.rar)
