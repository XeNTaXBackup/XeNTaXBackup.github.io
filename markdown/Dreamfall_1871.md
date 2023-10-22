## Post #1
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-04-27T12:52:47+00:00
- Post Title: Dreamfall

Hey,

Any chance you can expand this great program to support the recent game, Dreamfall: The Longest Jouney?  It uses PAK files, but I don't know any more than that.
## Post #2
- Username: adamsucks
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 30, 2006 1:30 am
- Post datetime: 2006-04-29T17:50:56+00:00
- Post Title: Dreamfall

Hey guys.  I would also like to make a request for this game.  The soundtrack is phenominal and I really want to get ahold of some of the tracks.

It looks to me like the archives are not compressed.  I was able to compress one of the files from 16 MB to 3.7 MB.  They are in a custom .PAK format, and appear to also include all the event triggers and animation sequences and whatnot.

I wish I knew how to do this, I'd do it myself.  I have included the 3MB sample archive for examination. 

[[Download Here](http://hyperupload.com/download/01bb8e7c73/interrogation_room.zip.html)] (sorry for the crappy host.. my usual one is dead)

Would really appreciate if someone could check this one out.  

Thanks!!
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-30T08:50:20+00:00
- Post Title: Dreamfall

archive contains mostly DDS images
and WAVE files. also some script files, (like vertex shaders and stuff).

Jaeder Naub could be used to rip out data from this archive type.

i dont have the soundtrack archives so i dont know if jaeder naub supports
ripping those yet.

[http://wiki.xentax.com/index.php/Jaeder_Naub](http://wiki.xentax.com/index.php/Jaeder_Naub)

be sure to have DDS and RIFF selected as ripping options.
## Post #4
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-02T07:49:30+00:00
- Post Title: Dreamfall

Thanks a lot for the tip.  It doesn't extract the sound effect, voice, or music files, unfortunately.  I'm looking at creating a high-resolution texture pack for this game, is there any way to update the files in a pak file such as this?
## Post #5
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-02T17:43:55+00:00
- Post Title: Dreamfall

I went through the pak files with a hex editor, and it seems the textures are in png format (I see code like "art/npc/casablanca/helena_zhang/textures/helena_tex_casual.png<bh:00>4art/npc/casablanca/helena_zhang/
textures/syringe.png<bh:00>8art/npc/casablanca/helena_zhang/textures/syringe_nml.png<bh:00>3art/npc/
casablanca/watilla/textures/watilla_nml.png<bh:00>3art/npc/casablanca/watilla/textures/watilla_tex.png", however the ripped textures are in dds format.  Any idea why?  The voice and music all seem to be mp3.
## Post #6
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-04T18:43:01+00:00
- Post Title: Dreamfall

Is there an appropriate time to wait before bumping the topic?  Will I be told if adding support isn't going to happen, or may happen, or anything?  I don't want to be impatient, just thought I'd ask.
## Post #7
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-06T19:50:14+00:00
- Post Title: Dreamfall

Hm?  Anyone around?
## Post #8
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-08T11:09:19+00:00
- Post Title: Dreamfall

I'd like some help with the injector in Jaeder Naub - I have a DDS that I've edited, can you please help me put it back into the pak file, so it will be read by the game?
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-08T11:57:30+00:00
- Post Title: Dreamfall

Oh shit. someone actually tries to use the injector =o
*omfg*, errhh. ill get back to this later today. first of all be sure to
back up the original archive you are trying to inject too.

because, if jaeder naub does ANYTHING wrong it will screw up the whole archive. just 1 byte wrong and the game would be destroyed.

i have myself successfully used the injector on some games just
for testing. 

ill try to write a tutorial and put it up later today. im fully aware
of that the injector is kinda shit too use, its not very userfriendly yet,
sorry for that :/
## Post #10
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-08T14:31:43+00:00
- Post Title: Dreamfall

Oh yeah, I backed everything up beforehand, of course.  I couldn't get it to do anything at all though, in the end.  Thanks for your help, it's really appreciated
## Post #11
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-11T07:42:35+00:00
- Post Title: Dreamfall

How about that tutorial?
## Post #12
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-14T17:54:26+00:00
- Post Title: Dreamfall

*cough*
## Post #13
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-14T20:10:49+00:00
- Post Title: Dreamfall

Hi there !!! =D , i was busy as hell. and went away from my appartment
the last 5 days. but ill try too give a quick explanation.


lets say you rip out a DDS texture from an archive, it would be named
like "dds_ 929_ 128755.dds"

the 929 number would be the offset were in the file it was located,
and the 128755 number would be the detected length of the texture.

now, open up photoshop and manipulate the texture as you want,
and make sure to save it with the same name as the ripped name,
because the injector will use the variables stored in the name
when it was first ripped.

you could however name it too ddx_ 929_ 128755.dds instead
to keep the original.

when you want to replace the texture, (Make sure you have it saved in the exact same format as it was ripped in, like DXT1, DXT3 or DXT5 or else the archive would be fucked up) start up jaeder naub, press file open
and select sourcefile (the DDS texture you want to inject),
now press "injector" and select the destination archive,
after the archive is selected make sure to press "Destination Archive" button in order to open it. you could also press "Reload Source" to be sure the correct offset values have been calculated.

when all this is done, press both check boxes "SafeCheck A" and "SafeCheck B", and then "INJECT".

this should inject your manipulated texture into the archive at the same place and length as it was ripped in. it will not matter if your file is larger or smaller than the ripped file, it will still go for the values stored in the name to prevent corruption of the archive.

if this works i would be glad to hear it, ive tried it on Max Payne 2 without
good results, but i think they have some CRC checking or something, because when i hex the archive after injection everything looks just as it
should.

i can only hope it works =o

maybe i could make an graphical walkthrough if this doesnt help,
just not right now =D

the current version of jaeder saves the DDS length with -128 in bytes, and
is not correct. BUT, it should not affect the injection of the textures anyway. the new version has this fixed but will not be released yet due to
other fixes being made.
## Post #14
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-15T11:47:24+00:00
- Post Title: Dreamfall

Thanks!  That seemed to work allright, but I'm still having issues.  I'll try to work them out myself first, because I think it's something I'm doing, rather than a problem with the program.  As a test, I'm trying to change the colour of a purple monkey.  The changed texture only appears in certain places on the model, the ones closer to the camera.  I think that means it's something to do with mipmapping, so I'm gonna look into it some more.  If you have any ideas though, please let me know.  Thanks so much for the tut
## Post #15
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-15T13:27:27+00:00
- Post Title: Dreamfall

That certainly has to do with mip maps, you could try
pressing the "Generate Mip Maps" button on the DDS Plugin.

but if you loaded the texture it should have displayed a
dialog with "This texture contains mip maps, do you want to load them?"
, you should press "No" there if you want to generate them later upon saving.

glad atleast the archive wasnt fucked up =D, that meens the injector
has now been tested IRL and seems to work actually.
## Post #16
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-17T11:10:45+00:00
- Post Title: 

Can I put the file up so you can download it and try to edit the texture?  I've tried all those things with the same result, so I'm not sure if it's me doing something wrong or not...
## Post #17
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-17T16:27:15+00:00
- Post Title: 

post the texture here. (the ripped original one, and your modified),
or if its too large, zip it and mail them too: [vital_@hotmail.com](mailto:vital_@hotmail.com)
## Post #18
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-18T08:31:07+00:00
- Post Title: 

This is the result of my efforts so far
Screens:
[http://members.iinet.net.au/~jeffriesfa ... /Test1.JPG](http://members.iinet.net.au/~jeffriesfamily@iinet.net.au/img/Test1.JPG)
[http://members.iinet.net.au/~jeffriesfa ... /Test2.JPG](http://members.iinet.net.au/~jeffriesfamily@iinet.net.au/img/Test2.JPG)

Textures:
[http://members.iinet.net.au/~jeffriesfa ... iginal)dds](http://members.iinet.net.au/~jeffriesfamily@iinet.net.au/img/%28original%29dds)_ 84145472_ 524288.dds
[http://members.iinet.net.au/~jeffriesfa ... edited)dds](http://members.iinet.net.au/~jeffriesfamily@iinet.net.au/img/%28edited%29dds)_ 84145472_ 524288.dds
## Post #19
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-18T09:45:38+00:00
- Post Title: 

I didn't edit these textures myself, by the way.  I'm crap with photoshop, I just got a friend who's reasonable with it to follow your directions, and as far as I can tell in nVidia's dds viewer, the mipmaps are fine.  I'm just paving the way to create a high-def pack, got a small team of artists ready to start work when I know how to make the textures work.
## Post #20
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-22T09:14:46+00:00
- Post Title: 

*cough* *cough*
## Post #21
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-22T14:23:51+00:00
- Post Title: 

hi there!!!!! =D

i almost recall me replying to this but obviously i didnt!

Everything looks just fine. the ripped texture and the modded texture 
look okay. so infact...i dont know why there are still purple artefacts on
the modded character in game, there must be something else
that is modifying some parts or textures of the characters,
because i really dont see anything wrong with the textures themselves.
,...hmmms.....
## Post #22
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-22T15:21:45+00:00
- Post Title: 

Any suggestions?
## Post #23
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-22T16:38:33+00:00
- Post Title: 

Well, I've figured out something.  It's a problem with Jaeder Naub, I'm pretty sure.  I ripped the archive again, after injecting the updated texture, and look at what came out...

[http://members.iinet.net.au/~jeffriesfa ... ripped.dds](http://members.iinet.net.au/~jeffriesfamily@iinet.net.au/img/ripped.dds)
## Post #24
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-05-22T18:37:35+00:00
- Post Title: 

Have you tried using my [file ripper & reinjector](http://www.turfster.be/FileStripper.rar) (version 2.1, there used to be a small DDS bug in 2.0, if you tried that)?
## Post #25
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-22T19:03:16+00:00
- Post Title: 

The link doesnt work =(

if its a problem with the ripper/injector i would really like to
investigate whats happening. try turfsters File Stripper 
and see if it "produces" the same error.

=o
## Post #26
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-23T04:06:35+00:00
- Post Title: 

Yeah, I uploaded the file after I posted the link, and my ftp is playing up.  I'll post a new one shortly.  Basically, the injector only injected the largest mipmap, and left the others purple.

EDIT: Link below.
[http://the-divide.org/img/ripped.dds](http://the-divide.org/img/ripped.dds)
## Post #27
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-23T04:50:51+00:00
- Post Title: 

Now this is interesting.
notice how the ripped texture of yours (the new modded one 700kb)
is bigger than the ripped one before. where the old
one was around 510kb. this means the injector simply couldnt upload
the mipmaps because there was no length in the name that
told it too do that.

there could be several factors for this. try modding this texture again
and use the other length in the filename, 
which should be "699195".

............hmms.....
## Post #28
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-23T04:54:15+00:00
- Post Title: 

yes. the name is faulty in the ripped texture.

simply rename your modded texture to "dds_ 84145472_ 699192.dds"
for the proper length and try injecting again.
(be aware of the spaces in the name also)

now i just have too search jaeder why it renders this incorrect name though.

for less confusion i rename it and zipped it, this texture SHOULD be
the correct one to inject without errors.

[http://jaedernaub.ath.cx/greenmod.zip](http://jaedernaub.ath.cx/greenmod.zip)

i really hope this one works =O
(still have the error in the ripper too fix though)
## Post #29
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-23T05:08:06+00:00
- Post Title: 

Ive looked through the code of the DDS ripper now, and i can confirm
this naming error is a bug in the code due to that the lenght is nowhere
stored in the DDS image when ripping, so Jaeder tries to approximate
the length, however it does this by not counting the Mipmaps.
this will be fixed in the next version. :X

EDIT:

[http://jaedernaub.ath.cx](http://jaedernaub.ath.cx)

download 1.8.9j - I hope the issue is fixed in this version. atleast
it should be, but havent had time too check it for myself yet :/ *sigh*
## Post #30
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-23T19:18:42+00:00
- Post Title: 

Almost fixed, it would seem.  The ripped texture's filename is now dds_ 84145472_ 699193.dds, but you said it should be dds_ 84145472_ 699192.dds.  Anyway, when I injected it under dds_ 84145472_ 699192.dds, it was a perfect success, thanks a lot .  Thankyou also, Turfster.  I couldn't work out your injector, but your ripper worked on the audio pak files, where Jaeder Naub didn't rip the audio.  I've got another question.  The main pak files for the game, when opened in a hex editor, say the path for the texture lies in \3art\npc\casablanca\watilla\textures\watilla_tex.png.  Here's how the game is set up though.  Root directory contains the game exe, some other random unimportant-looking dlls, the manual, ect.  Only 17MB total.  Then there's a "saves" directory, a "screenshot" directory, and a "bin" directory.  Inside "bin" is the "res"directory, and nothing else.  Inside "res" is all the pak files, and nothing but pak files.  One for each location.  There's also a bink video folder in there, but that's unimportant.  The textures for the player characters are in "common.pak", the voices are all in "vox_en_00.pak" to "vox_en_04.pak", and each of the npcs' textures reside in their location.  But here's where it gets interesting.  If, for example, you meet Bob first in Bob's house, his texture would reside in a file probably named "bobs_house.pak".  If you also meet Bob in a bar, his texture would not be in "bar.pak", so it must be assumed it's referenced to in "bobs_house.pak".  To explain a bit more, Bob is now "watilla".  In the hex editor, in "castillo_home.pak" (where watilla first appears), I've found a line saying \3art\npc\casablanca\watilla\textures\watilla_tex.png.  In "bar.pak", I've found the same line.  Do you have any idea what exactly is going on, and how the game could be completely unpacked, and the pak files deleted, to work with everything more directly?
## Post #31
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-24T10:44:09+00:00
- Post Title: 

In addition, would you have any idea how to find the subtitle files?
## Post #32
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-26T05:11:41+00:00
- Post Title: 

Actually, do you use MSN or ICQ, by any chance?  Would it be a possibility to get some help on there, perhaps?
## Post #33
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-26T06:04:47+00:00
- Post Title: 

Yes. Im using MSN right now. you could
add [vital_@hotmail.com](mailto:vital_@hotmail.com), just have to remind you that currently
im a little busy with different projects.
(recoding some parts of jaeder naub, making tunes for a compo,
and creating stuff for a demo, with more) so at the moment
i might not be the nicest person too talk with! 

but i will always try to help out when i have time!
## Post #34
- Username: Pirateguybrush
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 27, 2006 8:51 pm
- Post datetime: 2006-05-27T09:02:58+00:00
- Post Title: 

Since I've now added Strobe on MSN, I'll be continuting this discussion there.  If anyone was following this thread and wants to know more about Dreamfall, or this project, feel free to drop me an email, add me on msn, or visit me on The Divide (A TLJ/Dreamfall forum).  My email and msn are my username at gmail dot com, and The Divide can be located at [http://s14.invisionfree.com/The_Divide/](http://s14.invisionfree.com/The_Divide/)
