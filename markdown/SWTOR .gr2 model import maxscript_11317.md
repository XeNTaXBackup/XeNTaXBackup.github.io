## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-15T09:14:38+00:00
- Post Title: SWTOR .gr2 model import maxscript

Hi guys! Here's maxscript to import SWTOR models with bones (3ds max 2009-2011)

Instruction:
1. Load SWTOR_BONES.ms
2. Point it to a file like ***_skeleton.gr2
3. Bones will be loaded

4. Load SWTOR.ms
5. Point it to a file like ***.gr2 without word "skeleton"
6. Model will be loaded above bones

Done

[](http://piccy.info/view3/6067969/47cf3fd9c0bb20f5463538c3c179e2af/orig/)[](http://i.piccy.info/a3c/2014-03-15-09-07/i9-6067969/744x574-r)
[SWTOR.7z](https://xentaxbackup.github.io/file/7132_SWTOR.7z)
## Post #2
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-03-15T10:49:52+00:00
- Post Title: SWTOR .gr2 model import maxscript

Thanks so much!
## Post #3
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-03-15T11:18:57+00:00
- Post Title: SWTOR .gr2 model import maxscript

Sorry for posting twice but it works great on Satele, but when I test it on Malgus he doesn't get every weight he should, he has Right Toe, Pelvis, Right Hip, and those bones are even weighted on the correct part (pelvis is weighted to most of the upper body)
Is this a bug in the script? Im glad that the script works great for Satele though
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-15T11:26:07+00:00
- Post Title: SWTOR .gr2 model import maxscript

Hi, no it's not a bug in the script. Mine Malgus model I had to fix manually, because base bmsnew_skeleton doesn't have extra bones for cape, which Malgus model needs (those weights which you got importing Malgus model on base bmsnew_skeleton are default 3ds max generated)   So I guess somewhere should be skeleton for Malgus, that's the skeleton-finding problems I told you. There's a "my way" to fix this, but it's a little crappy lol
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-03-15T12:01:40+00:00
- Post Title: SWTOR .gr2 model import maxscript

Oh I see lol. That's fine then, maybe Malgus' cape has a skeleton somewhere else lol.
## Post #6
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2014-03-24T19:54:15+00:00
- Post Title: SWTOR .gr2 model import maxscript

So this script is for characters and creatures only? I'm getting some errors when i'm trying to load ships.

But anyway, it's wonderful script! I've been looking for something like this literally 2 years!
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-24T20:06:37+00:00
- Post Title: SWTOR .gr2 model import maxscript

Hi! Send me not working models, I'll try to fix my script.
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-25T07:50:03+00:00
- Post Title: SWTOR .gr2 model import maxscript

very cool work man, thanks for that, gratz.
## Post #9
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2014-03-25T10:39:33+00:00
- Post Title: SWTOR .gr2 model import maxscript

> Reply from zaramot
>
> Hi! Send me not working models, I'll try to fix my script.
Agent's ship here [http://www.mediafire.com/download/vufwu ... nt_ext.rar](http://www.mediafire.com/download/vufwu3d3jl9566i/spc_ps_agent_ext.rar). Well, none of the player ship are loading.
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-25T13:10:04+00:00
- Post Title: SWTOR .gr2 model import maxscript

Hi! Thanks for sample, I fixed script to import Agent's ship. But it would be great, if you send me more ships to test.

[](http://piccy.info/view3/6124884/111b892887cd1bacaa065725dfd6472a/1200/)[](http://i.piccy.info/a3c/2014-03-25-13-07/i9-6124884/744x574-r)
## Post #11
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2014-03-25T13:57:17+00:00
- Post Title: SWTOR .gr2 model import maxscript

Thank you very much! Here some more examples + some interior models of those ships. [http://www.mediafire.com/download/xthn9 ... /ships.rar](http://www.mediafire.com/download/xthn9phyuczt70q/ships.rar)
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-25T16:17:21+00:00
- Post Title: SWTOR .gr2 model import maxscript

I tested all model samples and they imported fine. Check first post for updated scripts.

[](http://piccy.info/view3/6125780/aa5deeb19636fc69a1160b7a989a4b1a/1200/)[](http://i.piccy.info/a3c/2014-03-25-16-15/i9-6125780/744x574-r)
## Post #13
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2014-03-25T16:27:41+00:00
- Post Title: SWTOR .gr2 model import maxscript

Yes, it's all working now! Thank you very much!
## Post #14
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-04-02T08:47:58+00:00
- Post Title: SWTOR .gr2 model import maxscript

Hi! Can you modify your script to import models with Z-axis up? Because it is a pain in a... rotating all the models (100+) I've imported, especially ones with bones.
## Post #15
- Username: ribbonowq
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 09, 2014 1:28 am
- Post datetime: 2014-11-08T18:09:04+00:00
- Post Title: SWTOR .gr2 model import maxscript

hi . I need Satele Shan model。 can you give me
## Post #16
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-07-07T05:50:07+00:00
- Post Title: Re: SWTOR .gr2 model import maxscript

I know this is not correct place, but you can check this gr2 files?

[https://cloud.mail.ru/public/3GAG/DREcr9q4Y](https://cloud.mail.ru/public/3GAG/DREcr9q4Y)
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-16T18:57:40+00:00
- Post Title: Re: SWTOR .gr2 model import maxscript

Update for the script, in case anyone interested.

EDIT: Skipped one line
[SWTOR.7z](https://xentaxbackup.github.io/file/12648_SWTOR.7z)
## Post #18
- Username: daddyrus1994
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 24, 2017 4:36 am
- Post datetime: 2018-05-18T10:29:48+00:00
- Post Title: Re: SWTOR .gr2 model import maxscript

I can not load a bone, I change the file chest_armor01_bfa_architect on chest_armor01_bfa_archetype_skeleton, what should I do?
