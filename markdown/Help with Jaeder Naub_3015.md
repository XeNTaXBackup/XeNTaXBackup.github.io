## Post #1
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-17T11:51:29+00:00
- Post Title: Help with Jaeder Naub

Every time I try to open Jaeder Naub 2.0.6c it just says: the parameter is incorrect.

And when right-click then run as a specific user (I only have one on my laptop) it then displays an error message saying: invalid picture.

I'm using Windows XP, and I've tried running in different compatibility modes, but that doesn't seem to help.

I'm trying to find and extract the foley and weapon sound effects from MGS3, I think they're in the slot.dat, as it's the only one I haven't opened.  (VOX.dat was just 4963 vocal files and no sound effects)  I can't seem to find any way to open slot.dat besides trying Jaeder Naub (once it works of course).
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-17T19:41:29+00:00
- Post Title: Help with Jaeder Naub

You are using JN stand alone?
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-18T01:32:28+00:00
- Post Title: Help with Jaeder Naub

I believe so, it's the main download on the Jaeder Naub site.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-18T07:15:19+00:00
- Post Title: Help with Jaeder Naub

At the Gile File Format Central? 
[Jaeder Naub](http://wiki.xentax.com/index.php?title=Jaeder Naub)

I can start that one without error. It's a previous version though. You should PM Strobe on this here at the forum. He's the author of JN.
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-18T11:08:51+00:00
- Post Title: Help with Jaeder Naub

> Reply from Mr.Mouse
>
> At the Gile File Format Central? 
Jaeder Naub

I can start that one without error. It's a previous version though. You should PM Strobe on this here at the forum. He's the author of JN.

It gives me the same two errors again depending on how I run it.  I'm going to PM him right now.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T18:55:18+00:00
- Post Title: Help with Jaeder Naub

Interesting......

so it only gives errors with specific files or do i need new glasses?

if its specific files i would love to have those. i have never heard of those runtime errors before when using 
the program =X

this needs to be investigated!

Edit:
Okay, i needed new glasses. so the error happens everytime you start it.
Ill check this out. *brb*

Edit 9582:
Try this new betapackage, i changed a thing in the Icon structure which "could" somehow be quirky on 
specific systems.

[http://jaedernaub.ath.cx/jntest.zip](http://jaedernaub.ath.cx/jntest.zip)

Let me know if it works or not!
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-18T21:08:56+00:00
- Post Title: Help with Jaeder Naub

Oh well, good news and bad news.  it gives me the same errors, but for some reason now when I run as a specific user it takes a little longer, like it's doing something, but then pops up saying "invalid picture" again.

I just did a little searching on the "invalid picture" thing (seems a little weird to be talking about pictures at startup) and I found this:

> I found the solution on the following forum
>
> 
>
> http://www.911cd.net/forums//index.php? ... st&p=13789
>
> 
>
> In a nutshell, make sure your temp environment variable is pointing to a writeable area, ie ramdisk, hdd.
>
> 
>
> Next time you fire up a vb6 application have a look in your temp directory and you'll see a ~blah.tmp file in there, that exists for the duration of the application.

Could this be related?

Edit: Wait a sec.  I think it's telling me that "the parameter is incorrect" because for some reason it can't find and execute it.  the whole variable thing is also happening because it can't find the location again. Am I on the right track or should I leave it up to you guys?  It's just that above "parameter is incorrect" is says the file path of the Jaeder Naub executable making me think that that is what's incorrect.  It's probably some weird problem with my system.
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T21:27:12+00:00
- Post Title: Help with Jaeder Naub

I did make some specific tests now, and i finally made it too run with an error.


What i did was running it in an virtual Win XP 32bit environment, took "Run as..." and had
"Protect blah blah blah" clicked. and then i also get the "Invalid picture" error.

However, running this natively with Protected blah in the real windows environment didnt
display the error. So im guessing you have some sort of harsh security checkings or somehow
running a protected mode environment to make this happen.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-18T21:52:36+00:00
- Post Title: Help with Jaeder Naub

WooW!! Nice reproducing the error, Strobe! Way to go!
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T21:55:34+00:00
- Post Title: Help with Jaeder Naub

Well, i still dont really know why it happens =P , and Pepper is the first one i ever heard had this to happen!
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-18T22:18:19+00:00
- Post Title: Help with Jaeder Naub

Hmm... I'll try changing any security settings I can. Oh, and thanks for all the help so far. :>

Oh and the main error is the incorrect parameter one.
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T22:34:39+00:00
- Post Title: Help with Jaeder Naub

Okay, lets try one more edit of the startup crap.

[http://jaedernaub.ath.cx/jntest2.zip](http://jaedernaub.ath.cx/jntest2.zip)
## Post #13
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-04-18T23:30:41+00:00
- Post Title: Help with Jaeder Naub

Nope, same two errors depending on how it's opened.  I really appreciate all the help, but in the mean time I ripped sounds out of another ps2 game, BLACK, instead.  So if you still want to help I'm all up for it because Jaeder Naub looks like a wonderful tool.
## Post #14
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2009-02-06T21:43:59+00:00
- Post Title: Help with Jaeder Naub

Ahah!  way back when i posted this i had some problems with other software and games shortly after, I reformatted and it works perfectly now.
## Post #15
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2011-02-13T03:06:54+00:00
- Post Title: Help with Jaeder Naub

> Reply from Pepper
>
> Nope, same two errors depending on how it's opened.  I really appreciate all the help, but in the mean time I ripped sounds out of another ps2 game, BLACK, instead.  So if you still want to help I'm all up for it because Jaeder Naub looks like a wonderful tool.

Pepper

How did you rip the sound out of Black I am trying to do this right now and I've tried MFAudio and ADPCM player but I cannot get the sounds to play right they keep skipping no matter what. I did get the settings right at one time in MFAudio but sadly I didnt document the settings and I forgot them. all I want to do is rip the stuff inside the .BKS archives, they have a .SSH file accompanying each .BKS file. What program(s) did you use to rip the Black sounds? 
Thanks.
## Post #16
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-04-03T01:09:10+00:00
- Post Title: Re: Help with Jaeder Naub

Bit of a bump to that bump, but i used Psound i believe, some of the files were also raw pcm samples, it seemed like their audio engine combined a raw pcm sample (for the highs) and standard ps2 VAG (for the lows) and viola, gunshots that sound amazing.
## Post #17
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2012-04-03T05:45:59+00:00
- Post Title: Re: Help with Jaeder Naub

Where does one download the latest version of Jaeder Naub?
The "official" web site seems to be offline.
Thanks.
