## Post #1
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2016-07-01T16:14:09+00:00
- Post Title: Mad Max - Unpacking and Packing

There's probably no one interested in the game anymore, but i'm starting that thread anyways.

I've wrote an Unpakke module that support both packing and unpacking for the .TAB and the SARC files (BL, CL, EE, FL and NL)

There's one pitfall, tho:

Some of the original archives (.TAB) has header section that I wasn't able to completely reverse engineer. Repacking these files will crash your game.
However, you can still build your own patches or DLC's so, that's at least something...

As most of you probably already know, the game uses checksum based file naming.
I was able to fish out ~45000 out of ~50000 file names with their complete file pathes, so you can *theoretically* unpack the whole game and play it without using the .TAB/.ARC files (didn't test it completely).

Lastly, i didn't checked if anyone in here already built such tool, so if this thread repeats another one, you can just delete it.

Overall, that's all.

You can find Unpakke and the Mad Max module here: [http://www.nullsecurity.org/unpakke](http://www.nullsecurity.org/unpakke)
Just make sure you read the readmies provided before asking questions.

And now, here's some stupid screenshots.
## Post #2
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2016-07-24T22:10:12+00:00
- Post Title: Mad Max - Unpacking and Packing

Is it possible to translate this game with your unpakke module?
## Post #3
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2016-08-03T09:11:49+00:00
- Post Title: Mad Max - Unpacking and Packing

> Reply from desperado
>
> Is it possible to translate this game with your unpakke module?
It's possible to unpack and pack back the files. Still, you will have to figure out the texts format by yourself.
## Post #4
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2016-08-15T13:51:20+00:00
- Post Title: Mad Max - Unpacking and Packing

I'm extacting stuff of game0.arc & game0.tab in patch_win64 path to a folder named game0, than when i moved extracted files to patch_win64 path game doesn't work correctly.  What should i do?

Also you said like that when i repack game0.arc & game0.tab size is decreases and game crashing.
## Post #5
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2016-08-21T20:22:53+00:00
- Post Title: Mad Max - Unpacking and Packing

> Reply from desperado
>
> I'm extacting stuff of game0.arc & game0.tab in patch_win64 path to a folder named game0, than when i moved extracted files to patch_win64 path game doesn't work correctly.  What should i do?

Also you said like that when i repack game0.arc & game0.tab size is decreases and game crashing.
Move the content of game0 directly to the "Mad Max" folder.
## Post #6
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2016-08-21T22:43:27+00:00
- Post Title: Mad Max - Unpacking and Packing

> Reply from XpoZed
>
> desperado wrote:I'm extacting stuff of game0.arc & game0.tab in patch_win64 path to a folder named game0, than when i moved extracted files to patch_win64 path game doesn't work correctly.  What should i do?

Also you said like that when i repack game0.arc & game0.tab size is decreases and game crashing.
Move the content of game0 directly to the "Mad Max" folder.

Can you fix this repacking thing if you try?

It still doesn't work correctly, i didn't figure it out 

Can you make a briefing and write your way to do that like step 1, step 2, step 3 ?
## Post #7
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-28T23:56:59+00:00
- Post Title: Mad Max - Unpacking and Packing

Sorry to sound stupid if I do, but I'm sort of getting my head around all this... I've managed to unpack the .tab/.arc files and have been given .bins. What should I be doing to open up these? Really keen to get my hands on the models and have a look through what's in there!
## Post #8
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2017-03-22T17:04:46+00:00
- Post Title: Mad Max - Unpacking and Packing

> Reply from XpoZed
>
> desperado wrote:Is it possible to translate this game with your unpakke module?
It's possible to unpack and pack back the files. Still, you will have to figure out the texts format by yourself.

Can you help me with packaging Archives game???
## Post #9
- Username: CheekySparrow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 03, 2018 7:41 pm
- Post datetime: 2018-05-03T11:46:36+00:00
- Post Title: Mad Max - Unpacking and Packing

Hello XpoZed and thanks for this great tool. I'm trying to unpack the Mad Max files and Unpakke creates proper folder and file structure, however if I open any of the files in notepad++, all files are full of "NULLs". Am I doing something wrong? I put the Mad Max module (avalanche.umod and other files) inside the modules folder, updated the ini file, and also put ZLIB1.DLL inside libs folder.
## Post #10
- Username: Centics
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 02, 2021 11:27 am
- Post datetime: 2021-06-02T23:48:44+00:00
- Post Title: Mad Max - Unpacking and Packing

> Reply from trexjones ↑Mon Aug 29, 2016 7:56 am at Mon Aug 29, 2016 7:56 am
>
> 
Sorry to sound stupid if I do, but I'm sort of getting my head around all this... I've managed to unpack the .tab/.arc files and have been given .bins. What should I be doing to open up these? Really keen to get my hands on the models and have a look through what's in there!

hi, did you ever find out how to open the .bins? i also want to have the models but i don't know how to open the .bins
## Post #11
- Username: JohnBarleycorn
- Rank: n00b
- Number of posts: 11
- Joined date: Sat May 30, 2015 12:42 am
- Post datetime: 2021-06-29T16:50:26+00:00
- Post Title: Mad Max - Unpacking and Packing

Indeed. What is the point of all this? In the end bin files either you have the proper decoding, or they're pretty useless.
