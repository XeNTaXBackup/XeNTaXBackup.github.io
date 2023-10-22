## Post #1
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-09T05:56:53+00:00
- Post Title: Extracting models from Conker Live & Reloaded

hello im trying to extract modles from conker live and reloaded. So far, i was able to decrompress the iso file and found the particular model i am looking for, but its in a very weird format, "RBM". I tried reading it on HxD and cant seem to find the files im looking for because its all a bunch of random variables. Can someone please help me? 

[http://www.mediafire.com/?d1htggzc5pf2m9k](http://www.mediafire.com/?d1htggzc5pf2m9k)
## Post #2
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-09T19:34:30+00:00
- Post Title: Extracting models from Conker Live & Reloaded

Doesn't look 3D.
First 4 bytes say CAFF - audio format or compressed data.
## Post #3
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-09T23:31:57+00:00
- Post Title: Extracting models from Conker Live & Reloaded

Hmm I don't understand, I didn't see a model or sound folder, just one titled "characters" they all have default.rbm as the file inside. If its not 3d what could be the compressed data?
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-09T23:55:41+00:00
- Post Title: Extracting models from Conker Live & Reloaded

if I recall they use a level package setup, but I could be wrong. I glanced at it soo many years ago prior to the xbox360
## Post #5
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-10T01:47:31+00:00
- Post Title: Extracting models from Conker Live & Reloaded

Would it be possible for you to help me find the models through the package? I can PM the files if neccesary.
## Post #6
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-13T02:02:55+00:00
- Post Title: Extracting models from Conker Live & Reloaded

Okay, so after getting off my lazy ass and doing a bit of research online, i found a tutorial on how to extract files using HxD, (that quick bms tutorial by chrrox) so Im becoming pretty familar with the language. However, I still want to extract these files (or "file") inside this .rbm. 



Ninja told me that the file format is CAFF which is either sound or a compressed format, so there must be more than one file inside. I know that once i extract this file, ill have to go and try to extract the files within the files. I do not care though, i think its worrth the process. 

I noticed that not only is there a CAFF but a .data and .gpu(gpu?) as well, and if you look at the pictures below, the .data (2E 64 61 74 61 on 00000040) and gpu(2E 67 70 75 on 00000060) remain the same,

 so im guessing those are the files? 






I want to extract these files using quick bms, however i remain stuck because i cant figure out what to do once ive divcovered the difference in the .rbm files.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-13T02:28:03+00:00
- Post Title: Extracting models from Conker Live & Reloaded

its a chunk based format that uses an unkown compression.
[viewtopic.php?f=21&t=8498](http://forum.xentax.com/viewtopic.php?f=21&t=8498)
## Post #8
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-13T03:38:47+00:00
- Post Title: Extracting models from Conker Live & Reloaded

There has to be a slight possibility, i was able to extract a .file which doesn't help much because its only a chunk of the file. There must be a way! You sure quick Hms wont do the trick?
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T03:44:00+00:00
- Post Title: Extracting models from Conker Live & Reloaded

From the data alone you probably won't get good results.
Then again it's an XBOX game right?

I don't know if there are methods to try to reverse compression on console games.
## Post #10
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-13T03:55:01+00:00
- Post Title: Extracting models from Conker Live & Reloaded

So if there is little to NO possibility, what are some suggestions? The only solution I can think of is a 3d ripping tool
## Post #11
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2012-03-13T05:31:36+00:00
- Post Title: Extracting models from Conker Live & Reloaded

Okay this is starting to piss me off, i have tried every xbox emulator that is available, and one would read the iso but says its incompatible, whoever was working on cxbx closed their site. So for now, unless someone happens to know how to decrypt something like this, I'm fucked.
## Post #12
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2021-01-25T12:59:32+00:00
- Post Title: Extracting models from Conker Live & Reloaded

i know this post is dead but i have an idea.. something like this but with xemu maybe? [https://www.reddit.com/r/BanjoKazooie/c ... pping_can/](https://www.reddit.com/r/BanjoKazooie/comments/jj2s8a/thanks_to_xenias_recent_build_model_ripping_can/) of course xemu needs to be able to intercept draw calls but its an idea non the less. if you're still here please reply, thanks.
## Post #13
- Username: SRSONIC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 18, 2021 2:33 am
- Post datetime: 2021-10-17T18:34:32+00:00
- Post Title: Extracting models from Conker Live & Reloaded

hi men hope the search is not dead im looking for the models to
## Post #14
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2022-03-27T12:51:28+00:00
- Post Title: Extracting models from Conker Live & Reloaded

I GOT SOMETHING! finally tried renderdoc and... [https://imgur.com/a/SeZ6v5l](https://imgur.com/a/SeZ6v5l) 
not too sure how to use this program properly but it's a start
## Post #15
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2022-03-31T16:35:24+00:00
- Post Title: Extracting models from Conker Live & Reloaded

got a mesh but its messed up, some faces just aren't there. will keep tinkering but best i got so far  [https://imgur.com/a/U4Uc915](https://imgur.com/a/U4Uc915)
## Post #16
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2022-03-31T21:47:59+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

manually adding faces is a pain but close as i can get so far  [https://imgur.com/a/x2JSqux](https://imgur.com/a/x2JSqux)
## Post #17
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2022-04-01T20:28:04+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

"fixed" the mesh but not sure it's 100% accurate :/ good as i can get so far unless i can fix the problem with the gaps [https://imgur.com/a/DhlWBk1](https://imgur.com/a/DhlWBk1)
## Post #18
- Username: uberk2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 13, 2021 1:09 am
- Post datetime: 2022-04-03T00:06:19+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

[https://imgur.com/a/2XsZItF](https://imgur.com/a/2XsZItF) got some uv's (not original) this is probably the best i can do
## Post #19
- Username: Hplayer01
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 19, 2022 9:31 am
- Post datetime: 2022-11-19T01:36:11+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

Whoa this is a very interesting forum, did you actually successfully extracted a model and texture of Conker from the game?
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-19T12:14:46+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

Posting pictures is totally uninteresting, imho, as long as people tend to keep their knowledge secret.

Last state of public research afaik, see links (2015, 2013) contained here (April 2017):
[viewtopic.php?f=16&t=16174&p=129839&hil ... er#p129839](https://forum.xentax.com/viewtopic.php?f=16&t=16174&p=129839&hilit=conker#p129839)

Or read here (click up arrow) from about 10 years ago:

> Reply from chrrox ↑Fri Mar 16, 2012 5:27 pm at Fri Mar 16, 2012 5:27 pm
>
> 

No time to deal with but mojobojo's caffextractor could be a start (SizeOfHeader seems to be bogus, though, maybe wrong .rbm file used):
.



caffextractor.jpg (197.64 KiB) Viewed 65 times



edit: caffreader works with CAFF07.08.06.003
example: 
> Reply from andrewly3 ↑Wed May 12, 2021 1:54 am at Wed May 12, 2021 1:54 am
>
>
## Post #21
- Username: vitalflea
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 24, 2022 5:29 am
- Post datetime: 2022-11-23T22:20:16+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

> Reply from shakotay2 ↑Sat Nov 19, 2022 8:14 pm at Sat Nov 19, 2022 8:14 pm
>
> 
Posting pictures is totally uninteresting, imho, as long as people tend to keep their knowledge secret.

It's very interesting. It led me to using the tool that he mentioned.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-24T06:11:19+00:00
- Post Title: Re: Extracting models from Conker Live & Reloaded

> Reply from vitalflea ↑Thu Nov 24, 2022 6:20 am at Thu Nov 24, 2022 6:20 am
>
> 
shakotay2 wrote: ↑Sat Nov 19, 2022 8:14 pm
Posting pictures is totally uninteresting, imho, as long as people tend to keep their knowledge secret.


It's very interesting. It led me to using the tool that he mentioned.You got a point.

Oakieland (u/Plebian_Donkey_Konga) wrote: 
> Thanks to Xenia's recent build, model ripping can be done for Banjo-Kazooie: Nuts & Bolts we can intercept the draw calls and extract models from the emulator. You can view the draw calls with RenderDoc.(I wasn't aware of the progress of XBOX emulation... But you'll need to be a real fan of those models to dig into this. What I thought of was a "simple" ripping from model data.)
