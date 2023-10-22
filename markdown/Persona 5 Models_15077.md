## Post #1
- Username: kenji1997
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 02, 2016 7:43 am
- Post datetime: 2016-09-23T04:49:59+00:00
- Post Title: Persona 5 Models

Hello everyone,

I was able to extract the CPK and find what I believe to be the model files (.GMD). I tried using the Noesis script that works with the Persona dancing GMD files. located in this thread: [viewtopic.php?f=16&t=14321](http://forum.xentax.com/viewtopic.php?f=16&t=14321)
Unfortunately, that script does not seem to work with the models from this game. 

My first time trying to do this. Sorry if I am missing something obvious.

I have attached a sample of the model files. I would appreciate any help.  

[https://www.mediafire.com/?iu36ofy7eo35q7s](https://www.mediafire.com/?iu36ofy7eo35q7s)
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-09-26T09:03:07+00:00
- Post Title: Persona 5 Models

[https://puu.sh/rnP3O.png](https://puu.sh/rnP3O.png)

I've been working on a maxscript for a while. It'll be done in about a day or maybe 2.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-09-28T15:57:28+00:00
- Post Title: Persona 5 Models

> Reply from TGE
>
> https://puu.sh/rnP3O.png

I've been working on a maxscript for a while. It'll be done in about a day or maybe 2.

Does your script work with environments too or only player models?
## Post #4
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-09-29T05:45:23+00:00
- Post Title: Persona 5 Models

> Reply from lionheartuk
>
> 
Does your script work with environments too or only player models?
It works on both character and field models. 
For characters the dds texture files are embedded in the file itself, for field models they're encoded into a container which uses its own custom header for each texture (presumably the internal header layout for dds loaded in memory) though those get converted to compatible dds files by the script on import.
## Post #5
- Username: kenji1997
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 02, 2016 7:43 am
- Post datetime: 2016-10-05T04:20:57+00:00
- Post Title: Persona 5 Models

TGE,

I hope you are having better luck than me. I have some experience in scripting, but extracting models is alien to me. Hopefully, I will gain insight into this once I have a look at your script.
## Post #6
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-06T01:14:25+00:00
- Post Title: Persona 5 Models

> Reply from kenji1997
>
> TGE,

I hope you are having better luck than me. I have some experience in scripting, but extracting models is alien to me. Hopefully, I will gain insight into this once I have a look at your script.
Hah, I really hope It'll be able to teach you a thing or 2.
Anyways, progress video:
[https://www.youtube.com/watch?v=VfYXCAdFtPQ](https://www.youtube.com/watch?v=VfYXCAdFtPQ)

Animations!
Aside from that there's still quite a few things to implement but also some things to fix (there's some difficult to track down bugs causing models to be displaced -> somewhat visible in the video, but it gets worse for some models)
## Post #7
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-10-06T04:18:33+00:00
- Post Title: Persona 5 Models

TGE, there are some P4D models that do not work with the existing Noesis script. Will you be adding support for those in the P5 MaxScript?
## Post #8
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-06T16:54:45+00:00
- Post Title: Persona 5 Models

> Reply from anime663
>
> TGE, there are some P4D models that do not work with the existing Noesis script. Will you be adding support for those in the P5 MaxScript?
Which ones are you speaking of?
## Post #9
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-10-06T17:03:55+00:00
- Post Title: Persona 5 Models

> Reply from TGE
>
> Which ones are you speaking of?
I posted a sample here 
[viewtopic.php?f=16&t=14321&p=123212#p123212](http://forum.xentax.com/viewtopic.php?f=16&t=14321&p=123212#p123212)
And I'll try and get some more samples later, if you want. Right now I can't.
## Post #10
- Username: oneaccount
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 09, 2016 1:39 am
- Post datetime: 2016-10-09T00:42:19+00:00
- Post Title: Persona 5 Models

Are you still working on this? 
Do you plan on releasing it to the public?
## Post #11
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-11T11:41:18+00:00
- Post Title: Persona 5 Models

I'm still working on fixing some pressing issues with the format. And yes, it will be released in due time.
## Post #12
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-17T17:02:20+00:00
- Post Title: Persona 5 Models

In case anyone hasn't seen, I've released the importer.
[viewtopic.php?f=16&t=15363](http://forum.xentax.com/viewtopic.php?f=16&t=15363)
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-10-23T07:18:19+00:00
- Post Title: Persona 5 Models

Can someone please share what they used to extrat the persona 5 cpk files, I've tried a bunch of QuickBMS scripts and even some other tools but none of them seem to work on the cpk files from this game.
## Post #14
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-10-23T07:55:47+00:00
- Post Title: Persona 5 Models

> Reply from lionheartuk
>
> Can someone please share what they used to extrat the persona 5 cpk files, I've tried a bunch of QuickBMS scripts and even some other tools but none of them seem to work on the cpk files from this game.
I used a slightly edited version of CriPakTools (it had some issues with japanese characters in the paths). Link: [http://puu.sh/rSA0q.7z](http://puu.sh/rSA0q.7z)
## Post #15
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-10-23T09:30:20+00:00
- Post Title: Persona 5 Models

Continue here: [viewtopic.php?f=16&t=15363](http://forum.xentax.com/viewtopic.php?f=16&t=15363)

Thanks!
