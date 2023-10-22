## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-08T14:27:15+00:00
- Post Title: Modding Results

```
This thread was formerly known as "PAINKiller - 1st experiences


```



Let me be the first to post some small modding experience here then. 

Game: Painkiller

- Using the DDS plugin for Adobe Photoshop 
(available here: ttp://developer.nvidia.com/object/nv_texture_tools.html )
- Using Painfull 
(extractor/importer for Painkiller PAK files availabe here : [viewtopic.php?p=3626#3626](http://forum.xentax.com/viewtopic.php?p=3626#3626) )

I was able to alter some sounds for creatures (took some from C&C Generals) in sounds.pak, and textures in textures.pak. See below  
[Shot0000.JPG](https://xentaxbackup.github.io/file/25_Shot0000.JPG)

[Shot0008.JPG](https://xentaxbackup.github.io/file/24_Shot0008.JPG)

[Shot0014.JPG](https://xentaxbackup.github.io/file/23_Shot0014.JPG)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T09:01:30+00:00
- Post Title: Modding Results

You can toggle different view modes from within the editor (simply select another and return to the game):
[Shot0023.JPG](https://xentaxbackup.github.io/file/31_Shot0023.JPG)
## Post #3
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-21T11:26:40+00:00
- Post Title: Modding Results

Ok really, no teasing here - how are you doing that ?
The only way I have been able to get the box outlines to show is in the no clip mode, but they are only displayed while clipping is turned off.
Cmon dude, share the beans.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T11:33:37+00:00
- Post Title: Modding Results

(get the new version of Painfull first)
-Start Painfull
-Start the game (start a level)
-Press escape to view options menu, then switch to Windows and Painfull
-In Painfull, select Game->View PainEditor
-From within Pain Editor (the mouse is invisible, but you just have to do some target practice) select the view mode (see screenshot from Killerpain)
-Return to the game (don't worry, Pain Editor will stay visible) and resume the level, voila

Look for this in Pain Editor:
 You can select different views at one, here Wireframe is highlighted. I have to work on a way to get the mouse visible.
## Post #5
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-21T13:34:13+00:00
- Post Title: Modding Results

Alright, this is where ya lost me :
-In Painfull, select Game->View PainEditor
 What do you mean " select game" ?
I'm using v 1.1, and I dont see anything for "select Game "
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T14:01:16+00:00
- Post Title: Modding Results

> Reply from Mr.Mouse
>
> (get the new version of Painfull first)-Start Painfull
-Start the game (start a level)
-Press escape to view options menu, then switch to Windows and Painfull
-In Painfull, select Game->View PainEditor
-From within Pain Editor (the mouse is invisible, but you just have to do some target practice) select the view mode (see screenshot from Killerpain)
-Return to the game (don't worry, Pain Editor will stay visible) and resume the level, voila

So, get the new version already ! (1.3)
[viewtopic.php?t=732](http://forum.xentax.com/viewtopic.php?t=732)
## Post #7
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-21T15:25:21+00:00
- Post Title: Modding Results

OK, got it.

And thank you, this rocks !![/img]
[Shot0020.JPG](https://xentaxbackup.github.io/file/33_Shot0020.JPG)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T15:58:17+00:00
- Post Title: Modding Results

Hehe, yeah, i'd seen that mode too  
Still need to figure out a way to make that damn mouse come back in the Editor window, they turned it off, but Killerpain made a screenshot and HIS mouse was visible. I'm just too stupid to know how to get it back, apparently.
## Post #9
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-21T16:02:00+00:00
- Post Title: Modding Results

Use the force, luke.

Ha ha ha ha.

Cursors ? we dont need no stinking cursors !!!

Actually, yeah - a cursor would be great.
But since I haven't a clue where you went to get all this working, I wouldn't know where to start looking for the instructions for capturing the mouse.
## Post #10
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-21T18:18:52+00:00
- Post Title: Modding Results

Wait - here's a thought...
Have you tried exporting the cursors as .res files out of paingame.exe and into painfull.exe ?
Since it is Painfull.exe that enables the viewing of the editor, perhaps it will use the cursors if you put them in there ?
Or, place all of the .cur files in a new .pak file named cursors.pak and have loader.lua load it ?
Just a thought.

EDIT : 
Well crap, I created cursors.pak and nothing.
but since loader.lua loads scripts and not .pak files, this isn't much of a surprise.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-05T11:52:29+00:00
- Post Title: Modding Results

I just thought this would make a subject for the Holy Cow! forum. There's a lot of questions asked about this or that file type, people figuring out archive formats and the like. The general idea behind this all is of course modding a favourite game. 

But what happens after the analyses are complete?

Are people effectively changing the way a game looks, plays or sounds? 

Personally, I'd like to hear about it, because then we know why we do it .

So, if you have any mods to share - even though small, like changing a model or even texture - then share it here! 

You might just make us shed a tear from happiness. It would bring so much joy to our grey and hexeditor-bound lives!
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-30T07:46:06+00:00
- Post Title: Modding Results

As you can see, no-one shares the final results of their modding efforts.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-06-30T16:08:44+00:00
- Post Title: Modding Results

That kind of sucks... But then, no one responded to my thread on the new Wiki BBCode, and I posted that as a global announcement two months ago...
## Post #14
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-06-30T17:26:48+00:00
- Post Title: Modding Results

I once changed the intro of a Yu-Gi-Oh! game for the PS2 to an episode of Yu-Gi-Oh! The Abridged Series
d4mn fun I say...btw if you're wondering what that has to do with the topic...well you asked for modding results right?...
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-01T06:05:55+00:00
- Post Title: Modding Results

Yes, I did. Perhaps we should have a MOD your favourite game contest, no big professional stuff, but the stuff ordinary people could do using the right tools...
## Post #16
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-01T09:45:50+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
>  Yes, I did. Perhaps we should have a MOD your favourite game contest, no big professional stuff, but the stuff ordinary people could do using the right tools...

I believe I still have it around, if you want I can capture my screen playing it and eter the contest...but there are two problems...one is the quality would suck and I have no other way of capturing it, and the other is that something happened (proably my mistake because I'm inexperienced with MPEG-2 and PSS multi/demultiplexing and all, I could have set something wrong) when I converted the video to pss and after replacing it manually with the intro movie file (same name and all), everything went smoothly but when I played the game it seems that the audio had some problems...it wasn't synchronised with the video and it ended up being some second after the place it was supposed to be which means it came out crap...also some times the video presents flickering problems (but other than that the quality is very good and it only lasts for a split second)...I could do it again, I wanted to change a movie in Shin Megami Tensei Persona 3 (inside a .cvm archive containing the game's files), the movies were in .sfd form, that's softdec video for you, I was able to demultiplex them (standard MPEG-2 video but .adx audio I think) and they played fine but when I started looking for a way to make/convert to a .sfd file I only found the Dreamcast SDK (specifically the SEGA DREAMCAST Movie Creator) ...which is impossible for me to get for these reasons:

1. DC is dead
2. Even if it was alive the SDK is for Windows 98/2k
3. Even if they still sold the SDK there would be no way for me to afford it
4. Even if I could afford it my parents wouldn't let me spend my money on it
5. Even if my parents said yes there's no way SEGA could ever give me the licensing thingie

so if you know something that can convert to .sfd please tell me also I'd like a program that would let me convert to .m2v, for some reason SUPER's .mpg conversion does something wrong, even if I select MPEG-2, I used tmpgenc for the Yu-Gi-Oh! trick but my trial has expired...
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-03T11:40:28+00:00
- Post Title: Re: Modding Results

Well, perhaps there are some tools that could do that. Or you could "obtain" the SDK from somewhere, perhaps "borrow" it. You got an example SFD file? If it is a simple format, perhaps it would not be difficult to create a tool that merges the ADX and MPG back to SDF.
## Post #18
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-03T15:11:55+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Well, perhaps there are some tools that could do that. Or you could "obtain" the SDK from somewhere, perhaps "borrow" it. You got an example SFD file? If it is a simple format, perhaps it would not be difficult to create a tool that merges the ADX and MPG back to SDF.

right now no but I can get one in 30 seconds, I open the data.cvm file with isobuster, find the folder with the .sfd files and extract them...it's that easy, and I use pss_demux to demultiplex them, I'm not 100% sure about the .adx audio  layer extension though, but I think that's what it is...if you want I can upload an .sfd for you to take a look at, I can upload pss_demux too
I've noticed the .sfd extension in other games too but I don't remember which ones...I may be wrond but I think Way of the Samurai 2 uses the format, either that, or .pss, anyway I can't validate now 'cause I don't feel like playing, and besides, I'd have to go to the video club and rent it again, and I'm too bored for that right now...
The .cvm file in P3 is an image or something, I can replace the files in it with my own, I tried it with an .adx and it works, I replaced the battle bgm of the final boss with In the End by linkin' park, totally awesome, I like doing stuff like that 
I'll upload a small .sfd if you want.
I can create a .pss file using PSS Plex and I still have 10 days left for the free trial of tmpgenc it seems, funny, time passes way slower than I though, but 10 days don't last for long any way you look at it so any freeware program would be appreciated.
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-03T16:38:29+00:00
- Post Title: Re: Modding Results

Yeah, sure why not upload an example of a sfd file. Wouldn't hurt to take a peek at one. 

 "Awaiting upload"
## Post #20
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-03T19:56:51+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Yeah, sure why not upload an example of a sfd file. Wouldn't hurt to take a peek at one. 

 "Awaiting upload"

Well ok I've confirmed the adx audio since there is a file called adx.dll in pss_demux's folder, I'll upload PSS_DEMUX, too the output files are m2v and wav converted from adx when I use it on a .sfd
I'll upload the output files too just in case, not that you can't do it yourself, but what the heck
The movies are split into parts, there are 30 movies, and they are like this: P3CT[movie number]_[movie part].SFD
the files I chose are P3CT030_01.SFD and P3CT030_02.SFD, there are the credits and the intro too but I'm bored to upload these, if you want them tell me but I don't see why they would be so different...
Right now I'm archiving them, I'll edit my post with the Rapidshare link.

Edit:

Done, voila (around 120 mb file):

[http://rapidshare.de/files/39905125/SFD.rar.html](http://rapidshare.de/files/39905125/SFD.rar.html)
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T07:37:59+00:00
- Post Title: Re: Modding Results

Okay, yesterday I've taken a brief look at them and I should be able to extract an mv2 file from the SFD. When I compare the mv2 and the SFD, I notice there's a 0x1c bytes extra information part every 0x7e0 bytes in the video file in the SFD, that is removed in the mv2 file. I wonder what that is, perhaps info pointing to the sound part of the file. The SFD file is divided up in chunks of 2048 (0x800) bytes, and we've still got to find out what all the header information means. 

I think we've got to move this discussion to the Graphics Forum, so others can take a look at this at the same time. The question is basically, what is the File Format of SFD files.
## Post #22
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-04T09:29:33+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Okay, yesterday I've taken a brief look at them and I should be able to extract an mv2 file from the SFD. When I compare the mv2 and the SFD, I notice there's a 0x1c bytes extra information part every 0x7e0 bytes in the video file in the SFD, that is removed in the mv2 file. I wonder what that is, perhaps info pointing to the sound part of the file. The SFD file is divided up in chunks of 2048 (0x800) bytes, and we've still got to find out what all the header information means. 

I think we've got to move this discussion to the Graphics Forum, so others can take a look at this at the same time. The question is basically, what is the File Format of SFD files.

I'll create a topic in the graphics sectionsince moving this topic wouldn't really be the best since this was originally a topic for people to post what modding they did
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T10:30:49+00:00
- Post Title: Re: Modding Results

No need, I can split this topic.
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-08T19:36:44+00:00
- Post Title: Re: Modding Results

Mods eh? I don't have any pictures with me... will videos do?  

[Console maps recreated in Doom 2](http://www.youtube.com/watch?v=04kJnyP3afA)

[Fester's Quest monsters in Doom 2](http://www.youtube.com/watch?v=g92iByDO5lE)

[Fester's Quest cyclops in Doom 2](http://www.youtube.com/watch?v=ERjp6EwqBQ8)

[zCorridor, Corridor 7 in GZDoom](http://www.youtube.com/watch?v=zQ3LfhZ9XNs)

[zCorridor, exhibiting some more modded in goodness](http://www.youtube.com/watch?v=KoMfpsGZ7R0)

I'm also working on a Megaten Doom.
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-08-08T21:22:00+00:00
- Post Title: Re: Modding Results

Hey that's pretty good, I like the cylops creature and the lighting and textures of the zCorridor.  

Back in the day I also did some mapbuilding with the original stuff, I believe in an editor called DoomEd. I remember The Gee recreated our university building and filled it up with enemies. My own was pretty nifty with hidden stuff, airshafts and surprise attacks.
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-08T22:14:21+00:00
- Post Title: Re: Modding Results

zCorridor is my big project. I'm happy on how it is progressing, and thanks. The cyclops thing is from Fester's Quest, an NES game. Ah retro. XD

I remember the old doom too, and thats pretty cool! Today we have Doom Builder which is pretty great, new doom builds like zDoom, GZDoom and so on use scripts and can have several custom enemies, weapons, items and so on perfect for the modder. Also GZDoom supports high res and fully colored PNG graphics as seen in the Shin Megami Tensei map. The textures for that map came directly from the Playstation port of the game converted from TIM to PNG, later I may make an animated texture for the doors instead of them being black openings.

Anyways, thanks! 

Edit: Also, back in the day I used to mess with Duke Nukem 3D but I got no examples there >_<.

Also here's a few more older ones I did for Revenant:

[Wraith player](http://www.youtube.com/watch?v=Sxb9MiumuS4)

[Solifuge 1](http://www.youtube.com/watch?v=jdob6shSC4A)

[Shadow Minion](http://www.youtube.com/watch?v=Lu9-h_tNXQM)

[Solifuge 2 with left and right attack](http://www.youtube.com/watch?v=eP2UgmqhtQA)
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-24T10:10:07+00:00
- Post Title: Re: Modding Results

Hey, made a slight revision to my zCorridor TC taking advantage of GZDoom's GL features like reflective floors.

[Here](http://www.youtube.com/watch?v=7CfiDuBdwJ4)

I also changed many of the menu graphics to look more Corridor 7ish. The idea here is to not just remake the old Corridor 7 game, but give it some atmosphere with the reflections and lighting. Also improve some stale points in the original game hopefully.

The main idea though is to keep it fun of course! 

Edit: Also, forgot to mention that another great addition thanks to zDoom/GZDoom is cooperative gameplay and multiplayer deathmatches. Something the original Corridor 7 was limited in.

[Early Cooperative Gameplay](http://www.youtube.com/watch?v=DloAIR1XfyA)

Just me and a friend, we were bugtesting... but... mainly goofing off.
## Post #28
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-01T01:08:31+00:00
- Post Title: Re: Modding Results

Since Settlers 2: Rise of Cultures seems to be only available in German, I started to translate the UI file into English. Hopefully it gains some popularity as a result 

I included both the unencrypted version in case someone wants to translate it further and the encrypted one that is ready to be used in the game (by putting it in the data/game/language/de folder).
[AdKEng.rar](https://xentaxbackup.github.io/file/1671_AdKEng.rar)
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-01T01:10:04+00:00
- Post Title: Re: Modding Results

Heh, interesting! Not often I see PC games get translated.
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-01T07:29:10+00:00
- Post Title: Re: Modding Results

That's cool! Can you make some screenshots of the translation in action ? (I don't have the game) , perhaps a nice Before and After screenshot. So we can make a newspost out of it! 

Are you going to put this also up at trass3r.xentax.com ?  You really should fix that download problem there :p
## Post #31
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-01T12:21:50+00:00
- Post Title: Re: Modding Results

Well it's a lot of strings, I haven't translated much yet, only the most important stuff.
Yeah I know, but as always the problem is time. I have many projects going.

btw, as you see, I always started with capital letters, e.g. Create flag, Lumberjack, Fishing lodge,..
is this ok or should I use small letters for building names, etc.
## Post #32
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-01T19:48:04+00:00
- Post Title: Re: Modding Results

Personally I have no issue with it. I think snags the attention well enough.
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-01T21:31:25+00:00
- Post Title: Re: Modding Results

That looks good! I think it works well with the characters like that.
## Post #34
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-08T17:29:29+00:00
- Post Title: Re: Modding Results

I used MultiEX Commander to make mods for the game MX vs ATV Unleashed for the PC. 

My mods are called: Caffeine I, Caffeine II, Caffeine III, and Tweaks.

Basically the Caffeine mods take all of the motorcycles and ATVs and make them way faster than stock. The mod also makes it harder to crash the bikes/ATVs and adds some other features listed below.

My Tweaks mod took the curse filter off of the in-game chat and added some other features listed below.

If anyone is interested in these mods: 

Caffeine III [http://www.xentax.com/uploads/author/mr ... ne_III.zip](http://www.xentax.com/uploads/author/mrmouse/SHI_Caffeine_III.zip)

Tweaks [http://www.xentax.com/uploads/author/mr ... Tweaks.zip](http://www.xentax.com/uploads/author/mrmouse/SHI_Tweaks.zip)

There are plenty of haters out there than like to delete the file from their sites and then there are others that understand what it is and leave it posted.

I get a lot of love and hate for making these mods from the game's players. There are a lot of kids out there that think mods ruin a game or that mods are the cause of game companies not producing updates or new products -- you wouldn't believe the ridiculous comments I hear on this matter. Then there are the gamers that truly appreciate a great mod and understand that mods keep old games alive, etc.


Here are the read_me's from Caffeine III and Tweaks (warning: they are long!):

=========================
WHAT IS CAFFEINE (A NOT-SO-BRIEF HISTORY OF CAFFEINE)?

Let's face it, the stock physics for MX vs ATV Unleashed are slow and boring. So, back in November of 2006, I released the original Caffeine (a.k.a. Caffeine I).


CAFFEINE I:

Caffeine took the stock physics for the ATVs and the 50cc, 125cc, 250cc, and 500cc bikes and made them all faster and better handling. Caffeine also added further enhancements. Some of the key features of Caffeine I are:

* Race and Pro physics handling are identical (both are based on the original Race physics), so no more jittery handling when using Pro physics.

* Both physics models are enhanced, so you're never riding stock. Instead, you choose which level of speed you prefer. Race physics are faster than a stock bike/ATV, but not as fast as Pro physics. Other than the raw speed there is no difference between Race and Pro physics.

* Wheelies and Stoppies are enhanced. Try them at any speed and see.

* Backflip and 360 rotation/braking speeds are increased.

* Landing off any jump is virtually crash-proof! Try landing into corners in the direction you want to exit. Landing perpendicular to a jump (almost 180 degrees from your launch trajectory is doable.) Try landing into the face of a jump! (Hint: Due to the nature of this mod, it is better to wreck than to time out. So, if you go off the track be ready to hit one of the stunts and ride it to the ground to force a wreck. This method will get you back into the race ASAP.)

* On the rare occasion when you do wreck, the time you spend on the ground is cut in half.


CAFFEINE II:

In April of 2007 Caffeine II was released. Caffeine II built on Caffeine I's popularity with more speed and other enhancements. Some of the key features of Caffeine II are:

* Wheelies and Stoppies are further enhanced. Try them at any speed and see. Your stunt score for wheelies and stoppies is unlimited with Caffeine II.

* Reverse on all bikes and ATVs has been increased from 10 MPH to 50 MPH! Freak your buddies out and race them backwards! 

* Caffeine II's 360 and Backflip rotation speeds have been slowed down, as compared to the original Caffeine, to make them more useable, but they are still way faster than stock.

* Landing off any jump is virtually crash-proof! Try landing into corners in the direction you want to exit. Landing perpendicular to a jump, or now with Caffeine II you can land completely backwards (180 degrees from your launch trajectory). Bad-ass whips and 360s without the stunt button are easily accomplished with Caffeine II.

* On the rare occasion when you do wreck, the time you spend on the ground is virtually ZERO with Caffeine II.


CAFFEINE III:

Here it is January of 2008 and Caffeine III has been released. Caffeine III takes all of the features of Caffeine I and II to the next level and adds a few new features. Some of the key features of Caffeine III are:

* The speed of all bikes/ATVs has been pumped up even more! All I can say about the 500 Pro bike is, you'd better be holding on for dear life (especially on the MX tracks when the power really kicks in!) The power/speed of all bikes/ATVs are more proportionate than they were with Caffeine I or II -- I think this makes it much more realistic.

* The bikes/ATVs will stay closer to the ground, in most cases, allowing you to get back down to earth sooner and ripping around the track. Be warned, however, the bikes/ATVs will feel "heavier" and if you mess up the timing on most tracks, you will pay the price! It can take some time to get back up to speed and in the rhythm of the track again, especially on the smaller displacement bikes. You may have to learn new lines that you normally wouldn't run with either Caffeine I or II in order to go as fast as possible with Caffeine III.

* Engine braking has been greatly enhanced. Instead of dragging your brakes while still on the throttle, or outright using them, try letting off the throttle when you're in a corner or just before leaving the face of a jump. The enhanced engine braking will scrub major speed from the bike/ATV allowing you to hold your line in the corners and help prevent over jumping on the track. Brakes are virtually a thing of the past! One consequence of the increased engine braking is that your stoppies will be shorter than they were with Caffeine II -- this is a small price to pay, though.

* The RACE physics for all Caffeine III bikes/ATVs are now the equivalent of Caffeine II's PRO physics. The PRO physics for all Caffeine III bikes/ATVs are the new Caffeine III physics. So, as with all past versions of Caffeine, RACE physics are slower than PRO physics, but both will crush a stock bike.

* Added Caffeine and Tweaks credits to the game's scrolling credits.

* All of the features of my Tweaks mod are included in the Caffeine III PAK file. Tweaks adds the following features to both online and offline play, unless otherwise noted:

   - Eliminates the ridiculous kiddy filter from the game's chat window. Therefore, no more AAAAAAAAAAAAA's when trying to chat with your online buddies.

   - All 500cc bikes now sound like 2-strokes, instead of the unrealistic and piggish 4-stroke audio used within the game.

   - Fireworks now sound when the winner crosses the finish line of most outdoor events. Now you will know when the leader has finished the race. Note: this doesn't work for user tracks, but it in no way hinders the use of user tracks.

   - The starting gate now randomly drops on events that use one. This is more realistic than the gate always dropping at the same time in every race. Note: this doesn't work for online play, but it in no way hinders online play.

* All of the other features of Caffeine III, not mentioned above, are exactly the same as Caffeine II.


INSTALLATION:

UnZIP the contents of the SHI_Caffeine_III.zip file into a temporary directory on your hard drive. 

If you have any of the following files in your MX vs ATV Unleashed game's Data directory, remove them (they may conflict with Caffeine III):

!!!_MVA_WFOO_MOD_motocrossWboy.PAK
!SHI_Caffeine.PAK
!SHI_Caffeine_II.PAK
!SHI_Tweaks.PAK
$500_2stroke_audio.pak
dirty.pak

Note: Remove any program that may alter the same game functions as any of the above files -- I may not have a complete list of all the mods that change the same functions now, or in the future.

Copy only the !SHI_Caffeine_III.PAK file to your MX vs ATV's Data directory. This ReadMe text file and the SHI_Caffeine_III.jpg picture are included in the ZIP archive for your reading and viewing pleasure, but they are not necessary in order to use Caffeine III.
=========================


Tweaks for MX vs ATV Unleashed

Tweaks adds the following features to both online and offline play, unless otherwise noted:

* Eliminates the ridiculous kiddy filter from the game's chat window. The list of filtered words is long and quite funny, at times. So, no more AAAAAAAAAAAAAAAA's when trying to chat with your online buddies.

* All 500cc bikes now sound like 2-strokes, instead of the unrealistic and piggish 4-stroke audio used within the game. Thanks to FrAnTiK for the use of his work on the 2-stroke 500cc bike audio.

* Fireworks sound when the winner crosses the finish line of most outdoor events. Now you will know when the leader has finished the race. Note: this doesn't work for user tracks, but it in no way hinders the use of user tracks.

* The starting gate now randomly drops on events that use one. This is more realistic than the gate always dropping at the same time in every race. Note: this doesn't work for online play, but it in no way hinders online play.

* Added Caffeine and Tweaks credits to the game's credits.

Tweaks WILL NOT ALTER THE PHYSICS OF THE BIKES/ATVs IN ANY WAY WHATSOEVER. IF YOU ARE RUNNING STOCK THEN YOU WILL STILL BE 100% STOCK WITH THIS MOD.

Tweaks is fully compatible with !SHI_Caffeine (original version, AKA Caffeine 1) and !SHI_Caffeine_II. Tweaks and either version of Caffeine will peacefully coexist in the Data directory.

If you are already using dirty.pak and/or $500_2stroke_audio.pak just remove them from your game's Data dir before installing Tweaks.

To install Tweaks just unpack the !SHI_Tweaks.PAK file to your MVA/Data directory.
=========================
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-08T20:28:41+00:00
- Post Title: Re: Modding Results

Nice stuff you go there! We could host those files, maybe?
## Post #36
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-08T20:32:51+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Nice stuff you go there! We could host those files, maybe?

Sure, if you guys want to host them, I'm all for it. 

The problem with the MX vs ATV Unleashed community is that it's full of little crybabies that think any mod ruins the game (they call it "cheating"). Some sites will delete it as soon as they realize it's a mod, and others will leave it up. Different strokes for different folks, I say.

Let me know how/where to upload them to this site.

Also, please check your PMs concerning GTR Evolution.
## Post #37
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-08T23:13:22+00:00
- Post Title: Re: Modding Results

Well, just how big are these mods? You could always upload them at some upload.com or whatever them sites are called, and I could then easily download them.
## Post #38
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-08T23:22:50+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Well, just how big are these mods? You could always upload them at some upload.com or whatever them sites are called, and I could then easily download them.

They are only 475k and 600k.

Is there an upload area here, I honestly never looked.
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-08T23:26:52+00:00
- Post Title: Re: Modding Results

With those sizes, you can simply attach to your post at the forum! Click the button when you post a new message, to attach files to your message.
## Post #40
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-09T00:17:11+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> With those sizes, you can simply attach to your post at the forum! Click the button when you post a new message, to attach files to your message.

256k maximum allowable attachment limitation.
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-09T00:25:50+00:00
- Post Title: Re: Modding Results

Okay, well, email them to me
## Post #42
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-09T02:44:13+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Okay, well, email them to me

Hmmm, well... I would, except your profile shows no Email address, only PM.
## Post #43
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-09T06:55:43+00:00
- Post Title: Re: Modding Results

But below each of my post you should see my email. anyway: [mr.mouse@xentax.com](mailto:mr.mouse@xentax.com)
## Post #44
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-09T14:09:48+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> But below each of my post you should see my email. anyway: mr.mouse@xentax.com

Email on the way, and a screenshot too!
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-09T15:54:27+00:00
- Post Title: Re: Modding Results

Cool... I've fixed the email issue I think.



SHI_Caffeine_III.jpg (561.6 KiB) Viewed 3152 times



Caffeine III
[http://www.xentax.com/uploads/author/mr ... ne_III.zip](http://www.xentax.com/uploads/author/mrmouse/SHI_Caffeine_III.zip)

Tweaks
[http://www.xentax.com/uploads/author/mr ... Tweaks.zip](http://www.xentax.com/uploads/author/mrmouse/SHI_Tweaks.zip)
## Post #46
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-09T23:13:23+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Cool... I've fixed the email issue I think.

The attachment downloads work great, but I still don't see an Email option for you.

I also changed my board prefs to allow other members to contact me via Email, but I thought a button would appear at the bottom of each of my posts for Email, like the PM button does.
## Post #47
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-10T01:57:50+00:00
- Post Title: Re: Modding Results

Would you like a newspost?
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-10T08:09:26+00:00
- Post Title: Re: Modding Results

Yeah, nice idea!
## Post #49
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-12T02:06:31+00:00
- Post Title: Re: Modding Results

[Here it is.](http://www.xentax.com/?p=201)  

Thanks for the posted readme, Bogey. I don't think I would have figured it out without that.
## Post #50
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-12T02:27:07+00:00
- Post Title: Re: Modding Results

> Reply from Zench
>
> Here it is.  

Thanks for the posted readme, Bogey. I don't think I would have figured it out without that.

Thanks for the newspost, guys! 

Sure would love to try modding GTR Evolution if I could get file support for it.
## Post #51
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-14T12:02:32+00:00
- Post Title: Re: Modding Results

Nice work, Zench!  

I can look into that Revolution you asked for, Bogey, however, it's the Steam format I think. Let me check.
## Post #52
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-11-14T15:08:50+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Nice work, Zench!  

I can look into that Revolution you asked for, Bogey, however, it's the Steam format I think. Let me check.

All I know is that they are .GCF files. I can send you one of the smaller files, if you need it.

Thanks, Mr. Mouse, I appreciate it.
## Post #53
- Username: Clint Rutjes
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Apr 04, 2007 8:39 pm
- Post datetime: 2008-12-16T21:39:06+00:00
- Post Title: Re: Modding Results

Bogey, where's the credit for other people's work? For example:

> Reply from Bogey
>
> 
* Eliminates the ridiculous kiddy filter from the game's chat window. The list of filtered words is long and quite funny, at times. So, no more AAAAAAAAAAAAAAAA's when trying to chat with your online buddies.

I believe I made that.
## Post #54
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-16T23:38:32+00:00
- Post Title: Re: Modding Results

> Reply from Clint Rutjes
>
> Bogey, where's the credit for other people's work? For example:
Bogey wrote:
* Eliminates the ridiculous kiddy filter from the game's chat window. The list of filtered words is long and quite funny, at times. So, no more AAAAAAAAAAAAAAAA's when trying to chat with your online buddies.

I believe I made that.

Clint did make a mod that achieved this, but I hardly copied yours. It's not exactly rocket science to delete all the filtered words from a text file and repack it. No offense.

I also made a mod that added back all the factory hidden bikes, as you did, but I didn't copy your code. I didn't release that one as it crashes the game during online play, as you already know.

Where's the credit for all the ripoff mods made with my hard work on Caffeine? Tea 2 Sugers and Turbine come immediately to mind.  Both of those are direct ripoffs of my EXACT code with very minor changes. Hell, the little shits that made those weren't even smart enough to rename the mod or take out my comments! I'm not saying that you made either of those mods, Clint.

Also, Clint, considering all the bullshit you allowed to take place at MGF, I hardly am in the mood for any bullshit from you here on this site. Here's a laxative for your constipation and you're lucky you didn't have a lawsuit on your hands.
## Post #55
- Username: Clint Rutjes
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Apr 04, 2007 8:39 pm
- Post datetime: 2008-12-18T23:14:46+00:00
- Post Title: Re: Modding Results

It's not just about the word filter removal. Some of your other 'tweaks' have been made by others before aswell. Even if you didn't just copy/paste the stuff you still took other's work in a way. The fireworks tweak has been done by RaceX, the random gate time has been done, can't remember who did that, might be RaceX aswell, it wasn't you tho.

> Reply from Bogey
>
> Also, Clint, considering all the bullshit you allowed to take place at MGF, I hardly am in the mood for any bullshit from you here on this site. Here's a laxative for your constipation and you're lucky you didn't have a lawsuit on your hands.

You still crack me up with that lawsuit nonsense.  Thanks for that, it's allways nice to hear a good joke.
## Post #56
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-18T23:58:05+00:00
- Post Title: Re: Modding Results

> Reply from Clint Rutjes
>
> It's not just about the word filter removal. Some of your other 'tweaks' have been made by others before aswell. Even if you didn't just copy/paste the stuff you still took other's work in a way. The fireworks tweak has been done by RaceX, the random gate time has been done, can't remember who did that, might be RaceX aswell, it wasn't you tho.

You are a joke, Clint. Now go back to your hacked web site that you weren't bright enough to backup. 

So, let me get this straight, every person who writes any mods/code for a computer must first search out the entire history of every program that was ever written before, no matter how obscure, and then write a credit listing of thousands/millions of names thanking them and acknowledging their previous work. I guess Bill Gates should thank Xerox PARC for stealing the whole GUI/mouse thing, eh? You are more of an imbecile than I first thought. Have you ever heard of the concept of independent thinking/ideas?

Also, why don't you just admit that you are another of the many juvenile dolts that frequent your web site and hate my awesome mods (Caffeine I, II, III) that was downloaded THOUSANDS of times. Ask around and see which mod is more well known in the MvA community (like it or hate it): Caffeine or SIM/EP.

Also, not that you deserve any explanation, Mr. Mouse asked what mods I had made with the wonderful MiltiEX Commander utility and I told him. HE offered to host Caffeine and Tweaks here and another member offered to write that front page bit. Jealousy gets you no where, Clint.

> Reply from Bogey
>
> Also, Clint, considering all the bullshit you allowed to take place at MGF, I hardly am in the mood for any bullshit from you here on this site. Here's a laxative for your constipation and you're lucky you didn't have a lawsuit on your hands.

You still crack me up with that lawsuit nonsense.  Thanks for that, it's always nice to hear a good joke.

Really? So, allowing an admin of your web site (I know it was an inside job) to make posts under my account stating that I am a pedophile is a laughing matter to you? Then you allow them to ban my account for 5 months (which was quickly reversed) because I was making posts about being a pedophile. Do you really think I couldn't have sued the shit out of you for allowing it to remain posted until I pointed it out? You'd better check into the law if you are going to continue pretending to be a web site admin.

Run away now, so I don't have to air anymore of your dirty laundry on this site. I didn't ask you to come here and start garbage with me.
## Post #57
- Username: Clint Rutjes
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Apr 04, 2007 8:39 pm
- Post datetime: 2008-12-19T02:28:16+00:00
- Post Title: Re: Modding Results

> Reply from Bogey
>
> Clint Rutjes wrote:Really? So, allowing an admin of your web site (I know it was an inside job) to make posts under my account stating that I am a pedophile is a laughing matter to you? Then you allow them to ban my account for 5 months (which was quickly reversed) because I was making posts about being a pedophile. Do you really think I couldn't have sued the shit out of you for allowing it to remain posted until I pointed it out? You'd better check into the law if you are going to continue pretending to be a web site admin.

Run away now, so I don't have to air anymore of your dirty laundry on this site. I didn't ask you to come here and start garbage with me.

If you are so sure it was an inside job then please prove it because I have checked all moderator and admin logs and I am 100% sure it was not an inside job. Maybe you just chose an easy to come up password and some random f*ckup got figured it out to get in your account? I wouldn't be too suprised if you did it yourself tough.

And next time, tough it did made me laugh, please don't come with empty threats.
## Post #58
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-19T02:45:37+00:00
- Post Title: Re: Modding Results

> Reply from Clint Rutjes
>
> Bogey wrote:Clint Rutjes wrote:Really? So, allowing an admin of your web site (I know it was an inside job) to make posts under my account stating that I am a pedophile is a laughing matter to you? Then you allow them to ban my account for 5 months (which was quickly reversed) because I was making posts about being a pedophile. Do you really think I couldn't have sued the shit out of you for allowing it to remain posted until I pointed it out? You'd better check into the law if you are going to continue pretending to be a web site admin.

Run away now, so I don't have to air anymore of your dirty laundry on this site. I didn't ask you to come here and start garbage with me.

If you are so sure it was an inside job then please prove it because I have checked all moderator and admin logs and I am 100% sure it was not an inside job. Maybe you just chose an easy to come up password and some random f*ckup got figured it out to get in your account? I wouldn't be too suprised if you did it yourself tough.

And next time, tough it did made me laugh, please don't come with empty threats.

Yeah, I posted the stuff myself. What a mental midget you are. What possible motivation would I have to make derogatory (look that word up, Clit <- not a typo) about myself? I remember you basically accusing me of just that in an Email. Speaking of Emails, you and your other representative from MGF were mighty humble in those Emails -- you're rather brave now, eh?

I see your whole argument as to crediting other people's work was shot down with ease -- you don't stand a chance debating me on any subject, Clit.

Here's another for your tiny mind to contemplate... Many modders make custom weapons and scopes etc. for FPS games -- by your logic, should they all credit everyone who has ever programmed a similar weapon or a SCOPE? Why don't we start back in the Pong days and work our way forward... Hell, there's probably only about a million programmers that need to be credited in EVERY GAME PRODUCED going forward. LOL, you fool.

This subject is closed AFAIC, go back to your hacked and rundown site where you allow prepubescent boys to run wild with filthy language and insults. I see the same thing is happening at your site AGAIN and MessiaH has some posts concerning the conduct of your members. Maybe if you'd have an age cutoff of 21 or so you might cut down on the trash, the only problem is that that would eliminate you! Either that or learn how to moderate a site. I recall MGF being overrun my porn ads for the longest time -- great work. Please don't lecture me on the work involved in moderating and operating a site. I know what's involved and you've done a sub par job.

As they say in the U.K., piss off Clit.
## Post #59
- Username: Clint Rutjes
- Rank: Banned
- Number of posts: 4
- Joined date: Wed Apr 04, 2007 8:39 pm
- Post datetime: 2008-12-19T12:40:37+00:00
- Post Title: Re: Modding Results

Why would you abuse your own account? To get attention, to be able to threaten with lawsuits, etc. I've seen that shit before.

My argument hasn't been shot down as you say, you just don't understand the point. Just give it some more tought and maybe you'll realize it's people like you that ruined the community. People like you chased away some of the best modders the community had. This goes all the way back to the MCM1 days.

Obvisously you do not know what's involved in moderating and operating a site.

Oh and the clit thing, very original! It shows what level you're on.
## Post #60
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-19T14:39:29+00:00
- Post Title: Re: Modding Results

The user Clint Rutjes has been banned for reason of trolling and hijacking a thread to start a personal fight with one of the members.
## Post #61
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-19T14:58:00+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> The user Clint Rutjes has been banned for reason of trolling and hijacking a thread to start a personal fight with one of the members.

Thanks, Mr. Mouse. There was only one reason he came here.

As for my ruining the community... please. Clint is one of those that went along with the kids crying that mods are what makes a game publisher stop producing products. 

They were actually blaming my mod as the reason that the next version of MX vs ATV wouldn't be released for the PC! LOL, what a joke, every publisher is in it to make money. 

AFAIC, mods breathe life into an otherwise dead game. Look at how long some of them have still been around (Unreal Tournament II comes to mind) -- if not for the tons of mods for that game it would have been dead years ago.

The problem with Clint and his crew at the now-hacked-and-dead MGF is that they liked mods like SIM Physics because it didn't make the bikes nearly as fast as my Caffeine mods do (but it still made them faster than the stock bikes that came with the game). SIM still changed the physics, but they didn't call it a "mod". They loved to call Caffeine a "mod" and of course, as we all know, mods ruin games. Ouch -- that was another argument we had over there. ANYTHING that "modifies" a game from its original form is a mod. Just because you like one person's mod over another doesn't mean that one of the projects is a mod and the other isn't. They just couldn't grasp the concept and couldn't appreciate the untold hours that went into making the Caffeine series.

OK, I digress....
## Post #62
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-19T18:24:23+00:00
- Post Title: Re: Modding Results

I personally believe that mods indeed ensure a long lifespan of many games, that otherwise would have died much sooner. I am always annoyed when I learn that game developers fail to include an editor with the retail version, as many games would be perfect to mod. Luckily, people such as Blizzard and Bethesda know this well and offer sophisticated tools with many a game (e.g. StarCraft, WarCraft, Morrowind, Oblivion, Fall Out 3). And I applaud 'amateurs' that create their own tools for otherwise unmoddable games, and provide the games' fanbase with more good stuff to play. Counterstrike was an excellent mod of Half Life and still one of the most played on line shooters to date. 
Good to see that many developers release SDK's at some point that enable modders to take modding even great leaps further.
## Post #63
- Username: TheGeneral
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 13, 2008 8:35 am
- Post datetime: 2008-12-19T19:16:19+00:00
- Post Title: Re: Modding Results

I was able to turn wire frame mode on in Portal: Still Alive
## Post #64
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-19T19:35:30+00:00
- Post Title: Re: Modding Results

Nice  How you'd do that?
## Post #65
- Username: TheGeneral
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 13, 2008 8:35 am
- Post datetime: 2008-12-19T19:42:28+00:00
- Post Title: Re: Modding Results

I added this to modoptions.360.txt

```
	{
		"name"		"Wireframe"
		"convar"	"mat_wireframe"
		"priority"	"0980"
		"type"		"choice"
		"choices"
		{
			"Off"		"0"
			"On"		"1"
			"Mode 2"	"2"
			"Mode 3"	"3"
		}
	}

```


Then I got a friend with some special Xbox 360 hardware to test it out and take pictures
## Post #66
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-20T03:21:02+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> I personally believe that mods indeed ensure a long lifespan of many games, that otherwise would have died much sooner. I am always annoyed when I learn that game developers fail to include an editor with the retail version, as many games would be perfect to mod. Luckily, people such as Blizzard and Bethesda know this well and offer sophisticated tools with many a game (e.g. StarCraft, WarCraft, Morrowind, Oblivion, Fall Out 3). And I applaud 'amateurs' that create their own tools for otherwise unmoddable games, and provide the games' fanbase with more good stuff to play. Counterstrike was an excellent mod of Half Life and still one of the most played on line shooters to date. 
Good to see that many developers release SDK's at some point that enable modders to take modding even great leaps further.

I agree 100%. When the developers don't include a track/level/whatever editor I find it to be a huge let down.

Some of the mods for Unreal Tournament II would make you wonder what the game looked like in its original configuration.   But, that is what makes this community so cool.

I know I'm a very small time player on the mod scene, but I'm proud of what I did with the budget title MX vs ATV Unleashed for the PC. That game is going on 3 years old, but I think it's still a blast to play with my mods (of course I'm biased).

I also made a mod for Medal of Honor Allied Assault (MOHAA) quite a few years ago. Basically, it added 1,000 rounds of ammo to all weapons and also made the bazooka semi-automatic.   Now that was a blast to fire off bazooka rounds as fast as you could pull the trigger - the whole damned screen would shake from all the successive explosions! LOL 

But, once again, some people with poor senses of humor would complain about how unrealistic it was -- well, duh, of course it's unrealistic, but it was a helluva lot of fun to play.

I've never been one to aim for realism when it comes to modding. I like to push the limits of what I'm interested in and see how freaky I can make things play.
## Post #67
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-20T08:42:59+00:00
- Post Title: Re: Modding Results

Indeed, it was also fun to play with the rules.ini of the Red Alert range of games. Once, I had put tesla weaponry (that usually only were for Tesla towers, stationary turrets) in the hands of infantry. That was devastation! A small company of tesla soldiers could wreak immense havoc and it was awesome to look at, all the rays going criss-cross over the screen. 
In later versions (C&C3 and RA3) these soldiers were officially implemented, but my modded soldiers at the time had much more tesla firepower! Hehe.
## Post #68
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2008-12-20T11:43:55+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Indeed, it was also fun to play with the rules.ini of the Red Alert range of games. Once, I had put tesla weaponry (that usually only were for Tesla towers, stationary turrets) in the hands of infantry. That was devastation! A small company of tesla soldiers could wreak immense havoc and it was awesome to look at, all the rays going criss-cross over the screen. 
In later versions (C&C3 and RA3) these soldiers were officially implemented, but my modded soldiers at the time had much more tesla firepower! Hehe.

LMAO, THAT'S what I'm talking about!

Did you ever release it, or was it just for your own amusement? If you released it, did you have any little babies crying about how it ruined the game or was unfair?
## Post #69
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2008-12-20T16:36:49+00:00
- Post Title: Re: Modding Results

The only little baby crying was Mr. Mouse when I blew up his construction yard
## Post #70
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-20T17:01:38+00:00
- Post Title: Re: Modding Results

That's your word against mine, Captain. You have witnesses?
## Post #71
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2008-12-20T17:04:11+00:00
- Post Title: Re: Modding Results


## Post #72
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-01-02T02:20:52+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> I personally believe that mods indeed ensure a long lifespan of many games, that otherwise would have died much sooner. I am always annoyed when I learn that game developers fail to include an editor with the retail version, as many games would be perfect to mod. Luckily, people such as Blizzard and Bethesda know this well and offer sophisticated tools with many a game (e.g. StarCraft, WarCraft, Morrowind, Oblivion, Fall Out 3). And I applaud 'amateurs' that create their own tools for otherwise unmoddable games, and provide the games' fanbase with more good stuff to play. Counterstrike was an excellent mod of Half Life and still one of the most played on line shooters to date. 
Good to see that many developers release SDK's at some point that enable modders to take modding even great leaps further.

I third this. Unreal I was immortalized due to the mod scene and so have other games. Mods are not destructive and not insulting but a show of extreme interest and devotion. Testing the limits of said games I think is more so a compliment to the game maker, knowing that their engine could be used to do that. Even today Unreal I is subject to mods and is thoroughly supported online. And I too applaud people who make unmoddable games moddable.

I have seen a number of games that were great but failed to include means to expand their game in any way, not even a map editor/builder which gets to me. This may explain why they never get talked about. In my research,unless the game is really good, this unmodability actually hurts a game's lifespan tremendously.

This is further supported by the fact that Die By the Sword is actually still somewhat popular and Jane's Fighters Anthology is still actively modded.

As for C&C... I should start my mods back up. XD Other than Unreal, Tiberian Sun and Red Alert 2 was a load of modding fun. Floating rocks that shot out heat rays, Gas tanks that spewed toxic gas, and a beta of the Gargantua Tank which... exceeded it's bounding box sadly.
## Post #73
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-08-09T09:20:34+00:00
- Post Title: Re: Modding Results

The contents of this post was deleted because of possible forum rules violation.
## Post #74
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-07T23:42:55+00:00
- Post Title: Re: Modding Results

Here are some results from me and Balder's progress on the I.M.Meen graphics exploration.



An almost complete recreation of the first level from I.M.Meen in Doom Builder (hence the highlighted wall).

Soon I plan that we'll have the sprites and transparent walls and even animated doors so it'll be complete. And the enemies will be converted over in all their entirety as well.
## Post #75
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-08T00:14:21+00:00
- Post Title: Re: Modding Results

Nice man!  Never heard of this I M Meen before, actually, but looked it up in Moby Games. A childrens game eh? Why recreate it in ID's Doom engine?
## Post #76
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-08T04:48:23+00:00
- Post Title: Re: Modding Results

It is made by the same people who made the CD-i Zelda games and Hotel Mario. I don't plan to put in the grammar puzzles and such and make it a flat-out FPS. The game itself is hard to come by and features some decent music and laughable voice acting and animations.

As a FPS enthusiast I cannot just pass up the chance to tinker with such a project. I have in the past recreated many things in zDoom, including maps from Shin Megami Tensei. It is... fun.

Funny enough, I.M.Meen's ingame features a darker environment than the cartoony Doom TC: Chex Quest.

I.M.Meen in gameplay had similar light as Ken's Labyrinth or Nightmare 3D, though graphically superior, but more quirky in gameplay. I consider this a challenge for me to remake a game in zDoom to be challenging and fun that was originally intended as just a kid's educational game. Comparing it graphically to other older FPSes, it does have a graphical edge even though the gameplay is a bit clunky. But this is easily fixed by using the enhanced Doom engine.

This will also be in my series of "dead" (meaning that the companies have dissolved long ago) retro FPS games that will meet a zDoom equivalent and be given the benefirs of better control and more challenge while still having nearly the same feel.

My remake projects are:

zCorridor (works nearly like the original, using GZDoom for dynamic lights and smoother graphics, added GZDoom has developmental features, it also gives a co-op and better multiplayer than the original)
zMeen (will receive the benefit of a resampled soundtrack by me and dynamic lights and some smoother animations, also will lone the grammar puzzles and focus more of gameplay, perhaps additions will be given to enhance gameplay)
## Post #77
- Username: zabana
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jun 27, 2010 12:41 am
- Post datetime: 2010-08-17T22:14:35+00:00
- Post Title: Re: Modding Results

Hi all!

I received an email asking me why I decided to extract models from a game and what I want to do with them. Well, easier to answer that, I´m building an Iron Man armor, most of pieces are near completion, but someones not or I want to improve them, so I decide to use as reference game models.

That´s the main reason, in the other hand I enjoy learning things, coding and a lot of ways of doing what people doesn´t use to do.

If anyone wants to check my progress check it out here:

[http://www.therpf.com/f24/spanish-iron- ... rks-76175/](http://www.therpf.com/f24/spanish-iron-man-costume-wip-voice-recognition-system-suit-control-works-76175/)

You´ll see how is my armor these days and see my voice recognition helmet(it will speak too soon )

See you everyone and thanks for reading me and helped me too!!!
## Post #78
- Username: dairukan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 11, 2010 5:53 pm
- Post datetime: 2010-08-17T22:43:51+00:00
- Post Title: Re: Modding Results

I modified a level in New Super Mario Bros Wii to propose to my (now) wife. I needed to extract a model of Princess Peach so that I could modify it (the only one I could figure out how to insert in-game has her in a cage, which was not the message I intended to send with the proposal). Anyhow, it was lots of fun figuring out how to do it and even more fun being successful, so thanks for all the help guys!
## Post #79
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2010-08-17T23:16:33+00:00
- Post Title: Re: Modding Results

Got that "provide feeback" email as well.

Very simple, I just wanted to extract some images from Mafia II demo (and eventually the game), for my own interest and perhaps the interest of a few others. I already had DDS plugin for Photoshop. Thanks to the members on this forum, I was able to decompile the .sds files and hex edit the resulting .dat files to create .dds files.

Works brilliantly, thanks to the awesome members of this forum!

[http://www.bioshockarchives.com/empirebay](http://www.bioshockarchives.com/empirebay)

(If you go to my main site at the root URL, you'll notice it has tons of BioShock stuff. However, I still have a few questions about getting files from the BioShock games that I haven't been able to do yet. I might post about that elsewhere on this forum and see if anyone can help!)
## Post #80
- Username: Egger3rd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 22, 2010 10:58 am
- Post datetime: 2010-08-17T23:20:17+00:00
- Post Title: Re: Modding Results

I don't make mods, really; I make recut videos from video games.  I don't like to call it YouTube Poop though, since it's a bit more complicated than crappily splicing together video downloaded from YouTube.  Mods, ini tweaks and console commands help me manipulate the hud and camera for recording.  I also very much appreciate this site's audio extracting resources.

Here is a small beginner's tutorial I made on the subject that took me quite a while to get half-way decent at:
Extracting Sound Files from PC Games

Here are some examples of what I do:
[Sporeout 3: Part 1 (Fallout 3 / Spore Machinima)](http://www.youtube.com/watch?v=LnDnewDQc7U)
[Sporeout 3: Part 2 (Fallout 3 / Spore Machinima)](http://www.youtube.com/watch?v=5kGvHB34a-4)
[Deus Ex: The Recut](http://www.youtube.com/watch?v=Vxi7JRJrod4)
## Post #81
- Username: lavers
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 25, 2009 12:58 pm
- Post datetime: 2010-08-17T23:51:02+00:00
- Post Title: Re: Modding Results

hey all, I came to this forum is a dire effort to find someone to crack an lz compression variant known as LZH8. The reason I wanted this done is for use with Wii virtual console SNES games.

See, many SNES virtual console games only ever come out in japan, especially the great RPG ones. So HCS stepped up and cracked this compression for me.

Using his tool i was able to unpack the rom file from the U8 archive & LZH8 compression, patching the rom with English fan translations then compressing the rom back up in LZH8, the virtual console game recognized the rom as 'good'. Some other simple hex editing of japan text in the emulator files was easy enough, and the end result were these prior japan only releases in full English 

thanks go out to HCS since many many months i tried to find a taken to crack this compression and he blitzed it
## Post #82
- Username: practicing01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 29, 2010 10:52 am
- Post datetime: 2010-08-18T00:37:32+00:00
- Post Title: Re: Modding Results

I got an email from [forum@xentax.com](mailto:forum@xentax.com) requesting that I post what I've done with the info acquired from this forum.  In compliance, I ported the Vanessa Shneider & Morrigan models to Garry's Mod (found both models on the forum).  I use the forum to acquire 3d models from games and port them to Garry's Mod and archive them for later use.
## Post #83
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2010-08-18T00:54:43+00:00
- Post Title: Re: Modding Results

.
## Post #84
- Username: Typhox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 15, 2009 12:33 am
- Post datetime: 2010-08-18T01:16:11+00:00
- Post Title: Re: Modding Results

I first came here just for looking at the quickbms-things, since I wanted to "crack" and moreover repack a LZSS compressed file from Pokemon Colosseum. I needed it to convert the music files from the game into midi files so that I would be able to play the backgroundmusic on a piano.
Currently, I am hacking Godzilla Save the Earth and probably in a few month I will be completely done with it (meaning, I will be able to create own cities, monsters and user interface). Additionaly I am trying to decompile Pokemon Red. Sometimes, I am just hacking because I need to change a "setting" in a game. So I modded Age of Mythology to increase the population limit by 20.000 and Age of Empires II to increase the number of fields a player put in the loop.
## Post #85
- Username: seculi017
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 07, 2010 1:48 pm
- Post datetime: 2010-08-18T01:58:32+00:00
- Post Title: Re: Modding Results

Got the e-mail~

I've been trying to mod Aika Online, and one of the threads here had some info on how to crack the textures and models, but I guess it was too complicated for me, since I haven't been able to figure it out. I do most of my posting on another modding forum, and no one there has managed to crack the files, either. The thread seems to be dead, and the user who said he had a file converter running (but didn't post it for download) hasn't responded to a PM I sent him. It's too bad, I like the game and am dying to make myself some custom armors, but it doesn't look like it's going anywhere.
## Post #86
- Username: XeroNazoBlaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 06, 2009 3:34 am
- Post datetime: 2010-08-18T02:53:26+00:00
- Post Title: Re: Modding Results

Email received.

Actually I have no interest in modding, I'm just doing this for fun and because this caught my interest. Talking about success, I was able to unpack the UN2 files from Chaos Wars, a PS2 role-playing game, sadly well known for his horrible english voice dubbing.

Oh, and hai, this is my first time posting in the forum. Thanks a lot for the help and the resources. My English is not quite well yet, so I hope you can understand me.
## Post #87
- Username: gaolon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 21, 2010 2:15 am
- Post datetime: 2010-08-18T04:03:17+00:00
- Post Title: Re: Modding Results

the e-mail~~

hi all.

I wanna translate a game named "Magic The Gathering - Duels of the Planeswalkers".And I find the game diectory includes some .wad files,such as Data_Core.wad ,Data_DLC_0001.wad...I THINK these files contain the texts need to be translated.

Rick gives me this: [http://mod.gib.me/dotp/bin-temp2.zip](http://mod.gib.me/dotp/bin-temp2.zip) 
It works well at extracting and repacking .wad files.
Thx Rick.
## Post #88
- Username: Kiory
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 24, 2010 9:16 am
- Post datetime: 2010-08-18T05:51:38+00:00
- Post Title: Re: Modding Results

I only wanted to "mod" to extract certiain models out of some games in order to learn about edge loops. 

Other than that, there was no other reason.
## Post #89
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-08-18T06:55:17+00:00
- Post Title: Re: Modding Results

Excellent stuff ! Thanks to you all for replying to the email, it makes the work for us so much more worthwhile to know that good came out of it (and even a marriage! Great!).
## Post #90
- Username: nikethebike
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 24, 2010 1:57 pm
- Post datetime: 2010-08-18T10:25:30+00:00
- Post Title: Re: Modding Results

I also got the e-mail. 

This is what I did with with some help from the information in this forum:

[http://caws.ws/forum/topic/369009-smack ... -bike-ps2/](http://caws.ws/forum/topic/369009-smackdown-vs-raw-2010-roster-editor-by-nike-the-bike-ps2/)
## Post #91
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-08-18T22:55:05+00:00
- Post Title: Re: Modding Results

> Reply from Mr.Mouse
>
> Excellent stuff ! Thanks to you all for replying to the email, it makes the work for us so much more worthwhile to know that good came out of it (and even a marriage! Great!).
I'll second that! Are you gonna make a blog post out of this?
## Post #92
- Username: SimSaw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 04, 2009 6:52 am
- Post datetime: 2010-08-19T09:51:18+00:00
- Post Title: Re: Modding Results

As you were asking for feedback in an email, here it is:

I'm able to extract all files out of AGS games of specific versions and I can modify local scripts as far as they are not connected to global scripts. This is thanks to a tool from asmxtx.
Unfortunately, there is nothing to be done about global scripts which limits the possibilities of every user.
I would like to use here also the possiblity to point out interest in such tools and the wish for further development.

I'm currently thinking no one in the world is good enough at programming to make an extractor for global scripts of AGS games. I want to challenge you: Proof me the opposite! Proof that you are the best programmer in the world.
## Post #93
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2010-08-19T13:08:20+00:00
- Post Title: Re: Modding Results

Were able to make custom brightskins for Quake Live thanks to aluigi and his [tools](http://aluigi.org/papers.htm#q3)
On the right is custom 'sport' skin.

[](http://img69.imageshack.us/i/74039234.jpg/)
## Post #94
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2010-08-22T11:54:05+00:00
- Post Title: Re: Modding Results

In response to the email I received recently, I'd like to again thank 'john_doe' for working out the 'RA' compression scheme used in 'F22 Total Air War', one of the great flight sims released in 1998. 

The details are in this thread:
[viewtopic.php?f=15&t=1418&st=0&sk=t&sd=a&start=75](http://forum.xentax.com/viewtopic.php?f=15&t=1418&st=0&sk=t&sd=a&start=75)

It was four years ago, but I still use the utility quite often as this type of compression was used in all of DiD's games going back to at least 'TFX' in 1993.

I'd forgotten that the thread above contains information about how we may recompress any modded files and repackage them to speed up load times...so thanks Mr.Mouse for the reminder.
## Post #95
- Username: GameFreak612
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 20, 2010 4:57 am
- Post datetime: 2010-08-22T12:47:46+00:00
- Post Title: Re: Modding Results

Well, in response to the email, the game I've been attempting to reverse is Metal Gear Solid 3 which most of you probably know remains unbroken. While the info on this forum did help me avoid some redundancy in my attempt, I have decided to go the dis-assembly route with the game. It looks very challenging, I can't even begin to analyze this right now since I have to become very familiar with MIPS and the EE core/VU instructions not to mention the whole design structure of PS2 games. I probably won't get very far with this, but it makes me very frustrated to see PCSX2 running this game on my PC and see the game very clearly reading its archives on MY PC. It would be wonderful if there were some kind of PCSX2 debugger one could use to analyze the execution of PS2 games, but oh well. 

Great forum anyway, I expect to be using its resources for other more reasonable attempts in the future. Of course, I will share anything I happen to find/make.
## Post #96
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-08-23T03:04:43+00:00
- Post Title: Re: Modding Results

Also as a result of the e-mail, as I was previously unaware of this thread's existence. I haven't really modded games with knowledge gained from Xentax, but many people have modded games (and made horrifying media/videos) as a result of my work, which is also often rooted in Xentax. So I want to take the opportunity to thank a few people.

Mr.Mouse:
 -Hosts Noesis and its site!
 -Active admin and founder of XeNTaX! (we're not worthy)
 -Without his efforts toward XeNTaX, Noesis may never have been born.

aluigi:
 -Cracked encryption on Ys: The Oath in Felghanna archives, which allowed me to get at the .ymo data with ease.
 -I'm not sure what else, but he's constantly figuring out compression/encryption methods for various games, and he rules.

Surveyor:
 -Made public most of the ground work for the Capcom .mod format, and saved me hours (maybe even days) of hex-editing!
 -Is also generally awesome, and has tackled countless model formats on XeNTaX.

revelation:
 -Also assisted in the Capcom .mod format and made many of his findings public, which assisted me in conjunction with Surveyor's efforts.
 -Yet another awesome guy that is always popping up whenever there are models to be discovered.

This thread also made me realize that the readme for Noesis needs a "special thanks" section. 

Sometimes the people doing the core work on reverse-engineering formats and data can get kind of bummed out by people who just barge in and selfishly demand things, but their passion drives them to keep discovering and sharing despite that. It makes me very happy to see ingenuity, curiosity, and courtesy triumph over some of our more selfish and isolating traits as human beings. So to all of you guys, thank you. You are all awesome.
## Post #97
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-23T03:25:48+00:00
- Post Title: Re: Modding Results

Ok, so I got an email asking me to post my results, or rather, what I did with the knowledge I gained here, so in the interest of not being an ungrateful douche, I am doing so 
I used the tools for ripping the models and maps out of tekken 6 to extract Nina Williams, who I then turned into a survivor replacement for the game Left 4 Dead 2. Pic Attached...

[](http://img127.imagevenue.com/img.php?image=30997_rochelle_nina_122_196lo.jpg)

Overall she turned out pretty well, had to tweak a couple maps and re-rig her with the l4d2 bones instead of the tekken ones, and valve does something weird with the hand anims too(sigh), but I'm still mostly pleased with her considering I converted her to l4d2 in a matter of a few hours. Because she is a client side mod, she can be used in any mode of play, online or offline, which is also bonus. 
For those who are interested, she is available for download at [http://www.mrlanky.com](http://www.mrlanky.com) as are all my other l4d2 mods. Feel free to download, use, and modify them as you like. They were all made possible by the tools made available by people here and elsewhere, so I claim no ownership of them. I just make them for fun. 
On that note, I would like to once again thank all those responsible for making the tools and programs which make this possible, and for making these available to us all. Your efforts are truly and greatly appreciated. 
I know I would have stopped playing l4d2 ages ago if not for all the fun with mods I can have thanks in part to you guys.
## Post #98
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2010-09-03T08:30:37+00:00
- Post Title: Re: Modding Results

Hello all

Alas, I've had no luck whatsoever in trying to achieve what I set out to do, namely export models from Hellgate London (have extracted models but can't open them) and Aeon Flux -PS2 (ditto that one) and port them across to Fallout 3.
There just doesn't seem to be much interest for those two titles    

Still, 3dxripper will pull meshes in the case of hellgate, but they need a lot of reworking
But anyway, I have learned a lot since checking in here, though understanding hex dumps and then writing scripts just can't squeeze it's way in there when I am in the middle of trying to figure out zbrush and a foreign language  

Thanks to the hosts and all the generous contributors for this great collection of knowledge at Xentax:)
## Post #99
- Username: evildeadman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 31, 2010 12:13 pm
- Post datetime: 2010-09-06T22:23:19+00:00
- Post Title: Re: Modding Results

Many thanks go to Evin for the Alan Wake extraction tool!  I wanted to use the audio from the game for some personal projects, but just having the FSBs wouldn't have done either.  Previous modders' posts throughout the forums were greatly helpful in teaching me what I needed in order to get the WAV files I wanted from the data files I had.

Thank you XeNTaX Forums, and thank you to the rest of the community!
## Post #100
- Username: GMFattay
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 29, 2010 9:59 am
- Post datetime: 2010-09-15T08:18:25+00:00
- Post Title: Re: Modding Results

> Reply from dimwalker
>
> Were able to make custom brightskins for Quake Live thanks to aluigi and his tools
On the right is custom 'sport' skin.

Nice skin there.

I managed to downgrade the Quake Live exclusive maps to Quake 3 also using aluigi's tools. Having these maps in Quake 3 proves useful as it means you can play them on lan.

The maps more or less worked well. Had to use the ioquake3 because it supports the PNG textures Quake Live uses. Had a wee problem with the adverts. They use a Quake Live classname "advertisement" which shows up blank in Quake Live. This wouldn't be a problem except on some maps, looking at the advertisements, you can see through the level. Also couldn't get bots to work, kept getting a message saying the AAS file was out of date.

You can also play custom Quake 3 maps on Quake Live vs bots (not sure about hosting custom maps on servers). Just gotta encrypt the PK3 with aluigi's tool, set the map to read only (so QL doesn't delete it), start a practice game and load the map through the console.
## Post #101
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2012-07-02T05:57:14+00:00
- Post Title: Re: Modding Results

So I found the One Piece Ripper which worked quite well, then mucked around a bit to get everythibg combined into 3dsmax properly so I could then export it to the source engine...why? Left 4 dead 2....I just love porting models over to it. So here is captain buggy in l4d2...he's my first attempt. Enjoy!

[](http://img281.imagevenue.com/img.php?image=205083419_c1m2_streets0035_122_118lo.jpg) [](http://img277.imagevenue.com/img.php?image=205084912_c1m2_streets0038_122_90lo.jpg)
## Post #102
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-10-09T20:21:01+00:00
- Post Title: Re: Modding Results

Check out my video of The stranger’s plans with bickering Dutch politicians. [http://www.youtube.com/watch?v=fhW8rnDO4VI](http://www.youtube.com/watch?v=fhW8rnDO4VI). DutchPolitician mod and Briefcase nuke mod for Fall Out: New Vegas combined.
## Post #103
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-24T09:59:24+00:00
- Post Title: Re: Modding Results

Extracting the Racing Team logos from Tokyo Xtreme Racer Zero on PS2- as most of them were translated into future games, it's nice to have them pixel-perfect- albeit 200x200 or under- for forums and the like. Sadly the biggest fan forum of the bunch is pretty much dead, so I'll probably end up dumping them here alongside some models if I or anyone else can do something with CDDATA.000; so far I've only found one TIM2 file, so i'll probably post it to the Game archives section. However, I kinda need my other two posts gone (on the TXR series) because it kindof looks like spam from all of the similar threads, so I might just make a general Tokyo Xtreme Racer archive thread and host everything needed from all the games in just that. That'd be a better idea I guess..

That being said, does anyone even like cars on here?
## Post #104
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-03-02T00:09:02+00:00
- Post Title: Re: Modding Results

doom2_toplicht_levels_xentax.zip
(502.09 KiB) Downloaded 24 times



Our Doom 2 levels from 1995. 
Created in WADED (also in the zip file)

See also : 
[https://www.youtube.com/watch?v=VWXt4v_ ... 1vIy4CZO6a](https://www.youtube.com/watch?v=VWXt4v_8UdI&index=4&list=PLP26ZYnLb5EXlf7hNfXgI5K1vIy4CZO6a)
[waded.png](https://xentaxbackup.github.io/file/10544_waded.png)
## Post #105
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2017-11-18T15:17:40+00:00
- Post Title: Re: Modding Results

Speaking of Doom and Mods.......
## Post #106
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2017-11-18T21:11:47+00:00
- Post Title: Re: Modding Results

What is THAT ?
## Post #107
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2017-11-19T01:34:35+00:00
- Post Title: Re: Modding Results

[https://www.nexusmods.com/doom3/mods/10 ... %3D&pUp=1#](https://www.nexusmods.com/doom3/mods/1091/?tab=1&navtag=https%3A%2F%2Fwww.nexusmods.com%2Fdoom3%2Fajax%2Fmoddescription%2F%3Fid%3D1091%26preview%3D&pUp=1#)
## Post #108
- Username: Metal64
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 9:20 am
- Post datetime: 2021-05-24T03:36:05+00:00
- Post Title: Re: Modding Results

> Reply from TheDude ↑Sun Nov 19, 2017 9:34 am at Sun Nov 19, 2017 9:34 am
>
> 
https://www.nexusmods.com/doom3/mods/10 ... %3D&pUp=1#

This mod has been set to hidden
## Post #109
- Username: Metal64
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 9:20 am
- Post datetime: 2021-09-12T05:19:53+00:00
- Post Title: Re: Modding Results

[https://www.youtube.com/watch?v=X9XhjmoOjoA](https://www.youtube.com/watch?v=X9XhjmoOjoA)
## Post #110
- Username: handy333
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 04, 2015 5:31 am
- Post datetime: 2022-10-25T01:15:36+00:00
- Post Title: Re: Modding Results

Let me add to this something I was able to achieve in Ghidra with Tekken 6 on the psp.
[https://youtu.be/lS2urPyxaVc](https://youtu.be/lS2urPyxaVc)

I stumbled upon this mod while trying to figure out how to unpack the game file[s].
## Post #111
- Username: Metal64
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 9:20 am
- Post datetime: 2023-05-12T14:18:07+00:00
- Post Title: Re: Modding Results

[https://www.youtube.com/watch?v=JdVL1HIkgxE](https://www.youtube.com/watch?v=JdVL1HIkgxE)
