## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-13T11:14:34+00:00
- Post Title: Recoding my ripper engine totally.

I have started creating a totally new ripper engine.
it will be probably  1000% (or more) faster than the current
Jaeder Naub. 

Jaeder will though still be in development as the time to
totally rewrite the engine and convert file format detections
will take a pretty damn long time, but i felt it was neccessary
to do this for various of reasons.

i have made some current tests, and my beta scans about 30mb/s
in Deep scan mode, while Jaeder Naub scans at highest 1mb/s

I have tried my best to adapt this engine to jaeder naub, but it has failed,
as it works on a totally different level. *sigh* , so it seems like the only
way to integrate this scanner is by recoding the whole application.

well well, maybe its my destiny? =X

Edit:
On some more plus sides, the new engine is fully portable to Linux ))
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-13T11:26:25+00:00
- Post Title: Recoding my ripper engine totally.

Still, that's good news!! I wish you a swift conversion!
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-13T15:19:52+00:00
- Post Title: Recoding my ripper engine totally.

GO for it strobe.
Jaeder is still good.
Though maybe, I should add soem formats to the ripper we both worked on, and see if that can work any faster then jaeder.
Though, i dont have it on this new Laptop so il need the newest version il ask you on msn i guess.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-13T17:18:32+00:00
- Post Title: Recoding my ripper engine totally.

Nice to see this   
go 4 it!!!
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-14T01:57:06+00:00
- Post Title: Recoding my ripper engine totally.

Go Strobe Go! *waves pennant flag with "STROBE" on it, and giant foam hand with "JAEDER NAUB" on it*
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T16:03:13+00:00
- Post Title: Recoding my ripper engine totally.

Now i feel the pressure =O .....!!!

what if i give up?!! . then people will get my phonenumber and
address and send some "guys" over here ((
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-14T19:38:30+00:00
- Post Title: Recoding my ripper engine totally.

> Reply from Strobe
>
> Now i feel the pressure =O .....!!!

what if i give up?!! . then people will get my phonenumber and
address and send some "guys" over here ((

I certainly will, as I will start telling people to expect a brand new JN in the new MexCom release!!!
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T20:07:42+00:00
- Post Title: Recoding my ripper engine totally.

My life is ruined 

ill start making small flash games instead under the pseudonym "Pink Cuddler" =(
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-16T18:49:39+00:00
- Post Title: Recoding my ripper engine totally.


## Post #10
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-11-20T21:11:15+00:00
- Post Title: Recoding my ripper engine totally.

>>strobe.
what language have you programmed jaeder naub in?

if its delphi, then i would be able to help you, if you agree to it. to take off a little the pressure 

oh, btw. i've notice that in the current jaeder naub it looks like it eat one single file. if you want to optimize the speed, try cutting bigger files up in chunks and place it in thier own threads 

cheers FunteX!
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-20T22:32:45+00:00
- Post Title: Recoding my ripper engine totally.

> Reply from FunteX
>
> >>strobe.
what language have you programmed jaeder naub in?

if its delphi, then i would be able to help you, if you agree to it. to take off a little the pressure 

oh, btw. i've notice that in the current jaeder naub it looks like it eat one single file. if you want to optimize the speed, try cutting bigger files up in chunks and place it in thier own threads 

cheers FunteX!

Jaeder is programmed IN Visual Basic

As for the final message i thought that it already cut files up anyways
No wait yeah it does actually.
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-21T03:48:00+00:00
- Post Title: Recoding my ripper engine totally.

Funtex: Its coded in VB as lionheartuk said 

But the new engine im working on side by side is coded
in Freebasic. which has much better support for operations like this,
and also supports inline assembler.

Its WAAAAAY faster than VB. however im both updating the current
ripper and working on the new one, i do learn more tricks when
coding 2 things side by side, and im trying to adopt some of them
over to the current engine.

As a sidenote, i have never touched Delphi ! 

and the reason for the slow scanning in Visual Basic is because
of the lack of memory usage, i have to take everything in so
small chunks before i can process them, while in Freebasic
can cache a whole file in memory and do mem scanning instead.

but i am also testing new caching function for VB code, and hopefully
speeding up the old engine aswell :X
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-21T15:05:00+00:00
- Post Title: Recoding my ripper engine totally.

> Reply from Strobe
>
> Funtex: Its coded in VB as lionheartuk said 

But the new engine im working on side by side is coded
in Freebasic. which has much better support for operations like this,
and also supports inline assembler.

Its WAAAAAY faster than VB. however im both updating the current
ripper and working on the new one, i do learn more tricks when
coding 2 things side by side, and im trying to adopt some of them
over to the current engine.

As a sidenote, i have never touched Delphi ! 

and the reason for the slow scanning in Visual Basic is because
of the lack of memory usage, i have to take everything in so
small chunks before i can process them, while in Freebasic
can cache a whole file in memory and do mem scanning instead.

but i am also testing new caching function for VB code, and hopefully
speeding up the old engine aswell :XSounds good man.
go for it init.
I hope to see the changes oen day.
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-16T04:48:25+00:00
- Post Title: Recoding my ripper engine totally.

The scanner is so fast im sitting here wanking.

Tests revelead currently that it is able to scan
50 MB of data in about 3 seconds.
(and it isnt even really optimized yet)

that would mean roughly about 500mb of data in 30 seconds.
This includes loading cache time!!

(tested with about 6 formats implemented yet)
but not savedata time yet.

I will however keep the old VB jaeder naub engine, as i had an idea,
i will use this scanner to prescan a file, set up a list of addresses 
where it spots files, and let jaeder naub scan those addresses
and dump the files.

this may sound like im not really gaining any speed on it if im sending the information back to the old Scanner engine,
but yes i am, because then the old engine will only be used for the
Saving and conversion part.

havent tested this in reality yet though! :X stay tuned!

Edit:
And btw , this scanner will be commandline driven, so this could later
be a successor for the current JN implementation in MexCom.

Edit2: 
Okay, the scanner is now optimized. and makes about 100Mbs
per second. this is far beyond expectations when i first started
with it 

But now the system specs for this scanner is pretty high.
for optimal performance it would atleast require 2 GHZ and 1GB
of RAM.
## Post #15
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-16T10:55:18+00:00
- Post Title: Recoding my ripper engine totally.

Well.... I guess you all know what this picture means...

=D

Im now betatesting the external scanner and feeds jaeder naub
with the data it finds.

So far the results are brillant!!
[newscan.jpg](https://xentaxbackup.github.io/file/1059_newscan.jpg)
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-16T13:16:24+00:00
- Post Title: 

Looking good , pal!!
## Post #17
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-02-16T14:01:55+00:00
- Post Title: 

mmm. i cant' w8
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-02-16T17:27:12+00:00
- Post Title: 

AAUUUUGGGGHHHHHHHH!!!!!!!!!!!!! Such... large... requirements.... *has heart attack*

Nah, just kidding... Good work!
## Post #19
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-18T04:00:47+00:00
- Post Title: 

New scanner integrated! and should work as good as the old scanner
did on detection!, but now MUCH faster 

i did have to slow it down a bit due to error checks and validating data,
but overall its a huuuuuuuuuuuuUUUuuuuge improvement 

[http://jaedernaub.ath.cx](http://jaedernaub.ath.cx)

now i dont want to hear anymore complains about my ripper being slow!!!
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-18T09:04:59+00:00
- Post Title: 

Ok, uploaded it.

[http://wiki.xentax.com/index.php/Jaeder_Naub](http://wiki.xentax.com/index.php/Jaeder_Naub)

Please edit the info. 

Just to think of the version numbering, your last was 1.9.0 something, then you did a complete rewrite of the detecting engine and now it still is 1.9.3, isn't that a major update?
## Post #21
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-19T02:12:26+00:00
- Post Title: 

yay!

but i cannot enter the Wiki ....all i get is a blank page....

hmms....

and im allready fixing some other nasty bugs =X , next release
will for sure be 2.0.0 !!!
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-02-20T19:47:59+00:00
- Post Title: 

I'm not sure what your problem is, Strobe, the page loaded fine for me... Perhaps you should try again?

BTW, while we're on the subject of the WIKI, Mr.Mouse, would it be possible to move the Google adverts to the left side of the page, underneath the toolbar? It's not unusual for the ads to end up covering content on pages, especially on an 800x600 monitor, which is (to say the least) an annoyance...
## Post #23
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2007-02-20T20:19:28+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> I'm not sure what your problem is, Strobe, the page loaded fine for me... Perhaps you should try again?

BTW, while we're on the subject of the WIKI, Mr.Mouse, would it be possible to move the Google adverts to the left side of the page, underneath the toolbar? It's not unusual for the ads to end up covering content on pages, especially on an 800x600 monitor, which is (to say the least) an annoyance...
It's possible, but who the hell still has an 800x600 monitor?
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-21T10:26:45+00:00
- Post Title: 

Interestingly though, if Strobe uses [http://www.the-cloak.com](http://www.the-cloak.com) he can visit the WIKI. Is this a regional (Swedish) problem then?! Or something between him and his provider? 

Strobe, you should contact your provider perhaps.
## Post #25
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-21T10:33:12+00:00
- Post Title: 

if i run the page through [http://www.pornolize.com/](http://www.pornolize.com/)  (so sorry, but it was part of my testing program  )

the page gives a HTTP 400 ERROR.

i dont know if that has something to do with it, but atleast its the first
page ive tested that gives an error through that page.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-21T10:39:43+00:00
- Post Title: 

That's indeed interesting. It pornolizes forum.xentax.com normally, and also another wiki site I own. It seems then that there's something going on with the Xentax wiki, or the region where this Pornolize server is based at, perhaps the Wiki version that we are running. Or some other problem. Still very vague.
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-21T10:45:52+00:00
- Post Title: 

Okay, I isolated the problem. At least the Pornoliz0r problem was caused by the Bad Behaviour extension I had installed at the wiki, to block spammers. I have now removed the extension and the pr0n0l1z3r works with the wiki. 

I think you can access the site now, spammer.
## Post #28
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-21T10:50:05+00:00
- Post Title: 

Works now!!!!!

i promise to stop spamming!! =((
## Post #29
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-21T10:51:39+00:00
- Post Title: 

HUAHAHAHAHAHAHAHAHAHA

Now i know why it stops working!



its when i try to login.
once i log in the page turns white. and then i cannot access it again 

like now.......

Edit: and ive found a way to make it work again.
i have to delete everything, cookies, and cache, sessions
from the browser temp folder 

not just cache.

earlier i did just delete the cache, thats why i failed at fixing it.
but anyways, i cannot log in now instead 

because then it screws up again.
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-21T10:52:44+00:00
- Post Title: 

What? It doesn't work still??
## Post #31
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-21T10:57:17+00:00
- Post Title: =D

Correct!

it does work if i flush everything from the browser temp folders 
but as soon as i try to log in again, the error is back ;D
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-21T11:03:03+00:00
- Post Title: =D

> Reply from Strobe
>
> Correct!

it does work if i flush everything from the browser temp folders 
but as soon as i try to log in again, the error is back ;D

Please mail me your login information, so I can check if this is somehow related to your account.
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-02-22T20:22:28+00:00
- Post Title: =D

> Reply from Captain
>
> Dinoguy1000 wrote:I'm not sure what your problem is, Strobe, the page loaded fine for me... Perhaps you should try again?

BTW, while we're on the subject of the WIKI, Mr.Mouse, would it be possible to move the Google adverts to the left side of the page, underneath the toolbar? It's not unusual for the ads to end up covering content on pages, especially on an 800x600 monitor, which is (to say the least) an annoyance...
It's possible, but who the hell still has an 800x600 monitor?
My public library's computers, for one...  *stupid #$@% computers...*

Besides that, the ads infringe on text in category listings, even under a 1024x768 res...

It just occurred to me, what if you set the ads up so that they would go underneath the main body of a page, should they extend into it? Doesn't that have something to do with the Z-Buffer or Z-Layer or whatever the hell it's called CSS attribute?
## Post #34
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T12:31:52+00:00
- Post Title: =D

> Reply from Strobe
>
> Okay, the scanner is now optimized. and makes about 100Mbs
per second. this is far beyond expectations when i first started
with it
Sounds great. I currently only get 20 MB/s (EDIT: 48 MB/s in release version) with my scanner. But it's not optimized yet.
Which approach do you use? Brute-force?
Do you do any preprocessing on the data?
What's the time complexity of your algorithm?
## Post #35
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-02T15:02:30+00:00
- Post Title: =D

The current speed has drastically got down to about 10-20mbs when i added more complex formats, and because
i had so many rewrites of the jaederstorm component.

Im almost about to rethink the whole component once again to make it properly this time,
i think i can very fast speed with actual GOOD code even for complex checks on some formats.

thats also why i implemented the UltraFast option which only scans for easy detectable formats
which will scan about as fast as your harddrive goes =P

Now all i need is some.....more time :/
## Post #36
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-01-12T22:18:26+00:00
- Post Title: =D

Strobe did not log in since 2013, so I guess his new tool won't be coming any soon...

I searched the site for Jaeder Naub - found 2.1.4 being referred to as the latest.
I have 2.2.4g on my HDD. Must have grabbed it before the JaederNaub.com was shut down.

I don't want to upload it anywhere, so I will just attach it here so people can find it.

Edit
Seems it won't attach.
Is it because it's a RAR or is it because it contains an EXE?
I'll try a ZIP.

Edit 2
Hmmm.
Won't upload.
Well, let me know what I can do.
## Post #37
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-05T17:30:34+00:00
- Post Title: =D

you still have that version?
## Post #38
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-07-05T20:04:49+00:00
- Post Title: =D

> Reply from happydance
>
> you still have that version?
I you're asking me, then the answer is yes.
## Post #39
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-05T23:55:55+00:00
- Post Title: =D

> Reply from Csimbi
>
> Won't upload.
Well, let me know what I can do.
upload it to an external file host like mega or mediafire or something and you should be good
## Post #40
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-07-06T12:03:43+00:00
- Post Title: =D

[Here](https://mab.to/qUJGVGHDs).
