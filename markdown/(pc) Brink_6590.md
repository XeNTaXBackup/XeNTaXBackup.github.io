## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-05-10T21:37:44+00:00
- Post Title: (pc) Brink

Please, help me with unpacking sdpk2, sdmd2.

[http://www.multiupload.com/R6FTYIGBNS](http://www.multiupload.com/R6FTYIGBNS)
## Post #2
- Username: pesicha
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 17, 2010 6:16 pm
- Post datetime: 2011-05-11T11:43:28+00:00
- Post Title: (pc) Brink

english text 

```
http://www.megaupload.com/?d=OUN0MVX0
```


for á, í, é, ý change code the file to UTF-8
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-05-11T12:20:49+00:00
- Post Title: (pc) Brink

> Reply from pesicha
>
> english text 
Code: Select allhttp://www.megaupload.com/?d=OUN0MVX0

for á, í, é, ý change code the file to UTF-8
Is it from PC version?
## Post #4
- Username: pesicha
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 17, 2010 6:16 pm
- Post datetime: 2011-05-11T12:50:43+00:00
- Post Title: (pc) Brink

Yes, this is for PC version

copy the text to the game
## Post #5
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-05-11T21:19:15+00:00
- Post Title: (pc) Brink

I don't have the game yet, so I'm asking: how did you extract the text? Or they just in the Brink\base\localization\english\strings folder?
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-05-11T23:20:59+00:00
- Post Title: (pc) Brink

I think he means unpacking the compressed bigfiles, i have been trying to do it also and provided samples in my other thread.
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-12T00:41:49+00:00
- Post Title: (pc) Brink

[http://svn.gib.me/public/brink/trunk/](http://svn.gib.me/public/brink/trunk/)

Work in progress.
## Post #8
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2011-05-14T23:10:58+00:00
- Post Title: (pc) Brink

> Reply from Rick
>
> http://svn.gib.me/public/brink/trunk/

Work in progress.

hi, a question what i can exactly do with ur files? asked it me on a other game already
## Post #9
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-05-15T01:30:24+00:00
- Post Title: (pc) Brink

The game seems to be capped at 16 bots.  When using si_maxplayers and value higher then 16 doesn't work.  Is there another code I'm mising or is this game hard locked?
## Post #10
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-05-15T14:12:16+00:00
- Post Title: (pc) Brink

It is possible to now some filenames inside the "*.sdmd2"-files to code an unpacker/repacker?

Here are some from file "pak000.sdmd2"
Brink - pak000.sdmd2.zip
## Post #11
- Username: plash
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 14, 2011 7:56 pm
- Post datetime: 2011-05-15T18:23:48+00:00
- Post Title: (pc) Brink

> Reply from ZerOHearth
>
> It is possible to now some filenames inside the "*.sdmd2"-files to code an unpacker/repacker?The SDMD2 files don't list all of the path names for files in the larger SDPK2s. See the spec [here](http://github.com/komiga/brinktools/blob/master/formats/sdmd2/sdmd2.format).

EDIT: The best way is probably to extract and match all the strings from the Brink binary. That is assuming they didn't somehow compile every path hash when the code was compiled.
## Post #12
- Username: plash
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 14, 2011 7:56 pm
- Post datetime: 2011-05-15T18:26:32+00:00
- Post Title: (pc) Brink

> Reply from East
>
> The game seems to be capped at 16 bots.  When using si_maxplayers and value higher then 16 doesn't work.  Is there another code I'm mising or is this game hard locked?I don't know about single-player campaign, but dedicated servers can change the max players, and whether bots are turned on or not.
## Post #13
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-05-15T19:38:28+00:00
- Post Title: (pc) Brink

> Reply from plash
>
> The SDMD2 files don't list all of the path names for files in the larger SDPK2s.That´s right. But it´s not a problem to fit it.

I do it. See @ this [Post](http://forum.xentax.com/viewtopic.php?p=54033#p54033/url)
## Post #14
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-05-21T12:15:46+00:00
- Post Title: (pc) Brink

> Reply from plash
>
> The SDMD2 files don't list all of the path names for files in the larger SDPK2s.Sorry i forget.   

I have fix the path´s of the files COMPLETLY, but not for all *.sdmd2-files.

But if there chance to code a script for BMS or code a other tool, i will invest the/my time to do it for all files.
## Post #15
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2011-05-21T16:24:58+00:00
- Post Title: (pc) Brink

Hi,
i found this thread when i was searching for Brink Extraction, and it seems that you have done some good work. If you need a coder for an extractor, maybe I could help you (I'm also interested in this). If you need any help, I'm here.
You could PM me for contact via Skype if you want, I'm from germany too.
## Post #16
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-05-21T17:05:19+00:00
- Post Title: Re: (pc) Brink

@ StuKKa

Ok. Let´s go. Code please an extractor for the *.sdpk2-files. In the *.sdmd2 are the path (yes all   ) and filenames.

Tell me what you need. Hope i can help you, too.

Do it for the Community.
## Post #17
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2011-05-21T19:27:51+00:00
- Post Title: Re: (pc) Brink

Ok, I give it a try.....
## Post #18
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-05-25T17:45:47+00:00
- Post Title: Re: (pc) Brink

4 days later...

Well, what happened?
## Post #19
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2011-05-27T10:01:45+00:00
- Post Title: Re: (pc) Brink

I tried out some things with the files, but could get nothing working. I know which files are in the sdpk2 files, but i can't get it out of them. Sorry, it seems that I have to give up to a more talented coder. Damn, I also wanted the files inside the sdkp2. I wanted to know if the md5 files are the same as in the old engine version or not.
## Post #20
- Username: ghostyn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 05, 2011 6:09 pm
- Post datetime: 2011-06-03T13:29:06+00:00
- Post Title: Re: (pc) Brink

hey! does anyone knows how to use this?

[http://svn.gib.me/public/brink/trunk/](http://svn.gib.me/public/brink/trunk/)
## Post #21
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-06-03T14:18:35+00:00
- Post Title: Re: (pc) Brink

> Reply from ghostyn
>
> hey! does anyone knows how to use this?

http://svn.gib.me/public/brink/trunk/

You svn it to a local folder, then compile with VC studio 2010.
## Post #22
- Username: Dynamite Dan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 05, 2011 10:39 am
- Post datetime: 2011-06-04T18:21:45+00:00
- Post Title: Re: (pc) Brink

Any news? I need decompress sdpk2 too.

My mission is audio:english - text:spanish
## Post #23
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-07-28T15:13:45+00:00
- Post Title: Re: (pc) Brink

Any news? I want translate this game.

Can someone pack these aplications?

```
http://svn.gib.me/public/brink/trunk/
```
