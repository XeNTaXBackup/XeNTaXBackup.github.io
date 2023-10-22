## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-13T17:16:13+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-13T18:05:37+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

If you can view the textures with PSIcture then it is possible they aren't compressed but are just stored within. Just an observation.
## Post #3
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-13T18:27:18+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Very true indeed, Darkfox, and thank you for confirming a suspicion I had. Do you know how I might go about getting at the individual files that aren't .BMPs? If the files aren't compressed, they do seem to be strung together inside the .BIKs. Any way to "break the container," so to speak?

Also, I'd like to ask the XeNTaX community at large a silly question, just to make sure: FileStripper doesn't automatically stuff whatever it finds into .BIK files, right? I mean, it's supposed to find .BIKs and not output to .BIKs, to my understanding. It's hard to tell whether .BIKs are really the containers Squaresoft stored the Chrono Cross files in, since the Chrono Cross CD lacks a Table of Contents that allows Windows to see the file structure. Whereas you can pop in Final Fantasy VII and see .lzs and .bin archives all over the place, Chrono Cross leaves you staring at the SLUS file and a tiny System file.

*Sigh* I'm still such a newbie at accessing game resources. Thanks for bearing with me.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-13T19:47:38+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Also I would like to point out that PSIcture takes common and some uncommon/game specific image formats used by PSX titles and converts them to BMP. So in all likelihood they  are not BMPs to begin with, PSIcture converts them and saves them that way. So you can't reinsert the converted image because it would mess up the game.
## Post #5
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-13T20:40:28+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Right you are, Darkfox. After playing around with PSicture's plugins, I've determined that the images ripped are .TIMs in their native format, silly me. Good to know.
## Post #6
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-14T01:50:07+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Okay, now I've figured out that the .TIM files are not compressed within the .BIKs. I can locate a specific .TIM's signature within the files. 

For example, the attached .TIM takes up hex addresses 002B6340 through 002BA55F in the first .BIK linked above. Will such knowledge help in the quest to break down these .BIK files?

It's not possible for a container such as .BIK to compress some files and not others, is it? I would imagine the compression is uniform across all the files stored in a single container / archive.
[TIM File Example.zip](https://xentaxbackup.github.io/file/1366_TIM File Example.zip)
## Post #7
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-14T02:37:01+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Found out an interesting tidbit that may be extremely helpful. Luminaire85 at the Chrono Compendium forums just let me know the following:

> I also tried two of the *.bik files in RAD Video Tools 1.8w, and both failed with an error message saying "This Bink file uses an old or beta Bink file format - please re-Bink the original video file." This page states that way back before March 1999 they changed the Bink format. Seeing as how Chrono Cross came out in 1999, it wouldn't be surprising if they were still using the old Bink beta format. 

So, does anyone just happen to have a really old version of RAD Video Tools lying around?
## Post #8
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T12:05:54+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

To make sure that is the case, did you try to re-bink it with The RAD Video Tools? You can get them here: [http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm)

Hope this helps,


Nick Kusters
## Post #9
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-14T18:16:12+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Thanks for the reply, Nick!

If you're referring to the post above regarding the inability to unBINK the .BIKs, we've had several people try to decompose the .BIKs with various versions of Rad Video Tools, all with the same error messages. The earliest version we could access is Version .8i. We suspect that an extremely early version of Rad Video Tools may have been used to create the .BIK containers obtained from Chrono Cross.
## Post #10
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T18:43:12+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

> Reply from FaustWolf
>
> Thanks for the reply, Nick!

If you're referring to the post above regarding the inability to unBINK the .BIKs, we've had several people try to decompose the .BIKs with various versions of Rad Video Tools, all with the same error messages. The earliest version we could access is Version .8i. We suspect that an extremely early version of Rad Video Tools may have been used to create the .BIK containers obtained from Chrono Cross.

Ok, sorry, I must have read it wrong 

I've been googling a bit, but without any luck. I know that there are a few sites that host older versions of popular software, but can't seem to remember or find any of them, did you give that angle a try yet?

Sincerely,


Nick Kusters.
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-14T19:44:38+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Can attach a bik sample?
Thanks!
## Post #12
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-14T21:02:44+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Even using file cutter on the lowest setting I can only get the file sizes down to 300KB, just beyond the upload attachment limit here.

Is it okay if I provide a Rapidshare link to some examples, or is there another file sharing method you prefer Savage? 

How much data would you need to determine whether / how the .BIK container can be decomposed? I can provide .BIK beginnings/endings between 300KB and 1MB in length.

EDIT: I've got a direct link to a .rar with three sets of sample .BIK data hosted on my MediaMax account. The beginning and ending 1MB or so of each .BIK file is contained within; it's a 3MB .rar.
[http://www.mediamax.com/faustwolf/Hoste ... amples.rar](http://www.mediamax.com/faustwolf/Hosted/BIK%20Samples.rar)

This way you don't have to be bothered with countdown screens and the like.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-14T21:24:47+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

well. you sure are a bik files?
If i get the first head.bin from the example i can compress (with rar) this (1.048.576bytes) to 572.774bytes

I'm sure at 100% this files are not BIK files, the program ripped it 'coz the FOURCC it's BIK nothing else
## Post #14
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-14T22:32:25+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

Thanks for looking at it Savage!

Do you mean that the samples I gave you from MediaMax aren't .BIK files, or that the original files those samples came from aren't .BIKs?

I can provide a sample in another way perhaps, if necessary. I am aware that filecutter turned the beginnings and endings of the .BIK files into zipped .BINs; is that the problem?

I'm pretty sure that FileStripper didn't just add the .BIK format to the data it ripped. Judging from the Hexadecimal, these .BIKs appear in the larger .iso file. It also appears from our research that Squaresoft (the maker of Chrono Cross) has contracted with RAD Game Tools in the past, so I *believe* it's likely that the original files are indeed .BIKs. I'm not absolutely sure, of course.

By FOURCC, I assume you mean [http://www.fourcc.org/](http://www.fourcc.org/) ? Is there a codec there that should be able to "read" these files?
## Post #15
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T23:10:57+00:00
- Post Title: Chrono Cross (PSX) .BIK files - Could support be added?

> Reply from FaustWolf
>
> Thanks for looking at it Savage!

Do you mean that the samples I gave you from MediaMax aren't .BIK files, or that the original files those samples came from aren't .BIKs?

I can provide a sample in another way perhaps, if necessary. I am aware that filecutter turned the beginnings and endings of the .BIK files into zipped .BINs; is that the problem?

I'm pretty sure that FileStripper didn't just add the .BIK format to the data it ripped. Judging from the Hexadecimal, these .BIKs appear in the larger .iso file. It also appears from our research that Squaresoft (the maker of Chrono Cross) has contracted with RAD Game Tools in the past, so I *believe* it's likely that the original files are indeed .BIKs. I'm not absolutely sure, of course.

By FOURCC, I assume you mean http://www.fourcc.org/ ? Is there a codec there that should be able to "read" these files?

What savage ment was that if any part of the data can be shrunk by 50%, it's not BINK video, since they have an extremely high compressionrate out of the box, a 3rd party product wouldn't be able to effectively shrink it by that much.

It might just be a false positive (e.g. it's a different type of file that just happens to have the BINK video header sequence as part of its own data).


Hope this helps,


Nick Kusters.
## Post #16
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-15T00:11:09+00:00
- Post Title: 

It's not Bink. The header is completely different, and since Bink videos are in a proprietary cross-platform format, it's very, very unlikely they would contain PSX texture files.
From a quick browse through one file, it seems it's texture and model data of some sorts. I can't find any kind of archive header, so I don't think it's a general-purpose archive format.
## Post #17
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T00:51:46+00:00
- Post Title: 

Thank you all VERY much, Nick, Savage, and John Doe!! 

It's all making sense now. John Doe, how is it that you can tell model files are in there? Something in the hex code, or are you viewing the data in another way? I expect the company may be using a proprietary model format that won't be readily understandable, of course.

BTW, do you have an example of a true .BIK file header I could compare these against?
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T01:19:14+00:00
- Post Title: 

Perhaps when I get time I'll find my CC and check for the data format that you speak of. I was skeptical to begin with but I didn't know how you obtained these files as I've never checked CC before because I tend to deal with more obscure titles.
## Post #19
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T01:52:21+00:00
- Post Title: 

Yeah, I threw my Cross .iso at FileStripper, and it gave me these .BIKs along with a few false .MPEGs. Maybe I should have known from the obviously screwy MPEG files that the program was up to no good, huh? 

Beware though, before you try it Darkfox -- the program ran smoothly at first, then slowed my computer down unbearably once it got to the 500MB / 610MB mark or so in its scan. The .BIKs it produces from the Disc 1 iso are around 100MB or so. Also, if it matters, I ripped my iso with IsoBuster as <content -> user data> rather than as an <image>. When you rip as an "image," IsoBuster and possibly other programs seem to insert junk data every sector or so, needlessly expanding file size and screwing up rip-able .TIM texture files. 

On the other hand, I'm not sure if I've ever gotten an iso ripped in this way to work with my emulators. I usually use the isos for file exploration and play with the physical games in my CD drive.

The .BIKs are most likely false, as everyone here has now said, and it's pretty much the same feeling at the Chrono Compendium. I can say from viewing the false .BIKs in Hexadecimal that the headers are inconsistent - they each start with a "BIK" ascii string, then everything goes downhill from there. Though for the life of me I can't figure out why FileStripper would get trigger-happy upon seeing some BIK ascii strings and not others.

Hopefully the people I'm working with at the Chrono Compendium and I will come across a Table of Contents of some sort that tells where/what the REAL archives are that Squaresoft stored its files in. If that happens, I'll revive this thread and ask you all for your expertise again.

And while I've got people's attention here, I'd like to ask one final question: there SHOULD be honest-to-God archives on every game CD, right? I mean, a game company wouldn't just store its files uncompressed, would it? Have you folks seen anything like that, either for console games or PC games?

Thanx again for all your help!
## Post #20
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T02:14:45+00:00
- Post Title: 

Fact is, I DO NOT use file rippers on CD images. The results are bound to be screwy. Dunno why anyone would try it since it's so easier to use something that can open an ISO image or to explore the CD itself.

I do just fine mounting a CD image I've ripped for test play (it's faster to run on the hardrive in many cases) and I can even scan it with PSIcture just like it was a CD. No problems. I've tested the methods, no difference. I dunno if your unable to open them this way or what but using a file ripper on a CD image directly...

...

bad choice. File rippers/scanners are often intended for PC games, not console games though sometimes they use PC formats if your lucky.

I have used PSIcture on a CD Image and got scrambled images. Then I mounted it with VD and got perfect results. So ripping directly from an ISO isn't a good idea. The results can be messy.

> I mean, a game company wouldn't just store its files uncompressed, would it? Have you folks seen anything like that, either for console games or PC games?

Yes, quite a few actually. Not everyone compresses data. Some just store it in a library or just put the files in a folder. I've seen it a few times.
## Post #21
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T02:26:11+00:00
- Post Title: 

Thanks again Darkfox. We've got the PlayStation logo ripped as an uncompressed .TMD model, but I don't think that's any indication that all the model data is uncompressed on the CD...or is it?   

I assume it's the case that every PlayStation game has that model as part of its data. 

Do you have a certain favorite program for exploring console game CD data? I haven't come up with anything better than a hex editor, but then again I'm still a n00b at this sort of thing.
## Post #22
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T02:36:04+00:00
- Post Title: 

Exploring the CD itself or data contained within the files ON the CD? I use a variety of tools. If I'm looking for graphic data I use Texture Finder to search through files I suspect contain sprites, pictures, etc. For sound there are various sound tools to scan with. Exploring a CD, I just fumble through the CD as one normally would.

  With few exceptions CD consoles use normal CDs/DVDs to store the data. (One exception I know of is the PC-Engine Console CDs. But don't worry about that.) Often a filename will gives away it's content, like sound, bchar, bgm, etc.
## Post #23
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T02:48:24+00:00
- Post Title: 

I've used various tools to explore data archives ON the CD (e.g., .lzs archives in Final Fantasy VII), but it just bites when you can't see those archives like with Chrono Cross - it's the first game CD I've come across where Windows can't see anything once I've got it in my CD drive. So I've been keeping an eye out for tools that have the capability to scan an entire CD or ripped .iso.

Texture Finder sounds interesting. We've got most of the textures in Chrono Cross already via PSicture and TIMViewer, but not all of them. Perhaps exploring with a fresh tool will turn up a few more.

The Chrono Compendium is mainly trying to gather model data and pre-rendered background data for Cross. If you've got suggestions Darkfox, I'm all ears and would be happy to learn some tricks of the trade from someone with more experience in the game-resource gathering scene.
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T03:05:35+00:00
- Post Title: 

Sometimes the reason your not seeing all files is because they are hidden. Often all you have to do is set your browser to see these hidden files. Otherwise it would be something different that could be overcome with an alternative CD explorer or viewing it with an ISO tool. It varies though. I've never touched Chrono Cross myself... YET. XD I've worked more with more obscure titles. Never was for the popular games.
## Post #25
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T03:26:10+00:00
- Post Title: 

Man, yeah, I wish it were as simple as hidden files. I just re-checked to make sure, but sure enough my PC can't see a thing other than the SLUS and System files.
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T05:35:09+00:00
- Post Title: 

I see, so it is one of THOSE PSX games. Perhaps some form of workaround exists. I'll see if I can check it when I get time.
## Post #27
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-15T05:37:22+00:00
- Post Title: 

> Reply from FaustWolf
>
> Thank you all VERY much, Nick, Savage, and John Doe!!
Y
Your welcome 

> Reply from FaustWolf
>
> 
BTW, do you have an example of a true .BIK file header I could compare these against?

According to [http://wiki.xentax.com/index.php/BinkVideo](http://wiki.xentax.com/index.php/BinkVideo), the header is 56 Bytes long. Here's a dump of the first 56 bytes off of the BlueByte video intro from Settlers VI (this video didn't contain audio, just so you know).
[BINK_VIDEO_HEADER.zip](https://xentaxbackup.github.io/file/1369_BINK_VIDEO_HEADER.zip)
## Post #28
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-15T06:27:22+00:00
- Post Title: 

Very offtopic @john_doe, can you have a look to the .xxx files? 
It's LZO, we looking just the "inflate"  
[viewtopic.php?t=2466](http://forum.xentax.com/viewtopic.php?t=2466)
Thanks in advance

I attach the Multiex banner in bik file
[multiex.zip](https://xentaxbackup.github.io/file/1370_multiex.zip)
## Post #29
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-15T17:10:28+00:00
- Post Title: 

Thanks for the .BIK headers guys!

And thanks for checking out the PSX disc Darkfox. Hopefully something can be found. This is a another n00b question, but could the SLUS file help out in any way?
## Post #30
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T20:13:52+00:00
- Post Title: 

I'll be sure to try some various approaches. As it seems it has to do with software or something of that type where windows is not normally able to view the files. This doesn't mean they aren't there or are unreadable.
## Post #31
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-20T00:36:14+00:00
- Post Title: Possible Table of Contents

I'm ba~ack! 

Darkfox, or anyone with experience in this subject for that matter, could you take a look at the attached files? The first is a hex string I ripped from my Xenogears iso that should be a Table of Contents, i.e., the game's index that tells the console/emulator where all the files or archives are located. I ripped this based on documentation from the Qhimm community wiki (see it here: [http://wiki.qhimm.com/Xeno/IndexFileFormat](http://wiki.qhimm.com/Xeno/IndexFileFormat)). An important note: I believe the sectors on the Xenogears CD are 2048 bytes long.

There's no such documentation on the Chrono Cross index file yet, which is why I ripped the Xenogears index file first so I had an idea as to what I was doing. Thus the second attachment (see next post) is hopefully the Chrono Cross TOC, though quite frankly I'm not sure.

Any ideas regarding how these files might be viewed?
[Xeno Index Possibility.zip](https://xentaxbackup.github.io/file/1378_Xeno Index Possibility.zip)
## Post #32
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-20T00:37:06+00:00
- Post Title: Possible Table of Contents

Now for what is hopefully the Chrono Cross equivalent.
[CC Index Possibility.zip](https://xentaxbackup.github.io/file/1379_CC Index Possibility.zip)
## Post #33
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-20T04:23:48+00:00
- Post Title: Possible Table of Contents

Well I've had a look at Chrono Cross and yeah, they are not viewable by PC. I've tried several CD editing software and had no luck. Problematic indeed. But it's a wonderful reason to make a program that uses adapted PSX software to explore a PSX CD. XD

Perhaps the SLUS file offers some clue though I dunno if anyone here can do anything with that. I've seen it done before but it's all a bit iffy as I don't know how to myself. XD;

Edit: As I recall the Gameshark for the PSX had an explorer/player function where it could look through the PSX CD. Dunno if this is emulated or not...
## Post #34
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-20T05:50:08+00:00
- Post Title: Possible Table of Contents

Thanks for checking it out, Darkfox. I suppose you don't happen to know of any way to view the index files that have been ripped from PSX CDs, do you? I think the attachment above may very well be an index file (table of contents) for Chrono Cross, and I'm much more confident that the Xenogears attachment is the real deal for that game, based on the Qhimm wiki I linked to. But there's no way of knowing for sure until I can find some way of making the files intelligible.
## Post #35
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-21T20:53:29+00:00
- Post Title: Possible Table of Contents

Darkfox, if you're still interested at all in Chrono Cross exploration, just wanted to let you know we've broken down Disc 1 into its separate files over at the Chrono Compendium thanks to Ramsus over there.

The pertinent posts start here:
[http://www.chronocompendium.com/Forums/ ... l#msg83045](http://www.chronocompendium.com/Forums/index.php/topic,4729.msg83045.html#msg83045)
## Post #36
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-21T22:22:43+00:00
- Post Title: Possible Table of Contents

Looks like you got what you were trying to achieve. However the files are dumped from the CD Image as ######.out? I'm guessing that filenames are encrypted?
## Post #37
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-21T22:57:20+00:00
- Post Title: Possible Table of Contents

Yeah, we're not sure what's going on with the whole .OUT thing yet. It could be that the dumper just cut files out of the CD image as raw data and stuck its own header on or something. We're investigating, and I'd certainly be glad to have your input on matters as our research progresses.
## Post #38
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-09-22T00:29:04+00:00
- Post Title: Possible Table of Contents

Almost 4 years later and I'm bumping this topic.  I apologize if that's an annoyance or more than the appropriate time period, but I didn't find a resolution to the problem.  I just find links to the chrono compendium with empty posts.  

I was just wondering if anything came about with chrono cross, I believe I've seen something referred to as "Ramsus cctools", and "Ramsus Yazoo something or other".

any update would be greatly appreciated.
## Post #39
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-22T00:44:43+00:00
- Post Title: Possible Table of Contents

I'm aware of the tools and once had them, but no longer. I've been through a few computers since then. You should look into getting in touch with Faustwolf, whom should be a Compendium member, at least he was last time I was there. He can be a bit tough to get in touch with though.

Doesn't come here often as far as I know.
## Post #40
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-09-22T00:57:33+00:00
- Post Title: Possible Table of Contents

I sent him a PM through this forum, and I've been searching through Qhimm's site, but am still lead to chrono compendium posts that are either off limits or no longer available.  I've been googling it for a while but haven't come up with it yet.  

I'll try PMing him through chrono compendium though.  Thanks for your suggestion Satoh!!!
## Post #41
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-09-23T05:13:46+00:00
- Post Title: Possible Table of Contents

I do believe there was a C&D against the chrono compendium so that answers a little bit of the issue...
