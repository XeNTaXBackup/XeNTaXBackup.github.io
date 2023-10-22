## Post #1
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-09-08T05:37:00+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

I know this has been asked before, but I am in dire need of John Marston's model.

I read in this forum that Rage Research Project has a program called ".black", but I can't find it.

Any Help?
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-09-08T07:07:46+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Can you get me the unconverted models so I can convert them, as it's an xbox360 game so the only way I can get the files without having an xbox is by people sending them to me. Also send me the 'Zebra Donkey' model while you are at it please.
## Post #3
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-09-08T11:28:05+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

I probably can't right now, as they are locked in an .rpf file.

The the formatting of it is RPF6, and I can find a tool to extract it.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-09-08T12:07:51+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Can you try using the program called "offzip" to search for zip compressed components, in the file. If you do not know how to use this program send me a PM. Also have you tried the program Xboxdecompress that is posted on another topic. If works for many Xbox360 games, and even when it does not work, it gives different error messages depending on if it uses a compression based on xbox360 dev kit, or if it is a totally different compression message. I would also check the press releases on Rock Star Sandigo's website as they might mention the name of the game's Engine. The credits in the instruction menu and/or the game are helpful to, because if developer Joe Smith did Engine Design for this game, and also for a different game where we know the compression method, that will help us out to.
## Post #5
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-09-08T22:38:03+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

I can't seem to get xbdecompress to work. What native formats can it save to?

Everytime its the same thing

"Cannot save this file in a native format"



Here is my syntax:

xbdecompress /h rdr2_layer0.rpf rdr2_layer0.zip
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-08T23:09:58+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

all rockstar games are encrypted there is no pc version so its very hard to get the key.
## Post #7
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2010-12-18T18:52:10+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Has anyone made any headway yet? I've been checking daily on here and Rockstar's site (for mention of a PC release). This is my favorite game ever and I really cant wait to check out the models/textures in max. I also want to learn more about how they achieve such incredible lighting in their skydomes
## Post #8
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-01-28T22:12:20+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

I know this topic is very old, and I apologize, but has anyone made progress?
## Post #9
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-17T15:39:15+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Not too much progress just yet, but i currently at least have a brute-force extractor of the files.





i have only looked into the texture format so far, since it was the simplest.  Still have a good deal of background research to complete, as i now plan to look into as many of the RAGE engine based games and its formats as i can make time for.  Although others have already done a lot this work, unfortunately it seems they have no desire to release tools that support the console versions of the games.

i hate having to duplicate work others have already completed, but i guess it can't be helped.

Hopefully i can work this into the list of other formats i have on my todo list and make some more progress.

Will have to see how things go.
## Post #10
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-05-17T16:23:26+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Friend, I know that is not the right place, the more you got to extract the text?
## Post #11
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-17T16:44:49+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

For now i have just done a raw extraction of the individual file blocks.  Unfortunately i have not been keeping up with the GTA4/RAGE engine research being done on other forums, so i am a bit behind at the moment on how a lot of the internals work, thus i am researching and reverse engineering things as i go.

There are various flags in the file table and resource headers i have not deciphered yet.  Also i have not built a file name table yet so that i can convert the file hashes to readable names.  After decompression, the RSC data in particular, cannot always be reliably identified from what i have seen, so i have left all blocks thus far compressed until i can further determine which types of files are specified by the various id values.

Once i compile a larger list of directory and file names, hopefully i will be able to determine some of the non-RSC based files a bit easier.  i'll see if i can decompress a few more of the other types and determine which are the text/xml/script based formats when i get the chance.

i am guessing that a number of the formats will not have changed much unless they absolutely needed to for things like platform differences, which i would expect for things like textures and mesh data as each system handles certain things differently.

Not sure how much help it will be in the end, as i don't know of anyone planning on working on repacking the data for any of the console based games.

Will see how things go.
## Post #12
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-05-17T17:59:44+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

Well that guy.

I'm cheering, and I hope their work will evolve from this work.

I already did the port of 6 translations of PC games to PS3, I'll be cheering for us to work with a translation into RDR.
## Post #13
- Username: BuarBuar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 19, 2011 4:02 pm
- Post datetime: 2011-05-19T08:16:34+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

> Reply from CodeMan89
>
> I read in this forum that Rage Research Project has a program called ".black", but I can't find it.
Hey! Look what I just found on OpenIV site ([http://openiv.com/](http://openiv.com/)).
In the lasted video (it public yesterday) he used .black not OpenIV.
Here is screen from video:



black on video video1.png (126.16 KiB) Viewed 1362 times


You can see this video on youtube here [http://www.youtube.com/watch?v=0wbmjxy8U-8](http://www.youtube.com/watch?v=0wbmjxy8U-8)

So what do you think?
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-19T09:38:41+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

> Reply from BuarBuar
>
> CodeMan89 wrote:I read in this forum that Rage Research Project has a program called ".black", but I can't find it.
Hey! Look what I just found on OpenIV site (http://openiv.com/).
In the lasted video (it public yesterday) he used .black not OpenIV.
Here is screen from video:
video1.png
You can see this video on youtube here http://www.youtube.com/watch?v=0wbmjxy8U-8

So what do you think?
.black tool is for internal use only, it means that .black can use only developers of openIV.
## Post #15
- Username: gamerzworld
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 22, 2011 1:41 pm
- Post datetime: 2011-05-23T11:01:13+00:00
- Post Title: Red Dead Redemption .rpf converter/extractor

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-05-31T03:59:01+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Still a few things i am looking into regarding the shader groups, and then textures should be visible, but i finally got around to implementing the basics i needed for models so that i could test more of the other areas i am investigating.
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-31T04:31:28+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

i must admit your great work, revelation, keep it going and thank you
## Post #18
- Username: gamerzworld
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 22, 2011 1:41 pm
- Post datetime: 2011-05-31T11:04:57+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Awesome job man! I do hope your planing to release your work when your done. I have a friend who is an artist who would love to get a hold of the models and textures and personally I'd love the chance to grab the audio since the soundtrack omits a good number of songs from the game. Any chance you could take a quick look at Rockstar Table Tennis and MCLA also? They both use RAGE and RPFs.

Here is some research that has been done on the Table Tennis RPFs

```
|         Rage Package File         |
+-----------------------------------+
|      By Ac_K, UZI-I & ParoXum     |
+-----------------------------------+


+--------+
| Header |
+--------+
0x00 - 4 byte - CHAR[4]   - FourCC, Always "RPF0".
0x04 - 2 byte - WORD      - Unknow (Certainly a padding ?).
0x06 - 2 byte - BYTE      - Unknow (0x00 or 0x01).
0x08 - 2 byte - BYTE      - Number of entry + 1 (for actual file).

+-----------------------------+
| Declaration Positions/Names |
+-----------------------------+
0x800 - 4 byte - UNK      - Always 0x00 0x80.
0x804 - 4 byte - UNK      - Always 0x01 0x00.
0x808 - 2 byte - BYTE     - Number of entry (Files positions ?).
0x80C - 2 byte - BYTE     - Number of entry (Files names ?).

+-------------------------+
| Positions (on 16 Bytes) |
+-------------------------+
0x810 - 4 byte - BYTE     - Text position after the " / " ( " / " is after all the position).
0x814 - 4 byte - WORD     - File Offset (number of "block").
0x818 - 4 byte - DWORD    - Unknow (Certainly file size ?).
0x81C - 4 byte - DWORD    - Unknow (Equal to 0x818 in different RPF).

The next file is on the next 16 bytes.
The second next file is on the next 16 bytes.
Etc...

+-------+
| Names |
+-------+
The names begin after all position.
For reconize the begin of the names, the / and the byte 0x00 is present.
After, the names are separate by 0x00.

+-------+
| Files |
+-------+
Writing on as padding (block ?) to 2048 Bytes likely 0x1000, 01800, etc...

The different formats :

- *.anim          // animation array file
- *.bnd           // collisions
- *.cfg           // config basic file
- *.cm            // camera coordinates ?
- *.data          // -Unknow
- *.dds           // directx texture format
- *.dynamic       // -Unknow
- *.fx            // compiled universal shaders
- *.fxc           // another shader ?
- *.levelfx       // -Unknow
- *.list          // dictionnaries ?
- *.mesh          // 3D models
- *.mtl           // common material extension file
- *.phys          // -Unknow
- *.png           // universal image format
- *.rmtpx         // effects/particles files
- *.skel          // skeleton files
- *.sps           // shader libraries ?
- *.static        // Sound Bank
- *.strtbl        // Boot Screen
- *.sva           // -Unknow (Diffuse Texture?)
- *.td            // Sound Bank
- *.txt           // text, motd ?
- *.xeck          // -Unknow (Sounds?)
- *.xml           // input text files / ai files ?
- and other not discovery





 char  szFourCC[4];
 int  	iUnknow1;
 DWORD  dwFilesNumber1;
 char  szPadding1[2036];
 int  	iUnknow2;
 int  	iUnknow3;
 DWORD  dwFilesNumber2; // (x)
 DWORD  dwFilesNumber3; // (x)


And (Repeated 'x' time after the dwFilesNumber3):

CODE

 DWORD  dwStartNamePos;
 DWORD  dwPosition;
 DWORD  dwUnknow1;
 DWORD  dwUnknow2;
```
## Post #19
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-06-05T17:32:49+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

OMG! This is incredible. I've been looking at these pages and Project .black for ages, every week pretty much hoping, hoping. I can't believe you cracked it! Please please Revelations let us have access to your wisdom. I'm a 3d artist and it would be invaluable to me for research purposes. I'm actually building Armadillo in UDK and the environment assets would be really super cool to look at. I wish I had your knowledge/ability.
## Post #20
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-06-10T19:35:30+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

There is some possibility that at least release the program to extract the textures?
Excelent work
## Post #21
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-06-12T17:32:26+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

It looks like he used a brute/force extractor called Noesis (in the screenshot). I tried searching online for it but couldn't find anything. Anyone else know how to brute force extract the textures?
## Post #22
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-06-13T17:22:29+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Revelation, How can open rdr2_layer0.rpf?
edit
ohhhh, sorry. I don´t see "PS3". Its a PS3's Hard Disk.
Señor Casaroja?
## Post #23
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-06-13T19:25:52+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from pixeldamage
>
> It looks like he used a brute/force extractor called Noesis (in the screenshot). I tried searching online for it but couldn't find anything. Anyone else know how to brute force extract the textures?
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

Its right there. its never been a secret. the public release might not support rpf yet though.
## Post #24
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-06-15T20:33:00+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

There is some progress with textures revelation?
## Post #25
- Username: alz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 26, 2011 2:15 pm
- Post datetime: 2011-06-26T06:29:24+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

This is the first place I've found anything promising for peeking into the .rpf files!  It'd be great to rummage through textures and audio files.

Here's some audio files from one of the .rpf files:
[http://www.megaupload.com/?d=7QGEPHO7](http://www.megaupload.com/?d=7QGEPHO7)

My hard drive was overwritten accidentally a few months ago.  I used a file recovery program to sift through the bits.  I set it to find .mpg files and it found these 2 audio files.  They're strings of dialogue that don't make much sense by themselves.  If you're familiar with the story you'll recognize some lines, however.

Again, not sure how the recovery program picked out these bits.  Maybe the physical space the original .rpf files were sitting in were half-over written with new files and allowed the program to pick through the .rpf debris?
## Post #26
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-06-27T06:35:11+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I have not yet developed the tool. We all hope
## Post #27
- Username: alz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 26, 2011 2:15 pm
- Post datetime: 2011-08-12T13:43:01+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Any development on this?  Or at the very least, direction on brute force extraction of assets?
## Post #28
- Username: gamerzworld
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun May 22, 2011 1:41 pm
- Post datetime: 2011-08-12T16:30:10+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from alz
>
> Any development on this?  Or at the very least, direction on brute force extraction of assets?
I second this. I'd still love to get a look at the assets. I'm betting a number of things cut during development are still in the files.
## Post #29
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2011-08-22T17:20:29+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Awesome work on this o_O
## Post #30
- Username: Lyalenko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 28, 2009 5:11 am
- Post datetime: 2011-09-07T18:02:51+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Anyone work with rpf? Or it's dead
## Post #31
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-09-08T18:21:18+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from Lyalenko
>
> Anyone work with rpf? Or it's dead
it's dead
## Post #32
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-09-12T05:58:21+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Any progress
## Post #33
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-09-22T13:27:08+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

My hunch is we shouldn't give up hope just yet. I pm'd Revelation recently and he was kind enough to reply and say he's still planning on working on it. Something to do with working out the texture swizzling format used in the rpf. I looked it up ([http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)) and it looks insanely complicated to an artist like me. He's been stuck/waiting to get around to, this for at least the last four months and it sounds like he's got a lot of other commitments but he did say that's its still on his radar. We can only hope he keeps at it. If anyone else understands swizzling and can offer assistance then please do. Its a huge amount of work for one guy, and as he's said before, he's not had any help from the other teams who are keeping very secretive about their progress - i'm assuming *cough*, project black, *cough* ahem. Then again he's produced amazing stuff (alone?) - Noesis is incredible, so I have faith.

The other hope is that after the GOTY edition of RDR they might finally make a pc port which would make all our lives better . But this is seeming very unlikely since its so old now [sigh]. What do you guys think?
## Post #34
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-09-22T17:16:53+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I think there is still hope. Revelation is working on the project and see it but being able to get only very difficult
## Post #35
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-09-23T16:21:26+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

i am still working on things and have a number of updates i hope to have out at some point.  will have to see.

listener, GooD, Chipsman, etc. have all been very helpful with various insights into the RAGE engine internals.  i try not to pester them too much though.

There is plenty of information on how a lot of these formats work.  i think the decryption key information was even posted in one of the other RDR related threads (if it wasn't this one).  For the most part the process is almost the same across the rpf formats, with a few simple differences in data structure layout.  i'll see if i can gather and clarify some of it when i get the chance.

The 360 texture tiling is something i am looking into for many reasons, but suffice to say for now the functionality present in noesis works fine.  There are a few things i have to decipher from the shader information to apply the materials correctly in some cases, but for the most part it has not hindered my progress.  My main focus is to hopefully have some more work done towards the animation data.  i am also wanting to get back to the ps3 version of some of the formats in order to reverse the 'ps3 edge' form of index compression (which will also help with other ps3 games that use it).

The main thing is that i have worked and tend to work on a lot of formats (especially when there are unsolved areas of them), as well as a few other projects.  Although my hope is that some of those projects will end up being beneficial to the xentax community, or at least to my rate of progress on things throughout the forums, i have to make the time to get to all of it, heh.
## Post #36
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-09-23T16:56:59+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Great work and thanks for the effort
## Post #37
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-09-25T16:05:02+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Thanks revelation & Good Luck I hope to make a GTA RDR one day
## Post #38
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-09-28T22:24:13+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from revelation
>
> i am still working on things and have a number of updates i hope to have out at some point.  will have to see.

listener, GooD, Chipsman, etc. have all been very helpful with various insights into the RAGE engine internals.  i try not to pester them too much though.

There is plenty of information on how a lot of these formats work.  i think the decryption key information was even posted in one of the other RDR related threads (if it wasn't this one).  For the most part the process is almost the same across the rpf formats, with a few simple differences in data structure layout.  i'll see if i can gather and clarify some of it when i get the chance.

The 360 texture tiling is something i am looking into for many reasons, but suffice to say for now the functionality present in noesis works fine.  There are a few things i have to decipher from the shader information to apply the materials correctly in some cases, but for the most part it has not hindered my progress.  My main focus is to hopefully have some more work done towards the animation data.  i am also wanting to get back to the ps3 version of some of the formats in order to reverse the 'ps3 edge' form of index compression (which will also help with other ps3 games that use it).

The main thing is that i have worked and tend to work on a lot of formats (especially when there are unsolved areas of them), as well as a few other projects.  Although my hope is that some of those projects will end up being beneficial to the xentax community, or at least to my rate of progress on things throughout the forums, i have to make the time to get to all of it, heh.


Go revelation YOU ARE MY HERO
## Post #39
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2011-09-30T13:26:50+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

The update made my day!
Thanks so much for the effort^^
## Post #40
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-10-02T08:39:24+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

so i found out what the names of the weapons in RDR2MPSAVE.sav

for example the bufflo rifle = WP_BUF

so i started looking up in RDR2_layer0.rpf

i saw 2 of WP_BUF, which i think one for the single player and the other of Multiplayer mode


let me show you

WP_BUF.....WP_BUF2.....WP_BUF2_0.....WP_BUF2_0_des.....WP_BUF2_0_info.....WP_BUF2_1.....WP_BUF2_10.....WP_BUF2_10_des.....WP_BUF2_1_des.....WP_BUF2_1_info.....WP_BUF2_2.....WP_BUF2_2_des.....WP_BUF2_2_info.....



and the other one ( probably Multiplayer mode )

WP_BUF.....WP_BUF2.....WP_BUF2_0.....WP_BUF2_0_des.....WP_BUF2_0_info.....WP_BUF2_1.....WP_BUF2_10.....WP_BUF2_10_des.....WP_BUF2_1_des.....WP_BUF2_1_info.....WP_BUF2_2.....WP_BUF2_2_des.....WP_BUF2_2_info.....WP_BUF2_DYNAMIC_GOAL.....WP_BUF2_DYNAMIC_TITLE.....WP_BUF_DYNAMIC_XP.....WP_BUF_HLP_1.....WP_BUF_HLP_3.....WP_BUF_num.....



we'll know every weapon in Red Dead has his own power, rate of fire, reload speed, range, ammo, title, ..etc

we could get better than this if we have the "undead nightmare iso" so we can have more information about the other weapons just like Explosive Rifle,


so tell me guys what do you think ???
## Post #41
- Username: pro spy
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 12, 2011 11:36 am
- Post datetime: 2011-10-02T09:21:02+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

i'm downloading the full version of Red Dead Redemption, which is "Undead Nightmare"

it'll take time just wait
## Post #42
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-17T16:59:49+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Hi i tried open the rpf files with the noesis but i cant,how you guys viewed the textures and 3d models from red dead with this program?And you guys could extract the rpf files with noesis or just could make a vizualization?And if was posible extract,you guys could convert the red dead animations files to other file?
## Post #43
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-10-18T15:28:40+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

lionKing7 - Good to see you're working at it. The screen shots posted of the textures in Noesis are by the author of Noesis himself and probably with a lot of extra coding /handy work/blood sweat and tears. I very much doubt you can open RDR RPFs in the currently available version of Noesis as revelation is still trying to understand their swizzling / tech methods. I'm a noob when it comes to this stuff but my understanding is that rockstar encrypt their RPFs to stop this kind of thing. I think GTAIV had different encryption of their packages to the RPFs in RDR. The way around this (I believe) is by doing brute force extractions, though I have no idea how revelation did this. 

disclaimer: I could be totally wrong on everything above. If I am then please educate me as I'm eagerly watching this thread. Roll on more RDR content.
## Post #44
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-19T14:03:03+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Hi pixeldamage ,thanks for answer.Yah i understood this too,i just want to know if the people had some progress,i will try talk to Revelation to know that,if you discover something new let me know ok friend?I will start to study this now.
## Post #45
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-19T15:15:24+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Hi i know this topic is for us to try to get the files from RDR,but if someone know something to help me.... i extracts the Red dead revolver(to have some fun while we dont get the Rdr files...) .dat files,but i dont know what i got.The Streams.dat give to me files.stm,and the others .dat give files without extension.The .stm begin like this (STMAji @ À]   V V ) and the unknow files begin with the word Sia0,anyone knows what it means?And about the stm,i thought was animation files from the program Speedtree mesh from 3d max who have a stm extension,but have a audio extension too called .stm,so i will try to open this files like audio to see what they really are.Someone know if streams in games is a audio game directory or is possible that files can be animations?I extracts the .dat files with the program Game extractor from Watto studios.
## Post #46
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-21T20:08:03+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Hi revalation,you could got the maps files with the program modification that you make?
## Post #47
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-10-23T19:43:19+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

[viewtopic.php?p=61224#p61224](http://forum.xentax.com/viewtopic.php?p=61224#p61224)
## Post #48
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-10-24T07:25:04+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Wowwww. I am testing the plugnig. Long time to unzip the file, I look forward to. Thank you very much revelation, you are my idol. One question: If you're Russian, that your site has a very Spanish name as "Señor Casaroja"?

edit:
I could extract all but I can not preview it. Noesis tells me:  "This file cannot be prewied but can see exportable".I exported the file but can not find

> Reply from revelation
>
> 


.



because I can not see it? my pc is new and has windows 7. I have MV C++ 2005,2008,2010. I need any tool?
## Post #49
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-10-24T19:54:12+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from lUIGUIPIETRO
>
> Wowwww. I am testing the plugnig. Long time to unzip the file, I look forward to. Thank you very much revelation, you are my idol. One question: If you're Russian, that your site has a very Spanish name as "Señor Casaroja"?

edit:
I could extract all but I can not preview it. Noesis tells me:  "This file cannot be prewied but can see exportable".I exported the file but can not find
revelation wrote:


.



because I can not see it? my pc is new and has windows 7. I have MV C++ 2005,2008,2010. I need any tool?

Sounds like you're making progress  so to be clear what files did you extract? did you open the rpf?
## Post #50
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-10-24T19:59:30+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Yes, you can extract rpf. viewtopic.php?p=61224#p61224
 use this plugning with "Noesis" and you can extract the files. Its very slow becouse need unpacker 7 Gb
## Post #51
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-10-24T23:45:01+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I updated the Noesis thread to mention this.  You do not need to choose the correct filter to be able to open a file type that is supported, simply choosing it from All Files has the same effect.
## Post #52
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-10-25T04:44:04+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from revelation
>
> I updated the Noesis thread to mention this.  You do not need to choose the correct filter to be able to open a file type that is supported, simply choosing it from All Files has the same effect.
but nonetheless, still unable to view the files. I can not even export
## Post #53
- Username: saitek1911
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 09, 2012 5:26 am
- Post datetime: 2012-10-09T09:15:34+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

People here will probably be so mad at me for giving life in a dead thread, but i'v gotten so far that i'v been able to open the rpf files, all i can see is models and dat files.
I just really want to extract all the music from the game, i'v seen some post a bit behind that somebody extracted a few lines from the game

can anyone give me any idea on how to extract the music from the game? this would be of super help to me! i'v been wanting the complete thing for YEARS!

Thanks ALOT!
## Post #54
- Username: saitek1911
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 09, 2012 5:26 am
- Post datetime: 2012-10-09T18:06:41+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

bumb
## Post #55
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2013-05-14T10:27:13+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Would really like to see this revived. Some great work was done!

PS- Noesis "All files" never worked for me. I have to choose the specific type to see that file (eg Rsc0a). At work now but I remember in Noesis there is a way of live unpacking certain textures into multiple textures (bundled inside it) via a main menu dropbdown (you'll also see these if you export the texture). Note there is a tonne of duplicates most likely due to streaming requirements. Not all files work and models dont appear with their textures. I did export some terrain pieces into max but there's no vertex data or way of resetting up the original textures (for terrain). Didn't find any building textures.
## Post #56
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2013-09-25T10:53:10+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

[http://dfiles.eu/files/wvc2r7hxs](http://dfiles.eu/files/wvc2r7hxs)
The post is old but to see if someone can take a look at these files.
I wonder if anyone is able to extract texture files human characters (or zombies) RDR. With NOESIS plugnin of REVELATION to be extracted many 3d models and textures but the textures of the game's characters are packed into these files (XFD).
## Post #57
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2015-04-09T12:03:48+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

...
## Post #58
- Username: marked
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 17, 2015 11:37 pm
- Post datetime: 2015-08-14T19:58:20+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

bump -> XFD files
## Post #59
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2015-08-19T16:57:36+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Just been PM'd by someone here and it looks like there's some renewed interest. I'll give some feeback of my own experiences trying to do this a few years ago. When I last looked at this I managed to get some models (mainly props, some terrain, characters etc) and textures and sorted them into 50+ folders. 

Tools:

Noesis with Revelations RAGE plugin is needed.
You need to decompress / export the data before Noesis can read it (God2Iso/w360 etc)
Files should have the extension: RSCOA (textures)  rsc85  (models) rsc8A (terrain) - if you haven't got these you need to decompress further

Noesis(+Revelations) is a bugger to use. I found it's ability to open files really really temperamental and I think I had to manually point it to the file each time via File>Open. Browsing through the folder structure on the left sometimes worked. It tended to show either textures or models but I never saw a textured model in the viewer. I know Noesis is capable of this but the Revelations plugin didn't allow this (at least I couldn't get it to work)

90% of the models were duplicates. I spent many nights and hours going through god knows how many untextured low poly hat models. This is likely due to duplication of assets for efficient streaming. 

Tip: If you go into the Noesis menus there's a Data Viewer for the selected asset. It allows you (most of the time) to see what other textures are packed in with the current asset. For instance you might find the AO or normal map as well. You'll find these anyway when you export (which is what led me to finding the Data Viewer - I'd suddenly find a bunch of other stuff I hadn't exported). 

My laborious method:

1) search for all RSC0A etc files and copy them to a folder. Organize by biggest to smallest (click size tab in Explorer)
2) Right Click / Copy Path / Alt-Tab to Noesis / Open
3) Another hat!? Yay?... Repeat 1-3 Nay? Go to 4
4) Look at the Data viewer / Export
5) take it into 3dsmax and investigate it. (note models and textures stored separately. If you found a wolf texture and a wolf model then it's obvious what it's for but a lot of the time it isn't).
6) I'll have a look (wrote it down somewhere) but normal maps have the channels flipped and inverted (one of them). Likely R<>G and B- or similar.

Takeaways:

It's painful. This method allows you to export certain models but UV2 and vertex colors are missing. That means terrain is untextured and empty - like most processes like this you get individual assets and not scenes eg no bushes/shrubs/rocks/props. Since there's no UV2 the AO maps for whole towns can't be used and because buildings use tiling textures you'll have to go into the game and see what textures they used. Then you have to hope you can find those (it's literally easier looking for a needle in a haystack). To be honest it's easier to make your own versions of the assets (see my site). 

It would've been so awesome to have been able to get some tools like those available for GTA but I've kinda given up hope on that one. Back to working on my own game 


A bit of Inspiration for the new guys:

Probably the coolest thing I found was several assets for Coots Chapel which I put together in max:
## Post #60
- Username: reditec
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 28, 2015 11:08 pm
- Post datetime: 2015-10-28T15:50:04+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I opened the RPFs with a tool called RPFTool. I dound the key in the .xex file.
But I sometimes have random file names (looking like hashes). How to fix that?
## Post #61
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-18T01:25:07+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Well I know what I'm doing for the next .. 5 years
## Post #62
- Username: AviCG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 27, 2018 8:31 pm
- Post datetime: 2018-12-27T12:46:26+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Hello, 

I have been looking everywhere for the Arthur Morgan model from Red Dead Redemption 2, Would it be at all possible for you to extract it from the game for me? I understand that it is the second Red Dead redemption game and not the first, but I hope that you can help me all the same, or maybe suggest someone who could? 

Thank you for your time, 

Avi
## Post #63
- Username: GuiCORLEONE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 29, 2020 9:05 am
- Post datetime: 2020-11-30T01:15:30+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from pixeldamage ↑Tue May 14, 2013 6:27 pm at Tue May 14, 2013 6:27 pm
>
> 
Would really like to see this revived. Some great work was done!

PS- Noesis "All files" never worked for me. I have to choose the specific type to see that file (eg Rsc0a). At work now but I remember in Noesis there is a way of live unpacking certain textures into multiple textures (bundled inside it) via a main menu dropbdown (you'll also see these if you export the texture). Note there is a tonne of duplicates most likely due to streaming requirements. Not all files work and models dont appear with their textures. I did export some terrain pieces into max but there's no vertex data or way of resetting up the original textures (for terrain). Didn't find any building textures.

I know this is a old topic but, how do i get ped textures? Textures for Bill, Jack, Javier etc...
I got models and some random textures like icons etc but still no textures for peds. Thanks in advance.
## Post #64
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-06-03T12:38:49+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Does anyone know structure for rpf8 rdr2 (ps4 or pc)?
Thanks
## Post #65
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-11-27T01:29:56+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

Well, 11 years since the publication of the plugin for Noesis. A few days ago I started writing a tool that will convert RDR models to GTA IV openFormat. So far, I've only explored the shader sections and the model sections from the XVD file. Unfortunately, I did not figure out where the UV coordinates are in the file, so now it is possible to export without UV coordinates. Everything else works fine, it exports shaders, correctly exports each model separately from xvd to odd file. I think when there is progress with uv channels, I will be able to publish the tool here.

Several screenshots with RDR models in 3ds max imported by OFIO



and with shaders
## Post #66
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-11-27T12:12:47+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

@d3g0n, really cool to see the progress! Do you have something released? I'm interested in textures for characters and objects. Because since 11 years they were never converted by anyone.
## Post #67
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-11-27T17:19:28+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from Tosyk ↑Sun Nov 27, 2022 8:12 pm at Sun Nov 27, 2022 8:12 pm
>
> 
@d3g0n, really cool to see the progress! Do you have something released? I'm interested in textures for characters and objects. Because since 11 years they were never converted by anyone.
instrument is very raw. I'm stuck in place due to the missing uv channel or I just don't understand where it is. I studied the files after the conversion to fbx (converted by the plugin), but I could not link the uv coordinates to the original xvd file. Also today I received Chipsman's work in the form of four odr files that he converted from rdr to gta iv, but this did not help me either. The tool can unpack version 133(xvd) files, but it ignores the skeleton section.
In the future, I also plan to add support for other formats, but first I need to finish the xvd file converter.
As for the shaders, I need to create a ShaderManager, which will contain information about all shaders, because in the model files the shader parameters are sorted by type (texture, float4, etc.)
## Post #68
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-11-28T07:23:24+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from d3g0n ↑Mon Nov 28, 2022 1:19 am at Mon Nov 28, 2022 1:19 am
>
> 
Tosyk wrote: ↑Sun Nov 27, 2022 8:12 pm
@d3g0n, really cool to see the progress! Do you have something released? I'm interested in textures for characters and objects. Because since 11 years they were never converted by anyone.

instrument is very raw. I'm stuck in place due to the missing uv channel or I just don't understand where it is. I studied the files after the conversion to fbx (converted by the plugin), but I could not link the uv coordinates to the original xvd file. Also today I received Chipsman's work in the form of four odr files that he converted from rdr to gta iv, but this did not help me either. The tool can unpack version 133(xvd) files, but it ignores the skeleton section.
In the future, I also plan to add support for other formats, but first I need to finish the xvd file converter.
As for the shaders, I need to create a ShaderManager, which will contain information about all shaders, because in the model files the shader parameters are sorted by type (texture, float4, etc.)
it seems you dive deep into the reversing. I once asked for the source of noesis plugin but didn't get the response. Maybe you will be more lucky with your actual work and screens
## Post #69
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-12-02T14:27:08+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I updated the tool and added support for diffuse(aka vertex color), specular and all uv channels. Before publishing this tool, I also need to add bone support (if it is in the resource) and add all shaders to my ShaderManager
## Post #70
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-12-02T19:39:22+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from d3g0n ↑Fri Dec 02, 2022 10:27 pm at Fri Dec 02, 2022 10:27 pm
>
> 
I updated the tool and added support for diffuse(aka vertex color), specular and all uv channels. Before publishing this tool, I also need to add bone support (if it is in the resource) and add all shaders to my ShaderManageroh you actually had the source of noesis plugin? great!
## Post #71
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-12-03T19:01:59+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from Tosyk ↑Sat Dec 03, 2022 3:39 am at Sat Dec 03, 2022 3:39 am
>
> 
d3g0n wrote: ↑Fri Dec 02, 2022 10:27 pm
I updated the tool and added support for diffuse(aka vertex color), specular and all uv channels. Before publishing this tool, I also need to add bone support (if it is in the resource) and add all shaders to my ShaderManager
oh you actually had the source of noesis plugin? great!
Unfortunately, I didn't have the source for the Noesis plugin. I relied on my old experience with the IV and Max Payne 3 models.
I tried to find the source of the plugin to improve it, but all attempts were not successful
## Post #72
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-12-05T20:20:57+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

I added support for xft and xfd, also I added bone export and skinned mesh. I want to test the tool on different files before publishing to avoid bugs in the public version, so if someone has the desire and free time to help me, write to me in Discord <ḏ̵̉3̶̾̕g̶̾́0̷̾̓ṉ̵̂#8929>. If you speak RU/UA, write right away.
## Post #73
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-12-06T08:20:42+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from d3g0n ↑Tue Dec 06, 2022 4:20 am at Tue Dec 06, 2022 4:20 am
>
> 
I added support for xft and xfd, also I added bone export and skinned mesh. I want to test the tool on different files before publishing to avoid bugs in the public version, so if someone has the desire and free time to help me, write to me in Discord "ḏ̵̉3̶̾̕g̶̾́0̷̾̓ṉ̵̂#8929". If you speak RU/UA, write right away.I would like to test it out but I can't find you in discord
## Post #74
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-12-06T14:26:20+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from Tosyk ↑Tue Dec 06, 2022 4:20 pm at Tue Dec 06, 2022 4:20 pm
>
> 
d3g0n wrote: ↑Tue Dec 06, 2022 4:20 am
I added support for xft and xfd, also I added bone export and skinned mesh. I want to test the tool on different files before publishing to avoid bugs in the public version, so if someone has the desire and free time to help me, write to me in Discord "ḏ̵̉3̶̾̕g̶̾́0̷̾̓ṉ̵̂#8929". If you speak RU/UA, write right away.
I would like to test it out but I can't find you in discord

d3g0n#8929
## Post #75
- Username: d3g0n
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 27, 2022 8:53 am
- Post datetime: 2022-12-09T09:31:44+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

download the converter here
[https://gtaforums.com/topic/987186-relw ... converter/](https://gtaforums.com/topic/987186-relwiprdrred-dead-redemption-model-converter/)
## Post #76
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-12-23T20:13:05+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from d3g0n ↑Sun Nov 27, 2022 9:29 am at Sun Nov 27, 2022 9:29 am
>
> 
Well, 11 years since the publication of the plugin for Noesis. A few days ago I started writing a tool that will convert RDR models to GTA IV openFormat. So far, I've only explored the shader sections and the model sections from the XVD file. Unfortunately, I did not figure out where the UV coordinates are in the file, so now it is possible to export without UV coordinates. Everything else works fine, it exports shaders, correctly exports each model separately from xvd to odd file. I think when there is progress with uv channels, I will be able to publish the tool here.

Several screenshots with RDR models in 3ds max imported by OFIO



and with shaders

Is this from the PS3 version or Xbox 360? I don't know how to open the rpf file from the PS3 version and I saw somebody rip models from RDR1 PS3 and upload them to Deviantart like so:

[https://www.deviantart.com/heliosal/art ... -887249548](https://www.deviantart.com/heliosal/art/Red-Dead-Redemption-Bonnie-MacFarlane-887249548)
## Post #77
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-12-23T20:24:09+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

> Reply from d3g0n ↑Tue Dec 06, 2022 10:26 pm at Tue Dec 06, 2022 10:26 pm
>
> 
Tosyk wrote: ↑Tue Dec 06, 2022 4:20 pm
d3g0n wrote: ↑Tue Dec 06, 2022 4:20 am
I added support for xft and xfd, also I added bone export and skinned mesh. I want to test the tool on different files before publishing to avoid bugs in the public version, so if someone has the desire and free time to help me, write to me in Discord "ḏ̵̉3̶̾̕g̶̾́0̷̾̓ṉ̵̂#8929". If you speak RU/UA, write right away.
I would like to test it out but I can't find you in discord 


d3g0n#8929

hello I sent you a friend request on discord, I need some help with this. Thank you!
## Post #78
- Username: justuser
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 23, 2021 3:25 am
- Post datetime: 2023-04-25T19:08:36+00:00
- Post Title: Re: Red Dead Redemption .rpf converter/extractor

How to open RDR1 rpf? I got rdrexplorer, but its always show a window with "access denied" and programm closes. Can anyone help?
