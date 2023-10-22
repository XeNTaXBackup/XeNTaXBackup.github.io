## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-09T01:01:31+00:00
- Post Title: Esoteria: a game no one has ever heard of

I plan to resurrect this game, but I need access to the archive.
Could someone help me out?

Here is the file archive:
[http://home.1asphost.com/bitterbanana/segs.22k](http://home.1asphost.com/bitterbanana/segs.22k)

Thanks in advance.
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-09T01:03:45+00:00
- Post Title: Esoteria: a game no one has ever heard of

Ok, just registered.    Thanks in advance again.
## Post #3
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-09T03:32:53+00:00
- Post Title: Esoteria: a game no one has ever heard of

I'm willing to pay money for someone to figure this out...
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-09T06:55:00+00:00
- Post Title: Esoteria: a game no one has ever heard of

We'll have a look a it. At no cost. The next release of MultiEx Commander will offer more functionality if you donate once (whatever amount), but for now, taking a look is free of charge.  

[EDIT]

```
Get FNum Long 0 ;
Math FNum -= 1 ;
For T = 1 to FNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos ST 0 ;
Get FS Long 0 ;
Math FS -= FO ;
Log "" FO FS FOO 0 ;
GoTo ST 0 ;
Next T ;

```


That's the MexScriptor script for the format. You can use MexBinder to create the 22k.bms file (start the scriptor) that you must import (using MexBinder) into your MC.MRF file in the data/config directory of MultiEx Commander. Just open the MC.MRF and select Add Single Format, point to the 22k.bms file and give the name of the game. Then save the new mc.mrf.
## Post #5
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-09T13:26:30+00:00
- Post Title: Esoteria: a game no one has ever heard of

oh thanks alot, I'll be sure to donate soon. I promise
## Post #6
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-09T23:36:02+00:00
- Post Title: Esoteria: a game no one has ever heard of

I can't get it working.  It gives me a runtime error 9 (subscript out of range). I copy and pasted your code into the scriptor and tried to save it but that error popped up.  Could you help me please?
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T02:54:08+00:00
- Post Title: Esoteria: a game no one has ever heard of

Hi mate,

I managed to get it compiled eventually, and have attached it here (22k.zip). 

1. Unzip the file, then load up the MexBinder program.
2. Click the "Open MRF" button and choose the file called mc.mrf
3. Click the "Add Single Format" button and choose the file you unzipped
4. Type the game name
5. Click the "Create MRF" button and choose the mc.mrf file

Hopefully that should be ready to go - so load up MultiEx Commander and test it out.

Also, just in case you need or want it, I have attached a Game Extractor plugin that will open the archives (Plugin_22K_CGDS.zip) - you can get Game Extractor from [http://www.watto.org/extract](http://www.watto.org/extract) . Just unzip the plugin into the plugins/ directory, run Game Extractor, and open the archive.

Good Luck!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[22k.zip](https://xentaxbackup.github.io/file/115_22k.zip)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T02:57:04+00:00
- Post Title: Esoteria: a game no one has ever heard of

Hmm, it appears as though you can only attach one file to a post, so here is the Game Extractor plugin.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_22K_CGDS.zip](https://xentaxbackup.github.io/file/116_Plugin_22K_CGDS.zip)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-10T08:20:37+00:00
- Post Title: Esoteria: a game no one has ever heard of

Well, I perhaps should have told you that when you copy paste Windows adds some extra spaces at the end of each line. Each line should end with a semi-colon ';' and not have trailing spaces. Then it will compile right.

Anyway, here's the ready-made mc.mrf:
[mc.mrf](https://xentaxbackup.github.io/file/120_mc.mrf)
## Post #10
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-11T01:15:44+00:00
- Post Title: Esoteria: a game no one has ever heard of

thank you friendsofwatto and Mr.Mouse

It worked and now I can view the archive file.  But I have one problem.  All the files are unnamed without any description of a filetype.  Is this normal?

The files in the archive should have .e3 extensions for some of the game sprites, I think.  Raven.e3 is one of them.

Also, my java doesn't work anymore.  It gives me blank windows all the time.  I've reinstalled it countless times, new and old versions.  So I can't use Game Extractor.  (I'm on XP)

You guys have helped me more than I expected you would.  Thank you very much for taking the time.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-11T06:24:36+00:00
- Post Title: Esoteria: a game no one has ever heard of

Well, we did not find any information in the archive about filenames of the files that were stored. Basically it's just a list of files without names. It may be possible however that the authors stored another file with the names in. Look for a file that has the same name as the archive, but with a different extension, or perhaps even another bigger file that has all filenames in all archives stored.
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-11T11:08:43+00:00
- Post Title: Esoteria: a game no one has ever heard of

Hey,

Um yeah, there are no filenames with this format - unless there is a separate file of filenames like Mr Mouse said. Otherwise, you'll just have to open each file until you find the right one.

As for the Java problem, I'm not sure why it is giving you those problems. Take a look at the help and installation pages at [http://www.watto.org/extract](http://www.watto.org/extract) to see if you can fix the problem. Alternately, install Game Extractor, run it, and close it. Go to the logs/ directory and if there are any files in there, email the last few to me and I will try to fix the issue.

Thanks mate, and good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-11T22:54:08+00:00
- Post Title: Esoteria: a game no one has ever heard of

I think these are the lists of the names separated into different files.
The segs.22k that I gave you a couple days ago is actually a smaller file from an old demo.  The newer 22k file is about 23mb. But the new one is the same format, so I'm hoping that doesn't matter.

Here is one of the files.  I tried to zip all of them and attach it but I got an upload error.  This is the file that contains the sprites names I think.

(Is this stuff hard to learn.  Should I be doing this myself?)

If you guys want the demo with all the files in it, here it is.  In this version of the demo, it has a segs.22k and a data.z file.
[http://downloads.pcworld.com/pub/new/fu ... stdemo.zip](http://downloads.pcworld.com/pub/new/fun_and_games/action/estdemo.zip)

Many thanks
[SPRITES.zip](https://xentaxbackup.github.io/file/127_SPRITES.zip)
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-12T11:24:01+00:00
- Post Title: Esoteria: a game no one has ever heard of

Well here is the structure of the e3 format you attached - I am not sure whether they actually relate to the filenames in the other archives though. Do you know how many files are in the sprites archive? If there are 7, then we have the right filenames, otherwise these files do something else.

Anyway, here are the specs for the e3 files...

```
| Esoteria *.e3 |
+---------------+

// NOTE:
// if filenameLength or typeNameLength = 99, then the name field is
// 4 bytes long and is all nulls

7 - Header (ESv1.0 )
4 - Number Of Files

// for each file
  64 - Filename (null)
  4 - Offset
  4 - Length

// for each file
  7 - Header (ESv1.0 )
  1 - Unknown
  4 - null
  4 - Type Name Length (including 1 null)
  X - Type Name
  1 - null
  4 - Filename Length (including 1 null)
  X - Filename
  1 - null
  18 - null
  4 - Unknown
  12 - null
  4 - Unknown
  4 - Unknown
  12 - null
  4 - Unknown
  2 - Unknown
```


Yeah, I didn't worry about the unknowns too much, basically just wanted to outline the file structure.

I may try to get the demo if it isn't too big - it may help to link the files together better.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-12T19:53:55+00:00
- Post Title: Esoteria: a game no one has ever heard of

Thanks for taking a look at it Watto.  

I'm a bit lost, but I know it's an outline of how the data is allocated in the file. I'm not completely helpless, so is there something I can read to understand the code you just gave me? I really want to start helping myself, rather than bug you guys.  I just joined the "game-hacking" community so I have no experience in this type of thing.  I can hex-edit and concurrently debug a game, but nothing with files yet.

The demo is 12 mb. If you want to play the game to test out anything, you'll have to go to start, run, dxdiag.  Under display, disable the accelerations.

Thank you very much.

EDIT:
I just remembered the definitive guide you released, so I'll check that out.
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-13T12:31:24+00:00
- Post Title: 

Ok, I downloaded the demo and have figured it all out - dead easy with the Bitmaps archive!

Here is the format...

```
| Esoteria *.e3 |
+---------------+

7 - Header (ESv1.0 )
1 - Sub-type ((byte)96 or (byte)97 or (byte)99 or (byte)104 or (byte)105)
4 - Number Of Files

// for each file
  64 - Filename (null)
  4 - Offset
  4 - Length
```


and here is a MexCom script...

```
GoTo 8 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
SavePos JP 0 ;
Math JP += 64;
Get FN String 0 ;
GoTo JP 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS FOO FSO ;
Next n ;
```


and finally, I have attached a compiled MexCom script for opening the e3 files.

The e3 files are separate archives - they have no relation to the 22k archives at all. My guess is that the 22k archive is just the audio, and the e3 archives contain the other information.

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[e3.zip](https://xentaxbackup.github.io/file/129_e3.zip)
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-14T08:06:29+00:00
- Post Title: 

Back from a weekend in Paris to visit some close friends and have a laugh after only a 7-hour drive. 

And lo and behold two scripts ready to add to the next release! Great work!
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-14T09:18:50+00:00
- Post Title: 

yeah, I noticed you were away for a few days - hope you had a good time!  It must be nice for you to finally have other people writing scripts for your program - I know its usually hard to get people to help with things like that.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-14T10:29:36+00:00
- Post Title: 

> Reply from friendsofwatto
>
>  yeah, I noticed you were away for a few days - hope you had a good time!  It must be nice for you to finally have other people writing scripts for your program - I know its usually hard to get people to help with things like that.

WATTO
watto@watto.org
http://www.watto.org

Yes, it's very cool! I love teamwork ! 

Anyway, here's the new mc.mrf with that E3 script. The importation also works! 

Note that you will have to put it in the data/config dir of MexCom. 

Also, due to a bug in MexCom (that's fixed already for the next release) you may have trouble finding the .e3 file of your choice after selecting Open Archive in MexCom. Just type *.* on the filename line and you will see all files. Then you can just point to the .e3 file and open it with the right script selected (i.e. Esoteria .e3) !
[mc.mrf](https://xentaxbackup.github.io/file/132_mc.mrf)
## Post #20
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2005-02-14T12:13:15+00:00
- Post Title: 

*freaks out*
I'm in a total state of ecstatic shock right now.  I love you guys so much.
Once I get my job this summer, you're getting half my paycheck. Seriously.

The bitmaps extracted! They're upside down and inverted, but that's easily fixed.

Oh no, the sprites!  Can I ask one last favor?  I can't figure out how to open up the sprites.  Well they showed up, and I extracted the e3 files and tried to open them, but no avail.  This is the main thing that I want and I feel that I am so close. And by "I", I mean you. haha.

Is there also a way to rebuild the archive?

I need to calm down or my head'll explode.  Thank you very much.  I never thought I'd live to see the day.
## Post #21
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-14T13:09:05+00:00
- Post Title: 

We are both glad to help.

1. Yes, the Bitmaps are upside-down. The BMP format stores the image upside down, and the image editing/viewing program needs to turn it up right right way. The reason why the Bitmaps in this game are the wrong way is because the game developers did not strictly follow the standards. Luckily though, they are easy to fix, just open an image editing program and flip the image.

2. 
> Once I get my job this summer, you're getting half my paycheck. Seriously. Thanks mate - its greatly appreciated  - If you want to donate to Mr Mouse I think he has a button somewhere on the MultiEx website ( [https://sourceforge.net/donate/index.php?group_id=91699](https://sourceforge.net/donate/index.php?group_id=91699) ). If you want to donate to me, you can do it at my website ( [http://www.watto.org/extract/donate.html](http://www.watto.org/extract/donate.html) ).

3. The only thing in the Sprites.e3 file is a bunch of other e3 files. I will see if I can adjust the script to open these too, but I don't think they had much content. They certainly didn't have any images, if thats what you had hoped for.

4. Yes, the archive can be re-built. Using MultiEx Commander, there should be a button somewhere that lets you replace the files in the archive with files on your computer. If you need to be able to build these archives from scratch, I don't think you can use MultiEx Commander, but Game Extractor will do the job. When/If you end up donating to me via the link I gave above, you will also be able to download the full version of Game Extractor - hopefully it will work better than the free version.

Thats all mate - I'll see what can be done about the sprite files.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-15T11:08:43+00:00
- Post Title: 

I put all of the current scripts in on e file, see the sticky thread in the Game Request forum!
## Post #23
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-15T11:37:29+00:00
- Post Title: 

OK, well here is the format for the internal e3 files...

```
| Esoteria *.e3 (Internal Type) |
+-------------------------------+

7 - Header (ESv1.0 )
1 - Sub-type ((byte)48 or (byte)83 or (byte)84 or (byte)94)
4 - null

4 - Type Name Length (including null)
// NOTE: THE FOLLOWING 2 FIELDS DON'T APPEAR IF TypeNameLength=99
X - Type Name
1 - null

4 - null

4 - Filename Length (sometimes including null)
X - Filename (null) (without extension)

18 - null

X - File Data
```


I'm not sure how to write a script for this, mostly because of the comparison line and stuff like that, so I will leave it for Mr Mouse to do (please ). The main thing the script will need to do is check the 3rd field - if it has a number then it is the original format - if it is null then it is the format shown here.

Thats all guys.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #24
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-15T22:55:25+00:00
- Post Title: 

well, I checked out the file called PKDTEXTS.e3 - my guess is that it means player textures (the sprites that I want)

I tried swapping files in the sprites.e3, but that didn't accomplish anything, so I think you should ignore that file.

I tried swapping files in the pkdtexts.e3 and the enemies stopped showing up.  I think that's where the sprites are located.

thanks for still showing interest watto and mouse.
