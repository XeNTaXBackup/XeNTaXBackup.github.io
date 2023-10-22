## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-13T01:00:02+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

I see many requests in these forums, but seemingly only few people are actually able to do reverse engineering.
I think the problem is we don't share much knowledge. Wouldn't it be great to have a tutorials section?
I imagine tuts about tools of the trade, sample GRAF investigations, algorithms, approaches or something like the "guide to exploring file formats" 

But of course this is just an idea
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-13T01:25:32+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

Just want to give a quick overview of programs for creating video tutorials:

Wink is a freeware program available for Windows and Linux.
You can get it here: [http://debugmode.com/wink/download.php](http://debugmode.com/wink/download.php)

A trial version of Instant Demo can be downloaded here:
[http://www.instant-demo.com/download.php](http://www.instant-demo.com/download.php)

Camtasia Studio 3 is a screen capturing program and available for FREE at the moment because version 5 is out.
Just do the following:

> 1. Download the free trial version of Camtasia Studio 3 at:
>
> 
>
> http://download.techsmith.com/camtasias ... tasiaf.exe 
>
> 
>
> 2. Go to this promotion page, complete your name, country and e-mail address and TechSmith will send you the software key to unlock the program.
>
> 
>
> http://www.techsmith.com/camtasia/pcpls.asp 
>
> 
>
> 3. Just install the program you downloaded from step 1 above and then enter the software key you receive from TechSmith and you will have a fully working version of Camtasia Studio 3 on your PC.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-13T07:04:14+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

I think that's an excellent idea, and I propose it to have it's base at GFFC ( [http://wiki.xentax.com](http://wiki.xentax.com) ). Count me in! 

If you'd like to set this up, perhaps it will be convenient for you to be Sysop there, let me know and I'll make you one! 

We could discuss the nature and structure of the tutorial pages here and who does what.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-13T07:24:24+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

Don't know if I'm able to create good tuts but I'll try to make a test video tut.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-13T07:27:44+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

> Reply from Rheini
>
> Don't know if I'm able to create good tuts but I'll try to make a test video tut.

I'm already looking forward to it .
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-13T10:38:28+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

It's quite hard cause I don't know where to start and how to do it.
The problem is there is no specific way to explore a file format. It has a lot to do with experience.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-13T11:58:17+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

Watto and I had the same problem with The Def. Guide. 

The challenge is there in transferring your experience to the end-user in an understandable yet accurate way.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-12-13T17:53:49+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

Speaking of the DGTEFF, I've decided (for a variety of reasons) to stop working on updating it "behind closed doors"; rather, anyone who wants to contribute to it may do so freely on the GFFC (assuming you know what you're talking about  ).
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-17T23:08:20+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

> Reply from Mr.Mouse
>
> The challenge is there in transferring your experience to the end-user in an understandable yet accurate way.
Absolutely.
I guess the problem with DGTEFF is, it's too big and overwhelming. It's a comprehensive reference manual rather than something to start with when trying to figure out a format.
On the other hand it gives all information necessary for reversing file formats. Thus I don't know what to show.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T05:05:31+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

[http://uploaded.to/?id=quht29](http://uploaded.to/?id=quht29)

Just a rough draft.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-18T07:30:07+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

A very nice idea to do it like that!!  

A few remarks though, since it is a draft version. 

First: the screen resolution is quite big, I run 1280-x1024 and still had to scroll to see comments whole. 

You do jump a little to soon to some conclusions, especially if the student is an absolute beginner. 

When you start to use the Binary Editor, things can get confusing, as you type in the structure, without commenting on the position of those things in the actual archive (you switch to look at the structure, but don't point out what YOU are looking at). 

Being a tutorial you should explain most actions you perform. For instance, you switch to look at the System Time structure, but do not comment on it, so the student has to guess what you are doing, and if he or she is a beginner, he'll be in the dark. 

I visited Craptain once and took a look at some game archive while he was watching. I figured out the archive structure quickly, and then tried to go over it with him, but he didn't understand, let alone how I could do that in such a short time. Though this is probably due to my own meager tutorial skills, it does show that it can be difficult to explain the process. 

I should have stopped and explained those things that were old knowledge for me (and I wrongfully assumed known by the student as well), since they were actually new to the "student". 

In any event, this is a nice way to do a tutorial, and we should get more of these, discussing more formats in each. Good job!! What program is that you use?
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T10:36:56+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

The second part hasn't been edited yet at all.

I already tried Wink, Instant Demo, BB Flashback and Camtasia. Camtasia Studio is the one I used to do this.

It is really time-consuming to comment each step, but I'll try to improve this in the next version.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-18T11:38:20+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

> Reply from Rheini
>
> The second part hasn't been edited yet at all.

Oh okay, never mind then
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-18T23:17:17+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

I could also release the project files if this is of any help.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-19T09:08:17+00:00
- Post Title: Any other tutorials like "Guide To Exploring File Forma

For reference? Yes, might be handy once it is finished. 

We can host the tutorial(s) we create a the GFFC. We someone new to this tuff goes through a number of such tutorials it could be of great help to them.
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-19T13:24:11+00:00
- Post Title: 

Well maybe also for others to add important information and hints that I forgot 
Yes, hopefully other people will line up and also create tutorials.
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-20T01:53:03+00:00
- Post Title: 

[http://uploaded.to/?id=o1ubok](http://uploaded.to/?id=o1ubok)
second draft

[http://uploaded.to/?id=9z4dmp](http://uploaded.to/?id=9z4dmp)
third draft

please test and give feedback
## Post #18
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2007-12-20T19:50:38+00:00
- Post Title: 

the third one is clear and have a good size so can read and see all.
It's really nice for start i just hope this can let me edit other file with different header ( they are a lot of numbers    )
Good Job !
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-20T21:03:05+00:00
- Post Title: 

Thx, the problem is there is no "one and only" approach. It's all about experience and guessing the right things, so we'll need much more tutorials
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-20T21:59:57+00:00
- Post Title: 

[http://uploaded.to/?id=ce51hh](http://uploaded.to/?id=ce51hh)
Version 4:
mainly reduced file size, a few cosmetic changes
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-28T10:07:50+00:00
- Post Title: 

> Reply from Rheini
>
> http://uploaded.to/?id=ce51hh
Version 4:
mainly reduced file size, a few cosmetic changes

Yes, this is really nice. It covers only until you reach the pointer to the archive directory right? In any event, this is really handy and should help beginners understand the concept. 

Are you planning on doing one on the directory structure as well ?

When it is complete we can upload it to Xentax.
## Post #22
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-28T10:44:59+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Rheini wrote:http://uploaded.to/?id=ce51hh
Version 4:
mainly reduced file size, a few cosmetic changes

Yes, this is really nice. It covers only until you reach the pointer to the archive directory right? In any event, this is really handy and should help beginners understand the concept.Thanks, yes this covers everything till the directory pointer.

> Are you planning on doing one on the directory structure as well ?I already recorded the third part about the directory but the video was about 60MB, gotta do it again, this time doing things faster.

> When it is complete we can upload it to Xentax.Yeah, but hopefully more people also test this 4th version to give me some more feedback.
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-12-29T16:07:02+00:00
- Post Title: 

I'd test it, but most of my internet time comes from the library, and I can't do anything with .7z archives here...
## Post #24
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-29T18:02:29+00:00
- Post Title: 

WinRAR is able to open them, or you can use 7zip itself:
[http://www.7-zip.org/download.html](http://www.7-zip.org/download.html)
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-01-01T23:13:29+00:00
- Post Title: 

No, I mean I can't install the necessary software on the library computer...
## Post #26
- Username: Acewell
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-02T19:23:28+00:00
- Post Title: 

zip version of tut v4: [http://uploaded.to/?id=0r8mps](http://uploaded.to/?id=0r8mps)
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-01-04T19:53:30+00:00
- Post Title: 

Aah, thank you.
## Post #28
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2008-01-05T15:51:28+00:00
- Post Title: 

Me work fine.

nice idea to learn more!
## Post #29
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-05T20:58:53+00:00
- Post Title: 

Thank you. Will try to complete it next week.
## Post #30
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2008-01-12T12:46:33+00:00
- Post Title: 

Nice tutorial! It made me really wanna start using 010 Editor, the overview with such binary template looks great.
## Post #31
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T06:59:05+00:00
- Post Title: 

I found out that Hex Workshop also has a similar feature, called Structure Viewer, there.
## Post #32
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T18:37:15+00:00
- Post Title: 

> Reply from Rheini
>
> Thank you. Will try to complete it next week.
Not much time atm. Can't finish it in the near future. 
But nevertheless this is a start.
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-01-14T19:53:32+00:00
- Post Title: 

It sure is, and I really do like it. Hope you will finish it.
## Post #34
- Username: lydlcy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 29, 2008 9:41 pm
- Post datetime: 2008-06-30T19:17:51+00:00
- Post Title: 

Can Rheini release your tutorials again??
I have interesting in your tutorials ,thanks
## Post #35
- Username: Acewell
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-06-30T19:48:37+00:00
- Post Title: 

[1024bar.7z](http://www.filefactory.com/file/056b89/n/1024bar_7z)
## Post #36
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-06-30T23:33:13+00:00
- Post Title: 

> Reply from Rheini
>
> 1024bar.7z

thanks actually I wate them too but I thought it would be a bother if I asked...I haven't un7zipped yet but I'll look at them tomorrow, see what I can learn, also, nice to see a file hosting site not needing its cookies enabled to operate other than Rapidshare, but filefactory still has other nasty cookies...of the ones you'd be better of not having...not that its a virus or anything but it pisses me off...any site that does that...even xentax gives you onestat.com cookies if you're not registered, and one else I can't remember
## Post #37
- Username: lydlcy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 29, 2008 9:41 pm
- Post datetime: 2008-07-01T01:32:25+00:00
- Post Title: 

Rheini‘s flash tutorials is so good and easier understand rather than use letter description...
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-01T06:01:04+00:00
- Post Title: 

> Reply from lydlcy
>
> Rheini‘s flash tutorials is so good and easier understand rather than use letter description...

I know  I just hope he can find some time to finish some new ones 

@xrevenge: What other cookie besides onestat do you get at the forum here?
## Post #39
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-01T09:28:20+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> lydlcy wrote:Rheini‘s flash tutorials is so good and easier understand rather than use letter description...
 

I know  I just hope he can find some time to finish some new ones 

@xrevenge: What other cookie besides onestat do you get at the forum here?

I'll pm you later with details, I could also be mistaken and it could be just 2 onestat cookies but I don't think so, Ii'll try fishing around after I delete my cookies and restart the browser (Opera 9.50)
## Post #40
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-07-01T10:59:28+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I know  I just hope he can find some time to finish some new ones
Sorry no time atm. Maybe in August or September but I can't promise anything.
## Post #41
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-01T12:15:27+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> lydlcy wrote:Rheini‘s flash tutorials is so good and easier understand rather than use letter description...
 

I know  I just hope he can find some time to finish some new ones 

@xrevenge: What other cookie besides onestat do you get at the forum here?

well now I didn't find anything...not even the onestat cookie, so it could be just asecond onestat cookie or a sesion cookie...I'm still not 100% sure though, I'll try it again tomorrow, for the record, I'll tell you what I found
I tried going around the site, in the wiki there aren't any cookies at all, here on the forum I found some as well as the pages at the home page and the archived homepages, here is what I found:
[cookie pics.rar](https://xentaxbackup.github.io/file/1567_cookie pics.rar)
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T07:32:43+00:00
- Post Title: 

Hmm, well, those don't seem all too dangerous.
## Post #43
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-04T09:26:03+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Hmm, well, those don't seem all too dangerous.

yup I get them wherever I go, did you delete the onestat cookies though? I didn't see any the next time
I'm surprised that nobody else mentioned anything though...I mean, am I the only one who configures his/her browser (Opera) to ask the user if he wants to accept cookies or not?
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T09:30:07+00:00
- Post Title: 

looks like it
## Post #45
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-04T10:16:59+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> looks like it

so was that onebu++ cookie supposed to be adware or something?
## Post #46
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T10:30:12+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

I have no idea, the OneStat is a mere pagecounter. [http://www.onestat.com](http://www.onestat.com)
## Post #47
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-04T17:27:46+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

> Reply from Mr.Mouse
>
> I have no idea, the OneStat is a mere pagecounter. http://www.onestat.com

umm...bad news?
I got the onestat cookie again:
[2008-07-04_202430.jpg](https://xentaxbackup.github.io/file/1570_2008-07-04_202430.jpg)
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T21:12:03+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

I still don't think that is harmful.
## Post #49
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-04T21:55:54+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

> Reply from Mr.Mouse
>
> I still don't think that is harmful.

if you say so Mr.Stuart (no intent on being rude)
## Post #50
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T23:30:37+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

That's okay.
## Post #51
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-09-29T16:17:42+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

Hmmm.... Looks like all links are completely dead.... Actually i'm looking for some guide[AND/OR]tutorial on how to reverese games themselfes (for example when you want to know which encryption/compression used in package). Google doesn't talk much about reverse engeneering, probably i'm asking him wrong
## Post #52
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-29T16:35:31+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

the problem is that it's not a matter of guides but of practice.
for example the symmetric encryption algorithms (ecb versions, so without ivec) can be usually recognized because if the file has a series of identical bytes (for example 16 or 32 zeros) you can see the same pattern repeated inside all those pseudo-garbage bytes.
but the fact that you have an idea abou the algorithm doesn't help to figure it, in that case it's needed debugging and signsrch.

for the xor/rot related obfuscations instead it's a bit different because the xor key or the xor byte is visible when there are sequences of zeros, otherwise if in doubt I use a [quick scanner](http://aluigi.org/testz/findxor.zip) which tests and visualizes the data after having passed it with all the bytes from 0x00 to 0xff.

the rest is practice, for example during the debugging you see a strange algorithm which uses 16 bit registers and then you say "uhmmm I have already worked with something similar some years ago" and then you see that it's the IDEA algorithm and so on.

other helps could come from the semi-debug messages of the executable (like happened with Shift for XMemDecompress) but it's something not much common.

obviously this was for the encryption part, because for the fields of the archive it's just a matter of hex editor and calculator
## Post #53
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-29T17:11:55+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF) You can still read that if you need a place to start. There's also a piece on my reverse engineering of the Painkiller XOR encryption algorithm. 

But in general, it's like Bugtest said: practice and I would say experience. 

I've spend thousands of hours on figuring out file formats be simply using a hex editor and a calculator (preferably one that has hexadecimal numbering functions as well). 

When I was at Craptain's place some years ago, he saw me do it on a new file and was amazed by the speed by which I figured it out, but really,that was the years of experience doing the job, you start to spot immediately the structure of the standard formats. 

You must look at it as a game, a puzzle. You will come across difficult ones, but even the more the satisfaction of demystifying it. 

Yet, it all starts with a hex editor and a calculator.
## Post #54
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-09-29T17:40:33+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

I have no problems with just extracting files. Hex editor + win calc in engineer mode + some logic. That's right. But extracted files without knowlege of their format are useless.

I'm looking for a way to discover what exactly the given "game.exe" doing with some file in archive in order to decompress/decrypt it. Is there any specific soft for such research? I've heard about debuggers, disassemblers, decompilers... But info is smooth and not even about games.. 

So my question is - what tools to use to work with "game.exe", not with package ^__^
## Post #55
- Username: Corwin
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-29T18:07:25+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

Disassemblers, eg OllyDbg, Ida Pro etc
## Post #56
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-30T00:02:19+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

uhmmm I can list what I use in general, maybe it's useful also to other people interested in the reversing of file formats:
- ollydbg: the debugger
- xvi32: the hex editor, it's unsupported, not much optimized and with some bugs but it's confortable
- signsrch: to know the algorithms used in the executable and knowing where to set the breakpoints for verifying them
- calcc: the only calculator I use
- byte2hex/hex2byte/byte2c: for converting the various dumps of memory/files/pieces of data in various formats, very used
- offzip: to scan the archive if contains zlib or deflate data blocks
- some small testers of common algorithms like lzo, lzss, lzw and blast
- findxor: for scanning various xor and rot values
- mycrc: sometimes for confirming if a field is a crc/hash
- fcomp: for comparing some results like the uncompressed data obtained by me and the correct one obtained by the game
- xor: for verifying a xor key or retrieving it from a xored and plain-text data
- quickrva: used in some occasions but it's not useful when reversing formats
- chd: used only to know the hex values of some strings on the fly
- something else that I have forgotten as usual
## Post #57
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-07-18T06:43:04+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

Rheini can you upload the file again? I missed the file by 2 years but I really want to get into this stuff.
or if any one still have the file, do you mind mirroring it? thanks a lot
## Post #58
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-18T06:51:46+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

> Reply from MuffinMan123
>
> Rheini can you upload the file again? I missed the file by 2 years but I really want to get into this stuff.
or if any one still have the file, do you mind mirroring it? thanks a lot
This thread is four pages long; that's a lot of posts. It would help if you quoted the post containing the link you're talking about.
## Post #59
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-07-18T17:51:35+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

> Reply from Rheini
>
> http://uploaded.to/?id=ce51hh
Version 4

> Reply from Rheini
>
> 1024bar.7z

I am assuming 1024bar is also version 4, just reuploading back in 2009, but every link is dead now.
## Post #60
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-07-22T19:49:43+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

so no one kept a copy of the file somewhere?
## Post #61
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-22T22:09:34+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

Evidently not... Rheini may still have a copy, but we won't know until he replies.
## Post #62
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-07-23T03:01:43+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

> Reply from MuffinMan123
>
> so no one kept a copy of the file somewhere? I found this in my files, check it out and see if its what you wanted: [http://www.mediafire.com/?azao4qdyc4lcvfr](http://www.mediafire.com/?azao4qdyc4lcvfr)
## Post #63
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-23T04:21:13+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

That looks like it could be it (I never looked at the original downloads, so I can't be sure).
## Post #64
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-11-11T02:24:39+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

aww damn it, it barely started and didn't really get far. nice to know some header stuff, but I wish there's more. is the author considering continuing it?
## Post #65
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-12T07:29:28+00:00
- Post Title: Re: Any other tutorials like "Guide To Exploring File Forma

that would be great if anyone can continue with this, coz i think it is really great
