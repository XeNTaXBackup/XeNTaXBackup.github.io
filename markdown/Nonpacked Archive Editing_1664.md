## Post #1
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2006-01-04T19:06:29+00:00
- Post Title: Nonpacked Archive Editing

anyone know of a wav ripper which saves each file like file_offset.wav and can put them back in the position they where taken?

Or has someone an idea how to make it?

It could be a nice temp tool for ppl waiting for archive being openable...
Offcourse this would only work with archives without compression.
## Post #2
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2006-01-04T19:27:46+00:00
- Post Title: Nonpacked Archive Editing

Or just an wav/ogg/mp3 ripper which saves the offset in filenames
that way u can always put it back where it belongs..
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T21:43:20+00:00
- Post Title: Nonpacked Archive Editing

The main complication that prevents us from doing this, is that if you change the size of one file, it could potentially stop the game from working.

Most archives have some kind of directory that tells the offset to the file, and the file length. If we replace a file with one of exactly the same size - no problem. If the size is larger or smaller, we can replace the file but the other files in the archive won't work, stopping the game from working. This is because the directory needs to be changed so that it contains the new file lengths and offsets, and working out the directory is one of the hardest things that we have to do.

Basically what you want is not really possible, unless we come up with some amazing program that can alter the directory automatically without knowing anything about the directory at all. If this could happen, there wouldn't be any need for people like Mr Mouse and I, because a program can do it all for us 

Sorry mate - its a great idea but it just isn't possible.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T22:11:38+00:00
- Post Title: Nonpacked Archive Editing

Well, what could be done is to have a program like that replace files, but keep the size of the file intact. So only smaller files or files equal in size could be used, but that's for the user to fix. 

I once created a tool that would do just that for Doom WAD files (LOOONG TIME AGO!!!). 

I ripped the original sounds, altered them (making sure they were of same size) and then put them back.
## Post #5
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-04T23:03:29+00:00
- Post Title: Nonpacked Archive Editing

I had something in my code archive that should do what you want.
It's up on [my site](http://www.turfster.be) (Generic file ripper and re-injector).
I haven't looked at the code for ages, so if it doesn't work the way it should, drop me a line.
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-05T20:04:20+00:00
- Post Title: Nonpacked Archive Editing

Im' trying your reinjector..but maybe it's too experimental.

I'm trying to reinject the data audio from War of the ring (H2O format)

The extraction it's ok and creates a .log file.

I created a empty dummy file (Dialogue.H2O) only with the header using hex workshop, and filling the body of that with 0's. The file size it's 57mb's aprox.

I do the nexts steps:
I open the program and go to MAIN.
Open the log file.
Shows: 42 injection points found.
Go to Reinjector and select any ogg file and shows the:
"File not found in table."

Maybe i'm using wrong the program. Any idea? Thanks!!!
## Post #7
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-05T21:22:16+00:00
- Post Title: Nonpacked Archive Editing

The file needs to have the same name and size as the reinjected one, including position({filename}[8 digit hexvalue].ext).
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-05T21:54:53+00:00
- Post Title: Nonpacked Archive Editing

The file as the same filesize and file name, can you have a look a this zip?
Unpacked it's 55 mb's
[warring.rar](https://xentaxbackup.github.io/file/561_warring.rar)
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T22:31:49+00:00
- Post Title: Nonpacked Archive Editing

2pulposo -  How for you it did be possible to press file with weight 50 into one small RAR?
## Post #10
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T01:29:41+00:00
- Post Title: Nonpacked Archive Editing

> Reply from KorNet
>
> 2pulposo -  How for you it did be possible to press file with weight 50 into one small RAR?
It's a file containing zeroes, so it compresses well 

I've upped a new version (1.6) to the site which should fix the problems with the previous version (unless I missed something, that is. The code is a real mess  and it's rather late ). You'll have to delete the old log file and rerun an extraction on it, but it *should* work now.
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T11:02:35+00:00
- Post Title: Nonpacked Archive Editing

I'm trying the 1.6...but all time it's 

"access violation at adress xxx.xxxx.xxx" "Read of adress fffffff"



@Kornet, i replaced all data with 0's, except the header, of course the compression it's superb
## Post #12
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T11:29:48+00:00
- Post Title: Nonpacked Archive Editing

> Reply from pulposo
>
> I'm trying the 1.6...but all time it's 

"access violation at adress xxx.xxxx.xxx" "Read of adress fffffff"
Weird, it works fine here for every file I tried it on.
When exactly did you get the error?
I've upped a [new build](http://www.turfster.be/FileRipper.rar) with a few more bugs fixed and a different way of handling the log files. I hope that fixes it.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T11:42:14+00:00
- Post Title: Nonpacked Archive Editing

Still with errors, now less errors, but when i open a file appears the error:

And can't do nothing.   

Step2step:
-Run the program
-Go to MAIN>OPEN>select the file to open
ERROR.

My system it's Win Xp pro sp2
## Post #14
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T12:49:59+00:00
- Post Title: Nonpacked Archive Editing

Huh, weird, I can't reproduce it on any of my PCs...
OK, I fixed just about the only thing it could be (selecting fixed dir without actually specifying a directory in the options) and made it a little more verbose.
Try the [new build](http://www.turfster.be/FileRipper.rar). If it still gives access violations, I have no idea why.
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T14:33:03+00:00
- Post Title: Nonpacked Archive Editing

Okai, now extracts perfect, but i have a new error xD.
"File size does not match log file size or not a File Stripper log file"
The file it's the same of the example: 59227545 bytes

Any idea?
## Post #16
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-01-06T15:12:41+00:00
- Post Title: 

tried on a .naz videos files of 'total overdose' worked fine..at least no crash as above post.
## Post #17
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T16:10:46+00:00
- Post Title: 

> Reply from pulposo
>
> Okai, now extracts perfect, but i have a new error xD.
"File size does not match log file size or not a File Stripper log file"
The file it's the same of the example: 59227545 bytes
Any idea?
Uh... you didn't delete the old log file before trying the new build?
The log files for the current version for that file should look something like this (only with more lines, obviously):

```
0000DFB0.ogg|33989

```
## Post #18
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T17:26:51+00:00
- Post Title: 

I maked the unpack new again, another test with this file and the result it's the same.


Here the log created with your new version:

The data file you know it's attached in another post with a ogg sample.

Thanks
[warring.rar](https://xentaxbackup.github.io/file/563_warring.rar)
## Post #19
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T17:57:21+00:00
- Post Title: 

The attached rar contains an *old* log file.

```

```

Re-rip the file to create a new one, which should look like the bit I pasted in my previous post.
## Post #20
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T18:59:00+00:00
- Post Title: 

I can't!
I re-ripped the file again from 0. In a new directory and with last file ripper executable.

The log it's the same of attached before.
I'm using the file ripper 06/01/2005 13:48

Here it's the NEW log created from your fileripper
[Dialogue.rar](https://xentaxbackup.github.io/file/565_Dialogue.rar)
## Post #21
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T19:26:58+00:00
- Post Title: 

OK, this log *should* work (it works here).
Don't forget you need to open dialog.h2o again (not the log like in your screenshot).
[screenie.jpg](https://xentaxbackup.github.io/file/567_screenie.jpg)
## Post #22
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T19:36:32+00:00
- Post Title: 

Right...looks work actually...another thing..sorry...any way to add multiple files? 1000 files one to one....

Or a script?
## Post #23
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-06T19:53:22+00:00
- Post Title: 

I'll add some multiple file selection stuff this weekend if I find the time.
## Post #24
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-06T20:10:29+00:00
- Post Title: 

I tried with the music of War of the ring, the people knows this game have a h2O format, and i don't ofund a packer for this format.

I unpacked the music  and created a dummy/semi-empty file with only the header and addedd the 72 files -one by one-

I ran the game..and...ohhhhh!!  the game have music!! Really great!!!

Other test, the video files:

8 files detected, only 1 extracted, it's a bik video.

Many thanks!!!!!!!!!!
## Post #25
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-08T17:23:05+00:00
- Post Title: 

OK, the new version (2.0) is [up](http://www.turfster.be) now.
Now supports reinjecting multiple files at once.
## Post #26
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-08T23:37:39+00:00
- Post Title: 

Thanks again it works great!!!
## Post #27
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2006-01-09T15:53:02+00:00
- Post Title: 

any chance for some commandline?.. i mean so i could write a batfile to do it automaticly.. so i dont have to repeat each time i edit some data
## Post #28
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-09T16:45:51+00:00
- Post Title: 

Good work pulposo
## Post #29
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-09T18:10:18+00:00
- Post Title: 

> Reply from nikita
>
> any chance for some commandline?.. i mean so i could write a batfile to do it automaticly.. so i dont have to repeat each time i edit some data
I'll try to add command line stuff one of these days.
Depends on how much work I have this week.
## Post #30
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-01-09T18:28:46+00:00
- Post Title: 

"Good work pulposo"

Me? It's a Turfster work.
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-09T18:56:48+00:00
- Post Title: 

Nice stuff, Turfster!  

You should add your progs to the WIKI! 

The Fileripper would go nicely here, I think?

[http://wiki.xentax.com/index.php/Extraction_tools](http://wiki.xentax.com/index.php/Extraction_tools)
## Post #32
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-01-09T20:38:47+00:00
- Post Title: 

Done.
## Post #33
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-09T20:53:04+00:00
- Post Title: 

Cool
