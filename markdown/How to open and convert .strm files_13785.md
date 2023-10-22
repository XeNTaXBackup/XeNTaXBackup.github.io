## Post #1
- Username: tiramisu6
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 10, 2016 11:31 pm
- Post datetime: 2016-01-10T16:46:40+00:00
- Post Title: How to open and convert .strm files

I need to open/extract audio in .strm files from these specific games made by Electronic Arts for Wii.

Importing a raw .strm file into Adobe Audition CC results in this:
[http://www.mediafire.com/listen/w0mx2pg ... 1.strm.mp3](http://www.mediafire.com/listen/w0mx2pgk2x6x5xa/strm_mu_djbooth_d01_01.strm.mp3)

If you listen closely to the music in this file, it's supposed to sound something like this:
[http://www.mediafire.com/listen/u3hhf5x ... review.mp3](http://www.mediafire.com/listen/u3hhf5xumxjj95a/preview.mp3)

Now, here's the original .strm file ripped from the games files:
[http://www.mediafire.com/download/k2ce5 ... h_d01.strm](http://www.mediafire.com/download/k2ce5tr0i1gui97/strm_mu_djbooth_d01.strm)

There was a very similar question on this forum, but the user suddenly claimed to have found a program that converted the .strm files into .wave files in "crystal clear quality" ... but didn't mention the name of the program. That topic was posted a few years ago.
Can someone just please help me out here? There's even topics on converting .wav to .strm but nobody will tell how to do the vice versa.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-12T19:01:52+00:00
- Post Title: How to open and convert .strm files

Program is called SX.EXE

Example command line: 

sx.exe -wave strm_mu_djbooth_d01.strm -=strm_mu_djbooth_d01.wav
## Post #3
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T14:13:05+00:00
- Post Title: How to open and convert .strm files

This is what I get when using your command line:

```

ERROR: Couldn't open file "strm_mu_djbooth_d01.strm" for reading, skipping ...

Warning: 31 memory leaks occurred.
```


Any ideas?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-31T14:23:56+00:00
- Post Title: How to open and convert .strm files

Do you have this file? What are you trying to convert?

strm_mu_djbooth_d01.strm
## Post #5
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T14:28:02+00:00
- Post Title: How to open and convert .strm files

Yes I have this file, located in the same directory of sx.exe

I exactly used this command line:

```
C:\Users\Mattrio\Desktop\SoundExchange30101\sx.exe -wave strm_mu_djbooth_d01.strm -=strm_mu_djbooth_d01.wav
```
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-31T16:28:20+00:00
- Post Title: How to open and convert .strm files

then you probably opened this file in hex editor or extractor program, this means SX.exe just can't open it.
## Post #7
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T16:48:43+00:00
- Post Title: How to open and convert .strm files

Yeah that is what I thought.  Vgmstream manage to convert PC EA STRM files almost correctly, but not Wii EA STRM files at all. I don't know any other games that use this kind of file, and I would love to hear them in high quality and be able to do MySims sound modifications in [the MySims mod I'm working on](http://mysims.wikia.com/wiki/User_blog:HeronX232/TBM_-_Update_Blog).

Also, when importing a WII EA STRM file as raw data on Audacity, I get the music with the original length but a too high frequency with these parameters:


And the major problem whatever the parameters I use, there is these gravel bars every 1/4 seconds that ruins the music:


Do you have any other ideas to how read them properly?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-31T16:57:54+00:00
- Post Title: How to open and convert .strm files

> Reply from Mattrio
>
> You have no other ideas to how read them properly?

Why do we need other ideas, when this one works perfectly?

Maybe you don't know how to use command line? Exactly how are you doing this? Where do you enter this command? You can't just open command prompt and enter it. Do you know that? You must change dir.

If you can't, you better put the command into new "1.bat" file, and run it.
## Post #9
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T17:06:18+00:00
- Post Title: How to open and convert .strm files

> Reply from daemon1
>
> You can't just open command prompt and enter it. Do you know that?
That's what I did yeah. To be honest I don't really see what you means, my English is far from perfect, sorry about that.
## Post #10
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T17:12:10+00:00
- Post Title: How to open and convert .strm files

Oh okay I just understood now, it works perfectly! Thanks a lot. Do you know how to do the reverse, wav to EA WII STRM please? Thank you again, what a satisfaction.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-31T17:25:52+00:00
- Post Title: How to open and convert .strm files

yes, the same program can do this for you. Read its help
## Post #12
- Username: Mattrio
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jan 31, 2016 9:57 pm
- Post datetime: 2016-01-31T18:29:00+00:00
- Post Title: How to open and convert .strm files

Thanks a lot for your help, I've done it.
