## Post #1
- Username: giratinapoke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 22, 2015 11:11 am
- Post datetime: 2016-08-14T00:09:56+00:00
- Post Title: HeroWarz models

I would like to rip 3D models from HeroWarz and I got to the 'CookedPC' where I think where the models are.
I am working with .upk files and when I use umodel.exe I get  error 'wrong tag in package FEFEEFEF'.
I was only able to find this link related to this topic: [http://www.gildor.org/smf/index.php?topic=2926.new](http://www.gildor.org/smf/index.php?topic=2926.new)

you can get umodel from: [http://www.gildor.org/downloads](http://www.gildor.org/downloads)

any help would be appriciated.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-14T16:41:42+00:00
- Post Title: HeroWarz models

The game might have encrypted UPK files or the format was slightly altered by the developers. Hard to tell with no samples.
## Post #3
- Username: giratinapoke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 22, 2015 11:11 am
- Post datetime: 2016-08-16T07:19:37+00:00
- Post Title: HeroWarz models

Here is some sample files here I hope it helps. 

[https://drive.google.com/folderview?id= ... sp=sharing](https://drive.google.com/folderview?id=0B_Rg91GYFYN1WndNMXR3NkV0RVU&usp=sharing)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-16T14:13:08+00:00
- Post Title: HeroWarz models

> Reply from giratinapoke
>
> I was only able to find this link related to this topic: http://www.gildor.org/smf/index.php?topic=2926.new
h4x0r says "Just xored by 0xB6" 

you can use "xor" program by aluigi here
[http://aluigi.altervista.org/mytoolz/xor.zip](http://aluigi.altervista.org/mytoolz/xor.zip)

usage example

```
xor.exe 00000014.upk out_00000014.upk 0xB6
```
## Post #5
- Username: divinelyjade
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 14, 2016 6:20 pm
- Post datetime: 2016-09-14T10:24:17+00:00
- Post Title: HeroWarz models

Hi there ! I am also looking for the herowarz models. I'm a MMD modeller- therefore I use PMX editor to rig models and would like to see herowarz models on my list of completed ones.. I know how to use blender to convert to directx (the format I need), so if you're ever able to extract the upks for me, I'd appreciate it if anyone could do that. I really would! 

(I'm a huge noob at extracting, I only know how to use QuickBMS and els_kom)
## Post #6
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2017-01-06T06:03:12+00:00
- Post Title: HeroWarz models

> Reply from AceWell
>
> giratinapoke wrote:I was only able to find this link related to this topic: http://www.gildor.org/smf/index.php?topic=2926.new
h4x0r says "Just xored by 0xB6" 

you can use "xor" program by aluigi here
http://aluigi.altervista.org/mytoolz/xor.zip

usage example
Code: Select allxor.exe 00000014.upk out_00000014.upk 0xB6

When I finished xor.exe 00000014.upk out_00000014.upk 0xB6 after the same can not be opened with umodel
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-06T06:42:36+00:00
- Post Title: HeroWarz models

don't know, you have to talk with Gildor about extraction, my post was just about the xoring
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-06T07:55:35+00:00
- Post Title: HeroWarz models

@liuxing
Have a look at the un-xored model data. You won't expect to have a model in 463 bytes, do you?
Then check for chrrox' post as of Dec. 6th, 2016 here:
[http://zenhax.com/viewtopic.php?t=2933](http://zenhax.com/viewtopic.php?t=2933)

Doesn't work for the upks that giratinapoke  uploaded. Seems you'll need an upk which has a DWORD (index?) table before the name table.
## Post #9
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2017-01-07T09:15:20+00:00
- Post Title: HeroWarz models

> Reply from shakotay2
>
> @liuxing
Have a look at the un-xored model data. You won't expect to have a model in 463 bytes, do you?
Then check for chrrox' post as of Dec. 6th, 2016 here:
http://zenhax.com/viewtopic.php?t=2933

Doesn't work for the upks that giratinapoke  uploaded. Seems you'll need an upk which has a DWORD (index?) table before the name table.

Thanks for your help, this method should look right. But to each file I do not know how to be specific to add the missing part.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-07T09:41:18+00:00
- Post Title: HeroWarz models

> Reply from liuxing
>
> Thanks for your help, this method should look right. But to each file I do not know how to be specific to add the missing part.I don't see where the problem should be.

Add 4 zero bytes before the "size of first namestring" DWord (and after the last DWord of the index table).



fix_upk.JPG (55.6 KiB) Viewed 112 times
