## Post #1
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-08-18T04:39:59+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

oh my god im finally registered at this forum 
Ok so, I have been trying to open this file called "BIGFILE.BIG" from the very well known game for PSX called "Crash Team Racing". As you can see, it has a ".big" format, which I tried to open with programs like "FinalBIG" but with no sucess (Though I'm pretty sure it was because the program was made for EA .big files, not Naughty Dog ones) ...So, does anyone know if there's a way to open those files?
Also, thanks for reading the topic. That already means a lot, haha.
## Post #2
- Username: hypnolem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 18, 2014 7:41 pm
- Post datetime: 2014-08-18T11:44:28+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

cool
## Post #3
- Username: PolarSoda
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-18T20:49:54+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

I was working on the format days ago. The format is very simple it works like this:

```
{
      unsigned int null;
      unsigned int fileCount;
      BigFileEntry[fileCount];
};

struct BigFileEntry
{
       unsigned int fileAlignment; //Offset is this * 0x800
       unsigned short fileUnknown00; //Possibly type info
       unsigned short fileUnknown01; //Possibly type info
};

```


It's not really intended to be extracted. Just read as it is... It could be extracted by taking the offset of the next file entry and using it to calculate the size of the previous one. My findings should be correct, I only spent a few minutes on it and I'm not taking it further so the information is now out here.

Hope it helps!

Cheers.
## Post #4
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-08-19T01:55:50+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

omfg thanks a lot!!
the people of this forum are so nice!!
## Post #5
- Username: PolarSoda
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-19T15:11:06+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

```
#By Gh0stBlade
#Version 1.0

get NULL long
get FILES long

set ENDFILE FILES
math ENDFILE -= 0x1

for i = 0 < FILES
	
	get OFFSET long
	get UNK00 short
	get UNK01 short
	math OFFSET *= 0x800
	
	savepos TBL_END
	
	if i == ENDFILE
		get SIZE asize
		math SIZE -= OFFSET
	else
		get OFFSET2 long
		math OFFSET2 *= 0x800
		set SIZE OFFSET2
		math SIZE -= OFFSET
		#print "FILES: %FILES% I: %i% END: %ENDFILE%"
	endif
	
	goto TBL_END
	
	get NAME basename
	string NAME += "_"
	string NAME += i
	string NAME += ".bin"
	
	log NAME OFFSET SIZE
next i

```


Not really necessary but it should extract the files fine.
## Post #6
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-08-23T06:35:31+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Thanks, it worked!
It extracted a lot of ".bin" files. (722 to be exact)
...That's indeed a lot.
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-23T16:04:50+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

> Reply from PolarSoda
>
> Thanks, it worked!
It extracted a lot of ".bin" files. (722 to be exact)
...That's indeed a lot.

Unfortunately, there are no filenames. Reason is that it's not supposed to be extracted. I just did it since it can potentially make things easier so people can see where the data starts and how the main archive format works.

The texture data looks like basic PlayStation TIM as usual. I don't know what you are trying to view exactly though you can expect that all those files should contain meshes/textures/audio/sound/animations! It's just finding the correct files which will be a pain.

It's kind of similar to Tomb Raider for the PlayStation in terms of how it's stored.
## Post #8
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-08-24T23:05:00+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Oooooh thanks!
And I was mainly looking how to extract the kart/track models.
Gotta find a way how to find the files with those .bins ... sorry im kinda new at this so yeah;;;
## Post #9
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2014-09-22T06:19:36+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

In 2010 HoRRoR described the bigfile.big format and used first pair of files to read the models (russian, use translator)
[http://www.emu-land.net/forum/index.php?topic=36640.0](http://www.emu-land.net/forum/index.php?topic=36640.0)

I tried to mess with CTR files as well, the best I found was this (russian again).
http://***/board/archive-f36/topic1413.html (link is down)

I also wrote an extractor that replaces bin extensions with known .str, .tim and .timarc. tim files here are actionly VRAM which is loaded directly into the memory and .timarc is nothing but 2 tims in a row.
## Post #10
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-09-24T01:25:13+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Thanks! By the way, The extractor works fine, but when I try to open the Viewer this happens...
[http://prntscr.com/4pqtas](http://prntscr.com/4pqtas)
I don't know why, the first time it worked just fine.
## Post #11
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2014-09-26T08:11:07+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

are files crash_0 and crash_1 in the same folder?
## Post #12
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2014-10-01T04:55:15+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Yes, they are.
EDIT: So... does anybody know how to fix this D: ?
## Post #13
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2014-10-22T14:01:47+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

well if it worked fine the first time, must be something wrong on your side.
## Post #14
- Username: StoneCold
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 09, 2015 6:53 am
- Post datetime: 2015-07-10T00:35:31+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Topic is somewhat dead but just thought I would mention a long time ago I managed to pull out the Karts into .obj format. GLXtractor (With OLGE Plugin) on the Model Viewer Program works for models, the texture section is a bit funky though.
## Post #15
- Username: AlexanderV
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2016 7:26 am
- Post datetime: 2016-06-18T23:38:32+00:00
- Post Title: Crash Team Racing BIGFILE.BIG

Hello, I know this thread is so old, but I want to ask you how I can extract the BIGFILE.big

Sorry, I'm little stupid and I don't understand how I can extract the file with the Gh0stBlade code

I want the track models too and I hope you can help me

Thanks and have a nice day!

PS: sorry for my bad english, I speak spanish
## Post #16
- Username: AlexanderV
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-06-19T19:06:45+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

> Reply from AlexanderV
>
> Hello, I know this thread is so old, but I want to ask you how I can extract the BIGFILE.big

Sorry, I'm little stupid and I don't understand how I can extract the file with the Gh0stBlade code

I want the track models too and I hope you can help me

Thanks and have a nice day!

PS: sorry for my bad english, I speak spanish
You need quickbms.
## Post #17
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T12:19:44+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

> Reply from StoneCold
>
> Topic is somewhat dead but just thought I would mention a long time ago I managed to pull out the Karts into .obj format. GLXtractor (With OLGE Plugin) on the Model Viewer Program works for models, the texture section is a bit funky though.

Wow, any chance of sharing the .Obj files you managed to get out? still got em around, or (im new here) if not allowed to link then could we get a little more info about how that feat was acheived...?

Would love to surprise people with an Assetto Corsa - Crash Bandicoot etc ... Kart/Car Mod
## Post #18
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2016-07-17T13:45:04+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

these are the files linked before in this thread. the crash universe link seems to be down, should've copy that info here back then.

[http://www.mediafire.com/download/4kozk ... _split.exe](http://www.mediafire.com/download/4kozk3djg41grvn/ctr_big_split.exe)
[http://www.mediafire.com/download/9jj1p ... est0000.7z](http://www.mediafire.com/download/9jj1pjgz4ahbqgs/crash_test0000.7z)
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-07-19T08:46:34+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

Having a look-see.
## Post #20
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2017-04-13T19:26:07+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

Sorry for the colossal bump, but does anyone know how to change the models in the model viewer to something else?
## Post #21
- Username: adebisi8888
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 28, 2017 5:17 pm
- Post datetime: 2017-05-28T09:21:44+00:00
- Post Title: Re: Crash Team Racing BIGFILE.BIG

Hello everyone, I have extracted the bigfile.big in 607 file (.bin, .timarc and .tim).
So now what should I do now?
Thank you
